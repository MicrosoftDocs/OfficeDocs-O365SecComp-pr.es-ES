---
title: Aislamiento de inquilino de Office 365 en la búsqueda de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: una explicación del aislamiento de inquilinos en Office 365 Search.'
ms.openlocfilehash: 5254ffe2e6b92c6ba100a9e45b35b456ead1b000
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262602"
---
# <a name="tenant-isolation-in-office-365-search"></a>Aislamiento de inquilino en búsqueda de Office 365
La búsqueda de SharePoint Online usa un modelo de separación de inquilinos que equilibra la eficiencia de las estructuras de datos compartidos con protección frente a la pérdida de información entre los inquilinos. Con este modelo, se evita que las características de búsqueda de:
- Devolver resultados de consulta que contienen documentos de otros inquilinos
- Exponer la información suficiente en los resultados de la consulta que un usuario cualificado puede deducir información sobre otros inquilinos
- Mostrar esquema o configuración de otro espacio empresarial
- Mezclar información de procesamiento de análisis entre espacios empresariales o los resultados de almacén en el inquilino incorrecto
- Uso de entradas de Diccionario de otro espacio empresarial

Para cada tipo de datos de espacio empresarial, usamos una o más capas de protección en el código para evitar pérdidas accidentales de información. Los datos más críticos tienen la mayor parte de las capas de protección para asegurarse de que un solo defecto no produce fugas de información reales o percibidas.

## <a name="tenant-separation-for-the-search-index"></a>Separación de inquilinos para el índice de búsqueda
El índice de búsqueda se almacena en el disco en los servidores que hospedan los componentes de índice y los inquilinos comparten los archivos de índice. Los documentos indizados de un inquilino solo son visibles para las consultas de ese espacio empresarial. Tres mecanismos independientes evitan la fuga de información:
- Filtrado de ID de inquilino
- Prefijo del período del identificador de espacio empresarial
- Comprobaciones de LCA

Los tres mecanismos tendrían que producir un error en la búsqueda para devolver documentos al inquilino incorrecto.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtrado de ID de inquilino e identificador de espacio empresarial con prefijo
Prefijos de búsqueda todos los términos que se indizan en el índice de texto completo con el identificador de inquilino. Por ejemplo, cuando el término "*foo*" está indizado para un inquilino con el identificador "*123*", la entrada en el índice de texto completo es "*123foo".*

Todas las consultas se convierten para incluir el identificador de inquilino mediante un proceso denominado filtrado de ID de inquilino. Por ejemplo, la consulta "*foo*" se convierte en "<*GUID*>. *foo* Y *tenantID*: <*GUID*_GT_ ", donde <*GUID*> representa al inquilino que realiza la consulta. Esta conversión de consulta se produce dentro de cada nodo de índice y ni la consulta ni el procesamiento de contenido pueden influir en él. Dado que el identificador de inquilino se agrega a cada consulta, no se puede inferir la frecuencia de un término en otros inquilinos mirando la clasificación de mejor coincidencia en un espacio empresarial.

La prefijo del período del identificador de espacio empresarial solo se produce en el índice de texto completo. Las búsquedas con campo, como "*Título: foo*", van a un índice de búsqueda sintética donde los términos no tienen prefijo por identificador de inquilino. En su lugar, las búsquedas con campos se anteponen al nombre del campo. Por ejemplo, la consulta "*title: foo*" se convierte en "*Fields. title: foo y Fields. tenantID*: <*GUID*>". Debido a que la frecuencia de un término no influye en la clasificación de aciertos en el índice de búsqueda sintético, no es necesario que la separación de inquilinos por term prefijo. Para una búsqueda con campo como "*title: foo*", la separación del contenido del espacio empresarial depende del filtrado de identificador de inquilino por conversión de consulta.

## <a name="document-access-control-list-checks"></a>Documentar las comprobaciones de listas de control de acceso
La búsqueda controla el acceso a los documentos a través de las ACL que se guardan en el índice de búsqueda. Cada elemento se indiza con un conjunto de términos en un campo de ACL especial. El campo ACL contiene un término por grupo o usuario que puede ver el documento. Cada consulta se aumenta con una lista de términos de entrada de control de acceso (ACE), una para cada grupo al que pertenece el usuario autenticado.

Por ejemplo, una consulta como "<*GUID*>. *foo y tenantID*: <*GUID*> "se convierte en:"*GUID*de < >. *foo and tenantID*: <*GUID*> *and* (*docACL:*<*ACE1*> *o docACL*: <*ace2*> *o docACL*: <*Ace3*> *... *)"

Como los identificadores de usuario y de grupo y por tanto las ACE son únicos, esto proporciona un nivel adicional de seguridad entre los inquilinos para los documentos que solo son visibles para algunos usuarios. Lo mismo sucede con la ACE especial "todos excepto usuarios externos" que concede acceso a los usuarios habituales del espacio empresarial. Pero, puesto que las ACE para "everyone" son las mismas para todos los inquilinos, la separación de inquilinos para documentos públicos depende del filtrado de ID de inquilino. También se admiten las ACE de denegación. El aumento de la consulta agrega una cláusula que quita un documento del resultado cuando hay una coincidencia con una ACE de denegación.

En la búsqueda de Exchange Online, el índice se particiona en el identificador de buzón para los buzones de correo del usuario individual en lugar de con el identificador de inquilino (identificador de suscripción) como en SharePoint Online. El mecanismo de partición es el mismo que el de SharePoint Online, pero no hay ningún filtrado de LCA.

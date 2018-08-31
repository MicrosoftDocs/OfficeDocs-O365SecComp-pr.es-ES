---
title: Aislamiento de inquilinos de Office 365 en la búsqueda de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Una explicación de aislamiento de inquilinos de la búsqueda de Office 365.'
ms.openlocfilehash: cc73f3c157ffd20b3891a6b7c58e7d0b2adf4e55
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535594"
---
# <a name="tenant-isolation-in-office-365-search"></a>Aislamiento de inquilino en búsqueda de Office 365
Búsqueda de SharePoint Online usa un modelo de separación de inquilinos que equilibra la eficacia de las estructuras de datos compartidos con protección contra la pérdida de entre los inquilinos de información. Con este modelo, se evitar que las características de búsqueda de:
- Devolver resultados de consulta que contienen los documentos de otros inquilinos
- Exponer información suficiente en los resultados de consulta que un usuario cualificado puede inferir información acerca de otros inquilinos
- Esquema que muestra o la configuración desde otro inquilino
- Mezcla de procesamiento de información entre los inquilinos o los resultados de almacenamiento en el inquilino incorrecto de análisis
- Uso de entradas de diccionario desde otro inquilino

Para cada tipo de datos de inquilinos, usaremos una o más capas de protección en el código para evitar la pérdida accidental de la información. Los datos más críticos tienen la mayoría de las capas de protección para asegurarse de que no se produce un solo defecto fuga de información real o detectadas.

## <a name="tenant-separation-for-the-search-index"></a>Separación de inquilino para el índice de búsqueda
El índice de búsqueda se almacena en el disco en los servidores que hospedan los componentes de índice y los inquilinos compartan los archivos de índice. Documentos indizados de un inquilino son visibles sólo para las consultas para ese inquilino. Tres mecanismos independientes para evitar fugas de información:
- Filtrado de identificador de inquilino
- Término prefijo de identificador de inquilino
- Comprobaciones de ACL

Los tres mecanismos tendría que producirá un error de búsqueda devolver los documentos para el inquilino incorrecto.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtrado de identificador de inquilino y el término de identificador de inquilino como prefijo
Prefijos de búsqueda todos los términos que se indiza en el índice de texto completo con el identificador del inquilino. Por ejemplo, cuando no se indiza el término "*foo*" para un inquilino con el identificador "*123*", la entrada en el índice de texto completo es "*123foo.*"

Todas las consultas se convierten para incluir el identificador de inquilino mediante un proceso denominado filtrado de identificador del inquilino. Por ejemplo, se convierte la consulta "*foo*" a "<*guid*>. *foo* Y *tenantID*: <*guid*> ", donde <*guid*> representa el inquilino a realizar la consulta. Esta conversión de consulta se produce dentro de cada nodo de índice y procesamiento de consulta ni contenido puede influir en. Debido a que se agrega el identificador de inquilino para cada consulta, no se puede inferir la frecuencia de un término en otros inquilinos mirando en el mejor coincidencia de clasificación en un inquilino.

Término prefijo de identificador de inquilino se produce sólo en el índice de texto completo. Las búsquedas clasificadas por campos, como "*título: foo*", van a un índice de búsqueda sintéticas donde no tienen el prefijo de términos por identificador del inquilino. En su lugar, las búsquedas clasificadas por campos llevan el prefijo con el nombre del campo. Por ejemplo, se convierte la consulta "*título: foo*" a "*fields.title:foo AND fields.tenantID*: <*guid*>." Debido a que la frecuencia de un término no influir en la clasificación de visitas en el índice de búsqueda sintéticas, no es necesario para la separación de inquilino anteponiendo términos. Separación de contenido de inquilino para una búsqueda clasificadas por campos como "*título: foo*", depende de identificador de inquilino filtrado por conversión de consulta.

## <a name="document-access-control-list-checks"></a>Comprobaciones de lista de Control de acceso de documento
Búsqueda controla el acceso a documentos a través de ACL que se guardan en el índice de búsqueda. Todos los elementos se indizan con un conjunto de términos en un campo ACL especial. El campo ACL contiene un término por grupos o usuarios que pueden ver el documento. Todas las consultas se incrementa con una lista de términos de entrada (ACE) de control de acceso, uno para cada grupo al que pertenece el usuario autenticado.

Por ejemplo, una consulta como "<*guid*>. *foo AND tenantID*: <*guid*> "se convierte en:" <*guid*>. *foo AND tenantID*: <*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*: <*ace2*> *OR docACL*: <*ace3*> *... *)"

Debido a que los identificadores de grupo y de usuario y, por tanto, las entradas ACE son únicas, esto proporciona un nivel adicional de seguridad entre los inquilinos para los documentos que sólo son visibles para algunos usuarios. El mismo es el caso de especial "todos excepto los usuarios externos" ACE que conceda acceso a los usuarios regulares en el inquilino. Pero, dado que las entradas ACE para "Todos" son los mismos para todos los inquilinos, separación de inquilino para los documentos públicos depende de filtrado de identificador del inquilino. También se admiten las entradas ACE de denegación. El aumento de la consulta agrega una cláusula que quita un documento desde el resultado cuando hay una coincidencia con una ACE de denegación.

En la búsqueda de Exchange Online, el índice se divide en identificador de buzón de correo para los buzones de usuario individual en lugar de identificador de inquilino (identificador de suscripción) como en SharePoint Online. El mecanismo de partición es el mismo que SharePoint Online, pero no hay ninguna ACL filtrado.

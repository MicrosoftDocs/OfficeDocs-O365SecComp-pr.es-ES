---
title: Inmutabilidad de datos 365 de Office
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
description: Define y explica la inmutabilidad de datos o datos que se deben poder detectar y no se pueden destruir ni modificar.
ms.openlocfilehash: b23a62dd95ec2ca554997fc667d89e6979e5b747
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262872"
---
# <a name="immutability-in-office-365"></a>Inmutabilidad en Office 365
Para algunas organizaciones, el cumplimiento normativo, los requisitos de control interno o el riesgo por litigio requieren la preservación de correo electrónico y datos asociados en un formulario reconocible. Todos los datos del sistema deben ser detectables y no se puede destruir ni alterar ninguno de ellos. El término estándar de la industria para esto es "inmutabilidad". 

Los métodos tradicionales para lograr inmutabilidad suelen realizarse moviendo los mensajes de correo electrónico a una ubicación de almacenamiento separada de solo lectura. Aunque estos sistemas sirven para conservar los elementos de los buzones para la detección, suelen afectar a la experiencia del usuario de maneras significativas, ya que se quitan los elementos que conservan del flujo de trabajo diario habitual. Para los profesionales de ti, este enfoque para la inmutabilidad requiere la implementación y el mantenimiento continuo de una infraestructura de almacenamiento y servidor independiente. La propia detección se realiza con herramientas externas al sistema de correo, con costes de implementación y mantenimiento asociados.

A través de la configuración de las características de directiva de conservación y retención local del archivado en Office 365 y en conjunción con servicios en el conjunto de aplicaciones de Office 365, como Exchange Online, SharePoint Online, OneDrive para la empresa y Skype empresarial. el archivado en Office 365 puede preservar y conservar muchas clases de datos entrantes, internos y salientes, entre los que se incluyen:
- Comunicaciones de correo electrónico entrante y saliente
- Libros y registros contenidos en un formulario de correo electrónico o en documentos compartidos en línea
- Convocatorias de reunión
- Faxes
- Mensajes instantáneos
- Documentos compartidos durante reuniones en línea
- Correos

Además, Microsoft ha desarrollado características complementarias para permitir el [archivado de datos](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) de otros orígenes mediante la integración con soluciones de administración y captura de datos de terceros. Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Office 365 a los datos, como la retención por juicio, la exhibición de documentos electrónicos y la retención en el lugar, la búsqueda de cumplimiento, el archivado local, la auditoría y las directivas de retención. Por ejemplo, cuando un buzón se pone en Retención por juicio, se conservan los datos de terceros. Puede buscar datos de terceros mediante Exhibición de documentos electrónicos local o Búsqueda de cumplimiento. También puede aplicar las directivas de archivado y retención a los datos de terceros, del mismo modo que a los datos de Microsoft. En Resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

El archivado en Office 365 proporciona el almacenamiento compatible con la norma 17a-4 de los valores y la Comisión de Exchange (SEC), y conserva los archivos permanentes de todos los datos recopilados en un formato no regrabable y que no se puede borrar mediante directivas de retención locales y directivas de conservación , incluido el bloqueo de conservación. En particular:
- Todos los registros que se almacenan con las directivas de retención indicadas anteriormente se conservan en un área de almacenamiento dedicada del ámbito del usuario ordinario. Además, solo los usuarios autorizados pueden tener acceso a estos registros y buscar en ellos, pero no pueden modificarlos ni borrarlos.
- Los metaDatos de cada elemento incluyen una marca de tiempo que se usa en el cálculo de la duración de la retención. Las marcas de hora se aplican cuando se recibe o se crea un nuevo elemento y no se puede modificar ni quitar posteriormente de los metadatos.
- El archivado en Office 365 permite a los usuarios combinar distintas directivas de retención y mantener acciones para crear directivas de retención granulares a fin de definir el tipo o la ubicación de los elementos que se conservarán inmutablemente y la duración de dicha conservación.
- La característica de bloqueo de preservación permite a los usuarios elegir si desean convertir la Directiva en una directiva restrictiva. Una directiva restrictiva prohíbe a cualquiera tener la posibilidad de quitar, deshabilitar o realizar cambios en la Directiva de retención. Esto significa que una vez que el bloqueo de preservación está habilitado, no se puede deshabilitar y no existirá ningún mecanismo en el que los datos de custodios existentes que hayan sido recopilados por las directivas de retención en vigor puedan ser sobrescritos, modificados, borrados o eliminados durante el período de conservación. Además, el período de retención establecido por el bloqueo de conservación no puede reducirse ni disminuir. Sin embargo, se puede alargar en el caso de un requisito legal para continuar la retención de los datos almacenados, como se indicó anteriormente. El bloqueo de preservación garantiza que nadie, ni siquiera los administradores o los que tienen acceso a control, puedan cambiar la configuración o sobrescribir o borrar datos que se hayan almacenado, lo que aportará el archivado en Office 365 en línea con las instrucciones descritas en la versión 2003 de la SEC Rule 17a-4.

Para que los clientes comprendan mejor cómo se puede aprovechar Office 365 para cumplir sus obligaciones regulatorias, en concreto en relación con los requisitos de reglas 17a-4, hemos lanzado un [documento](https://go.microsoft.com/fwlink/?linkid=830440) que incluye el archivaDo de Exchange Online, SharePoint Online, OneDrive para empresas y Skype empresarial. El documento también ofrece un análisis exhaustivo de las características y funcionalidades de archivado de Office 365 para cada uno de los requisitos de la regla SEC 17a-4 y demuestra a los clientes regulados cómo Office 365 el archivado puede permitirles cumplir estos requisitos.
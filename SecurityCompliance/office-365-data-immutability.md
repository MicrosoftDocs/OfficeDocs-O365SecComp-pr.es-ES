---
title: Inmutabilidad de datos de Office 365
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
description: Define y se explica la inmutabilidad de los datos, o los datos que deben ser detectable y no se destruye o se modifica.
ms.openlocfilehash: 3a9e897734c1805e25a2e2dd5e0c5f8a3e3de3fd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536470"
---
# <a name="immutability-in-office-365"></a>Inmutabilidad en Office 365
Para algunas organizaciones, el cumplimiento de normativas, requerimientos de control interno o riesgo de litigio requieren la conservación del correo electrónico y los datos asociados en un formulario que se pueda detectar. Todos los datos en el sistema deben ser detectable, y ninguno de los puede destruye o se modifica. El término estándar del sector para esto es "inmutabilidad." 

Los métodos tradicionales de lograr inmutabilidad han trabajado normalmente al mover mensajes de correo electrónico a una ubicación de almacenamiento independientes, como de solo lectura. Aunque estos sistemas tienen el propósito de conservar los elementos del buzón de correo para la detección, a menudo afectan a la experiencia del usuario de maneras significativas quitando conserva los elementos desde el flujo de trabajo diaria habitual. Para los profesionales de TI, este enfoque para la inmutabilidad requiere la implementación y el mantenimiento continuado de una infraestructura de almacenamiento y servidor independiente. Detección sí se lleva a cabo con herramientas externas para el sistema de correo, con implementación asociado y los costos de mantenimiento.

A través de la configuración de las características de directiva de conservación de archivado en Office 365 y junto con los servicios en el conjunto de aplicaciones de Office 365, como Exchange Online, SharePoint Online, OneDrive para la empresa y Skype para la empresa y retención en contexto archivado en Office 365 puede conservar y conservar muchas clases de datos entrantes, salientes e internos, incluidos:
- Comunicaciones de correo electrónico entrante y saliente
- Libros y registros contenidos en el formulario de correo electrónico o en los documentos compartidos en línea
- Convocatorias de reunión
- Faxes
- Mensajes instantáneos
- Documentos compartidos durante las reuniones en línea
- Correos de voz

Además, Microsoft ha desarrollado características complementarias para permitir el [archivado de datos](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) desde otros orígenes a través de la integración con soluciones de administración y captura de datos de terceros. Después de importan datos de otro fabricante, puede aplicar las características de cumplimiento de normas de Office 365 a los datos, incluidos juicio, exhibición de documentos electrónicos en contexto y retención, búsqueda de cumplimiento, en lugar de archivado, auditoría y las directivas de retención. Por ejemplo, cuando un buzón de correo se coloca en suspensión por litigio, se conservarán los datos de otro fabricante. Puede buscar datos de terceros mediante el uso de exhibición de documentos electrónicos en contexto o búsqueda de cumplimiento. O puede aplicar el archivado y las políticas de retención a los datos de terceros, al igual que puede utilizar para datos de Microsoft. En resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización mantenga la compatibilidad con el gobierno y las directivas de las normativas.

Archivado en Office 365 proporciona almacenamiento compatibles con 17a-4 de regla de títulos and Exchange Commission (SEC) y conserva los archivos permanentes de todos los datos recopilados en un formato no regrabable, no se puede borrar mediante las directivas de retención en contexto y las directivas de conservación , incluido el bloqueo de conservación. En concreto:
- Todos los registros que se almacenan con las directivas de retención que se ha indicado anteriormente se conservan en un área de almacenamiento de información dedicado fuera de la purview del usuario normal. Además, sólo los usuarios autorizados pueden tener acceso a y buscar estos registros, pero no puede modificar ni eliminarlas.
- Metadatos para cada elemento incluyen una marca de tiempo que se usa en el cálculo de la duración de retención. Las marcas de tiempo se aplican cuando se recibe un elemento nuevo o creado y no puede ser posteriormente modificado o quitado de los metadatos.
- El archivado en Office 365 permite a los usuarios combinar diferentes directivas de retención y suspensión acciones para crear políticas de retención granulares para definir el tipo o la ubicación de los elementos que se conserven inalterados y la duración de dicha conservación.
- La característica de bloqueo de conservación permite a los usuarios elegir si desea realizar la directiva de una directiva restrictiva. Una directiva restrictiva impide que cualquiera tener la posibilidad de quitar, deshabilitar o realizar cambios en la directiva de retención. Esto significa que una vez que el bloqueo de conservación está habilitado, no se puede deshabilitar y no existirá ningún mecanismo en que los datos de custodia existente que ha sido recopilado por la retención se pueden sobrescribir las directivas en su lugar, modificado, borra o se elimina durante la período de conservación. Además, no se puede más cortos o disminuir la suspensión período establecido por el bloqueo de conservación. Sin embargo, puede ampliar las reglas kashida, en el caso de un requisito legal para continuar la retención de los datos almacenados, como se indicó anteriormente. Bloqueo de conservación se asegura de que nadie, ni siquiera los administradores o aquellos con determinados controlar el acceso, puede cambiar la configuración o sobrescribir o borrar los datos que se ha almacenado, incorporación de archivado en Office 365 en consonancia con las instrucciones recogidas en la versión 2003 de seg. Norma 17a-4.

A los clientes comprender mejor cómo se puede sacar provecho a Office 365 para cumplir con sus obligaciones normativas, específicamente en relación con los requisitos de 17a-4 de la regla, hemos publicado un [informe detallado](https://go.microsoft.com/fwlink/?linkid=830440) que incluye el archivado de Exchange Online, SharePoint Online, OneDrive para la empresa y Skype para la empresa. Las notas del producto también proporcionan un análisis en profundidad de las características de archivado de Office 365 y funcionalidades frente a cada uno de los requisitos de la norma 17a-4 y muestra a los clientes regulados cómo archivado de Office 365 puede habilitarlas para satisfacer estos requisitos.
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
description: Define y explica la inmutabilidad de datos en Office 365.
ms.openlocfilehash: bc9805be446ad1d696e20a4bee6e449b311970fe
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622450"
---
# <a name="immutability-in-office-365"></a>Inmutabilidad en Office 365

El cumplimiento normativo, los requisitos de control interno o los riesgos de litigio requieren que las organizaciones conserven el correo electrónico y los datos asociados en un formulario reconocible. Todos los datos del sistema deben ser detectables y no se puede destruir ni alterar ninguno de ellos. El término estándar de la industria para esto es "inmutabilidad".

Los métodos tradicionales para la inmutabilidad suelen trabajar mediante el movimiento de mensajes de correo electrónico a una ubicación de almacenamiento separada y de solo lectura. Aunque estos sistemas sirven para conservar los elementos de buzón para la detección, suelen afectar a la experiencia del usuario al quitar los elementos conservados del flujo de trabajo diario habitual. Para los profesionales de ti, este enfoque de inmutabilidad requiere la implementación y el mantenimiento continuo de una infraestructura de almacenamiento y servidor independiente. La detección se realiza con herramientas externas al sistema de correo e incluye los costos de implementación y mantenimiento asociados.

Mediante la conservación local y las características de directiva de conservación del archivado en Office 365 y sus servicios, puede conservar y conservar muchas clases de datos entrantes, internos y salientes. Esto incluye:

- Comunicaciones de correo electrónico entrante y saliente
- Libros y registros contenidos en un formulario de correo electrónico o en documentos compartidos en línea
- Convocatorias de reunión
- Faxes
- Mensajes instantáneos
- Documentos compartidos durante reuniones en línea
- Correos

Además, Microsoft ha desarrollado características complementarias para permitir el [archivado de datos](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) de otros orígenes mediante la integración con soluciones de administración y captura de datos de terceros. Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Office 365 a los datos, entre los que se incluyen:

- [Retención por juicio](create-a-litigation-hold.md)
- [Exhibición de documentos electrónicos local y retención](manage-legal-investigations.md)
- [Búsqueda de cumplimiento](search-for-content.md)
- [Archivado local](enable-archive-mailboxes.md)
- [Auditoría de buzones](enable-mailbox-auditing.md)
- [Directivas de retención](retention-policies.md)

Por ejemplo, cuando un buzón de correo se coloca en retención por juicio, se conservan los datos de terceros. Puede buscar datos de terceros mediante la exhibición de documentos electrónicos local o la búsqueda de cumplimiento. O bien, puede aplicar directivas de archivado y retención a datos de terceros, como lo haría con los datos de Microsoft. El archivado de datos de terceros en Office 365 ayuda a su organización a cumplir con las directivas gubernamentales y reglamentarias.

El archivado en Office 365 proporciona información sobre el almacenamiento conforme a la norma 17a-4 de la Comisión de Exchange y los valores de la Comisión (SEC). Office 365 conserva los archivos permanentes de todos los datos recopilados en un formato no regrabable, que no se puede borrar, mediante directivas de retención locales y directivas de conservación, incluido el bloqueo de conservación.

En particular:

- Todos los registros almacenados con las directivas de retención indicadas anteriormente se conservan en un área de almacenamiento dedicada del ámbito del usuario ordinario. Solo los usuarios autorizados pueden tener acceso a estos registros y realizar búsquedas, pero no pueden modificarlos ni borrarlos.
- Los metadatos de cada elemento incluyen una marca de tiempo usada en el cálculo de la duración de la retención. Las marcas de hora se aplican cuando se recibe o se crea un nuevo elemento y no se puede modificar ni quitar de los metadatos.
- El archivado en Office 365 permite a los usuarios combinar distintas directivas de retención y mantener acciones para crear directivas de retención granulares. Estas directivas definen el tipo o la ubicación de los elementos que se conservan y la duración de conservación.
- La característica de bloqueo de preservación permite que los usuarios elijan si la Directiva es una directiva restrictiva. Una directiva restrictiva prohíbe a cualquiera tener la capacidad de quitar, deshabilitar o realizar cambios en la Directiva de retención. Esto significa que una vez que el bloqueo de preservación está habilitado, no se puede deshabilitar y no existirá ningún mecanismo en el que los datos de custodios existentes que hayan sido recopilados por las directivas de retención en vigor puedan sobrescribirse, modificarse, borrarse o eliminarse durante el período de conservación. Además, el período de retención establecido por el bloqueo de conservación no puede reducirse ni disminuir. Sin embargo, se puede alargar en el caso de un requisito legal para continuar la retención de los datos almacenados, como se indicó anteriormente. El bloqueo de preservación garantiza que nadie, ni siquiera los administradores o los que tienen acceso a control, puedan cambiar la configuración o sobrescribir o borrar datos que se hayan almacenado, lo que aportará el archivado en Office 365 en línea con las instrucciones descritas en la versión 2003 de la SEC Rule 17a-4.

Para comprender cómo Office 365 le ayuda a cumplir con las obligaciones reglamentarias, en concreto en relación con los requisitos de reglas 17a-4, consulte este [artículo técnico](https://go.microsoft.com/fwlink/?linkid=830440) que trata el archivado de Exchange Online, SharePoint Online, OneDrive para la empresa y Skype empresarial. El documento también ofrece un análisis exhaustivo de las características y funcionalidades de archivado de Office 365 para cada uno de los requisitos de la regla SEC 17a-4 y demuestra a los clientes regulados cómo Office 365 el archivado puede permitirles cumplir estos requisitos.
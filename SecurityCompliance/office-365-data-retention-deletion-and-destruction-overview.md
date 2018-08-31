---
title: Retención, eliminación y destrucción de datos en Office 365
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
description: Una descripción general de las directivas de Microsoft para Office 365 con respecto a la retención de datos, eliminación y destrucción.
ms.openlocfilehash: 4d952058df8d0efb664f23e5495796fdb9e006f2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535955"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Retención, eliminación y destrucción de datos en Office 365

## <a name="introduction"></a>Introducción
Microsoft tiene una directiva estándar de tratamiento de datos para Office 365 que especifica cuánto tiempo se conservarán los datos de cliente después va a eliminar. Por lo general, incluido en Office 365, hay dos escenarios en los que se eliminan los datos de cliente:
- **Eliminación active** - un usuario elimina datos, o datos privados de un usuario se eliminarán después de que el usuario se elimina por el Administrador de un inquilino activo.
- **Eliminación de pasivo** - los extremos de suscripción del inquilino.

La directiva estándar de tratamiento de datos de Microsoft para Office 365 especifica cuánto se va a conservar los datos en cada uno de estos escenarios. Las secciones siguientes describen las categorías de datos (que se basa en la clasificación de activos de Office 365 estándar de Microsoft) y los períodos de retención para los escenarios de eliminación activas y pasivas.

## <a name="active-deletion-retention"></a>Retención de eliminación activo

| Categoría de datos | Conservar al menos | Conservar como máximo |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| Datos de Control de acceso | N/D | N/D |
| Contenido de cliente | 7 días | 30 días |
| Información de identificación personal del usuario final | 90 días | 180 días |
| Datos de la cuenta | 1 año | 3 años |
| Información de identificación de organización | 90 días | 180 días |
| Metadatos del sistema | Consulte los registros de seguridad | Consulte los registros de seguridad |
| Registros de seguridad | Min 1 año | 1 año de Max |
| Registros de archivado en línea de Exchange | Min 3 años | 3 años de Max |

## <a name="passive-deletion-retention"></a>Retención de eliminación pasivo

| Categoría de datos | Conservar al menos | Conservar como máximo |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| Datos de Control de acceso | 90 días (para la recuperación de contenido) | 180 días (para la recuperación de contenido) |
| Contenido de cliente | 90 días (cuenta de función limitada) | 180 días |
| Información de identificación personal del usuario final | 90 días | 180 días |
| Datos de la cuenta | 1 año | 3 años |
| Información de identificación de organización | 90 días | 180 días |
| Metadatos del sistema | Consulte los registros de seguridad | Consulte los registros de seguridad |
| Registros de seguridad | Min 1 año | 1 año de Max |
| Registros de archivado en línea de Exchange | Min 3 años | 3 años de Max |

## <a name="subscription-rentention"></a>Limpieza de suscripción

Contenido de cliente se define como el contenido del buzón Exchange Online (cuerpo, las entradas de calendario y el contenido de los datos adjuntos de correo electrónico, correo electrónico y, si procede, Skype para contenido empresarial), SharePoint Online contenido del sitio y los archivos almacenados dentro de los sitios y cargar a OneDrive para empresa o de Skype para la empresa.

En todo momento durante el término de una suscripción, un suscriptor puede tener acceso y extraer los datos del cliente almacenados en Office 365. Excepto en versiones gratuitas y servicios de LinkedIn, Microsoft mantiene datos almacenados en Office 365 en una cuenta limitada función durante 90 días después de la caducidad o la terminación de la suscripción para habilitar el suscriptor extraer los datos de los clientes. (En el caso de una versión de prueba gratuita, cuando expire la versión de evaluación, lo traslada a un período de gracia, que confiere 30 días (para la mayoría ensayos, en la mayoría de países y regiones) para adquirir Office 365. Si decide no comprar Office 365, puede let su caducidad de prueba o Cancelar. Poco después del período de gracia de 30 días, su información de cuenta de prueba y los datos se permanentemente borrará.)

Después de que finalice el período de retención de 90 días, Microsoft deshabilita la cuenta y elimina los datos del cliente. No más de 180 días después de la expiración o terminación de una suscripción a Office 365, Microsoft deshabilitar la cuenta y eliminar todos los datos de cliente de la cuenta. Una vez que haya transcurrido el período de retención máximo para todos los datos, los datos se representan comercialmente irrecuperables.

Microsoft también dispone de una directiva estándar de tratamiento de datos que resuelve el reciclaje y la eliminación de unidades de disco y con errores o retirar servidores. Antes de volver a usar las unidades de disco dentro de Office 365, Microsoft lleva a cabo un proceso de limpieza físico que sea compatible con NIST SP 800-88. Unidades de disco que no se puede volver a utilizadas se eliminan mediante un proceso de destrucción física que se lleva a cabo en el sitio del centro de datos que contiene los discos que se va a destruir. Estos procedimientos se llevan a cabo mediante la infraestructura de nube de Microsoft & operaciones (MCIO). Para obtener más información, consulte el MCIO de informes en la [Vista previa de confianza del servicio](https://aka.ms/STP)de auditoría.

## <a name="expedited-deletion"></a>Eliminación acelerada
En todo momento durante el término de una suscripción, un suscriptor puede ponerse en contacto con Microsoft Support y solicitud EF Desaprovisionamiento de suscripción. En este proceso, todos los datos de usuario, incluidos los datos de SharePoint Online, Exchange Online que puede estar en suspensión o almacenados en los buzones de correo inactivos, es eliminados tres días después de que el administrador escribe el código de bloqueo proporcionado por Microsoft. Para obtener más información sobre desaprovisionamiento acelerada, vea [Cancelar Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).

## <a name="related-links"></a>Vínculos relacionados
- [Eliminación de datos en Exchange Online](/office365/enterprise/office-365-exchange-online-data-deletion)
- [Eliminación de datos en SharePoint Online](/office365/enterprise/office-365-sharepoint-online-data-deletion)
- [Eliminación de datos en Skype Empresarial](/office365/enterprise/office-365-skype-data-deletion)
- [Inmutabilidad en Office 365](/office365/enterprise/office-365-data-immutability)
- [Destrucción de datos](/office365/enterprise/office-365-data-destruction)
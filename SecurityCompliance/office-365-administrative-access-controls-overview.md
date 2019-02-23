---
title: Controles de acceso administrativo en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: información general sobre los controles de acceso administrativo de Office 365 y la categorización de datos.'
ms.openlocfilehash: b23fcdcb6c790b3860a24a555424beb3bb99e4f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216030"
---
# <a name="administrative-access-controls-in-office-365"></a>Controles de acceso administrativo en Office 365 

## <a name="introduction"></a>Introducción
Microsoft ha invertido intensamente y en consecuencia en sistemas y controles que automatizan la mayoría de las operaciones de Office 365 mientras limita intencionadamente el acceso de Microsoft al contenido de los clientes. Los seres humanos rigen el servicio y el software opera el servicio. Esto permite a Microsoft administrar Office 365 a escala, así como administrar los riesgos de amenazas internas para el contenido de los clientes, como actores malintencionados, la suplantación de identidad (phishing) de un ingeniero de Microsoft, etc.

De forma predeterminada, los ingenieros de Microsoft tienen privilegios administrativos que no tienen ningún derecho de acceso permanente al contenido del cliente en Office 365. Un ingeniero de Microsoft puede tener un acceso limitado, auditado y seguro al contenido de un cliente durante un período de tiempo limitado, pero solo cuando sea necesario para operaciones de servicio, y solo cuando lo apruebe un miembro de la administración Senior de Microsoft (y para los clientes que tiene licencia para la característica de caja de caja del cliente, el cliente).

Microsoft proporciona servicios en línea, como Office 365, con varios formularios de entrega de nube:

- **Nubes públicas** : incluye versiones de varios inquilinos de Office 365, Azure y otros servicios hospedados en Norteamérica, Sudamérica, Europa, Asia, Australia, etc.
- **Nubes nacionales** : incluye todas las nubes con soberano y de terceros operados fuera de los Estados Unidos (excepto los que se indicaron anteriormente), como Office 365 en China (que es operado por 21Vianet) y Office 365 en Alemania (operaDo por Microsoft, pero en un modelo en el que un administrador de confianza de datos en alemán, Deutsche Telekom, controla y supervisa el acceso de Microsoft a los datos de clientes y sistemas que contienen datos del cliente).
- **Nubes gubernamentales** : incluye los servicios de Office 365 y Azure que están disponibles para los clientes del gobierno de Estados Unidos.

A efectos de este artículo, los servicios de Office 365 incluyen [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online), [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview), [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) (incluido [OneDrive para la empresa](https://docs.microsoft.com/OneDrive/onedrive)) y [Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online), con información adicional sobre algunos controles de acceso de [Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) . Otros servicios de Office 365 están fuera del ámbito de este artículo.

## <a name="office-365-access-controls"></a>Controles de acceso de Office 365
Para fines de control de acceso, los datos de Office 365 se clasifican como datos de cliente u otros tipos de datos. Los datos de clientes son todos los datos proporcionados por o en nombre de un cliente a través del uso que el cliente haga de los servicios 365 de Office, como el contenido del cliente (contenido directamente creado o cargado por los usuarios de Office 365, incluidos los mensajes de correo electrónico, el contenido de SharePoint Online, los mensajes instantáneos, los elementos de calendario, los documentos y los contactos almacenados en Office 365) y la información de identificación del usuario final (EUII) (datos que son únicos para un usuario o que son vinculables a un usuario individual pero que no incluyen contenido del cliente). 

Otros tipos de datos incluyen datos de la cuenta (incluye datos administrativos, que es la información que proporcionan los administradores cuando registran o compran servicios, y datos de pago, que es información acerca de los instrumentos de pago, como los detalles de la tarjeta de crédito). información de identificación organizativa (datos que se pueden usar para identificar un inquilino o datos de uso; no se puede vincular a un usuario individual y no incluye contenido del cliente) y metadatos del sistema (incluye registros de servicio que contienen opciones de configuración, Estado del sistema, direcciones IP de Microsoft e información técnica sobre suscripciones e inquilinos).

Microsoft ha establecido mecanismos de control de acceso para garantizar que nadie tenga acceso no aprobado a datos de clientes o datos de control de acceso (se usa para administrar el acceso a otros tipos de datos o funciones dentro del entorno, incluido el acceso al contenido del cliente o EUII; se incluye contraseñas de Microsoft, certificados de seguridad y otros datos relacionados con la autenticación) o un acceso físico, lógico o remoto no aprobado al entorno de producción de Office 365.

Los controles de acceso que usa Microsoft para Office de operación 365 se pueden agrupar en tres categorías:
- Controles de aislamiento
- Controles de personal
- Controles de tecnología

Cuando se combinan, estos controles ayudan a evitar y detectar acciones malintencionadas en Office 365. Además de los controles de aislamiento, personal y tecnología que usa Microsoft, hay una cuarta categoría de controles: los implementados por los clientes.

Office 365 le permite administrar los datos en la misma forma en la que se administran los datos en entornos locales. La persona que registra una organización para Office 365 se convierte automáticamente en un administrador global (Administrador). El administrador global tiene acceso a todas las características de los portales de administración (por ejemplo, centros de administración y PowerShell remoto) y puede crear o editar usuarios, asignar roles de administrador a otros, restablecer contraseñas de usuario, administrar licencias de usuario, administrar dominios y aprobar cajas de caja de clientes. solicitudes, entre otras cosas. Se recomienda que cada organización designe al menos dos cuentas de administrador, y según el tamaño de la organización, es posible que desee designar a varios administradores que atienden funciones diferentes. Para obtener información acerca de la asignación de roles y permisos de administrador, vea [asignar roles de administrador en Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) y [acerca de Office 365 roles de administrador](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).


## <a name="related-links"></a>Vínculos relacionados

- [Controles de aislamiento](office-365-isolation-controls.md)
- [Controles de personal](office-365-personnel-controls.md)
- [Controles de tecnología](office-365-technology-controls.md)
- [Auditoría y supervisión de controles de acceso](office-365-monitoring-and-auditing-access-controls.md)
- [Controles de acceso de Yammer Enterprise](office-365-yammer-enterprise-access-controls.md)
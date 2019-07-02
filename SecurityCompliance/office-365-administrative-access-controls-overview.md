---
title: Controles de acceso administrativo en Office 365
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
description: 'Resumen: información general sobre los controles de acceso administrativo de Office 365 y la categorización de datos.'
ms.openlocfilehash: 38519fe4e9c05e3468ac3f9f6367c096fb64d195
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520700"
---
# <a name="administrative-access-controls-in-office-365"></a>Controles de acceso administrativo en Office 365 

Microsoft ha invertido mucho en sistemas y controles que automatizan la mayoría de las operaciones de Office 365 mientras limitan de forma intencionada el acceso al contenido del cliente por parte de Microsoft. Los seres humanos rigen el servicio y el software opera el servicio. Esto permite que Microsoft administre Office 365 a escala y administre los riesgos de las amenazas internas para el contenido de los clientes.

De forma predeterminada, los ingenieros de Microsoft tienen privilegios administrativos que no tienen ningún derecho de acceso permanente al contenido del cliente en Office 365. Un ingeniero de Microsoft puede tener un acceso limitado, auditado y seguro al contenido de un cliente durante un período de tiempo limitado. El acceso solo es necesario para las operaciones de servicio y solo cuando lo aprueba un miembro de la administración Senior de Microsoft. Para los clientes con licencia de caja de caja de clientes, el cliente proporciona la aprobación de acceso a su contenido hospedado en Office 365.

Microsoft proporciona servicios en línea con varios formularios de entrega de nube:

- **Nubes públicas:** Incluye versiones de varios inquilinos de Office 365, Azure y otros servicios hospedados en Norteamérica, Sudamérica, Europa, Asia, Australia, etc.
- **Nubes nacionales:** Incluye todas las nubes soberanos y de terceros operadas fuera de los Estados Unidos (excepto las que se han mencionado anteriormente), como Office 365 en China (operado por 21Vianet) y Office 365 en Alemania (operado por Microsoft, pero bajo un modelo en el que se confía en los datos en alemán; Deutsche Telekom, controla y supervisa el acceso de Microsoft a los datos de los clientes y los sistemas que contienen datos del cliente).
- **Nubes gubernamentales:** Incluye los servicios de Office 365 y Azure que están disponibles para los clientes del gobierno de Estados Unidos.

A efectos de este artículo, los servicios de Office 365 incluyen:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive para la Empresa](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype Empresarial](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="office-365-access-controls"></a>Controles de acceso de Office 365

Para fines de control de acceso, Microsoft clasifica los datos de Office 365 como datos de cliente u otros tipos de datos.

### <a name="customer-data"></a>Datos de cliente

Los datos de los clientes son todos los datos proporcionados por o en nombre de un cliente cuando se usan los servicios de Office 365. Se trata de contenido de cliente que se crea o carga directamente con los usuarios de Office 365, incluidos los siguientes:

- Mensajes de correo electrónico
- Contenido de SharePoint Online
- Mensajes instantáneos
- Elementos de calendario
- Documents
- Contactos
- Información de identificación del usuario final (EUII) (datos que son únicos para un usuario o que son vinculables a un usuario individual pero que no incluyen contenido del cliente).

### <a name="other-types-of-data"></a>Otros tipos de datos

Otros tipos de datos son:

- **Datos de la cuenta:** Incluye datos administrativos (información proporcionada por los administradores cuando registran o compran servicios) y datos de pago (información sobre instrumentos de pago, como detalles de la tarjeta de crédito).
- **Información de identificación organizativa:** Incluye datos que se usan para identificar un espacio empresarial, datos de uso y no vinculables a un usuario individual o incluidos en el contenido del cliente.
- **Metadatos del sistema:** Incluye registros de servicios que contienen opciones de configuración, estado del sistema, direcciones IP de Microsoft e información técnica sobre suscripciones e inquilinos.

Microsoft ha establecido mecanismos de control de acceso para garantizar que nadie tenga acceso no aprobado a datos de clientes o a datos de control de acceso. Los datos de control de acceso administran el acceso a otros tipos de datos o funciones dentro del entorno, incluidos el acceso al contenido del cliente o la EUII, las contraseñas de Microsoft, los certificados de seguridad y otros datos relacionados con la autenticación. Los mecanismos de control de acceso también protegen contra el acceso físico, lógico o remoto no aprobado al entorno de producción de Office 365.

Microsoft usa tres categorías de controles de acceso para Office de operaciones 365:

- Controles de aislamiento
- Controles de personal
- Controles de tecnología

Cuando se combinan, estos controles ayudan a evitar y detectar acciones malintencionadas en Office 365. Además de los controles de aislamiento, personal y tecnología que usa Microsoft, hay una cuarta categoría de controles: los implementados por los clientes.

Office 365 permite administrar los datos de la misma manera que los datos se administran en entornos locales. La persona que registra una organización para Office 365 se convierte automáticamente en un administrador global. El administrador global tiene acceso a todas las características de los portales de administración y puede:

- Crear o editar usuarios
- Asignar roles de administrador a otros
- Restablecer contraseñas de usuario
- Administrar licencias de usuario
- Administrar dominios
- Aprobar solicitudes de caja de caja de cliente

Se recomienda que cada organización configure al menos dos cuentas de administrador. Para grandes organizaciones empresariales, recomendamos cuentas de administrador especializadas que atienden diferentes funciones.

Para obtener información acerca de la asignación de roles y permisos de administrador, vea [asignar roles de administrador en Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) y [acerca de Office 365 roles de administrador](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).

## <a name="related-links"></a>Vínculos relacionados

- [Controles de aislamiento](office-365-isolation-controls.md)
- [Controles de personal](office-365-personnel-controls.md)
- [Controles de tecnología](office-365-technology-controls.md)
- [Auditoría y supervisión de controles de acceso](office-365-monitoring-and-auditing-access-controls.md)
- [Controles de acceso de Yammer Enterprise](office-365-yammer-enterprise-access-controls.md)
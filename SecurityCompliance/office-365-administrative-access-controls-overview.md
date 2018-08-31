---
title: Controles de acceso administrativo en Office 365
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
description: 'Resumen: Información general de la categorización de datos y los controles de acceso administrativo de Office 365.'
ms.openlocfilehash: afa15d37aa8542985c59dbd9e3d82368421530e8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536203"
---
# <a name="administrative-access-controls-in-office-365"></a>Controles de acceso administrativo en Office 365 

## <a name="introduction"></a>Introducción
Microsoft ha invertido muy y según corresponda en sistemas y controles que automatizan la mayoría de las operaciones de Office 365 mientras se limita intencionadamente access de Microsoft para el contenido del cliente. Personas controlan el servicio y software funciona el servicio. Esto permite a Microsoft administrar Office 365 a escala, así como para administrar los riesgos de amenazas internas en el contenido de cliente como actores malintencionados, la suplantación de identidad lanza de un ingeniero de Microsoft y así sucesivamente.

De forma predeterminada, los ingenieros de Microsoft tienen cero privilegios administrativos permanente y cero acceso permanente al contenido del cliente en Office 365. Un ingeniero de Microsoft ha limitado, auditar y protege el acceso a un cliente contenido durante un período limitado de tiempo, pero únicamente cuando sea necesario para las operaciones de servicio y sólo cuando sea aprobada por un miembro de los directivos de Microsoft (y para los clientes que están licencia para la característica de caja de seguridad del cliente, el cliente).

Microsoft proporciona servicios en línea, incluidos Office 365, con varios formularios de entrega en la nube:

- **Las nubes públicas** - incluye versiones de varios inquilinos de Office 365, Azure y otros servicios que se hospedan en Norteamérica, Sudamérica, Europa, Asia, Australia, etcetera.
- **Nubes nacional** - incluye todas las nubes soberanos y operado por terceros fuera de los Estados Unidos (excepto los que se ha mencionado anteriormente), como Office 365 en China (que funciona a través de 21Vianet) y Office 365 en Alemania (que es operado por Microsoft, pero en un modelo en el que un administrador de datos alemán, Deutsche Telekom, controla y supervisa access de Microsoft para datos de clientes y sistemas que contienen los datos de cliente).
- **Nubes de gobierno** - incluye Office 365 y Azure servicios que están disponibles para clientes del gobierno de Estados Unidos.

Para propósitos de este artículo, servicios de Office 365 incluyen [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online), [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview), [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) (incluidos [OneDrive para la empresa](https://docs.microsoft.com/OneDrive/onedrive)) y [Skype para la empresa](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online), con información adicional Algunos controles de acceso [De Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) . Otros servicios de Office 365 están fuera del ámbito de este artículo.

## <a name="office-365-access-controls"></a>Acceso a controles de Office 365
Con fines de control de acceso, de datos de Office 365 se categoriza como los datos de cliente o de otros tipos de datos. Los datos de cliente están todos los datos proporcionados por o en nombre de un cliente a través del uso del cliente de servicios de Office 365, como el contenido de cliente (contenido directamente creados o cargados por usuarios de Office 365 incluidos los correos electrónicos, SharePoint Online contenido, los mensajes instantáneos, los contactos almacenados en Office 365, documentos y elementos de calendario) y la información de identificación para el usuario final (EUII) (datos que sea único a un usuario o que es linkable a un usuario individual, pero no incluye el contenido del cliente). 

Otros tipos de datos incluyen datos de la cuenta (incluye datos administrativos, que es la información proporcionada por los administradores cuando puedan inscripción o servicios de compra y datos de pago, que es información acerca de instrumentos de pago, como crédito tarjeta detalles), información de identificación de organización (datos que se pueden usar para identificar un inquilino; o los datos de uso; no es linkable a un usuario individual y no incluye el contenido del cliente) y los metadatos del sistema (incluye los registros de servicio que contienen valores de configuración, estado del sistema, las direcciones IP de Microsoft e información técnica acerca de las suscripciones y los inquilinos).

Microsoft ha establecido mecanismos de control de acceso para asegurarse de que nadie tenga acceso no autorizados a los datos de control de acceso o los datos de cliente (usado para administrar el acceso a otros tipos de datos o funciones en el entorno, incluido el acceso a contenido de atención al cliente o EUII; se incluye las contraseñas, certificados de seguridad y otros datos relacionados con la autenticación de Microsoft) o no aprobado físico, lógico o de acceso remoto para el entorno de producción de Office 365.

Los controles de acceso utilizados por Microsoft para el funcionamiento de Office 365 pueden agruparse en tres categorías:
- Controles de aislamiento
- Controles de personal
- Controles de tecnología

Cuando se combina, estos controles ayudan a evitar y detectar acciones malintencionadas en Office 365. Además de aislamiento, personal y controles de tecnología utilizados por Microsoft, hay una cuarta categoría de controles: aquellas implementan por los clientes.

Office 365 le permite administrar los datos de que gran parte de la misma forma que los datos se administra en entornos local. La persona que se registra una organización para Office 365 automáticamente se convierte en un administrador global (admin). El administrador global tiene acceso a todas las características de los portales de administración (por ejemplo, centros de administrador y PowerShell remoto) y puede crear o editar usuarios, asignar roles de administrador a otras personas, restablecer contraseñas de usuario, administrar licencias de usuario, administrar dominios y aprobar la caja de seguridad del cliente solicitudes, entre otras cosas. Se recomienda que cada organización designar al menos dos cuentas de administrador y, según el tamaño de la organización, es posible que desea designar varios administradores que realizan distintas funciones. Para obtener información acerca de cómo asignar permisos y roles de administrador, vea [asignación de roles de administrador en Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) y [las funciones de administración de acerca de Office 365](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).


## <a name="related-links"></a>Vínculos relacionados

- [Controles de aislamiento](office-365-isolation-controls.md)
- [Controles de personal](office-365-personnel-controls.md)
- [Controles de tecnología](office-365-technology-controls.md)
- [Auditoría y supervisión de controles de acceso](office-365-monitoring-and-auditing-access-controls.md)
- [Controles de acceso de Yammer Enterprise](office-365-yammer-enterprise-access-controls.md)
---
title: Controles de tecnología de Office 365
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
description: 'Resumen: información general sobre las prácticas de control de tecnología de Microsoft para Office 365.'
ms.openlocfilehash: ce2e09ce7db881197d2598c52283ecde7ed46e61
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622440"
---
# <a name="office-365-technology-controls"></a>Controles de tecnología de Office 365 

Microsoft usa varias herramientas y tecnologías para controlar, administrar y auditar el acceso a los datos de los clientes en sus servicios en línea. Estos se aplican a Exchange Online, SharePoint Online, caja de seguridad y caja de seguridad del cliente, autenticación multifactor y más. Yammer usa controles similares descritos en [los controles de acceso de Yammer Enterprise](office-365-yammer-enterprise-access-controls.md).

Los ingenieros de Office 365 tienen un acceso sin el mismo día a los datos de cliente de Office 365. Los ingenieros deben pasar por un proceso de aprobación de Microsoft antes de que se pueda obtener acceso a los datos de los clientes para las operaciones de servicio. Si el cliente concede la característica de caja de seguridad del cliente para Exchange Online y SharePoint Online, el acceso a los datos del cliente requiere la aprobación del cliente. Una vez aprobadas, las cuentas administrativas específicas del servicio reciben acceso Just-in-Time para las tareas requeridas por la solicitud de servicio.

## <a name="lockbox-and-customer-lockbox"></a>Caja de liquidación y caja de caja del cliente

Aunque rara vez, un cliente podría solicitar ayuda de Microsoft que exponga contenido de clientes a un ingeniero de Microsoft. Para controlar el acceso a Exchange Online, Microsoft usa un sistema de control de acceso denominado Lockbox. Antes de que cualquier Ingeniero de Microsoft tenga acceso a cualquier sistema o datos de Exchange online o SharePoint Online, debe enviar una solicitud de acceso con la caja de seguridad. Todas las solicitudes de servicio de Exchange Online y SharePoint Online se controlan mediante el sistema de liquidación. Tanto con Lockbox como con caja de control de cliente, se puede realizar un seguimiento del acceso aprobado a un usuario único, lo que hace que los ingenieros se encargan de la administración de los datos del cliente.

> [!NOTE]
> Exchange Online incluye todos los datos de Skype empresarial almacenados en buzones de usuario. La cobertura de Skype empresarial no incluye las grabaciones de difusión de reunión de Skype ni el contenido cargado en las reuniones por los usuarios. SharePoint Online incluye OneDrive para la empresa.

Lockbox procesa solicitudes de permisos que conceden a los ingenieros la capacidad de realizar funciones operativas y administrativas dentro del servicio. Los ingenieros envían solicitudes a través del Lockbox y un administrador de Microsoft debe aprobar la solicitud antes de que el técnico pueda acceder a los datos del cliente. Tras la aprobación del administrador, el ingeniero tiene acceso limitado al tiempo y a los datos de los clientes con limitaciones limitadas en cuanto al problema del cliente.

Caja de caja de cliente para Office 365 ayuda a cumplir con las obligaciones de cumplimiento si necesita procedimientos para la autorización explícita de acceso a datos. Se trata de un requisito para algunas normas de cumplimiento, como FedRAMP e HIPAA. La caja de seguridad del cliente le inserta en el proceso de aprobación de la liquidación y le ofrece la posibilidad de controlar la autorización de Microsoft Access a su contenido de Exchange online o SharePoint Online para operaciones de servicio.

En el caso poco frecuente de que un ingeniero de servicios de Microsoft necesite tener acceso a sus datos, sólo debe conceder acceso a los datos necesarios para resolver el problema y durante un período de tiempo limitado. Si rechaza una solicitud de acceso, los ingenieros de Microsoft no tienen acceso a su contenido y no podrán completar las operaciones de servicio. Si aprueba la solicitud, los ingenieros de Microsoft tienen un acceso Just-in-Time limitado al contenido a través de interfaces de administración restringidas y supervisadas.

Las acciones llevadas a cabo por el ingeniero de soporte se registran con fines de auditoría y son accesibles a través de la [API de actividad de administración de Office 365](https://msdn.microsoft.com/library/office/dn707383.aspx) y el [centro de seguridad y cumplimiento](http://protection.office.com/).

>[!NOTE]
> La caja de caja de cliente está disponible en [Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software) como una compra de complemento. Para obtener más información, consulte [Solicitudes de caja de seguridad del cliente de Office 365](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

## <a name="just-in-time-access"></a>Acceso Just-in-Time

Microsoft usa el principio de acceso Just-in-Time (JIT) para Office 365 para mitigar los riesgos de manipulación de las credenciales y los ataques transversales. JIT quita el acceso administrativo persistente a los servicios y reemplaza los derechos por la capacidad de elevar a esas funciones a petición. La eliminación de los derechos de acceso persistente de los administradores garantiza que las credenciales solo están disponibles cuando se necesitan y reduce los riesgos de robo de credenciales.

El modelo de acceso JIT requiere que los ingenieros soliciten privilegios elevados durante un período limitado para realizar tareas administrativas. Además, los ingenieros usan cuentas temporales creadas con contraseñas complejas generadas por el equipo y que conceden solo los roles que les permiten realizar las tareas necesarias. Por ejemplo, el acceso administrativo que conceda la liquidación está limitado por el tiempo y la cantidad de tiempo que se concede el acceso depende del rol solicitado. Un ingeniero especifica la duración de tiempo de acceso necesario en la solicitud al sistema de liquidación. El sistema de liquidación rechaza las solicitudes cuando el tiempo solicitado supera el tiempo máximo permitido para la elevación. Tras la expiración, se quita el acceso administrativo y expira la cuenta temporal.

Cuando se autorizan y se aprueban para el acceso, los ingenieros reciben una contraseña administrativa de un solo uso generada por el sistema de autorización. Las nuevas contraseñas se generan cada vez que se aprueba una solicitud de acceso elevado. La contraseña se copia en una contraseña segura, es independiente de las credenciales del ingeniero para el entorno corporativo de Microsoft y es buena sólo para la sesión de acceso elevado aprobada.

## <a name="constrained-management-interfaces"></a>Interfaces de administración restringidas

Los ingenieros usan dos interfaces de administración para realizar tareas administrativas: escritorio remoto a través de puertas de enlace de terminal de servicio seguras (TSGs) y PowerShell remoto. En estas interfaces de administración, las directivas de software y los controles de acceso imponen importantes restricciones sobre qué aplicaciones se ejecutan y qué comandos y cmdlets están disponibles.

Los servidores de Office 365 restringen las sesiones simultáneas a una sesión de administrador de equipo por servicio, por servidor. TSGs permite solo una sesión simultánea para los usuarios y no permite varias sesiones. Si se usa una sola sesión por servidor, TSGs permitir que los administradores de equipo de servicio de Office 365 se conecten a varios servidores a la vez para que los administradores puedan realizar sus tareas de manera efectiva. Los administradores de equipo de servicio no tienen permisos en los propios TSGs. El TSG solo se usa para exigir la autenticación multifactor (MFA) y los requisitos de cifrado. Una vez que el administrador del equipo de servicio se conecta a un servidor específico a través de un TSG, el servidor específico aplica un límite de sesión de uno por administrador.

Las directivas de grupo de Active Directory establecen las restricciones de uso y los requisitos de conexión y configuración para Office 365 personal. Estas directivas incluyen las siguientes características:

- TSGs usar solo el cifrado validado [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2.
- Las sesiones de TSG se desconectan después de 30 minutos de inactividad.
- Las sesiones de TSG cierran sesión automáticamente transcurridas 24 horas.

Las conexiones a TSGs también requieren MFA con una tarjeta inteligente física independiente y una cuenta separada de las credenciales de la empresa de Microsoft del ingeniero. Los ingenieros reciben diferentes tarjetas inteligentes para diversas plataformas y plataformas de administración de secretos, con lo que garantizan el almacenamiento seguro de las credenciales. TSGs usar directivas de grupo de Active Directory para controlar quién puede iniciar sesión en servidores remotos, el número de sesiones permitidas y la configuración del tiempo de espera de inactividad. Las directivas adicionales limitan el acceso a las aplicaciones permitidas y restringen el acceso a Internet.

Además del acceso remoto mediante TSGs configurados especialmente, Exchange Online permite a los usuarios con la función de operaciones de Ingeniero de servicios tener acceso a determinadas funciones administrativas en los servidores de producción mediante PowerShell remoto. Para ello, el usuario debe tener autorización para el acceso de solo lectura (depuración) al entorno de producción de Office 365. La elevación de privilegios está habilitada del mismo modo que se habilita para TSGs mediante el proceso de liquidación.

Para el acceso remoto, cada centro de recursos tiene una IP virtual de carga equilibrada que sirve como punto de acceso único. Los cmdlets de PowerShell remoto disponibles se basan en el nivel de privilegio identificado en la notificación de acceso obtenida durante la autenticación. Estos cmdlets proporcionan la única funcionalidad administrativa accesible para los usuarios que se conectan con este método. PowerShell remoto limita el ámbito de los comandos disponibles para el ingeniero y se basa en el nivel de acceso que se concede a través del proceso de liquidación. Por ejemplo, en Exchange Online, Get-Mailbox puede estar disponible, pero Set-Mailbox no.

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
ms.openlocfilehash: a8dcb65880fc729fc067b2f2bcf25c7db76dbca9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262342"
---
# <a name="office-365-technology-controls"></a>Controles de tecnología de Office 365 

Microsoft usa varias herramientas y tecnologías para controlar, administrar y auditar el acceso a los datos de los clientes en Exchange Online y SharePoint Online, incluida la caja de seguridad y la caja de seguridad del cliente, la autenticación multifactor y mucho más. Yammer Enterprise usa controles similares, como se describe en [controles de acceso de Yammer Enterprise](office-365-yammer-enterprise-access-controls.md).

Los ingenieros de Office 365 tienen acceso de cero a los datos de cliente de Office 365 y deben pasar por un proceso de aprobación que incluya a Microsoft y, si el cliente concede la característica de caja de seguridad del cliente para Exchange Online y SharePoint Online: cliente aprobación, antes de que se pueda realizar el acceso a los datos de cliente de las operaciones de servicio. Cuando se concede la aprobación, las cuentas administrativas específicas del servicio se aprovisionan en un momento con el acceso suficiente para realizar las tareas requeridas por la solicitud de servicio.

## <a name="lockbox-and-customer-lockbox"></a>Caja de liquidación y caja de caja del cliente
Aunque es muy raro, un cliente podría solicitar asistencia de Microsoft que podría exponer a un ingeniero de Microsoft en el contenido del cliente para ayudarles a resolver un problema. Para controlar el acceso a Exchange Online (que incluye los datos de Skype empresarial almacenados en los buzones de los usuarios) (la cobertura de Skype empresarial no incluye las grabaciones de difusión de reunión de Skype ni el contenido cargado en las reuniones por los usuarios)) y SharePoint Online (que incluye OneDrive para la empresa), Microsoft usa un sistema de control de acceso denominado Lockbox. Antes de que cualquier Ingeniero de Microsoft pueda tener acceso a cualquier sistema o datos de Exchange online o SharePoint Online, debe enviar una solicitud de acceso con Lockbox. Se requiere el uso de la caja de seguridad para todos los accesos elevados a Exchange online o SharePoint Online.

Lockbox procesa solicitudes de permisos que conceden a los ingenieros la capacidad de realizar funciones operativas y administrativas dentro del servicio. Los ingenieros envían solicitudes a través del Lockbox, que debe ser aprobada por un administrador antes de que el ingeniero obtenga acceso a los datos de los clientes. Tras la aprobación del Director, el ingeniero tiene un acceso limitado al tiempo y limitado a los datos del cliente para que funcionen en el problema del cliente.

La caja de caja de cliente de Office 365 puede ayudarle a cumplir con las obligaciones de cumplimiento, como las que se encuentran en FedRAMP e HIPAA, si necesita procedimientos en su ubicación para la autorización explícita de acceso a datos. En la instancia rara, cuando un ingeniero de servicios de Microsoft necesita tener acceso a los datos, sólo tiene que conceder acceso a los datos necesarios para resolver el problema y durante un período de tiempo limitado. Las acciones llevadas a cabo por el ingeniero de soporte se registran con fines de auditoría y son accesibles a través de la [API de actividad de administración de Office 365](https://msdn.microsoft.com/library/office/dn707383.aspx) y el [centro de seguridad y cumplimiento](http://protection.office.com/). La caja de seguridad del cliente inserta el cliente en el proceso de aprobación de la liquidación y les proporciona la capacidad de controlar la autorización de Microsoft Access a su contenido de Exchange online o de SharePoint Online para las operaciones de servicio.

>**Nota**: las cajas de caja de clientes están disponibles en [Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software) y como una compra de complemento, pero debe realizarse una acción manual en el centro de administración de Microsoft 365 (en configuración del servicio | Caja de caja del cliente) para habilitarla. Para obtener más información, consulte [Solicitudes de caja de seguridad del cliente de Office 365](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

Todas las solicitudes de servicio de Exchange Online y SharePoint Online se controlan mediante el sistema de liquidación. Y con caja de caja del cliente, cualquier operación de servicio que requiera el acceso a estos servicios con la exposición a los datos de los clientes pasa por el proceso de aprobación de la liquidación y, a continuación, permite al cliente aprobar o rechazar la solicitud a partir de ese momento.
 
*Figura 1: flujo de trabajo de caja de cliente*

Si el cliente rechaza la solicitud, el ingeniero de Microsoft no tendrá acceso al contenido del cliente y no podrá completar la operación del servicio. Si la solicitud está aprobada por el cliente, el ingeniero de Microsoft tendrá un acceso Just-in-Time limitado al contenido del cliente a través de interfaces de administración restringidas y supervisadas. Tanto con Lockbox como con caja de control de cliente, se puede realizar un seguimiento del acceso aprobado a un usuario único, lo que hace que los ingenieros se encargan de la administración de los datos del cliente.

## <a name="just-in-time-access"></a>Acceso Just-in-Time
Microsoft usa el principio de acceso Just-in-Time (JIT) para Office 365 para mitigar aún más el riesgo de manipulación de credenciales y ataques laterales. JIT quita el acceso administrativo persistente a los servicios y los reemplaza con la capacidad de elevarlas a las funciones a petición. La eliminación de los derechos de persistencia de los administradores garantiza que las credenciales solo están disponibles cuando se necesitan y elimina el riesgo que supone para la empresa en caso de robo de credenciales.

El modelo de acceso JIT requiere que los ingenieros soliciten privilegios elevados durante un período limitado para realizar tareas administrativas. Además, los OCEs usan cuentas temporales que se crean con contraseñas complejas generadas por el equipo y que conceden solo los roles que les permiten realizar las tareas necesarias. Por ejemplo, el acceso administrativo que conceda la liquidación está limitado por el tiempo y la cantidad de tiempo que se concede el acceso depende de la función solicitada. Un ingeniero especifica la duración del tiempo de acceso necesario durante la solicitud al sistema de liquidación. El sistema de liquidación rechazará las solicitudes en las que el tiempo solicitado supere el tiempo máximo permitido para la elevación. Tras la expiración de la solicitud de elevación, se quita el acceso administrativo y la cuenta temporal expira.

Cuando se autoriza y se aprueba el acceso (por ejemplo, para depurar un sistema), los ingenieros reciben una contraseña administrativa de uso único que genera el sistema de autorización cada vez que se aprueba una solicitud para el acceso elevado. El ingeniero copia esta contraseña en una contraseña segura, es independiente de las credenciales del ingeniero para el entorno corporativo de Microsoft y solo es válida para la sesión para la que se aprobó el acceso elevado.

## <a name="constrained-management-interfaces"></a>Interfaces de administración restringidas
OCEs usar dos interfaces de administración para realizar tareas administrativas: escritorio remoto a través de puertas de enlace de Terminal Services protegidas (TSGs) y PowerShell remoto. En estas interfaces de administración hay directivas de software y controles de acceso que imponen importantes restricciones sobre las aplicaciones que se pueden ejecutar y qué comandos y cmdlets están disponibles. 

Los servidores de Office 365 restringen las sesiones simultáneas a una sesión de administrador de equipo por servicio, por servidor. TSGs están configuradas para permitir solo una sesión simultánea para los usuarios y no permiten varias sesiones. TSGs permitir que los administradores de equipo de servicio de Office 365 se conecten a varios servidores simultáneamente, mediante una única sesión por servidor, para que los administradores puedan realizar sus tareas de manera efectiva. Los administradores de equipo de servicio no tienen permisos en los propios TSGs. El TSG solo se usa para exigir la autenticación multifactor (MFA) y los requisitos de cifrado. Una vez que el administrador del equipo de servicio se conecta a un servidor específico a través de un TSG, el servidor específico aplicará un límite de sesión de uno por administrador.

Las directivas de grupo de Active Directory establecen las restricciones de uso y los requisitos de conexión y configuración para Office 365 personal. Estas directivas incluyen las siguientes características:
- TSGs están configuradas para usar solo el cifrado validado [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2
- Las sesiones de TSG están configuradas para desconectar después de 30 minutos de inactividad
- Las sesiones de TSG están configuradas para cerrar sesión automáticamente transcurridas 24 horas

Las conexiones a TSGs también requieren MFA con una tarjeta inteligente física independiente y una cuenta independiente de las credenciales corporativas de Microsoft del ingeniero. Los ingenieros reciben tarjetas inteligentes distintas para las distintas plataformas y las plataformas de administración de secretos se usan para garantizar el almacenamiento seguro de las credenciales. TSGs usar directivas de grupo de Active Directory para controlar quién puede iniciar sesión en servidores remotos, el número de sesiones permitidas y la configuración del tiempo de espera de inactividad. Se han implementado directivas adicionales para limitar el acceso a las aplicaciones permitidas y restringir el acceso a Internet.

Además del acceso remoto mediante la configuración especial TSGs, Exchange Online permite a los usuarios con la función Operations Engineer Service (operaciones) tener acceso a determinadas funciones administrativas en los servidores de producción mediante PowerShell remoto. Para ello, el usuario debe tener autorización para el acceso de solo lectura (depuración) al entorno de producción de Office 365. La elevación de privilegios está habilitada del mismo modo que se habilita para TSGs mediante el proceso de liquidación.

Para el acceso remoto, hay una IP virtual de carga equilibrada en cada centro de recursos que sirve como punto de acceso único. Los cmdlets de PowerShell remotos que se pueden ejecutar se basan en el nivel de privilegio identificado en la notificación de acceso obtenida durante la autenticación. Estos cmdlets son la única funcionalidad administrativa a la que pueden tener acceso y ejecutar los usuarios que se conectan con este método. PowerShell en remoto se usa para limitar el ámbito de los comandos disponibles para el técnico, que se basa en el nivel de acceso que se concede a través del proceso de liquidación. Por ejemplo, en Exchange Online, Get-Mailbox puede estar disponible, pero Set-Mailbox no.

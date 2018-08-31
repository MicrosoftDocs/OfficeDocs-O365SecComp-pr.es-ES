---
title: Controles de tecnología de Office 365
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
description: 'Resumen: Información general de las prácticas de control de tecnología de Microsoft para Office 365.'
ms.openlocfilehash: 2ef04b558f5fa82075d9aa602b83d437aa4b2ee6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536085"
---
# <a name="office-365-technology-controls"></a>Controles de tecnología de Office 365 

Microsoft utiliza varias herramientas y tecnologías para controlar, administrar y auditar el acceso a los datos de cliente en Exchange Online y SharePoint Online, incluyendo caja de seguridad y caja de seguridad del cliente, la autenticación multifactor y mucho más. Yammer Enterprise utiliza controles similares, como se describe en [Acceso a controles de empresa de Yammer](office-365-yammer-enterprise-access-controls.md).

Los ingenieros de Office 365 tienen cero acceso permanente a los datos de cliente de Office 365, y deben ir a través de un proceso de aprobación que incluye Microsoft y – si el cliente licencias de la característica de caja de seguridad de cliente para Exchange Online y SharePoint Online: cliente aprobación, antes de que puede producirse el acceso a los datos de cliente para las operaciones de servicio. Cuando se aprueban, las cuentas administrativas de específico del servicio son aprovisionado just-in-time con suficiente acceso para realizar las tareas requeridas por la solicitud de servicio.

## <a name="lockbox-and-customer-lockbox"></a>Caja de seguridad y la caja de seguridad del cliente
Si bien es muy poco habitual, un cliente podría solicitar asistencia de Microsoft que puede exponer un ingeniero de Microsoft para el contenido del cliente para ayudarles a con un problema. Para controlar el acceso a Exchange Online (que incluye cualquier Skype para datos profesionales almacenados en los buzones de los usuarios (Skype para cobertura de negocio no incluye grabaciones de reunión Difundir presentación de Skype o contenido que se cargan en las reuniones por los usuarios)) y SharePoint Online (que incluye OneDrive para la empresa), Microsoft utiliza un sistema de control de acceso llamado caja de seguridad. Antes de cualquier ingeniero de Microsoft puede obtener acceso a los sistemas de Exchange Online o SharePoint Online o datos, debe enviar una solicitud de acceso con la caja de seguridad. Uso de caja de seguridad se requiere para todo el acceso a Exchange Online o SharePoint Online con privilegios elevados.

Caja de seguridad procesa las solicitudes de permisos que se conceden a los ingenieros de la capacidad para realizar funciones operativas y administrativas dentro del servicio. Solicitudes de envío de ingenieros a través de la caja de seguridad, que debe ser aprobada por un administrador antes del ingeniero tengan la posibilidad de obtener acceso a los datos de cliente. Tras la aprobación del administrador, el ingeniero de tiene limitada en el tiempo y ámbito limitado el acceso a datos de clientes para trabajar en el problema del cliente.

Caja de seguridad del cliente para Office 365 puede ayudar a cumplir las obligaciones de cumplimiento de normas, como las que se encuentran en FedRAMP y HIPAA, si necesita procedimientos en lugar de autorización de acceso de datos explícitas. Cuando un ingeniero de servicio de Microsoft necesita tener acceso a los datos, en la instancia rara conceder ese acceso únicamente a los datos necesarios para resolver el problema y para un período de tiempo limitado. Acciones realizadas por el ingeniero de soporte técnico se registran con fines de auditoría y son accesibles a través de la [API de actividad de administración de Office 365](https://msdn.microsoft.com/library/office/dn707383.aspx) y el [Centro de cumplimiento y seguridad](http://protection.office.com/). Caja de seguridad del cliente inserta al cliente en el proceso de aprobación de la caja de seguridad y les proporciona la capacidad de controlar la autorización de Microsoft access a su contenido de SharePoint Online o Exchange Online para operaciones de servicio.

>**Nota**: caja de seguridad del cliente está disponible en [Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software) y como una compra del complemento, pero es necesario tomar medidas manual en el centro de administración de Office 365 (bajo Configuración del servicio | Caja de seguridad del cliente) para habilitarlo. Para obtener más información, vea [Office 365 las solicitudes de caja de seguridad del cliente](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

Todas las solicitudes de servicio de Exchange Online y SharePoint Online se controlan mediante el sistema de caja de seguridad. Y con caja de seguridad del cliente, cualquier operación de servicio que requiera acceso a estos servicios con la exposición a los datos de cliente circula a través del proceso de aprobación de la caja de seguridad y, a continuación, permite al cliente aprobar o rechazar la solicitud a partir de entonces.
 
*En la figura 1 - flujo de trabajo de caja de seguridad del cliente*

Si se rechaza la solicitud por el cliente, el ingeniero de Microsoft no tendrán acceso al contenido del cliente y no podrá completar la operación de servicio. Si la solicitud está aprobada por el cliente, el ingeniero de Microsoft habrá just-in-time de acceso limitado a contenido del cliente a través de interfaces de administración supervisada y limitada. Con la caja de seguridad y caja de seguridad del cliente, todo el acceso a aprobado es puede trazar a un único usuario, realizar ingenieros responsable de su manipulación de datos de clientes.

## <a name="just-in-time-access"></a>Acceso de Just-in-Time
Microsoft utiliza el principio de acceso just-in-time (JIT) para Office 365 para reducir más el riesgo de ataques laterales y alteración de credenciales. Manera oportuna quita persistente acceso administrativo a los servicios y reemplaza los derechos de ayuda con la capacidad de elevar en dichas funciones a petición. Quitar derechos persistentes de los administradores se asegura de que las credenciales están disponibles solo cuando son necesarios y quita el riesgo que supone para la empresa en los casos de robo de credenciales.

El modelo de acceso de manera oportuna requiere ingenieros solicitar privilegios elevados durante un período limitado para llevar a cabo tareas administrativas. Además, OCEs usar cuentas temporales que se crean con contraseñas complejas generadas por la máquina y concedido sólo los roles que les permiten realizar las tareas necesarias. Por ejemplo, acceso administrativo concedido por caja de seguridad es el límite de tiempo, y la cantidad de tiempo que se concede el acceso depende de la función que se solicita. Un ingeniero especifica la duración del acceso de tiempo necesaria durante la solicitud para el sistema de caja de seguridad. El sistema de caja de seguridad rechaza las solicitudes donde el tiempo solicitado supera el máximo permitido de tiempo para la elevación. Después de la expiración de la solicitud de elevación, se ha quitado el acceso administrativo y la cuenta temporal ha expirado.

Cuando autorizado y aprobado de access (por ejemplo, para depurar un sistema), los ingenieros de reciben una contraseña de un solo uso administrativas generado por el sistema de autorización cada vez que se aprueba una solicitud de acceso con privilegios elevados. Esta contraseña se copia por el ingeniero en una contraseña segura, es independiente de las credenciales del ingeniero para el entorno corporativo de Microsoft y es una buena sólo para la sesión para la que se ha aprobado acceso con privilegios elevados.

## <a name="constrained-management-interfaces"></a>Interfaces de administración limitada
OCEs usar dos interfaces de administración para realizar tareas administrativas: escritorio remoto a través de protegida Terminal servicio puertas de enlace (ETG) y PowerShell remoto. Dentro de la administración de estas interfaces existen las directivas de software y controles de acceso que colocan importantes restricciones en qué aplicaciones se pueden ejecutar y qué cmdlets y los comandos están disponibles. 

Los servidores de Office 365 restricción sesiones simultáneas a un administrador de equipo por el servicio de sesión, por servidor. ETG está configurados para permitir una sola sesión simultánea de los usuarios y no permitir varias sesiones. ETG permite a los administradores del equipo de servicio de Office 365 para conectarse a varios servidores simultáneamente, mediante una sola sesión por servidor, para que los administradores pueden realizar eficazmente sus funciones. Los administradores del equipo de servicio no es necesario ningún permiso en la ETG ellos mismos. El TSG se usa únicamente para exigir la autenticación multifactor (MFA) y requisitos de cifrado. Una vez que el administrador del equipo de servicio se conecta a un servidor específico a través de un TSG, el servidor específico impondrá un límite de sesión de uno por el administrador.

Restricciones de uso y los requisitos de conexión y la configuración para el personal de Office 365 se establecen mediante directivas de grupo de Active Directory. Estas directivas incluyen las siguientes características:
- ETG está configurados para usar sólo [FIPS](https://www.microsoft.com/en-us/TrustCenter/Compliance/FIPS) 140-2 validado cifrado
- Sesiones TSG están configuradas para desconectar después de 30 minutos de inactividad
- Sesiones TSG están configuradas para iniciar sesión automáticamente desactiva después de 24 horas

Las conexiones a ETG también requieren MFA con una tarjeta inteligente física independiente y una cuenta que es independiente de credenciales corporativas de Microsoft del ingeniero. Los ingenieros se emiten diferentes tarjetas inteligentes para diversas plataformas y plataformas de administración de claves secretas se utilizan para garantizar el almacenamiento seguro de credenciales. ETG usar directivas de grupo de Active Directory para controlar quién puede iniciar sesión en servidores remotos, el número de sesiones permitidas y la configuración de tiempo de espera de inactividad. Las directivas adicionales se encuentran disponibles para limitar el acceso a aplicaciones permitidas y para restringir el acceso a Internet.

Además del acceso remoto mediante ETG especialmente configurado, Exchange Online permite a los usuarios con la función de operaciones de ingeniero de servicio tener acceso a ciertas funciones administrativas en servidores de producción con PowerShell remoto. Para ello, el usuario debe estar autorizado para el acceso de solo lectura (depuración) en el entorno de producción de Office 365. Elevación de privilegios se habilita la misma manera que se habilita para ETG mediante el proceso de caja de seguridad.

Para el acceso remoto, hay una dirección IP virtual con equilibrio de carga en cada centro de datos que actúa como un único punto de acceso. Los cmdlets de PowerShell remoto que se pueden ejecutar se basan en el nivel de privilegios identificado en la notificación de acceso obtenida durante la autenticación. Estos cmdlets son la funcionalidad solo administrativa que puede tener acceso a y ejecutada por los usuarios se conecta mediante este método. PowerShell remoto se usa para limitar el ámbito de comandos disponibles para el técnico, que se basa en el nivel de acceso concedido a través del proceso de caja de seguridad. Por ejemplo, en Exchange Online, Get-Mailbox puede estar disponible, pero no sería Set-Mailbox.

---
title: Quitar un usuario desde el Portal de usuarios restringidos después de enviar correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Si un usuario envía continuamente mensajes desde Office 365 se clasifican como correo no deseado, se le bloqueará para que no pueda enviar más mensajes de correo electrónico.
ms.openlocfilehash: 56f1a34fe4b47a722ff1dace73dd001f0c4812a2
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854724"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Quitar un usuario desde el Portal de usuarios restringidos después de enviar correo no deseado

Si un usuario envía continuamente mensajes de correo electrónico que se clasifican como correo no deseado de Office 365, el envío de correo electrónico no se enviará, pero seguirá siendo posible recibirlo. El usuario se mostrará en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica:

> "No se pudo entregar el mensaje porque el remitente no es válido. La razón más común para este caso es que la dirección de correo electrónico sea sospechosa de que está enviando correo no deseado y ya no se le permite enviar correo.  Póngase en contacto con su administrador, para obtener ayuda. El servidor remoto devolvió "550 5.1.8 acceso denegado, remitente incorrecto de correo saliente".

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos
  
Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx).

El siguiente procedimiento también se puede llevar a cabo mediante PowerShell remoto. Use el cmdlet Get-BlockedSenderAddress para obtener la lista de usuarios restringidos y Remove-BlockedSenderAddress para quitar la restricción. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Quitar las restricciones de una cuenta de correo electrónico de Office 365 bloqueada

La tarea se completa en el centro de cumplimiento de & de seguridad (SCC). [Diríjase al Centro de seguridad y cumplimiento](go-to-the-securitycompliance-center.md)para obtener más detalles acerca SCC. Debe estar en el rol de grupo deAdministración organizacional o de laAdministración de seguridad** en orden para poder realizar estas funciones. [Diríjase al Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md)para obtener más detalles acerca de los grupos de rol de SCC.

1. Con una cuenta profesional o educativa con privilegios de administrador global de Office 365, inicie sesión en el centro de seguridad y cumplimiento de Office 365 y, en la lista de la izquierda, expanda**Administración de amenazas**, elija** revisar**y, a continuación elija**usuarios restringidos**.
    
    > [!TIP]
    > Para ir directamente a la **página de usuarios restringidos**(anteriormente conocida como el centro de actividades) en el &amp; centro de cumplimiento de seguridad, use esta dirección URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Esta página incluirá la lista de usuarios que se les ha bloqueado el envío de correo electrónico.  Busque el usuario del que quiere quitar las restricciones y seleccione **desbloquear**.

3. Una reaparición irá en los detalles de la cuenta cuyo envío está restringido. Debe revisar las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se ponga en peligro. Seleccione **Siguiente**cuando termine.

4. En la siguiente pantalla encontrará recomendaciones para evitar comprometer el futuro. Habilitar la autenticación multi factor (MFA) y cambiar las contraseñas es una buena defensa. Haga clic **desbloquear usuario**cuando haya finalizado.

5. Haga clic en **Sí** para confirmar el cambio.

    > [!NOTE]
    > Se pueden tardar 30 minutos o más antes de quitar las restricciones. 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Asegurarse de que se avisa a los administradores cuando esto sucede

La alerta "el usuario restringido para el envío de correo electrónico" está disponible como política en la página de cumplimiento normativo & seguridad de Office 365 de directiva de alertas. Esta era anteriormente la política de la salida de correo no deseado, pero ahora es la plataforma de alertas nativa de Office 365. Vaya a [políticas de alerta en el centro de cumplimiento & de seguridad ](alert-policies.md)para obtener más información sobre las alertas.

> [!IMPORTANT]
> Para que las alertas funcionen, debe activarse la búsqueda de registros de auditoría. Vea cómo [activar o desactivar](turn-audit-log-search-on-or-off.md) la búsqueda de registros de auditoría de Office 365 para obtener más información.

La política para esta alerta es la predeterminada y se proporciona con cada espacio empresarial de Office 365 y no es necesario configurarla. Se considera una alerta de gravedad elevada y enviará un correo electrónico al grupo configurado de TenantAdmins cuando se active la alerta siempre y cuando un usuario se haya restringido el envío del correo a un usuario. Los administradores pueden actualizar el grupo que se le notifica cuando se lleva a cabo esta alerta yendo a la alerta en el portal de SCC > las alertas > las directivas de alerta > a los usuarios el envío de correo electrónico.

Estará habilitado para editar la alerta en:
- Notificaciones por correo electrónico Encendido/Apagado
- Enviar por correo electrónico los destinatarios necesarios
- Limitar las notificaciones que recibe por día

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>Búsqueda y eliminación de restricciones con PowerShell
Los comandos de PowerShell para usuarios restringidos son:
- `Get-BlockedSenderAddress`: Ejecutar para recuperar la lista de usuarios a los que se les impide enviar correo electrónico
- `Remove-BlockedSenderAddress`: Ejecutar para quitar usuarios de la restricción

## <a name="for-more-information"></a>Para más información

[Responder a una cuenta de correo electrónico en comprometida](responding-to-a-compromised-email-account.md)


  [Información sobre el usuario con restricción de envío de alertas de correo electrónico](https://docs.microsoft.com/es-ES/office365/securitycompliance/alert-policies)

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md)


  [Políticas de alerta en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/es-ES/office365/securitycompliance/alert-policies)

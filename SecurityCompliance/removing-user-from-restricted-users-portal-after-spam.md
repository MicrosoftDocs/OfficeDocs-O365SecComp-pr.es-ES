---
title: Quitar un usuario desde el Portal de usuarios restringidos después de enviar correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Si un usuario envía mensajes de correo electrónico de forma continua desde Office 365 que se clasifican como correo no deseado, se les restringirá el envío de mensajes adicionales.
ms.openlocfilehash: 7a44ff7f2bcf88f2132ee4c372cc11b9657dd16a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157252"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Quitar un usuario desde el Portal de usuarios restringidos después de enviar correo no deseado

Si un usuario envía mensajes de correo electrónico de forma continua desde Office 365 que se clasifican como correo no deseado, se les restringirá el envío de mensajes salientes más. El usuario se mostrará en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica lo siguiente:

- No se pudo entregar el mensaje porque no se reconoció como remitente válido. La razón más común es que se sospecha que su dirección de correo electrónico envía correo no deseado y ya no se le permite enviar mensajes fuera de la organización. Póngase en contacto con su administrador de correo electrónico para obtener ayuda. El servidor remoto devolvió ' 550 5.1.8 acceso denegado, remitente de salida incorrecto '

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el tema "entrada contra correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

El siguiente procedimiento también se puede llevar a cabo mediante PowerShell remoto. Use el cmdlet Get-BlockedSenderAddress para obtener la lista de usuarios restringidos y Remove-BlockedSenderAddress para quitar la restricción. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Quitar restricciones para una cuenta de correo electrónico de Office 365 no admitida

Complete esta tarea en el centro de seguridad & cumplimiento (SCC). [Vaya al centro de cumplimiento de seguridad &](go-to-the-securitycompliance-center.md) para obtener más información sobre SCC. Debe estar en el grupo de roles administración de la **organización** o **Administrador de seguridad** para poder realizar estas funciones. [Vaya a permisos en el centro de seguridad _AMP_ cumplimiento](permissions-in-the-security-and-compliance-center.md) para obtener más información sobre los grupos de roles de SCC.

1. Con una cuenta profesional o educativa con privilegios de administrador global de Office 365, inicie sesión en el centro de seguridad y cumplimiento de Office 365 y, en la lista de la izquierda, expanda **Administración de amenazas**, elija **revisar**y, a continuación, seleccione **restringido Usuarios**de.
    
    > [!TIP]
    > Para ir directamente a la página **usuarios restringidos** (anteriormente denominada centro de actividades) en el centro &amp; de seguridad y cumplimiento, use esta dirección URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Esta página contendrá la lista de usuarios que han sido bloqueados para enviar correo a fuera de la organización.  Busque el usuario para el que desea quitar restricciones y, a continuación, haga clic en **desbloquear**.

3. Una reactivación irá a los detalles sobre la cuenta cuyo envío está restringido. Debe seguir las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se vea en realidad. Haga clic en **siguiente** cuando haya terminado.

4. La siguiente pantalla tiene recomendaciones para ayudar a evitar el futuro compromiso. La habilitación de multi-factor Authentication (MFA) y el cambio de contraseñas son una buena defensa. Haga clic en **desbloquear el usuario** cuando haya terminado.

5. Haga clic en **sí** para confirmar el cambio.

    > [!NOTE]
    > Las restricciones pueden tardar hasta 30 minutos en quitarse. 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Asegurarse de que se advierte a los administradores cuando esto ocurre

Los administradores de espacios empresariales también recibirán una alerta que indica que se ha restringido el envío de más mensajes salientes al usuario. Se trata de una alerta predeterminada que se proporciona para todos los inquilinos y que aparece en la página directivas de alerta de SCC, titulada "el usuario restringió el envío de correo electrónico". Vaya a [directivas de alerta en el centro de cumplimiento de & de seguridad](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) para obtener más información sobre la alerta.

## <a name="for-more-information"></a>Más información

[Responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md)

[Descripción del usuario restringido del envío de alertas de correo electrónico](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md)

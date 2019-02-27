---
title: Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifican como correo no deseado, se les bloqueará el envío de mensajes adicionales.
ms.openlocfilehash: 870e5eabca9e799dfca1e99846a5bfe845f65df4
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275941"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado

Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifican como correo no deseado, se les bloqueará el envío de mensajes adicionales. El usuario se mostrará en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica lo siguiente:

- No se pudo entregar el mensaje porque no se reconoció como remitente válido. La razón más común es que se sospecha que su dirección de correo electrónico envía correo no deseado y ya no se le permite enviar mensajes fuera de la organización. Póngase en contacto con su administrador de correo electrónico para obtener ayuda.  El servidor remoto devolvió ' 550 5.1.8 acceso denegado, remitente de salida incorrecto '

Los administradores de espacios empresariales también recibirán una alerta que indica que se ha restringido el envío de más mensajes salientes al usuario.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos
  
Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el tema "entrada contra correo electrónico no deseado" en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

El siguiente procedimiento también puede realizarse a través de PowerShell remoto. Use el cmdlet Get-BlockedSenderAddress para obtener la lista de usuarios restringidos y Remove-BlockedSenderAddress para quitar la restricción. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Quitar restricciones para una cuenta de correo electrónico de Office 365 no admitida

Complete esta tarea en el centro de seguridad & cumplimiento (SCC) de Office 365. [Vaya al centro de cumplimiento de & de seguridad de Office 365](go-to-the-securitycompliance-center.md) para obtener más información sobre SCC. Debe estar en el grupo de roles administración de la **organización** o **Administrador de seguridad** para poder realizar estas funciones. [Vaya a permisos en el centro de seguridad _AMP_ cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md) para obtener más información sobre los grupos de roles de SCC.

1. Con una cuenta profesional o educativa con privilegios de administrador global de Office 365, inicie sesión en el centro de seguridad y cumplimiento de Office 365 y, en la lista de la izquierda, expanda **Administración de amenazas**, elija **revisar**y, a continuación, seleccione **restringido Usuarios**de.
    
    > [!TIP]
    > Para ir directamente a la página **usuarios restringidos** (anteriormente denominada centro de actividades) en el centro &amp; de seguridad y cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Esta página contendrá la lista de usuarios que han sido bloqueados para enviar correo a fuera de la organización.  Busque el usuario para el que desea quitar restricciones y, a continuación, haga clic en **desbloquear**.

3. Haga clic en **sí** para confirmar el cambio. 
    
> [!NOTE]
> Hay un límite en el número de veces que el administrador de inquilinos puede desbloquear una cuenta. Si se ha superado el límite de un usuario, aparece un mensaje de error. Tendrá que ponerse en contacto con el soporte técnico para desbloquear al usuario.<br/><br/> Puede tardar hasta 1 hora antes de que el usuario se desbloquee.
  
## <a name="third-party-block-lists"></a>Listas de bloqueados de terceros

Exchange Online Protection también usa listas de bloqueo de terceros para ayudarle a tomar decisiones en el filtrado de correo no deseado. Los usuarios, los sitios web, los dominios y las direcciones IP se pueden agregar a las listas de bloqueados para que aparezcan en un mensaje de correo no deseado. Como administrador de Office 365, debe intentar quitar estos objetos de los proveedores de la lista de terceros si le pertenecen.

> [!NOTE]
> Si alguien externo a Office 365 no puede enviar mensajes a su cuenta de Office 365, es posible que su cuenta se encuentre en la lista de remitentes bloqueados externos. Los usuarios externos a Office 365 pueden intentar quitarlos por sí mismos mediante el portal de eliminación [de la lista](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)de autoasistencia. 

## <a name="for-more-information"></a>Más información

[Responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md)

[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Permisos en el centro de seguridad & cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md)

  


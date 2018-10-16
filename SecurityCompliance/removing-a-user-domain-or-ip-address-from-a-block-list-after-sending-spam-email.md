---
title: Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/16/2018
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
description: Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes.
ms.openlocfilehash: 295d92fc6a1cd26783b18304a2d119d2ea0d7f1f
ms.sourcegitcommit: b164d4af65709133e0b512a4327a70fae13a974d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "25577069"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado

Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes. El usuario se mostrarán en el servicio como un remitente de salida incorrecto y recibirá un informe de no entrega (NDR) que indica:

- No se pudo entregar el mensaje porque no se han reconocido como remitente válido. La razón más común de esto es que su dirección de correo electrónico es sospechosos de enviar spam y que ya no se permite para enviar mensajes de fuera de la organización. Para obtener ayuda, póngase en contacto con el Administrador de correo electrónico.  Servidor remoto devolvió '550 5.1.8 acceso denegado, remitente saliente incorrecta'

Puede configurar la configuración de directiva de correo no deseado saliente por lo que se recibe una notificación cuando un usuario de Office 365 está bloqueado de envío de correo electrónico. Una vez resuelto el problema con el buzón del usuario, puede quitar el bloque de ese remitente.
  
## <a name="unblock-a-blocked-office-365-email-account"></a>Desbloquear una cuenta de correo electrónico de Office 365

Complete esta tarea en la seguridad de Office 365 & Centro de cumplimiento (SCC). Para obtener más información acerca de control de código fuente, [vaya a la seguridad de Office 365 & Centro de cumplimiento](go-to-the-securitycompliance-center.md) .

1. Utilizando una cuenta de trabajo o escuela que tiene privilegios de administrador global de Office 365, inicie sesión en el centro de cumplimiento y seguridad de Office 365 y en la lista de la izquierda, expanda **Administración de amenaza**, elija la **revisión**y, a continuación, elija **restringidos Los usuarios**.
    
    > [!TIP]
    > Para ir directamente a la página **Usuarios restringidos** (anteriormente conocida como el centro de acción) en la seguridad &amp; centro de cumplimiento, use esta dirección URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Esta página contendrá la lista de usuarios que se han bloqueado de envío de correo a fuera de la organización.  Busque el usuario que desea quitar restricciones en y, a continuación, haga clic en **desbloquear**.

3. Haga clic en **Sí** para confirmar el cambio. 
    
> [!NOTE]
> Hay un límite para el número de veces que una cuenta puede ser desbloqueada por el Administrador de inquilinos. Si se ha superado el límite de un usuario, aparece un mensaje de error. A continuación, debe ponerse en contacto con soporte técnico para desbloquear el usuario.
  
## <a name="third-party-block-lists"></a>Listas de bloqueados de terceros

Exchange Online Protection también usa listas de bloqueo de otro fabricante para ayudar a tomar decisiones de filtrado de spam. Los usuarios, sitios, dominios y direcciones IP pueden agregarse a bloquear listas solo para que aparezca en un mensaje de spam. Como la administración de Office 365, debe intentar obtener estos objetos quitado de los proveedores de la lista de terceros si éstos pertenecen a usted.

> [!NOTE]
> Si alguien de fuera de Office 365 no puede enviar mensajes a su cuenta de Office 365, puede ser su cuenta en la lista de remitentes bloqueados externo. Los usuarios externos a Office 365 pueden intentar quitar a sí mismos mediante el [portal de autoservicio de eliminación de la lista](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis). 

## <a name="for-more-information"></a>Para obtener más información

[Responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md)

[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

  

  


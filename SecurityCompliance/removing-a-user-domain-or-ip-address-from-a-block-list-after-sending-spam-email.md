---
title: Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes.
ms.openlocfilehash: ce52ddfd96b582911bb519c15bbfe90351946db8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026337"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado

Si un usuario envía continuamente mensajes de correo electrónico de Office 365 que se clasifica como correo no deseado, se bloqueará de enviar más mensajes. 
  
Cuando un remitente está bloqueado de envío de mensajes de correos electrónicos, reciben un informe de no entrega (NDR o no se pudo enviar el mensaje de correo electrónico) que proporciona información específica acerca de los pasos que se tienen que tomar para desbloquear a sí mismos.
  
No sólo a los usuarios individuales se pueden bloquear por los dominios de servicio, pero determinados sitios Web, y también se pueden bloquear las direcciones IP. En algunos casos, dominios o sitios Web pueden agregarse a una lista de bloqueados sólo porque aparecen en un mensaje de spam. Como la administración de Office 365, puede intentar obtener los usuarios, sitios, dominios y direcciones IP quitadas de listas de bloqueo de otro fabricante. Use los vínculos en la tabla en la parte inferior de este tema para ponerse en contacto con cada tercero y, a continuación, siga las instrucciones. Si alguien de fuera de Office 365 no puede enviar mensajes a su cuenta de Office 365, su cuenta puede haya terminado en la lista de remitentes bloqueados externo. Los usuarios externos a Office 365 pueden intentar se quiten de la lista de remitentes bloqueados a través del [portal de autoservicio de eliminación de la lista](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).
  
Configuración de correo no deseado saliente puede configurar para que obtener anotification cuando un usuario de Office 365 está bloqueado de envío de correo electrónico que se clasifica como correo no deseado. Una vez resuelto el problema con el buzón del usuario, puede quitar el bloque de ese remitente.
  
## <a name="unblock-a-blocked-office-365-email-account"></a>Desbloquear una cuenta de correo electrónico de Office 365

Complete esta tarea en el centro de administración de Exchange (EAC). Desproteger [Exchange centro de administración en Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) para obtener información detallada sobre el CEF. 
  
> [!NOTE]
> No verá el centro de actividades a no ser que se encuentre en el EAC de Exchange Online. 
  
1. En el EAC, vaya a **protección** \> **Centro de acción**.
    
    ![Vaya al Centro de actividades del Centro de administración de Exchange.](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. Seleccione el icono de **búsqueda** y, a continuación, escriba la dirección SMTP del usuario bloqueado. 
    
    ![Buscar a un usuario bloqueado en el Centro de actividades](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. Haga clic en **Desbloquear la cuenta** en el panel Descripción. 
    
    ![Desbloquear a un usuario en el Centro de actividades](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. Haga clic en **Sí** para confirmar el cambio. 
    
> [!NOTE]
> Hay un límite para el número de veces que una cuenta puede ser desbloqueada por el Administrador de inquilinos. Si se ha superado el límite de un usuario, aparece un mensaje de error. Póngase en contacto con soporte técnico para desbloquear el usuario. 
  
## <a name="third-party-block-lists"></a>Listas de bloqueados de terceros

|**Nombre de la lista**|**Portal de eliminación de la lista**|**Más información**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[Sitio Web URIBL](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[Presentación de datos de reputación de URI SURBL](http://www.surbl.org/) <br/> |
|Spamhaus   <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[Descripción de filtrado de DNSBL](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[lista de lista contra correo no deseado](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank preguntas más frecuentes](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> Exchange Online Protection también utiliza las listas de bloqueados de terceros para el filtrado de spam. 
   
## <a name="for-more-information"></a>Más información

[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  


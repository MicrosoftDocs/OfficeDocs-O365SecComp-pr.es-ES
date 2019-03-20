---
title: Listas de remitentes seguros y bloqueados en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.
ms.openlocfilehash: 11ae38733418bb0842732978512698ca6a6274fd
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692229"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Listas de remitentes seguros y bloqueados en Exchange Online

Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización. 
  
 *Vea la versión actualizada de las sugerencias y los procedimientos para trabajar con estas listas como administrador en* [Prevent false positive email marked as spam with a safelist or other techniques (Impedir que el correo electrónico falso positivo se marque como correo no deseado con una lista de IP seguras u otras técnicas)](https://go.microsoft.com/fwlink/p/?LinkID=534224). 
  
Si no es un administrador y solo quiere administrar su propio correo electrónico no deseado en Outlook mediante una lista de remitentes seguros, vea los pasos de esta información general sobre [the Junk Email Filter (el filtro de correo electrónico no deseado)](https://go.microsoft.com/fwlink/?LinkId=817222). 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>¿Qué son los límites de remitentes seguros y bloqueados en Exchange Online?

Los límites de remitentes seguros y bloqueados en Exchange Online difieren de los límites de Outlook y Active Directory. Son los siguientes:
  
- Límite de remitentes seguros: 1.024
    
- Límite de remitentes bloqueados: 500
    
Nota:
  
Puede experimentar el error que se describe en [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Para resolver este problema, desactive la casilla "confiar en mensajes de correo electrónico de mis contactos". También puede reducir la cantidad de direcciones de correo electrónico que se encuentran en la carpeta contactos predeterminada para que pasen al límite máximo permitido de 1024 en Exchange online que se establece para el atributo "parámetros maxsafesenders". Para obtener más información sobre este atributo y el cmdlet Set-Mailbox, sobre elscript siguiente tema:
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>Vea también

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)


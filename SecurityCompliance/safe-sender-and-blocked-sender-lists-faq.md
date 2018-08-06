---
title: Listas de remitentes seguros y bloqueados en Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.
ms.openlocfilehash: fcb43f990750782788dc6f459dd5c7d296146a38
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028087"
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
  
Puede experimentar el error que se describe en KB 2590466 ("recibirá el error"Error de validación de correo electrónico no deseado"en Outlook Web App para Exchange Server 2010"). Para resolver este problema, desactive la casilla de verificación "Confiar en mensajes de correo electrónico de Mis contactos". Como alternativa, reducir la cantidad de direcciones de correo electrónico que están en la carpeta de contactos predeterminada para que aparezca en el máximo permitido limitar de 1.024 en Exchange Online que se establece para el atributo "MaxSafeSenders". Para obtener más información acerca de este atributo y el cmdlet Set-Mailbox, seethe siguiente tema:
  
[Set-Mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a>See also

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)


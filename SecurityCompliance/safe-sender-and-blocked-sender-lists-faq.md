---
title: Listas de remitentes seguros y bloqueados en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.
ms.openlocfilehash: a6e8f98d6cb5930f7eb6f2059c957112026dd5d8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156702"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="7533b-104">Listas de remitentes seguros y bloqueados en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7533b-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="7533b-p102">Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="7533b-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="7533b-107">*Vea la versión actualizada de las sugerencias y los procedimientos para trabajar con estas listas como administrador en* [Prevent false positive email marked as spam with a safelist or other techniques (Impedir que el correo electrónico falso positivo se marque como correo no deseado con una lista de IP seguras u otras técnicas)](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span><span class="sxs-lookup"><span data-stu-id="7533b-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="7533b-108">Si no es un administrador y solo quiere administrar su propio correo electrónico no deseado en Outlook mediante una lista de remitentes seguros, vea los pasos de esta información general sobre [the Junk Email Filter (el filtro de correo electrónico no deseado)](https://go.microsoft.com/fwlink/?LinkId=817222).</span><span class="sxs-lookup"><span data-stu-id="7533b-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="7533b-109">¿Qué son los límites de remitentes seguros y bloqueados en Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="7533b-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="7533b-p103">Los límites de remitentes seguros y bloqueados en Exchange Online difieren de los límites de Outlook y Active Directory. Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7533b-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="7533b-112">Límite de remitentes seguros: 1.024</span><span class="sxs-lookup"><span data-stu-id="7533b-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="7533b-113">Límite de remitentes bloqueados: 500</span><span class="sxs-lookup"><span data-stu-id="7533b-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="7533b-114">Nota:</span><span class="sxs-lookup"><span data-stu-id="7533b-114">Note:</span></span>
  
<span data-ttu-id="7533b-115">Puede experimentar el error que se describe en [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="7533b-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="7533b-116">Para resolver este problema, desactive la casilla "confiar en mensajes de correo electrónico de mis contactos".</span><span class="sxs-lookup"><span data-stu-id="7533b-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="7533b-117">También puede reducir la cantidad de direcciones de correo electrónico que se encuentran en la carpeta contactos predeterminada para que pasen al límite máximo permitido de 1024 en Exchange online que se establece para el atributo "parámetros maxsafesenders".</span><span class="sxs-lookup"><span data-stu-id="7533b-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="7533b-118">Para obtener más información sobre este atributo y el cmdlet Set-Mailbox, sobre elscript siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="7533b-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="7533b-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="7533b-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a><span data-ttu-id="7533b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7533b-120">See also</span></span>

[<span data-ttu-id="7533b-121">Sender filtering in Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="7533b-121">Sender filtering in Exchange 2016</span></span>](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)


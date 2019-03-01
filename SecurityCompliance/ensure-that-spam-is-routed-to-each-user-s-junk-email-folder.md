---
title: Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo enrutar correo no deseado a las carpetas de correo no deseado del usuario en Exchange Online Protection.
ms.openlocfilehash: 80c3e3cab1bdaf85e815ab1acc790cc907ebbb91
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341381"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="6a454-103">Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario</span><span class="sxs-lookup"><span data-stu-id="6a454-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a454-p101">Este tema solo se aplica a clientes de Exchange Online Protection (EOP) que hospedan buzones de correo localmente en una implementación híbrida. Los clientes de Exchange Online cuyos buzones se hospedan completamente en Office 365 no necesitan ejecutar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="6a454-p101">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="6a454-p102">La acción de bloqueo de correo no deseado predeterminada para los clientes de EOP es mover los mensajes de correo no deseado a la carpeta de correo no deseado de los destinatarios. Para que esta acción funcione con buzones locales, debe configurar las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores perimetrales locales o de concentradores para detectar los encabezados de correo no deseado agregados por EOP. Estas reglas de flujo de correo establecen el nivel de confianza contra correo no deseado (SCL) usado por la propiedad SclJunkThreshold del cmdlet Set-OrganizationConfig para mover el correo no deseado a la carpeta de correo no deseado de cada buzón.</span><span class="sxs-lookup"><span data-stu-id="6a454-p102">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP. These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="6a454-109">Para agregar reglas de flujo de correo para asegurarse de que el correo no deseado se mueve a la carpeta de correo no deseado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a454-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="6a454-p103">Obtenga acceso al Shell de administración de Exchange de su servidor Exchange local. Para obtener información sobre cómo abrir el Shell de administración de Exchange en su organización local Exchange, vea **Open the Shell**.</span><span class="sxs-lookup"><span data-stu-id="6a454-p103">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="6a454-112">Ejecute el siguiente comando para enrutar mensajes de correo no deseado de contenido filtrado a la carpeta de correo electrónico no deseado:</span><span class="sxs-lookup"><span data-stu-id="6a454-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="6a454-113">Donde  _NameForRule_ es el nombre de la regla nueva, por ejemplo, JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="6a454-113">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="6a454-114">Ejecute el siguiente comando para enrutar mensajes marcados como correo no deseado antes de alcanzar el filtro de contenido en la carpeta de correo electrónico no deseado:</span><span class="sxs-lookup"><span data-stu-id="6a454-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="6a454-115">Donde  _NameForRule_ es el nombre de la regla nueva, por ejemplo, JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="6a454-115">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="6a454-116">Ejecute el siguiente comando para asegurarse de que los mensajes de los remitentes que estén en una lista de bloqueados de la directiva de correo no deseado, como la de **remitentes bloqueados**, se enruten a la carpeta de correo no deseado:</span><span class="sxs-lookup"><span data-stu-id="6a454-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="6a454-117">Donde  _NameForRule_ es el nombre de la regla nueva, por ejemplo, JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="6a454-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="6a454-p104">Si no quiere usar la acción **Mover el mensaje a la carpeta de correo no deseado**, puede elegir otra acción en las directivas de filtro de contenido del Centro de administración de Exchange. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Para obtener más información sobre estos campos del encabezado del mensaje, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="6a454-p104">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a454-121">See also</span><span class="sxs-lookup"><span data-stu-id="6a454-121">See also</span></span>

[<span data-ttu-id="6a454-122">Cmdlet New-TransportRule</span><span class="sxs-lookup"><span data-stu-id="6a454-122">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)


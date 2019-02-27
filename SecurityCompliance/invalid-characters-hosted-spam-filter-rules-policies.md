---
title: Evitar caracteres no válidos en las reglas de filtro de correo no deseado y la Directiva de filtro de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Proporciona ayuda a los administradores que tienen caracteres no válidos en la configuración contra correo no deseado y tienen problemas al intentar usar el centro &amp; de seguridad y cumplimiento.
ms.openlocfilehash: 90cf89d019a34658b676f02baa84c70f27200262
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276085"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="b301f-103">Evitar caracteres no válidos en las reglas de filtro de correo no deseado y Directiva de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b301f-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="b301f-p101">Anteriormente, los administradores de Office 365 instalaron y configuraron reglas de filtro de correo no deseado y la Directiva de filtro de correo no deseado mediante el centro de administración de Exchange (EAC). Ahora, puede usar el centro &amp; de seguridad y cumplimiento para administrar la configuración contra correo no deseado. Los siguientes caracteres se admitiron en el EAC, pero no se admiten para su &amp; uso en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b301f-p101">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange Admin Center (EAC). Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration. The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="b301f-107">**Caracteres no válidos:**</span><span class="sxs-lookup"><span data-stu-id="b301f-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="b301f-108">Si las reglas de filtro de correo no deseado o la Directiva de filtro de correo no deseado contienen alguno de los caracteres no válidos, puede encontrarse alguno o todos estos problemas:</span><span class="sxs-lookup"><span data-stu-id="b301f-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="b301f-109">Es posible que no pueda encontrar la Directiva o las reglas en el &amp; centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b301f-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="b301f-110">Es posible que reciba errores al intentar obtener las reglas o la Directiva mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b301f-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="b301f-111">Es posible que la Directiva o la configuración no se ejecuten o no funcionen de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="b301f-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="b301f-112">Quitar los caracteres no válidos de la Directiva y reglas del filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b301f-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="b301f-113">Una vez que haya identificado la Directiva y las reglas que contienen caracteres no válidos, puede cambiar los nombres con los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b301f-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="b301f-114">[Conéctese a Exchange online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b301f-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="b301f-115">Para cambiar el nombre de la Directiva de filtro de correo no deseado, ejecute el cmdlet Set-HostedContentFilterPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b301f-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="b301f-116">Para cambiar el nombre de una regla de filtro de correo no deseado, ejecute el cmdlet Set-HostedContentFilterRule de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b301f-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="b301f-117">Más información</span><span class="sxs-lookup"><span data-stu-id="b301f-117">For more information</span></span>

[<span data-ttu-id="b301f-118">Administración de amenazas en el &amp; centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b301f-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="b301f-119">Set-HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="b301f-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="b301f-120">Set-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="b301f-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)

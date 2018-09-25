---
title: Evitar los caracteres no válidos en la directiva de filtro de correo y las reglas de filtro de spam
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Proporciona ayuda para los administradores que tienen caracteres no válidos en su configuración contra correo no deseado y ejecutan en problemas cuando se intenta usar la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: ca409b4daa7bec01417adb7cbfdfa2a128929e81
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018739"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="4d3a1-103">Evitar los caracteres no válidos en las reglas de filtro de spam y directiva de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="4d3a1-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="4d3a1-p101">Anteriormente, los administradores de Office 365 configuración y configurar la directiva de filtro de correo y las reglas de filtro de spam mediante el centro de administración de Exchange (EAC). Ahora, use la seguridad &amp; centro de cumplimiento para administrar la su configuración contra correo no deseada. Los siguientes caracteres se admitían en el CEF pero no son compatibles para su uso en la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4d3a1-p101">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange Admin Center (EAC). Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration. The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="4d3a1-107">**Caracteres no válidos:**</span><span class="sxs-lookup"><span data-stu-id="4d3a1-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="4d3a1-108">Si las reglas de filtro de spam o la directiva de filtro de spam contiene cualquiera de los caracteres no válidos, se podrían encontrarse con cualquier o todos estos problemas:</span><span class="sxs-lookup"><span data-stu-id="4d3a1-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="4d3a1-109">Es posible que no se puede encontrar la directiva o las reglas en la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4d3a1-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="4d3a1-110">Es posible que reciba errores al intentar obtener las reglas o directivas mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d3a1-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="4d3a1-111">Es posible que la directiva o configuración de no ejecutar o realizar según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="4d3a1-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="4d3a1-112">Quitar los caracteres no válidos de la directiva de filtro de spam y reglas</span><span class="sxs-lookup"><span data-stu-id="4d3a1-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="4d3a1-113">Una vez que haya identificado la directiva y las reglas que contienen caracteres no válidos, puede cambiar los nombres mediante el uso de los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d3a1-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="4d3a1-114">[Conectarse a Exchange Online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4d3a1-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="4d3a1-115">Para cambiar el nombre de la directiva de filtro de spam, ejecute el cmdlet Set-HostedContentFilterPolicy como sigue:</span><span class="sxs-lookup"><span data-stu-id="4d3a1-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="4d3a1-116">Para cambiar el nombre de una regla de filtro de spam, ejecute el cmdlet Set-HostedContentFilterRule como sigue:</span><span class="sxs-lookup"><span data-stu-id="4d3a1-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="4d3a1-117">Más información</span><span class="sxs-lookup"><span data-stu-id="4d3a1-117">For more information</span></span>

[<span data-ttu-id="4d3a1-118">Administración de la seguridad de amenazas &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4d3a1-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="4d3a1-119">Set-HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="4d3a1-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="4d3a1-120">Set-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="4d3a1-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)

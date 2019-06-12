---
title: Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Microsoft defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integre Office 365 Advanced Threat Protection con la protección contra amenazas avanzada de Microsoft defender para ver información más detallada sobre la administración de amenazas.
ms.openlocfilehash: 2d1c88f9911a9940589cdafcc7b12980f2e61a7e
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852564"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="4a759-103">Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="4a759-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="4a759-104">Si forma parte del equipo de seguridad de su organización, puede integrar la [protección contra amenazas avanzada de Office 365](office-365-atp.md) y las características de investigación y respuesta relacionadas con la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="4a759-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="4a759-105">Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están expuestos a riesgos cuando esté investigando amenazas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a759-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="4a759-106">Por ejemplo, una vez habilitada la integración, podrá ver una lista de equipos usados por los destinatarios de un mensaje de correo electrónico detectado, así como el número de alertas recientes que tienen esos equipos en la protección contra amenazas avanzada de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4a759-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="4a759-107">La siguiente imagen muestra la pestaña **dispositivos** que verá cuando tenga habilitada la integración de Microsoft defender ATP:</span><span class="sxs-lookup"><span data-stu-id="4a759-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Si ATP de Microsoft defender está habilitada, puede ver una lista de equipos con alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4a759-109">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro dispositivos y uno de ellos tiene una alerta.</span><span class="sxs-lookup"><span data-stu-id="4a759-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="4a759-110">Al hacer clic en el vínculo de un dispositivo se abre su página en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4a759-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4a759-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a759-111">Requirements</span></span>

- <span data-ttu-id="4a759-112">Su organización debe tener Office 365 ATP plan 2 (o Office 365 E5) y ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4a759-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="4a759-113">Debe ser administrador global de Office 365 o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en [el &amp; centro de seguridad y cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="4a759-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4a759-114">(Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="4a759-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4a759-115">Debe tener acceso a exploradores [(o detecciones en tiempo real)](threat-explorer.md) en el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4a759-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="4a759-116">Para integrar Office 365 ATP con Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="4a759-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="4a759-117">Integración de Office 365 ATP con Microsoft defender ATP se configura mediante el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4a759-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="4a759-118">Como administrador global de Office 365 o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a759-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="4a759-119">Elija **Threat Management** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4a759-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="4a759-120">![Explorador en el menú de administración de amenazas](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="4a759-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="4a759-121">En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.</span><span class="sxs-lookup"><span data-stu-id="4a759-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4a759-122">En el cuadro de diálogo conexión ATP de Windows Defender, Active conectarse a ATP de Windows.</span><span class="sxs-lookup"><span data-stu-id="4a759-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Conexión ATP de Microsoft defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="4a759-124">Habilite la conexión en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4a759-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="4a759-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4a759-125">Related topics</span></span>

[<span data-ttu-id="4a759-126">Respuesta y investigación de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a759-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4a759-127">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a759-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


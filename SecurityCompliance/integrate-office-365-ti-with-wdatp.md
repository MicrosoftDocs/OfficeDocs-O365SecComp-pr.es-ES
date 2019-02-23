---
title: Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrar la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Windows Defender para ver información más detallada acerca de la administración de amenazas.
ms.openlocfilehash: 892d04152d6029c48a52d37c6235d45a8ba67b81
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222819"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="9d1ab-103">Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9d1ab-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="9d1ab-p101">Si forma parte del equipo de seguridad de su organización, puede integrar las características de protección contra amenazas avanzada de Office 365 y de inteligencia sobre amenazas con la protección contra amenazas avanzada de Windows Defender. Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están expuestos a riesgos cuando esté investigando amenazas en Office 365. Por ejemplo, una vez habilitada la integración, podrá ver una lista de las máquinas que usan los destinatarios de un mensaje de correo electrónico detectado, así como el número de alertas recientes que tienen esos equipos en la protección contra amenazas avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="9d1ab-107">La siguiente imagen muestra la pestaña **dispositivos** que verá cuando tenga habilitada la integración de la protección contra amenazas avanzada de Windows Defender:</span><span class="sxs-lookup"><span data-stu-id="9d1ab-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![Si ATP de Windows Defender está habilitada, puede ver una lista de equipos con alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="9d1ab-p102">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro dispositivos y uno de ellos tiene una alerta. Al hacer clic en el vínculo de un dispositivo se abre su página en el portal de protección contra amenazas avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9d1ab-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d1ab-111">Requirements</span></span>

- <span data-ttu-id="9d1ab-112">Su organización debe tener Office 365 Threat Intelligence y ATP de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="9d1ab-p103">Debe ser administrador global de Office 365 o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en [el &amp; centro de seguridad y cumplimiento](https://protection.office.com). (Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="9d1ab-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="9d1ab-115">Debe tener acceso a inteligencia sobre amenazas de Office 365 y al portal de protección contra amenazas avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="9d1ab-116">Para integrar la inteligencia sobre amenazas de Office 365 con ATP de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9d1ab-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="9d1ab-117">Integración de Office 365 Threat Intelligence con la protección contra amenazas avanzada de Windows Defender se configura mediante el centro de cumplimiento de Office 365 Security & y el portal de protección contra amenazas avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="9d1ab-118">Como administrador global de Office 365 o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="9d1ab-119">Elija **Threat Management** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="9d1ab-120">![Explorador en el menú de administración de amenazas](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="9d1ab-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="9d1ab-121">En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="9d1ab-122">En el cuadro de diálogo conexión ATP de Windows Defender, Active conectarse a ATP de Windows.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Conexión ATP de Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="9d1ab-p104">Habilitar la conexión en la protección contra amenazas avanzada de Windows Defender. Consulte [usar el portal de protección contra amenazas avanzada de Windows Defender](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="9d1ab-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9d1ab-126">Related topics</span></span>

[<span data-ttu-id="9d1ab-127">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="9d1ab-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="9d1ab-128">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="9d1ab-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


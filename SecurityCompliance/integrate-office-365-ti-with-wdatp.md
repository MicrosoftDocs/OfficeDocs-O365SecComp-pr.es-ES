---
title: Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection: M365-security-compliance
description: Integrar la protección de amenaza avanzada de Office 365 con Windows Defender avanzada protección contra amenazas para ver información más detallada de administración de amenaza.
ms.openlocfilehash: f8f5f50af10fb668aa67b68604e95e8dd19c9e69
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995211"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="ffd3e-103">Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ffd3e-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="ffd3e-p101">Si forma parte del equipo de seguridad de su organización, puede integrar características de protección de amenaza avanzada de Office 365 y amenaza con protección de amenaza avanzada de Windows Defender. Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están en riesgo cuando investigue las amenazas en Office 365. Por ejemplo, una vez que se habilita la integración, podrá ver una lista de los equipos que se usan por los destinatarios de un mensaje de correo electrónico detectado, así como el modo en muchas alertas recientes esos equipos tienen en la protección de amenaza avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="ffd3e-107">En la siguiente imagen se muestra la ficha **dispositivos** que verá cuándo tiene la integración de la protección de amenaza avanzada de Windows Defender habilitada:</span><span class="sxs-lookup"><span data-stu-id="ffd3e-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![Cuando Windows Defender ATP está habilitada, puede ver una lista de las máquinas con las alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="ffd3e-p102">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo para un dispositivo, su página se abre en el portal de protección de amenaza avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ffd3e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffd3e-111">Requirements</span></span>

- <span data-ttu-id="ffd3e-112">Su organización debe tener información sobre amenazas de Office 365 y Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="ffd3e-p103">Debe ser un administrador Global de Office 365 o tener un rol de administrador de seguridad (por ejemplo, el Administrador de seguridad) asignado en la [seguridad &amp; centro de cumplimiento](https://protection.office.com). (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="ffd3e-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="ffd3e-115">Debe tener acceso a información sobre amenazas de Office 365 y el portal de protección de amenaza avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="ffd3e-116">Para integrar información sobre amenazas de Office 365 con Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ffd3e-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="ffd3e-117">Integración de Office 365 amenaza inteligencia con protección de amenaza avanzada de Windows Defender se configura mediante el uso de ambos la seguridad de Office 365 & centro de cumplimiento de normas y el portal de protección de amenaza avanzada de Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="ffd3e-118">Como un administrador global de Office 365 o un administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela para Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="ffd3e-119">Elija **administración de amenaza** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="ffd3e-120">![Explorador en el menú de administración de amenaza](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="ffd3e-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="ffd3e-121">En la esquina superior derecha de la pantalla, elija **Configuración de WDATP**.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="ffd3e-122">En el cuadro de diálogo de conexión de Windows Defender ATP, activar conectar a ATP de Windows.</span><span class="sxs-lookup"><span data-stu-id="ffd3e-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Conexión de Windows Defender ATP](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="ffd3e-p104">Habilitar la conexión en la protección de amenaza avanzada de Windows Defender. Cómo [usar el portal de protección de amenaza avanzada de Windows Defender](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="ffd3e-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="ffd3e-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ffd3e-126">Related topics</span></span>

[<span data-ttu-id="ffd3e-127">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd3e-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ffd3e-128">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="ffd3e-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


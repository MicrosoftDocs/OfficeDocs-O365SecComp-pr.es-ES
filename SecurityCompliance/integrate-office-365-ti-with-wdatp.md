---
title: Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Integrar la protección de amenaza avanzada de Office 365 con Windows Defender avanzada protección contra amenazas para ver información más detallada de administración de amenaza.
ms.openlocfilehash: 574594d5881853b268713e0bb74444ae80ffcf46
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535905"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="8b6d7-103">Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="8b6d7-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="8b6d7-p101">Si forma parte del equipo de seguridad de su organización, puede integrar Office 365 con Defender avanzada amenaza protección (ATP) de Windows. Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están en riesgo cuando investigue las amenazas en Office 365. Por ejemplo, una vez que se habilita la integración, podrá ver una lista de los equipos que se usan por los destinatarios de un mensaje de correo electrónico detectado, así como el modo en muchas alertas recientes esos equipos tienen en Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-p101">If you are part of your organization's security team, you can integrate Office 365 with Windows Defender Advanced Threat Protection (ATP). This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender ATP.</span></span>
  
<span data-ttu-id="8b6d7-107">En la siguiente imagen se muestra la ficha **dispositivos** que verá cuándo tiene integración de Windows Defender ATP habilitada:</span><span class="sxs-lookup"><span data-stu-id="8b6d7-107">The following image shows the **Devices** tab that you'll see when have Windows Defender ATP integration enabled:</span></span> 
  
![Cuando Windows Defender ATP está habilitada, puede ver una lista de las máquinas con las alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="8b6d7-p102">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro máquinas y uno tiene una alerta en Windows Defender ATP. Al hacer clic en el vínculo a una máquina, se abre la página de la máquina en Windows Defender ATP en una nueva ficha.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-p102">In this example, you can see that the recipients of the email message have four machines and one has an alert in Windows Defender ATP. Clicking the link to a machine opens the machine page in Windows Defender ATP in a new tab.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8b6d7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b6d7-111">Requirements</span></span>

- <span data-ttu-id="8b6d7-112">Su organización debe tener información sobre amenazas de Office 365 y Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="8b6d7-p103">Debe ser un administrador global de Office 365 o tener un rol de administrador de seguridad asignado en la seguridad &amp; centro de cumplimiento. (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="8b6d7-p103">You must be an Office 365 global administrator or have a security administrator role assigned in the Security &amp; Compliance Center. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="8b6d7-115">Debe tener acceso a información sobre amenazas de Office 365 y el portal de Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender ATP portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="8b6d7-116">Para integrar información sobre amenazas de Office 365 con Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8b6d7-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="8b6d7-117">Integración de inteligencia de amenaza de Office 365 con Windows Defender ATP se configura en Office 365 y en el portal de Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-117">Integrating Office 365 Threat Intelligence with Windows Defender ATP is set up both in Office 365 and in the Windows Defender ATP portal.</span></span>
  
1. <span data-ttu-id="8b6d7-118">Como un global de Office 365 o un administrador de seguridad, vaya a [https://portal.office.com](https://portal.office.com) y el inicio de sesión con la cuenta de trabajo o escuela para Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-118">As an Office 365 global or a security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="8b6d7-119">Elija **administración de amenaza** \> **el Explorador de amenaza**.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-119">Choose **Threat management** \> **Threat explorer**.</span></span>
    
3. <span data-ttu-id="8b6d7-120">En el menú **más** , elija **Configuración de WDATP**.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-120">On the **More** menu, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="8b6d7-121">Seleccione **conectarse a Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-121">Select **Connect to Windows ATP**.</span></span>
    
<span data-ttu-id="8b6d7-p104">Después de haber cambiado la configuración de Office 365, debe habilitar la conexión desde Windows Defender ATP. Para ello, vea [utilizar el portal de protección de amenaza avanzada de Windows Defender](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="8b6d7-p104">After you have changed the settings in Office 365, you must enable the connection from Windows Defender ATP. To do that, see [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8b6d7-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8b6d7-124">Related topics</span></span>

[<span data-ttu-id="8b6d7-125">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="8b6d7-125">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="8b6d7-126">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="8b6d7-126">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


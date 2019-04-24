---
title: Habilitar o deshabilitar las sugerencias de seguridad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Indica a Office 365 y a los administradores de EOP cómo habilitar y deshabilitar las sugerencias de seguridad en los mensajes de correo electrónico.
ms.openlocfilehash: 9be9c4cd7fc8e94208aac2ad8812c93a3465f58b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256968"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="5be3f-103">Habilitar o deshabilitar las sugerencias de seguridad en Office 365</span><span class="sxs-lookup"><span data-stu-id="5be3f-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="5be3f-104">Exchange Online Protection (EOP) agrega o marca una sugerencia de seguridad a los mensajes de correo electrónico que entrega.</span><span class="sxs-lookup"><span data-stu-id="5be3f-104">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers.</span></span> <span data-ttu-id="5be3f-105">Estas sugerencias de seguridad proporcionan a los destinatarios una forma rápida y visual de determinar si un mensaje proviene de un remitente protegido seguro, si el mensaje ha sido marcado como correo no deseado por Office 365, si el mensaje contiene algo sospechoso, como una estafa de suplantación de identidad (phishing), o si las imágenes externas tienen se ha bloqueado.</span><span class="sxs-lookup"><span data-stu-id="5be3f-105">These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked.</span></span> <span data-ttu-id="5be3f-106">Office 365 y EOP: los administradores independientes pueden editar una configuración de directiva de correo no deseado para habilitar o deshabilitar las sugerencias de seguridad para que no se muestren en el correo electrónico en Outlook y en otros clientes de correo electrónico de escritorio.</span><span class="sxs-lookup"><span data-stu-id="5be3f-106">Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="5be3f-107">Office 365 habilita sugerencias de seguridad de forma predeterminada para su organización y le recomendamos que las deje habilitadas para luchar contra el correo no deseado y los ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5be3f-107">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks.</span></span> <span data-ttu-id="5be3f-108">No puede deshabilitar las sugerencias de seguridad para Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="5be3f-108">You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="5be3f-109">Para ver ejemplos y obtener información sobre la información que se muestra en sugerencias de seguridad, vea [sugerencias de seguridad en los mensajes de correo electrónico en Office 365.](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5be3f-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="5be3f-110">En este tema:</span><span class="sxs-lookup"><span data-stu-id="5be3f-110">In this topic:</span></span>
  
- [<span data-ttu-id="5be3f-111">Para habilitar o deshabilitar las sugerencias de seguridad mediante el centro &amp; de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="5be3f-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="5be3f-112">Para habilitar o deshabilitar las sugerencias de seguridad con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5be3f-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="5be3f-113">Para habilitar o deshabilitar las sugerencias de seguridad mediante el centro &amp; de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="5be3f-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="5be3f-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="5be3f-114"></span></span>

1. <span data-ttu-id="5be3f-115">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="5be3f-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="5be3f-116">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="5be3f-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="5be3f-117">Elija \*\*\*\* \> **Directiva**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="5be3f-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="5be3f-118">En la página **Directiva** , elija **anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="5be3f-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![En esta captura de pantalla se muestra cómo obtener acceso a la página Configuración de correo &amp; no deseado en el centro de seguridad y cumplimiento.](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="5be3f-120">En la página **configuración contra correo no deseado,** elija la pestaña **personalizado** .</span><span class="sxs-lookup"><span data-stu-id="5be3f-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![Esta captura de pantalla muestra la ubicación de la pestaña personalizada en la página Configuración contra correo no deseado &amp; del centro de seguridad y cumplimiento.](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="5be3f-122">Si es necesario, elija el modificador de **configuración personalizado** para activar la configuración personalizada.</span><span class="sxs-lookup"><span data-stu-id="5be3f-122">If necessary, choose the **Custom settings** switch to turn on custom settings.</span></span> <span data-ttu-id="5be3f-123">Si el modificador de configuración personalizado está \*\*\*\* desactivado, no podrá modificar las directivas de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5be3f-123">If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![Esta captura de pantalla muestra la configuración de directiva de filtro contra correo no deseado personalizada desactivada.](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="5be3f-125">ExPanda la Directiva de correo no deseado que desea modificar y, a continuación, elija **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="5be3f-125">Expand the spam policy you want to modify and then choose **Edit policy**.</span></span> <span data-ttu-id="5be3f-126">Por ejemplo, seleccione la flecha abajo junto a **Directiva de filtro de correo no deseado predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="5be3f-126">For example, choose the down arrow next to **Default spam filter policy**.</span></span> <span data-ttu-id="5be3f-127">O bien, si lo desea, puede crear una nueva Directiva eligiendo **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="5be3f-127">Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="5be3f-128">ExPanda **correo no deseado y** acciones en masa.</span><span class="sxs-lookup"><span data-stu-id="5be3f-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="5be3f-129">Para habilitar las sugerencias de seguridad, en **sugerencias de seguridad**, active la casilla **de verificación activado** .</span><span class="sxs-lookup"><span data-stu-id="5be3f-129">To enable safety tips, under **Safety Tips**, check the **On** checkbox.</span></span> <span data-ttu-id="5be3f-130">Para deshabilitar las sugerencias de seguridad, desactive la casilla **de verificación activado** .</span><span class="sxs-lookup"><span data-stu-id="5be3f-130">To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="5be3f-131">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5be3f-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="5be3f-132">Para habilitar o deshabilitar las sugerencias de seguridad con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5be3f-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="5be3f-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="5be3f-133"></span></span>

<span data-ttu-id="5be3f-134">Los administradores pueden usar Exchange Online PowerShell para habilitar o deshabilitar las sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5be3f-134">Admins can use Exchange Online PowerShell to enable or disable safety tips.</span></span> <span data-ttu-id="5be3f-135">Use el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar las sugerencias de seguridad en una directiva de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5be3f-135">Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="5be3f-136">Conexión al PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5be3f-136">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="5be3f-137">Para obtener más información, vea [conectarse a Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="5be3f-137">For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="5be3f-138">Ejecute el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar las sugerencias de seguridad:</span><span class="sxs-lookup"><span data-stu-id="5be3f-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="5be3f-139">Donde:</span><span class="sxs-lookup"><span data-stu-id="5be3f-139">Where:</span></span>
    
  -  <span data-ttu-id="5be3f-140">*nombre de directiva* es el nombre de la Directiva que desea modificar; por ejemplo, **default**.</span><span class="sxs-lookup"><span data-stu-id="5be3f-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="5be3f-141">`$true`habilita las sugerencias de seguridad para la Directiva de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5be3f-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="5be3f-142">`$false`deshabilita las sugerencias de seguridad para la Directiva de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="5be3f-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="5be3f-143">Por ejemplo, para deshabilitar las sugerencias de seguridad para la Directiva de filtro de correo no deseado predeterminada, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5be3f-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="5be3f-144">Para obtener más información sobre este cmdlet, vea [set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span><span class="sxs-lookup"><span data-stu-id="5be3f-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="5be3f-145">¿Sigue necesitando ayuda?</span><span class="sxs-lookup"><span data-stu-id="5be3f-145">Still need help?</span></span>
<span data-ttu-id="5be3f-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="5be3f-146"></span></span>

<span data-ttu-id="5be3f-147">Si ha deshabilitado las sugerencias de seguridad, pero sigue apareciendo en los mensajes de correo electrónico, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5be3f-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="5be3f-148">No puede deshabilitar las sugerencias de seguridad para Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="5be3f-148">You can't disable safety tips for Outlook on the web.</span></span> <span data-ttu-id="5be3f-149">Pruebe a ver el mismo correo electrónico en otro cliente, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="5be3f-149">Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="5be3f-150">Las sugerencias de seguridad están habilitadas de forma predeterminada para cada uno que usa EOP, esto incluye a todos los usuarios que tienen Office 365.</span><span class="sxs-lookup"><span data-stu-id="5be3f-150">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365.</span></span> <span data-ttu-id="5be3f-151">Para deshabilitar las sugerencias de seguridad y que no se muestren en el correo electrónico, debe deshabilitarlas mediante una directiva de filtro de correo no deseado, como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="5be3f-151">In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic.</span></span> <span data-ttu-id="5be3f-152">Una vez configurada la Directiva, asegúrese de que está habilitada.</span><span class="sxs-lookup"><span data-stu-id="5be3f-152">Once you've set up the policy, ensure that it is enabled.</span></span> <span data-ttu-id="5be3f-153">Para obtener información sobre cómo habilitar las directivas de filtro de correo no deseado, consulte [configurar las directivas de filtro de correo no deseado](https://technet.microsoft.com/library/jj200684.aspx).</span><span class="sxs-lookup"><span data-stu-id="5be3f-153">For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="5be3f-154">Para obtener más información sobre cómo combatir el correo no deseado y el phishing, consulte [Office 365 email anti-spam protection](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5be3f-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  


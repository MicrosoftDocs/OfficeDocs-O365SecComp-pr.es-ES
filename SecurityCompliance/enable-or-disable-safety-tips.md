---
title: Habilitar o deshabilitar las sugerencias de seguridad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/6/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: Indica cómo habilitar y deshabilitar las sugerencias de seguridad en los mensajes de correo electrónico de los administradores de Office 365 y elevación de privilegios.
ms.openlocfilehash: 3a8257f9d34ec5def54e2b9c9e919172366d023f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536298"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="19c3c-103">Habilitar o deshabilitar las sugerencias de seguridad en Office 365</span><span class="sxs-lookup"><span data-stu-id="19c3c-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="19c3c-p101">Agrega Exchange Online Protection (EOP) o marcas, una seguridad sugerencia a los mensajes de correo electrónico que ofrece. Estas sugerencias de seguridad proporcionan los destinatarios con una forma rápida y visual para determinar si es un mensaje de forma segura comprobado remitente, si el mensaje se ha marcado como correo no deseado por Office 365, si el mensaje contiene algo sospechosos como un estafas de suplantación de identidad, o bien, si dispone de imágenes externas se ha bloqueado. Office 365 y los administradores de EOP independiente pueden modificar la configuración de directiva spam para habilitar o deshabilitar sugerencias de seguridad que no se muestren en el correo electrónico en Outlook y otros clientes de correo electrónico de escritorio.</span><span class="sxs-lookup"><span data-stu-id="19c3c-p101">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers. These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked. Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="19c3c-p102">Office 365 permite sugerencias de seguridad para la organización de forma predeterminada y se recomienda que deje de ellos habilita para ayudar a combatir los ataques de correo no deseado y suplantación de identidad. No se puede deshabilitar sugerencias de seguridad para Outlook en el web.</span><span class="sxs-lookup"><span data-stu-id="19c3c-p102">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks. You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="19c3c-109">Para ver ejemplos y para obtener más información acerca de la información que se muestra en sugerencias de seguridad, vea [sugerencias de seguridad en los mensajes de correo electrónico en Office 365.](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="19c3c-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="19c3c-110">En este tema:</span><span class="sxs-lookup"><span data-stu-id="19c3c-110">In this topic:</span></span>
  
- [<span data-ttu-id="19c3c-111">Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="19c3c-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="19c3c-112">Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="19c3c-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="19c3c-113">Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="19c3c-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="19c3c-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="19c3c-114"></span></span>

1. <span data-ttu-id="19c3c-115">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="19c3c-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="19c3c-116">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="19c3c-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="19c3c-117">Elija **administración de amenaza** \> **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="19c3c-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="19c3c-118">En la página **Directiva** , elija **contra correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="19c3c-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![Esta captura de pantalla muestra cómo llegar a la página de configuración contra correo no deseado en la seguridad &amp; centro de cumplimiento.](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="19c3c-120">En la página **configuración de correo no deseado** , elija la ficha **personalizado** .</span><span class="sxs-lookup"><span data-stu-id="19c3c-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![Esta captura de pantalla muestra la ubicación de la ficha personalizada en la página de configuración contra correo no deseado en la seguridad &amp; centro de cumplimiento.](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="19c3c-p103">Si es necesario, elija el modificador de **configuración personalizada** para activar la configuración personalizada. Si el modificador de configuración personalizada está establecido en **desactivado**, no podrá modificar directivas de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="19c3c-p103">If necessary, choose the **Custom settings** switch to turn on custom settings. If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![Esta captura de pantalla muestra los filtros contra correo no deseado personalizados desactivado de configuración de la directiva.](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="19c3c-p104">Expanda la directiva de correo que desea modificar y, a continuación, elija **Editar directiva**. Por ejemplo, elija la flecha hacia abajo junto a **spam predeterminada filtrar la directiva**. O bien, si lo desea, puede crear una nueva directiva mediante la opción **Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="19c3c-p104">Expand the spam policy you want to modify and then choose **Edit policy**. For example, choose the down arrow next to **Default spam filter policy**. Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="19c3c-128">Expanda acciones de **correo no deseado y masiva** .</span><span class="sxs-lookup"><span data-stu-id="19c3c-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="19c3c-p105">Para habilitar sugerencias de seguridad, en la sección **Sugerencias de seguridad**, active la casilla de verificación **en** . Para deshabilitar sugerencias de seguridad, desactive la casilla de verificación **en** .</span><span class="sxs-lookup"><span data-stu-id="19c3c-p105">To enable safety tips, under **Safety Tips**, check the **On** checkbox. To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="19c3c-131">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="19c3c-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="19c3c-132">Para habilitar o deshabilitar sugerencias de seguridad mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="19c3c-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="19c3c-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="19c3c-133"></span></span>

<span data-ttu-id="19c3c-p106">Los administradores pueden utilizar Exchange Online PowerShell para habilitar o deshabilitar sugerencias de seguridad. Use el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar sugerencias de seguridad en una directiva de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="19c3c-p106">Admins can use Exchange Online PowerShell to enable or disable safety tips. Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="19c3c-p107">Conectarse a Exchange Online PowerShell. Para obtener información, vea [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="19c3c-p107">Connect to Exchange Online PowerShell. For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="19c3c-138">Ejecute el cmdlet Set-HostedContentFilterPolicy para habilitar o deshabilitar sugerencias de seguridad:</span><span class="sxs-lookup"><span data-stu-id="19c3c-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

    <span data-ttu-id="19c3c-139">Donde:</span><span class="sxs-lookup"><span data-stu-id="19c3c-139">Where:</span></span>
    
  -  <span data-ttu-id="19c3c-140">*nombre de la directiva* es el nombre de la directiva que desea modificar, por ejemplo **predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="19c3c-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="19c3c-141">`$true`permite sugerencias de seguridad para la directiva de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="19c3c-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="19c3c-142">`$false`deshabilita las sugerencias de seguridad para la directiva de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="19c3c-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="19c3c-143">Por ejemplo, para deshabilitar sugerencias de seguridad para la directiva de filtro de spam de forma predeterminada, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="19c3c-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

    <span data-ttu-id="19c3c-144">Para obtener más información acerca de este cmdlet, vea [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span><span class="sxs-lookup"><span data-stu-id="19c3c-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="19c3c-145">¿Aún necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="19c3c-145">Still need help?</span></span>
<span data-ttu-id="19c3c-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="19c3c-146"></span></span>

<span data-ttu-id="19c3c-147">Si deshabilita las sugerencias de seguridad, pero son todavía los ver en los mensajes de correo electrónico, compruebe estas cosas:</span><span class="sxs-lookup"><span data-stu-id="19c3c-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="19c3c-p108">No se puede deshabilitar sugerencias de seguridad para Outlook en el web. Intente ver el correo electrónico mismo en otro cliente, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="19c3c-p108">You can't disable safety tips for Outlook on the web. Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="19c3c-p109">Sugerencias de seguridad se encuentran en de forma predeterminada para cada uno que usa EOP, esto incluye todas las personas que tiene Office 365. Con el fin de deshabilitar sugerencias de seguridad no se muestren en el correo electrónico, debe deshabilitar mediante una directiva de filtro de spam, tal como se describe en este tema. Una vez que ha configurado la directiva, asegúrese de que esté habilitado. Para obtener información acerca de cómo habilitar directivas de filtro de correo no deseado, consulte [configurar sus directivas de filtro de correo no deseado](https://technet.microsoft.com/library/jj200684.aspx).</span><span class="sxs-lookup"><span data-stu-id="19c3c-p109">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365. In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic. Once you've set up the policy, ensure that it is enabled. For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="19c3c-154">Para que obtener más métodos combatir el correo no deseado y suplantación de identidad, consulte [Protección contra correo no deseado de Office 365 correo](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="19c3c-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  


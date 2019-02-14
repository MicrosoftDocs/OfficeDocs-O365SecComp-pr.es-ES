---
title: Habilitar el complemento de mensajes de informe
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el complemento en el mensaje de informe para Outlook y Outlook en el web, para usuarios individuales o de toda la organización.
ms.openlocfilehash: 8c061d14d11aa868567487186c5dcca534b86215
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995161"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="b935c-103">Habilitar el complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="b935c-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="b935c-104">Información general</span><span class="sxs-lookup"><span data-stu-id="b935c-104">Overview</span></span>

<span data-ttu-id="b935c-p101">El mensaje de informe complemento para Outlook y Outlook en el web permite que las personas que desea incorporar fácilmente clasificación incorrecta de correo electrónico, si seguros o malintencionado, Microsoft y sus filiales para el análisis. Microsoft utiliza estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Además, si su organización usa [Protección de amenaza avanzada de Office 365](office-365-atp.md) o [Información sobre amenazas de Office 365](office-365-ti.md), el complemento en el mensaje de informe proporciona equipo de seguridad de su organización con información útil que puedan usar para revisar y actualizar directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b935c-p101">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="b935c-p102">Por ejemplo, suponga que las personas son informes una gran cantidad de mensajes como suplantación de identidad. Superficies de esta información en el [Panel de seguridad](security-dashboard.md) y otros informes. Equipo de seguridad de su organización puede usar esta información como una indicación de que las directivas contra suplantación de identidad es posible que deba actualizarse. O bien, si las personas informa de una gran cantidad de mensajes que se han marcado como correo no deseado como no deseado mediante el uso del complemento en el mensaje de informe, equipo de seguridad de su organización es posible que necesite ajustar [las directivas contra correo no deseadas](configure-the-anti-spam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b935c-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="b935c-112">El complemento en el mensaje de informe funciona con la suscripción de Office 365 y los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="b935c-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="b935c-113">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="b935c-113">Outlook on the web</span></span>
 - <span data-ttu-id="b935c-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="b935c-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="b935c-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b935c-115">Outlook 2016</span></span>
 - <span data-ttu-id="b935c-116">Outlook 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="b935c-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="b935c-117">Outlook incluido con Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="b935c-117">Outlook included with Office 365 ProPlus</span></span>

> [!NOTE]
> <span data-ttu-id="b935c-p103">El mensaje de informe complemento para Outlook y Outlook en el web no es exactamente lo mismo que el [Filtro de correo electrónico no deseado de Outlook](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), aunque ambos pueden usarse para marcar el correo electrónico como correo no deseado, no no deseado o un intento de suplantación de identidad. El mensaje de informe complemento para Outlook y Outlook en el web notifica a Microsoft acerca del correo electrónico clasificación incorrecta, mientras que el filtro de correo electrónico no deseado de Outlook se usa para organizar los mensajes de correo electrónico en el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="b935c-p103">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt. The Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 
  
<span data-ttu-id="b935c-120">Si es un usuario individual, se puede [Habilitar el complemento en el mensaje de informe para usted mismo](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="b935c-120">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="b935c-p104">Si usted es un administrador global de Office 365 o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, se puede [Habilitar el complemento en el mensaje de informe para la organización](#get-and-enable-the-report-message-add-in-for-your-organization). El complemento del mensaje de informe ahora está disponible a través de la [Implementación centralizado](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="b935c-p104">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="b935c-123">Obtener el mensaje de informe de complemento para usted mismo</span><span class="sxs-lookup"><span data-stu-id="b935c-123">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="b935c-124">En [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), busque el [complemento en el mensaje de informe](https://appsource.microsoft.com/product/office/wa104381180).</span><span class="sxs-lookup"><span data-stu-id="b935c-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="b935c-125">Elija **obtener TI ahora**.</span><span class="sxs-lookup"><span data-stu-id="b935c-125">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="b935c-126">![Notificar mensaje: obtenerlo ahora](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-126">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="b935c-p105">Revise los términos de uso y política de privacidad. A continuación, elija **continuar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-p105">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="b935c-129">Inicie sesión en Office 365 con su trabajo o cuenta school (para uso empresarial) o su cuenta de Microsoft (para uso personal).</span><span class="sxs-lookup"><span data-stu-id="b935c-129">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="b935c-130">Después de que el complemento está instalado y habilitado, verá los iconos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b935c-130">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="b935c-131">En Outlook, el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b935c-131">In Outlook, the icon looks like this:</span></span> <br/> ![Informe complemento icono mensaje de Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="b935c-133">En Outlook Web App (o Outlook en el web), el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b935c-133">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Outlook en el icono de web complemento en el mensaje de informe](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="b935c-135">Como un paso siguiente, obtenga información sobre cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="b935c-135">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="b935c-136">Obtener y habilitar el complemento en el mensaje de informe para la organización</span><span class="sxs-lookup"><span data-stu-id="b935c-136">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b935c-p106">Debe ser un administrador global de Office 365 o un administrador de Exchange Online para llevar a cabo esta tarea. Además, Exchange debe configurarse para usar la autenticación de OAuth para obtener más información, vea [requisitos de Exchange (centralizado de implementación de complementos)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span><span class="sxs-lookup"><span data-stu-id="b935c-p106">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="b935c-139">Vaya a la [página de complementos de servicios &](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b935c-139">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="b935c-140">![Página de servicios y complementos en el nuevo centro de administración de Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-140">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="b935c-141">Elija **+ implementar Add-in**.</span><span class="sxs-lookup"><span data-stu-id="b935c-141">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="b935c-142">![Elija implementar complemento](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-142">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="b935c-143">En la pantalla **Nuevo complemento** , revise la información y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b935c-143">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="b935c-144">![Detalles del complemento nuevo](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-144">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="b935c-145">Seleccione **Agregar un complemento de la tienda de Office**y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b935c-145">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="b935c-146">![Agregar un nuevo complemento](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-146">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="b935c-147">Búsqueda de **Mensaje de informe**y en la lista de resultados, junto a **Agregar mensaje de informe**, elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-147">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="b935c-148">![Buscar mensajes de informe y, a continuación, elija Agregar](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-148">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="b935c-149">En la pantalla del **Mensaje del informe** , revise la información y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b935c-149">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="b935c-150">![Detalles del informe de mensaje](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-150">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="b935c-151">Especificar la configuración predeterminada del usuario para Outlook y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b935c-151">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="b935c-152">![Informe de configuración de mensaje predeterminada para Outlook](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-152">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="b935c-153">Especificar quién obtiene el mensaje de informe complemento y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-153">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="b935c-154">![Que obtiene el mensaje de informe de complemento](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-154">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="b935c-155">Se recomienda [Configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span><span class="sxs-lookup"><span data-stu-id="b935c-155">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="b935c-p107">Dependiendo de lo que ha seleccionado al configurar el complemento (los pasos 7-8 anteriores), las personas de su organización tendrán el [mensaje de informe de complementos](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponibles. Las personas de su organización verán los iconos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b935c-p107">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="b935c-158">En Outlook, el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b935c-158">In Outlook, the icon looks like this:</span></span> <br/> ![Icono informe de mensaje, complemento para Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="b935c-160">En Outlook Web App (o Outlook en el web), el icono tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b935c-160">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Outlook en el icono mensaje de informe de Web, complemento](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="b935c-162">Cuando se notifica a los usuarios sobre el complemento en el mensaje de informe, incluir un vínculo a [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="b935c-162">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="b935c-163">Configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios</span><span class="sxs-lookup"><span data-stu-id="b935c-163">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b935c-164">Debe ser un administrador de Exchange Online para realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="b935c-164">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="b935c-p108">Puede configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios de la organización. Para ello, después de haber descargado y habilitado el complemento en el mensaje de informe para la organización.</span><span class="sxs-lookup"><span data-stu-id="b935c-p108">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="b935c-167">En el centro de administración de Exchange, elija **flujo de correo** \> **reglas**.</span><span class="sxs-lookup"><span data-stu-id="b935c-167">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="b935c-168">Elija **+** \> **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="b935c-168">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="b935c-169">En el cuadro **nombre** , escriba un nombre, como los envíos.</span><span class="sxs-lookup"><span data-stu-id="b935c-169">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="b935c-170">En la lista **aplicar esta regla si** , elija **la dirección del destinatario incluye …**.</span><span class="sxs-lookup"><span data-stu-id="b935c-170">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="b935c-171">En la pantalla **especificar palabras o frases** , agregue `junk@office365.microsoft.com` y `phish@office365.microsoft.com`y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-171">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="b935c-172">![Especificar las direcciones de correo electrónico no deseado y phishing para la regla](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-172">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="b935c-173">En la lista **haga lo siguiente...** , elija **CCO del mensaje a...**.</span><span class="sxs-lookup"><span data-stu-id="b935c-173">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="b935c-174">Agregar un administrador global, Administrador de seguridad o lector de seguridad que debe recibir una copia de cada mensaje de correo electrónico que informan de las personas a Microsoft y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-174">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="b935c-175">![Agregar un administrador global o de seguridad para recibir una copia de cada mensaje conocida](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-175">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="b935c-176">Seleccione **esta regla con nivel de gravedad de auditoría**y elija **medio**.</span><span class="sxs-lookup"><span data-stu-id="b935c-176">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="b935c-177">En **Elegir un modo para esta regla**, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-177">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="b935c-178">![Configurar una regla para obtener una copia de cada mensaje conocida](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-178">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="b935c-179">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b935c-179">Choose **Save**.</span></span> 
    
<span data-ttu-id="b935c-p109">Con esta regla en su lugar, siempre que una persona de su organización notifica un mensaje de correo electrónico mediante el complemento de mensaje de informe, el administrador global, Administrador de seguridad o lector de seguridad recibirá una copia de ese mensaje. Puede habilitar esta información le permite configurar o ajustar las directivas, como las directivas de [Office 365 ATP seguros vínculos](atp-safe-links.md) , o con la configuración [contra correo no deseado](anti-spam-protection.md) .</span><span class="sxs-lookup"><span data-stu-id="b935c-p109">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="b935c-182">Obtenga información sobre cómo usar el complemento en el mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="b935c-182">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="b935c-183">Cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="b935c-183">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="b935c-184">Revisar o modificar la configuración para el complemento en el mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="b935c-184">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="b935c-185">Puede revisar y modificar la configuración predeterminada para el complemento de mensaje de informe en la [página de servicios & Add-Ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span><span class="sxs-lookup"><span data-stu-id="b935c-185">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b935c-186">Debe ser un administrador global de Office 365 o un administrador de Exchange Online para llevar a cabo esta tarea.</span><span class="sxs-lookup"><span data-stu-id="b935c-186">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="b935c-187">Vaya a la [página de complementos de servicios &](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b935c-187">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="b935c-188">![Página de servicios y complementos en el nuevo centro de administración de Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="b935c-188">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="b935c-189">Busque y seleccione el complemento en el mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="b935c-189">Find and select the Report Message add-in.</span></span><br/>![Busque y seleccione el complemento en el mensaje de informe](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="b935c-191">En la pantalla de mensaje de informe, revisar y editar la configuración según corresponda para su organización.</span><span class="sxs-lookup"><span data-stu-id="b935c-191">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![Configuración para el complemento en el mensaje de informe](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a><span data-ttu-id="b935c-193">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b935c-193">Related topics</span></span>

[<span data-ttu-id="b935c-194">Use el complemento en el mensaje de informe</span><span class="sxs-lookup"><span data-stu-id="b935c-194">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="b935c-195">Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b935c-195">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="b935c-196">Visualización de informes para la protección de amenaza avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="b935c-196">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="b935c-197">Use el explorador en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b935c-197">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  


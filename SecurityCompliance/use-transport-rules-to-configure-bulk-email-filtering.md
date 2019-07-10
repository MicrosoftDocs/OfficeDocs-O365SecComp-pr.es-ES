---
title: Usar reglas de flujo de correo para configurar el filtrado masivo de correo electrónico en Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo en Exchange Online Protection para el filtrado masivo de correo electrónico.
ms.openlocfilehash: 185a1174ba3e0d400926b03c073feb100f8e812d
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600793"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="a1b1e-103">Usar reglas de flujo de correo para configurar el filtrado masivo de correo electrónico en Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1b1e-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="a1b1e-p101">Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) y [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) para obtener información sobre cómo configurar las directivas de filtro de contenido.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="a1b1e-106">Si desea más opciones para filtrar los mensajes masivos, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para buscar patrones de texto o frases que se encuentran con frecuencia en los correos masivos.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="a1b1e-107">Todos los mensajes que contienen estas características se marcarán como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="a1b1e-108">El uso de estas reglas puede ayudar a reducir la cantidad de correo electrónico masivo no deseado que una organización recibe.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1b1e-109">Antes de crear las reglas de flujo de correo documentadas en este tema, recomendamos que primero lea [cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo](what-s-the-difference-between-junk-email-and-bulk-email.md) y [los valores de nivel de queja masiva](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="a1b1e-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br><span data-ttu-id="a1b1e-p103">En los siguientes procedimientos se marca un mensaje como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solamente a destinatarios específicos en la organización. De este modo, la configuración agresiva de filtrado de correo masivo se puede aplicar a unos cuantos usuarios específicos, mientras que el resto de los usuarios (que en su mayor parte reciben el correo masivo por el que se suscribieron) no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-p103"> The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="a1b1e-113">Crear una regla de flujo de correo para filtrar mensajes de correo electrónico masivo en función de patrones de texto</span><span class="sxs-lookup"><span data-stu-id="a1b1e-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="a1b1e-114">En el Centro de administración de Exchange (EAC), vaya a **Flujo de correo**\>\*\* Reglas\*\*.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="a1b1e-115">Haga \*\*\*\* ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono Agregar y, a continuación, seleccione **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-115">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="a1b1e-116">Especifique un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="a1b1e-p104">Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo coincide con estos patrones de texto**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="a1b1e-119">En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes expresiones regulares que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine:</span><span class="sxs-lookup"><span data-stu-id="a1b1e-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   <span data-ttu-id="a1b1e-120">La lista anterior no es un conjunto exhaustivo de expresiones regulares que se encuentran en los correos electrónicos masivos; se pueden agregar o quitar más según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="a1b1e-121">Pero es un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-121">However, it's a good starting point.</span></span><br><span data-ttu-id="a1b1e-122">La búsqueda de palabras o patrones de texto en el asunto o en otros campos de encabezado del mensaje se produce *después* de que el mensaje se haya descodificado del método de codificación de transferencia de contenido MIME que se usó para transmitir el mensaje binario entre los servidores SMTP en texto ASCII.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-122">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="a1b1e-123">No puede usar condiciones ni excepciones para buscar los valores codificados sin formato (normalmente, Base64) del asunto o de otros campos del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="a1b1e-124">En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="a1b1e-125">En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="a1b1e-p107">Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1b1e-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="a1b1e-129">Si la acción configurada es poner en cuarentena el mensaje en lugar de enviarlo a la carpeta de correo electrónico no deseado de los destinatarios, el mensaje se enviará a la cuarentena de administrador como una coincidencia de regla de flujo de correo y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante el usuario final. notificaciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="a1b1e-130">Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a1b1e-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="a1b1e-131">Guarde la regla.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="a1b1e-132">Crear una regla de flujo de correo para filtrar mensajes de correo masivo según frases</span><span class="sxs-lookup"><span data-stu-id="a1b1e-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="a1b1e-133">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="a1b1e-134">Haga \*\*\*\* ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono Agregar y, a continuación, seleccione **crear una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-134">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="a1b1e-135">Especifique un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="a1b1e-p108">Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo incluye cualquiera de estas palabras**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-p108">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="a1b1e-138">En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes frases que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine:</span><span class="sxs-lookup"><span data-stu-id="a1b1e-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   <span data-ttu-id="a1b1e-139">Esta lista no es un conjunto exhaustivo de frases que se encuentran en los correos electrónicos en masa; se pueden agregar o quitar más según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="a1b1e-140">Pero es un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-140">However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="a1b1e-141">En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="a1b1e-142">En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="a1b1e-p110">Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1b1e-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="a1b1e-146">Si la acción configurada es poner en cuarentena el mensaje en lugar de enviarlo a la carpeta de correo electrónico no deseado de los destinatarios, el mensaje se enviará a la cuarentena de administrador como una coincidencia de regla de flujo de correo y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante el usuario final. notificaciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="a1b1e-147">Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a1b1e-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="a1b1e-148">Guarde la regla.</span><span class="sxs-lookup"><span data-stu-id="a1b1e-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a1b1e-149">Más información</span><span class="sxs-lookup"><span data-stu-id="a1b1e-149">For more information</span></span>

[<span data-ttu-id="a1b1e-150">¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?</span><span class="sxs-lookup"><span data-stu-id="a1b1e-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="a1b1e-151">Valores de nivel de queja de correo masivo</span><span class="sxs-lookup"><span data-stu-id="a1b1e-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="a1b1e-152">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a1b1e-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="a1b1e-153">Opciones avanzadas de filtrado de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="a1b1e-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)

---
title: Uso de reglas de transporte para configurar el filtrado de correo electrónico masivo
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte Configurar las directivas de filtro de correo no deseado y Set-HostedContentFilterPolicy para obtener información sobre cómo configurar las directivas de filtro de contenido.
ms.openlocfilehash: f72fa5cc50ab6aa5447e3af9fabc365457c82973
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027687"
---
# <a name="use-transport-rules-to-configure-bulk-email-filtering"></a><span data-ttu-id="e4789-104">Uso de reglas de transporte para configurar el filtrado de correo electrónico masivo</span><span class="sxs-lookup"><span data-stu-id="e4789-104">Use transport rules to configure bulk email filtering</span></span>

<span data-ttu-id="e4789-p102">Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) y [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) para obtener información sobre cómo configurar las directivas de filtro de contenido.</span><span class="sxs-lookup"><span data-stu-id="e4789-p102">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="e4789-p103">Si quiere más opciones para filtrar los mensajes masivos, puede crear reglas de transporte de Exchange para buscar patrones de texto o frases que se encuentran con frecuencia en los correos masivos. Todos los mensajes que contienen estas características se marcarán como correo no deseado. El uso de estas reglas puede ayudar a reducir la cantidad de correo electrónico masivo no deseado que una organización recibe.</span><span class="sxs-lookup"><span data-stu-id="e4789-p103">If you want to more options to filter bulk messages, you can create Exchange Transport rules to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4789-110">Antes de crear las reglas de transporte documentadas en este tema, le recomendamos que lea primero [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) y [Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="e4789-110">Before creating the Transport rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e4789-p104">En los siguientes procedimientos se marca un mensaje como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solamente a destinatarios específicos en la organización. De este modo, la configuración agresiva de filtrado de correo masivo se puede aplicar a unos cuantos usuarios específicos, mientras que el resto de los usuarios (que en su mayor parte reciben el correo masivo por el que se suscribieron) no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="e4789-p104">The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="e4789-114">Crear una regla de transporte de Exchange para filtrar mensajes de correo masivo según patrones de texto</span><span class="sxs-lookup"><span data-stu-id="e4789-114">Create an Exchange Transport rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="e4789-115">En el Centro de administración de Exchange (EAC), vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="e4789-115">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e4789-116">Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.png) y seleccione **Crea una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="e4789-116">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e4789-117">Especifique un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="e4789-117">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="e4789-p105">Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo coincide con estos patrones de texto**.</span><span class="sxs-lookup"><span data-stu-id="e4789-p105">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="e4789-120">En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes expresiones regulares que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine:</span><span class="sxs-lookup"><span data-stu-id="e4789-120">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
  - <span data-ttu-id="e4789-121">Si no puede ver el contenido de este correo\,</span><span class="sxs-lookup"><span data-stu-id="e4789-121">If you are unable to view the content of this email\, please</span></span>
    
  - <span data-ttu-id="e4789-122">\\>(seguro )?cancele su suscripción( aquí)?\\</a\\></span><span class="sxs-lookup"><span data-stu-id="e4789-122">\\>(safe )?unsubscribe( here)?\\</a\\></span></span>
    
  - <span data-ttu-id="e4789-123">Si no desea recibir más comunicaciones como esta\,</span><span class="sxs-lookup"><span data-stu-id="e4789-123">If you do not wish to receive further communications like this\, please</span></span>
    
  - <span data-ttu-id="e4789-p106">\\<img height\="?1"? width\="?1"? src\=.?http\://</span><span class="sxs-lookup"><span data-stu-id="e4789-p106">\\<img height\="?1"? width\="?1"? src\=.?http\://</span></span>
    
  - <span data-ttu-id="e4789-127">Para dejar de recibir estos\s+emails\:http\://</span><span class="sxs-lookup"><span data-stu-id="e4789-127">To stop receiving these\s+emails\:http\://</span></span>
    
  - <span data-ttu-id="e4789-128">Para cancelar su suscripción de \w+ (e\-?carta|e?-?mail|boletín)</span><span class="sxs-lookup"><span data-stu-id="e4789-128">To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)</span></span>
    
  - <span data-ttu-id="e4789-129">ya no (desea )?(que )?(se le envíe|recibir) \w+ email</span><span class="sxs-lookup"><span data-stu-id="e4789-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span></span>
    
  - <span data-ttu-id="e4789-130">Si no puede ver el contenido de este correo\, haga clic aquí</span><span class="sxs-lookup"><span data-stu-id="e4789-130">If you are unable to view the content of this email\, please click here</span></span>
    
  - <span data-ttu-id="e4789-131">Para asegurarse de que recibe (sus ofertas diarias|nuestros e-?mails)\, agregue</span><span class="sxs-lookup"><span data-stu-id="e4789-131">To ensure you receive (your daily deals|our e-?mails)\, add</span></span>
    
  - <span data-ttu-id="e4789-132">Si ya no desea seguir recibiendo estos mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e4789-132">If you no longer wish to receive these emails</span></span>
    
  - <span data-ttu-id="e4789-133">para cambiar su (preferencias de suscripción|preferencias o cancelar su suscripción)</span><span class="sxs-lookup"><span data-stu-id="e4789-133">to change your (subscription preferences|preferences or unsubscribe)</span></span>
    
  - <span data-ttu-id="e4789-134">haga clic (aquí para|la) cancelar su suscripción</span><span class="sxs-lookup"><span data-stu-id="e4789-134">click (here to|the) unsubscribe</span></span>
    
    <span data-ttu-id="e4789-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="e4789-135">**Notes**:</span></span>
    
  - <span data-ttu-id="e4789-p107">La lista anterior no es un conjunto exhaustivo de expresiones regulares que se encuentran en mensajes de correo electrónico masivo; más información puede que se agreguen o eliminen según sea necesario. Sin embargo, es un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="e4789-p107">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
  - <span data-ttu-id="e4789-p108">La búsqueda de palabras o patrones de texto en el asunto o en otros campos de encabezado en el mensaje se produce *después de que* el mensaje ha descodificada desde la transferencia de contenido MIME codificación (método) que se usó para transmitir el mensaje binario entre servidores SMTP de texto ASCII. No se puede usar las condiciones o excepciones para buscar el sin procesar (normalmente, Base64) codificado valores del asunto o en otros campos de encabezado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e4789-p108">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="e4789-140">En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="e4789-140">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="e4789-141">En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e4789-141">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
    <span data-ttu-id="e4789-p109">Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4789-p109">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4789-145">Si la acción configurada es poner en cuarentena el mensaje en vez de enviarlo a la carpeta Correo no deseado de los destinatarios, el mensaje se enviará a la cuarentena del administrador como coincidencia de regla de transporte y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="e4789-145">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a transport rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
    <span data-ttu-id="e4789-146">Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e4789-146">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="e4789-147">Guarde la regla.</span><span class="sxs-lookup"><span data-stu-id="e4789-147">Save the rule.</span></span>
    
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="e4789-148">Crear una regla de transporte de Exchange para filtrar mensajes de correo masivo según frases</span><span class="sxs-lookup"><span data-stu-id="e4789-148">Create an Exchange Transport rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="e4789-149">En el EAC, vaya a **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="e4789-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e4789-150">Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.png) y seleccione **Crea una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="e4789-150">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e4789-151">Especifique un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="e4789-151">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="e4789-p110">Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo incluye cualquiera de estas palabras**.</span><span class="sxs-lookup"><span data-stu-id="e4789-p110">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="e4789-154">En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes frases que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine:</span><span class="sxs-lookup"><span data-stu-id="e4789-154">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
  - <span data-ttu-id="e4789-155">para cambiar sus preferencias o cancelar su suscripción</span><span class="sxs-lookup"><span data-stu-id="e4789-155">to change your preferences or unsubscribe</span></span>
    
  - <span data-ttu-id="e4789-156">Modifique sus preferencias de correo electrónico o cancele su suscripción</span><span class="sxs-lookup"><span data-stu-id="e4789-156">Modify email preferences or unsubscribe</span></span>
    
  - <span data-ttu-id="e4789-157">Este es un correo electrónico promocional</span><span class="sxs-lookup"><span data-stu-id="e4789-157">This is a promotional email</span></span>
    
  - <span data-ttu-id="e4789-158">Está recibiendo este correo porque solicitó una suscripción</span><span class="sxs-lookup"><span data-stu-id="e4789-158">You are receiving this email because you requested a subscription</span></span>
    
  - <span data-ttu-id="e4789-159">haga clic aquí para cancelar su suscripción</span><span class="sxs-lookup"><span data-stu-id="e4789-159">click here to unsubscribe</span></span>
    
  - <span data-ttu-id="e4789-160">Recibió este correo electrónico porque está suscrito</span><span class="sxs-lookup"><span data-stu-id="e4789-160">You have received this email because you are subscribed</span></span>
    
  - <span data-ttu-id="e4789-161">Si ya no desea seguir recibiendo nuestro boletín electrónico</span><span class="sxs-lookup"><span data-stu-id="e4789-161">If you no longer wish to receive our email newsletter</span></span>
    
  - <span data-ttu-id="e4789-162">para cancelar sus suscripción de este boletín</span><span class="sxs-lookup"><span data-stu-id="e4789-162">to unsubscribe from this newsletter</span></span>
    
  - <span data-ttu-id="e4789-163">Si tiene problemas para ver este correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e4789-163">If you have trouble viewing this email</span></span>
    
  - <span data-ttu-id="e4789-164">Este es un anuncio</span><span class="sxs-lookup"><span data-stu-id="e4789-164">This is an advertisement</span></span>
    
  - <span data-ttu-id="e4789-165">desea cancelar su suscripción o cambiar su</span><span class="sxs-lookup"><span data-stu-id="e4789-165">you would like to unsubscribe or change your</span></span>
    
  - <span data-ttu-id="e4789-166">vea este correo como una página web</span><span class="sxs-lookup"><span data-stu-id="e4789-166">view this email as a webpage</span></span>
    
  - <span data-ttu-id="e4789-167">Está recibiendo este correo electrónico porque está suscrito</span><span class="sxs-lookup"><span data-stu-id="e4789-167">You are receiving this email because you are subscribed</span></span>
    
    <span data-ttu-id="e4789-p111">**Nota**: una vez más, esta lista no es un conjunto exhaustivo de frases que se encuentran en mensajes de correo electrónico masivo; más información puede que se agreguen o eliminen según sea necesario. Sin embargo, es un buen punto de partida.</span><span class="sxs-lookup"><span data-stu-id="e4789-p111">**Note**: Once again, this list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="e4789-170">En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="e4789-170">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="e4789-171">En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e4789-171">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
    <span data-ttu-id="e4789-p112">Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4789-p112">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4789-175">Si la acción configurada es poner en cuarentena el mensaje en vez de enviarlo a la carpeta Correo no deseado de los destinatarios, el mensaje se enviará a la cuarentena del administrador como coincidencia de regla de transporte y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="e4789-175">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a transport rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
    <span data-ttu-id="e4789-176">Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e4789-176">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="e4789-177">Guarde la regla.</span><span class="sxs-lookup"><span data-stu-id="e4789-177">Save the rule.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="e4789-178">Más información</span><span class="sxs-lookup"><span data-stu-id="e4789-178">For more information</span></span>

[<span data-ttu-id="e4789-179">¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?</span><span class="sxs-lookup"><span data-stu-id="e4789-179">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
[<span data-ttu-id="e4789-180">Valores de nivel de queja de correo masivo</span><span class="sxs-lookup"><span data-stu-id="e4789-180">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)
  
[<span data-ttu-id="e4789-181">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e4789-181">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="e4789-182">Opciones de filtrado de spam avanzado</span><span class="sxs-lookup"><span data-stu-id="e4789-182">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
  


---
title: Use reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Puede crear una regla de transporte que establezca el nivel de confianza contra correo no deseado (SCL) de un mensaje de correo electrónico. El SCL es una medida de la probabilidad de que un mensaje sea correo no deseado. El correo no deseado son mensajes de correo electrónico no solicitados (y a menudo no deseados). El servicio realiza diferentes acciones en un mensaje según su clasificación SCL. Por ejemplo, tal vez desee evitar el filtrado de contenido de correo no deseado para los mensajes enviados por personas dentro de la organización porque confía en que un mensaje que envía internamente un colega no es correo no deseado. El uso de reglas de transporte para establecer el valor SCL de un mensaje le da un mayor control para tratar con el correo no deseado.
ms.openlocfilehash: dfce98aa9d4fec25a06674eb68d6e00ae2964e87
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275630"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="a741c-108">Use reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL)</span><span class="sxs-lookup"><span data-stu-id="a741c-108">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="a741c-p102">Puede crear una regla de transporte que establezca el nivel de confianza contra correo no deseado (SCL) de un mensaje de correo electrónico. El SCL es una medida de la probabilidad de que un mensaje sea correo no deseado. El correo no deseado son mensajes de correo electrónico no solicitados (y a menudo no deseados). El servicio realiza diferentes acciones en un mensaje según su clasificación SCL. Por ejemplo, tal vez desee evitar el filtrado de contenido de correo no deseado para los mensajes enviados por personas dentro de la organización porque confía en que un mensaje que envía internamente un colega no es correo no deseado. El uso de reglas de transporte para establecer el valor SCL de un mensaje le da un mayor control para tratar con el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a741c-p102">You can create a transport rule that sets the spam confidence level (SCL) of an email message. The SCL is a measure of how likely a message is to be spam. Spam is unsolicited (and typically unwanted) email messages. The service takes different action on a message depending on its SCL rating. For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam. Using transport rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="a741c-115">**¿Qué necesita saber antes de comenzar?**</span><span class="sxs-lookup"><span data-stu-id="a741c-115">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="a741c-116">Tiempo estimado para finalizar este procedimiento: 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="a741c-116">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="a741c-p103">Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "reglas de transporte" en [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) o [Feature Permissions in EOP](eop/feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a741c-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="a741c-119">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="a741c-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="a741c-120">Para crear una regla de transporte que establezca el SCL de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a741c-120">To create a transport rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="a741c-121">En el Centro de administración de Exchange (EAC), elija **Flujo de correo** \> **Reglas**.</span><span class="sxs-lookup"><span data-stu-id="a741c-121">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="a741c-122">Elija **Nuevo**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y seleccione **Crea una nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="a741c-122">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="a741c-123">Especifique un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="a741c-123">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="a741c-124">Elija **Más opciones** y, en **Aplicar esta regla si**, especifique una condición que desencadenará la acción que establecerá para esta regla (que es establecer el valor SCL).</span><span class="sxs-lookup"><span data-stu-id="a741c-124">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="a741c-125">Por ejemplo, puede establecer que **El remitente** \> **es interno/externo** y, a continuación, en el cuadro de diálogo **seleccionar ubicación de remitente**, seleccionar **Dentro de la organización** y elegir **aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a741c-125">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="a741c-126">![Seleccionar ubicación del remitente](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="a741c-126">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="a741c-127">En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="a741c-127">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="a741c-128">En el cuadro de diálogo **especificar SCL**, seleccione uno de los siguientes valores y elija **aceptar**:</span><span class="sxs-lookup"><span data-stu-id="a741c-128">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="a741c-129">**Omitir el filtrado de correo no deseado**: establece el SCL en -1, lo que significa que no se realizará el filtrado de contenido.</span><span class="sxs-lookup"><span data-stu-id="a741c-129">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="a741c-130">**0-4**: cuando establece el SCL en uno de estos valores, el mensaje se pasará al filtro de contenido para su procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="a741c-130">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="a741c-p104">**5, 6**: cuando se establece el SCL en uno de estos valores, se aplicará la acción especificada en **Correo no deseado** en las directivas del filtro de contenido aplicable. De forma predeterminada, la acción es enviar el mensaje a la carpeta de correo no deseado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a741c-p104">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="a741c-p105">**7, -9**: cuando se establece el SCL en uno de estos valores, se aplicará la acción especificada en **Correo no deseado de confianza alta** en las directivas del filtro de contenido aplicable. De forma predeterminada, la acción es enviar el mensaje a la carpeta de correo no deseado del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a741c-p105">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="a741c-p106">Para obtener más información acerca de cómo configurar las directivas de filtrado de contenido, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Para obtener más información acerca de los valores de SCL en el servicio, vea [Niveles de confianza de correo no deseado](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a741c-p106">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="a741c-137">Especifique propiedades adicionales para la regla y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a741c-137">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a741c-138">Para obtener más información sobre las propiedades adicionales que puede seleccionar o especificar para esta regla, vea [Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span><span class="sxs-lookup"><span data-stu-id="a741c-138">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a741c-139">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="a741c-139">How do you know this worked?</span></span>

<span data-ttu-id="a741c-p107">Para comprobar que este procedimiento funciona correctamente, envíe un mensaje de correo electrónico a una persona de su organización y compruebe que la acción que se realiza en el mensaje sea como se esperaba. Por ejemplo, si **establece el nivel de confianza de correo no deseado (SCL)** en **Omitir el filtrado de correo no deseado**, el mensaje debe enviarse a la bandeja de entrada del destinatario especificado. Sin embargo, si **establece el nivel de confianza de correo no deseado (SCL)** en **9** y la acción **Correo no deseado de confianza alta** para las directivas de filtro de contenido aplicables es mover el mensaje a la carpeta de correo no deseado, el mensaje debe enviarse a la carpeta de correo no deseado del destinatario especificado.</span><span class="sxs-lookup"><span data-stu-id="a741c-p107">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  


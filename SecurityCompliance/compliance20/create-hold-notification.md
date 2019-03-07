---
title: Crear un aviso de suspensión legal
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: acfa0c635b361426542e91a55c8d75c315bfb831
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455202"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="7e7d2-102">Crear un aviso de suspensión legal</span><span class="sxs-lookup"><span data-stu-id="7e7d2-102">Create a legal hold notice</span></span>

<span data-ttu-id="7e7d2-103">Mediante el uso de comunicaciones por custodios de eDiscovery avanzado (versión preliminar), las organizaciones pueden administrar su flujo de trabajo a partir de la comunicación con los custodios.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-103">Using Advanced eDiscovery (Preview) custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="7e7d2-104">Mediante la herramienta de comunicaciones, los equipos legales pueden enviar, recopilar y realizar un seguimiento sistemático de las notificaciones de retención legal.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-104">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="7e7d2-105">El proceso de creación flexible también permite a Microsoft Teams personalizar el flujo de trabajo de notificaciones de retención y el contenido de los avisos que se envían a los custodios.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-105">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span> 

![Página de comunicaciones](../media/CommunicationPage.PNG)

<span data-ttu-id="7e7d2-107">En el artículo se describen los pasos del flujo de trabajo de la notificación de retención.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-107">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="7e7d2-108">Paso 1: especificar detalles de comunicación</span><span class="sxs-lookup"><span data-stu-id="7e7d2-108">Step 1: Specify communication details</span></span>

<span data-ttu-id="7e7d2-109">El primer paso es especificar los detalles adecuados para los avisos de suspensión legal u otras comunicaciones de custodios.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-109">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span> 

![Página de comunicación de nombres](../media/NameCommunication.PNG)

1. <span data-ttu-id="7e7d2-111">En el centro de seguridad & cumplimiento, vaya a **eDiscovery _GT_ Advanced eDiscovery (versión preliminar)** para mostrar la lista de casos de su organización.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-111">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="7e7d2-112">Haga clic en la pestaña **comunicaciones** y, a continuación, en **nueva comunicación**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-112">Click the **Communications** tab, and then click **New communication**.</span></span>
   
3. <span data-ttu-id="7e7d2-113">En la página **comunicación de nombre** , especifique los siguientes detalles de comunicación (obligatorios).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-113">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="7e7d2-114">**Name**: nombre de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-114">**Name**: This is the name for the communication.</span></span>
    
    - <span data-ttu-id="7e7d2-115">**Responsable**de la emisión: la lista desplegable muestra una lista de los miembros de caso.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-115">**Issuing officer**: The dropdown list displays a list of a case members.</span></span> <span data-ttu-id="7e7d2-116">Cada aviso que se envíe a los custodios se enviará en nombre del responsable de la expedición especificado.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-116">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

4. <span data-ttu-id="7e7d2-117">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-117">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="7e7d2-118">Paso 2: definir el contenido del portal</span><span class="sxs-lookup"><span data-stu-id="7e7d2-118">Step 2: Define the portal content</span></span>

<span data-ttu-id="7e7d2-119">A continuación, puede crear y agregar el contenido del aviso de suspensión.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-119">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="7e7d2-120">En la página **definir contenido del portal** del Asistente para **crear una comunicación** , especifique el contenido del aviso de retención.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-120">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="7e7d2-121">Este contenido se anexará automáticamente a los avisos de emisión, reEmisión, aviso y reAsignación de responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-121">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="7e7d2-122">Además, este contenido aparecerá en el portal de cumplimiento de la custodio.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-122">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![Página de contenido del portal](../media/PortalContent.PNG)

<span data-ttu-id="7e7d2-124">Para crear el contenido del portal:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-124">To create the portal content:</span></span>

1. <span data-ttu-id="7e7d2-125">Escriba (o corte y pegue desde otro documento) el aviso de suspensión en el cuadro de texto para el contenido del portal.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-125">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="7e7d2-126">Inserte las variables de combinación en el aviso para personalizar el aviso y compartir el portal de cumplimiento de custodios.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-126">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="7e7d2-127">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-127">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="7e7d2-128">Para obtener más información acerca de cómo puede personalizar el contenido y el formato del contenido del portal, consulte [use el editor de comunicaciones](using-communications-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-128">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="7e7d2-129">Paso 3: establecer las notificaciones necesarias</span><span class="sxs-lookup"><span data-stu-id="7e7d2-129">Step 3: Set the required notifications</span></span>

<span data-ttu-id="7e7d2-130">Una vez que haya definido el contenido del aviso de retención, puede configurar los flujos de trabajo para enviar y administrar el proceso de notificación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-130">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="7e7d2-131">Las notificaciones son mensajes de correo electrónico que se envían a notificar y realizar un seguimiento con custodios.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-131">Notifications are email messages that are sent to notify and follow-up with custodians.</span></span> <span data-ttu-id="7e7d2-132">Todos los custodios que se agreguen a la comunicación recibirán la misma notificación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-132">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="7e7d2-133">Para configurar y enviar un aviso de retención, debe incluir notificaciones de emisión, reEmisión y publicación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-133">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="7e7d2-134">Notificación de emisión</span><span class="sxs-lookup"><span data-stu-id="7e7d2-134">Issuance notification</span></span> 

<span data-ttu-id="7e7d2-135">Una vez creada la comunicación, la **notificación de emisión** la inicia el responsable de la emisión especificado.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-135">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="7e7d2-136">La notificación de emisión es la primera comunicación que se envía al custodio para informarles sobre sus obligaciones de conservación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-136">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="7e7d2-137">Para crear una notificación de emisión:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-137">To create an issuance notification:</span></span>

1. <span data-ttu-id="7e7d2-138">En el icono **emisión** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-138">In the **Issuance** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="7e7d2-139">Si es necesario, agregue miembros del caso o personal adicional a los campos **CC** y **CCO** .</span><span class="sxs-lookup"><span data-stu-id="7e7d2-139">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="7e7d2-140">Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-140">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="7e7d2-141">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-141">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="7e7d2-142">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-142">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7e7d2-143">Tenga en cuenta que el contenido del portal que definió en el paso 2 se agrega al final del aviso de emisión.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-143">Note that the portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 
   
5. <span data-ttu-id="7e7d2-144">Haga clic en **Guardar**</span><span class="sxs-lookup"><span data-stu-id="7e7d2-144">Click **Save**</span></span> 

### <a name="re-issuance-notification"></a><span data-ttu-id="7e7d2-145">Notificación de nueva emisión</span><span class="sxs-lookup"><span data-stu-id="7e7d2-145">Re-Issuance notification</span></span> 

<span data-ttu-id="7e7d2-146">A medida que avanza el caso, es posible que se necesiten custodios para conservar más o menos datos de los que se indicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-146">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="7e7d2-147">Después de actualizar el contenido del aviso de retención, la notificación de reemisión alerta a los custodios sobre los cambios en sus obligaciones de conservación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-147">After you update the contents of the hold notice, the re-issuance notification alerts the  custodians about the changes to their preservation obligations.</span></span>

<span data-ttu-id="7e7d2-148">Para crear una notificación de nueva emisión:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-148">To create a re-issuance notification:</span></span> 

1. <span data-ttu-id="7e7d2-149">En el \*\*\*\* icono de reemisión, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-149">In the **Reissue** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="7e7d2-150">Si es necesario, agregue miembros del caso o personal adicional a los campos **CC** y **CCO** .</span><span class="sxs-lookup"><span data-stu-id="7e7d2-150">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="7e7d2-151">Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-151">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="7e7d2-152">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-152">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="7e7d2-153">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-153">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7e7d2-154">Tenga en cuenta que el contenido del portal que definió en el paso 2 se agrega al final del aviso de reemisión.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-154">Note that the portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>
   
5. <span data-ttu-id="7e7d2-155">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-155">Click **Save**.</span></span>

>[!Note]
><span data-ttu-id="7e7d2-156">Si se modifica una notificación de retención, se enviará automáticamente la notificación de reemisión a todos los custodios asignados a la notificación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-156">If a hold notification is modified, the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="7e7d2-157">Una vez enviada la notificación, se pedirá a los custodios que vuelvan a confirmar su aviso de suspensión.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-157">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="7e7d2-158">Si ha configurado un flujo de trabajo de aviso o de escalado, también se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-158">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> 

### <a name="release-notification"></a><span data-ttu-id="7e7d2-159">Notificación de versiones</span><span class="sxs-lookup"><span data-stu-id="7e7d2-159">Release notification</span></span>

<span data-ttu-id="7e7d2-160">Después de resolver una cuestión o si un custodio ya no está sujeto a preservar contenido, puede liberar el custodio de un caso.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-160">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="7e7d2-161">Si el custodio ha emitido previamente un aviso de retención, la notificación de versión puede usarse para avisar a los custodios de que han sido entregados desde sus obligaciones.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-161">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="7e7d2-162">Para crear una notificación de versión:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-162">To create a release notification:</span></span> 

1. <span data-ttu-id="7e7d2-163">En el mosaico de **versión** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-163">In the **Release** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="7e7d2-164">Si es necesario, agregue miembros del caso o personal adicional a los campos **CC** y **CCO** .</span><span class="sxs-lookup"><span data-stu-id="7e7d2-164">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="7e7d2-165">Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-165">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="7e7d2-166">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-166">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="7e7d2-167">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-167">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>
   
5. <span data-ttu-id="7e7d2-168">Haga clic en **Guardar** y vaya al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-168">Click **Save** and go to the next step.</span></span> 

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="7e7d2-169">Opcional Paso 4: establecer las notificaciones opcionales</span><span class="sxs-lookup"><span data-stu-id="7e7d2-169">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="7e7d2-170">De manera opcional, puede simplificar el flujo de trabajo para seguir con los administradores que no responden mediante la creación y programación de notificaciones automatizadas de reaviso y reasignación de incidencias.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-170">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![Página aviso/reMisión](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="7e7d2-172">Avisos</span><span class="sxs-lookup"><span data-stu-id="7e7d2-172">Reminders</span></span>

<span data-ttu-id="7e7d2-173">Después de enviar una notificación de retención, puede realizar un seguimiento de los administradores que no responden mediante la definición de un flujo de trabajo de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-173">After you have sent a hold notification, you can follow-up with unresponsive custodians by defining a reminder workflow.</span></span> 

<span data-ttu-id="7e7d2-174">Para programar los avisos:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-174">To schedule reminders:</span></span>

1. <span data-ttu-id="7e7d2-175">En el icono de **aviso** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-175">In the **Reminder** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="7e7d2-176">Habilite el flujo de trabajo de **aviso** activando el **Estado** de alternancia (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-176">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>
   
3. <span data-ttu-id="7e7d2-177">Especifique el **intervalo de aviso (en días)** (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-177">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="7e7d2-178">Es el número de días que se debe esperar antes de enviar las notificaciones de aviso de primer y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-178">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="7e7d2-179">Por ejemplo, si establece el intervalo de recordatorio en 7 días, el primer aviso se enviaría 7 días después de la emisión inicial de la notificación de retención.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-179">For example, if you set the reminder interval to 7 days, then the first reminder would be sent 7 days after the hold notification was initially issued.</span></span> <span data-ttu-id="7e7d2-180">Todos los avisos subsiguientes se enviarán también cada 7 días.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-180">All subsequent reminders would also be sent every 7 days.</span></span>
   
4. <span data-ttu-id="7e7d2-181">Especifique el **número de avisos** (obligatorios).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-181">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="7e7d2-182">Este campo especifica cuántos avisos enviar a los custodios que no responden.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-182">This field specifies how many reminders to send to un-responsive custodians.</span></span> <span data-ttu-id="7e7d2-183">Por ejemplo, si establece el número de avisos en 3, un custodio recibirá un máximo de 3 avisos.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-183">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of 3 reminders.</span></span> <span data-ttu-id="7e7d2-184">Una vez que un custodio reconoce la notificación de retención, ya no se enviarán avisos a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-184">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>
   
5. <span data-ttu-id="7e7d2-185">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-185">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="7e7d2-186">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-186">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7e7d2-187">Tenga en cuenta que el contenido del portal que definió en el paso 2 se agrega al final de la notificación de aviso.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-187">Note that the portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>
   
7. <span data-ttu-id="7e7d2-188">Haga clic en **Guardar** y continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-188">Click **Save** and go the the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="7e7d2-189">Escalaciones</span><span class="sxs-lookup"><span data-stu-id="7e7d2-189">Escalations</span></span> 

<span data-ttu-id="7e7d2-190">En algunas situaciones, es posible que necesite otras formas de realizar un seguimiento de los administradores que no responden.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-190">In some situations, you may need additional ways to follow-up with unresponsive custodians.</span></span> <span data-ttu-id="7e7d2-191">Si un custodio no reconoce una notificación de retención después de recibir el número especificado de avisos, el equipo legal puede especificar un flujo de trabajo para enviar automáticamente un aviso de escalado al custodio y a su administrador.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-191">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="7e7d2-192">Para programar las escalaciones:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-192">To schedule escalations:</span></span>

1. <span data-ttu-id="7e7d2-193">En el \*\*\*\* mosaico escalado, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-193">In the **Escalation** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="7e7d2-194">Habilite el \*\*\*\* flujo de trabajo de escalado activando el **Estado** de alternancia.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-194">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>
   
3. <span data-ttu-id="7e7d2-195">Especifique el **intervalo de escalación (en días)** (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-195">Specify the **Escalation interval (in days)** (required).</span></span> 
   
4. <span data-ttu-id="7e7d2-196">Especifique el **número de escalaciones** (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-196">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="7e7d2-197">Este campo especifica cuántas escalaciones se deben enviar a los custodios que no responden.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-197">This field specifies how many escalations to send to un-responsive custodians.</span></span> <span data-ttu-id="7e7d2-198">Por ejemplo, si establece el número de escalaciones en 3, se enviará un aviso de remisión a la custodio y a su administrador un máximo de 3 veces.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-198">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of 3 times.</span></span> <span data-ttu-id="7e7d2-199">Después de que un custodio reconozca la notificación de retención, las escalaciones ya no se enviarán.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-199">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span> 
   
5. <span data-ttu-id="7e7d2-200">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-200">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="7e7d2-201">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7e7d2-201">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7e7d2-202">Tenga en cuenta que el contenido del portal que definió en el paso 2 se agrega al final de la notificación de escalamiento.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-202">Note that the portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>
   
7. <span data-ttu-id="7e7d2-203">Haga clic en **Guardar** y continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-203">Click **Save** and go the the next step.</span></span>
   
## <a name="step-5-assign-custodians"></a><span data-ttu-id="7e7d2-204">Paso 5: asignar custodios</span><span class="sxs-lookup"><span data-stu-id="7e7d2-204">Step 5: Assign custodians</span></span> 

<span data-ttu-id="7e7d2-205">Una vez que haya finalizado el contenido de las notificaciones, seleccione los custodios a los que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-205">After you have finalized the content for notifications, select the custodians that you would like to send the notifications.</span></span> 

![Página seleccionar custodios](../media/SelectCustodians.PNG)

<span data-ttu-id="7e7d2-207">Para agregar custodios:</span><span class="sxs-lookup"><span data-stu-id="7e7d2-207">To add custodians:</span></span>

1. <span data-ttu-id="7e7d2-208">Asigne custodios a la comunicación haciendo clic en la casilla situada junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-208">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="7e7d2-209">Una vez creada la comunicación, el flujo de trabajo de notificaciones se aplicará automáticamente a los custodios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-209">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>
   
2. <span data-ttu-id="7e7d2-210">Haga clic en **siguiente** para revisar la configuración y los detalles de comunicación.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-210">Click **Next** to review the communication settings and details.</span></span>
 
>[!NOTE]
><span data-ttu-id="7e7d2-211">Solo se pueden agregar custodios que se hayan agregado al caso y que no se haya enviado otra notificación en el caso.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-211">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="7e7d2-212">Paso 6: revisar la configuración</span><span class="sxs-lookup"><span data-stu-id="7e7d2-212">Step 6: Review settings</span></span>

<span data-ttu-id="7e7d2-213">Después de revisar la configuración y hacer clic en **Enviar** para completar la comunicación, el sistema iniciará automáticamente el flujo de trabajo de comunicación enviando el aviso de emisión.</span><span class="sxs-lookup"><span data-stu-id="7e7d2-213">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

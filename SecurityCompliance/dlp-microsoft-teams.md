---
title: Prevención de pérdida de datos y Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/26/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Ahora puede aplicar directivas de DLP a chats y canales de Microsoft Teams. Lea este artículo para obtener más información sobre cómo funciona.
ms.openlocfilehash: 712729972942d98afb5b3898ad357114ce1a6bae
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33367309"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="2751b-104">Prevención de pérdida de datos y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2751b-104">Data loss prevention and Microsoft Teams</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="2751b-105">Información general de DLP para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2751b-105">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="2751b-106">Recientemente, se ampliaron las capacidades de [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) para incluir Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2751b-106">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams.</span></span> <span data-ttu-id="2751b-107">Si su organización tiene DLP, ahora puede definir directivas que impiden que los usuarios compartan información confidencial en una sesión de chat o de canal de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2751b-107">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="2751b-108">A continuación, se muestran algunos ejemplos de cómo funciona esta protección:</span><span class="sxs-lookup"><span data-stu-id="2751b-108">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="2751b-109">**Ejemplo 1: proteger la información confidencial en los mensajes**.</span><span class="sxs-lookup"><span data-stu-id="2751b-109">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="2751b-110">Suponga que alguien intenta compartir información confidencial en un canal o chat de Microsoft Teams con invitados (usuarios externos).</span><span class="sxs-lookup"><span data-stu-id="2751b-110">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="2751b-111">Si tiene definida una directiva DLP para evitar esto, se eliminan los mensajes con información confidencial que se envían a los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="2751b-111">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="2751b-112">Esto sucede automáticamente y en segundos, según la configuración de la Directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="2751b-112">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

- <span data-ttu-id="2751b-113">**Ejemplo 2: protección de información confidencial en documentos**.</span><span class="sxs-lookup"><span data-stu-id="2751b-113">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="2751b-114">Suponga que alguien intenta compartir un documento con invitados en un canal o chat de Microsoft Teams, y que el documento contiene información confidencial.</span><span class="sxs-lookup"><span data-stu-id="2751b-114">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="2751b-115">Si tiene definida una directiva DLP para evitar esto, el documento no se abrirá para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="2751b-115">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="2751b-116">Tenga en cuenta que, en este caso, la Directiva DLP debe incluir SharePoint y OneDrive para que la protección esté en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="2751b-116">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="2751b-117">Las sugerencias de directivas ayudan a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2751b-117">Policy tips help educate users</span></span>

<span data-ttu-id="2751b-118">De forma similar a cómo funciona DLP en [Exchange, Outlook y Outlook en la web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [sitios de SharePoint y OneDrive para la empresa](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)y [clientes de escritorio de Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), las sugerencias de directiva aparecen cuando una acción entra en conflicto con una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="2751b-118">Similar to how DLP works in [Exchange, Outlook, and Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint and OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="2751b-119">A continuación, se muestra un ejemplo de una sugerencia de directiva:</span><span class="sxs-lookup"><span data-stu-id="2751b-119">Here's an example of a policy tip:</span></span>

![Notificación de mensajes bloqueados en Microsoft Teams](media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="2751b-121">En este caso, el remitente ha intentado compartir un número de la seguridad social en un canal de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2751b-121">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="2751b-122">El vínculo **¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="2751b-122">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="2751b-123">Observe que, en este caso, el remitente puede optar por invalidar la Directiva o notificar a un administrador que la revise y la resuelva.</span><span class="sxs-lookup"><span data-stu-id="2751b-123">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opciones para resolver el mensaje bloqueado](media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="2751b-125">En su organización, puede elegir si desea permitir que los usuarios invaliden una directiva DLP o no.</span><span class="sxs-lookup"><span data-stu-id="2751b-125">In your organization, you can choose whether to allow users to override a DLP policy, or not.</span></span> <span data-ttu-id="2751b-126">Y, cuando configure las directivas de DLP, puede usar las sugerencias de directiva predeterminadas o [personalizar las sugerencias de directiva](#to-customize-policy-tips) para su organización.</span><span class="sxs-lookup"><span data-stu-id="2751b-126">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span> 

<span data-ttu-id="2751b-127">Volviendo a nuestro ejemplo, en el que un remitente compartió un número de la seguridad social en un canal de Teams, esto es lo que vio el destinatario:</span><span class="sxs-lookup"><span data-stu-id="2751b-127">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![Mensaje bloqueado](media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="2751b-129">El vínculo **¿Qué es esto?** abre un [artículo](data-loss-prevention-policies.md) sobre las directivas de DLP, que ayuda a explicar por qué se bloqueó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2751b-129">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="2751b-130">Para personalizar las sugerencias de Directiva</span><span class="sxs-lookup"><span data-stu-id="2751b-130">To customize policy tips</span></span>

<span data-ttu-id="2751b-131">Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="2751b-131">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="2751b-132">Para obtener más información, [](data-loss-prevention-policies.md#permissions)consulte Permissions.</span><span class="sxs-lookup"><span data-stu-id="2751b-132">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="2751b-133">Vaya al centro de cumplimiento de & de seguridad de[https://protection.office.com](https://protection.office.com)Office 365 () e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2751b-133">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="2751b-134">Elija \*\*\*\* > **Directiva**de prevención de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="2751b-134">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="2751b-135">Seleccione una directiva y, junto a **configuración de directiva**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2751b-135">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="2751b-136">Puede crear una nueva regla o editar una regla existente para la Directiva.</span><span class="sxs-lookup"><span data-stu-id="2751b-136">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![Edición de una regla para una directiva](media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="2751b-138">En la pestaña notificaciones del **usuario** , seleccione **personalizar el texto del correo electrónico** o **personalizar las opciones de texto de la sugerencia de directiva** .</span><span class="sxs-lookup"><span data-stu-id="2751b-138">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="2751b-139">![Personalizar las notificaciones de usuario y las sugerencias de Directiva](media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-139">![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="2751b-140">Especifique el texto que desea usar para las notificaciones de correo electrónico o las sugerencias de directiva y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2751b-140">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span> 

7. <span data-ttu-id="2751b-141">En la pestaña **configuración de directiva** , elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2751b-141">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="2751b-142">Espere aproximadamente una hora para que los cambios funcionen en el centro de datos y sincronicen las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="2751b-142">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="2751b-143">Agregar Microsoft Teams como ubicación a las directivas de DLP existentes</span><span class="sxs-lookup"><span data-stu-id="2751b-143">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="2751b-144">Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="2751b-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="2751b-145">Para obtener más información, [](data-loss-prevention-policies.md#permissions)consulte Permissions.</span><span class="sxs-lookup"><span data-stu-id="2751b-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="2751b-146">Vaya al centro de cumplimiento de & de seguridad de[https://protection.office.com](https://protection.office.com)Office 365 () e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2751b-146">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="2751b-147">Elija \*\*\*\* > **Directiva**de prevención de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="2751b-147">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="2751b-148">Seleccione una directiva y mire los valores en **ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2751b-148">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="2751b-149">Si ve **los mensajes de chat y de canal**de Microsoft Teams, ya está todo configurado.</span><span class="sxs-lookup"><span data-stu-id="2751b-149">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="2751b-150">Si no lo hace, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2751b-150">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="2751b-151">![Ubicaciones para la directiva existente](media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-151">![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="2751b-152">En la columna **Estado** , active la Directiva para **los mensajes de chat y de canal**de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2751b-152">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="2751b-153">![DLP para los chats y canales de Microsoft Teams](media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-153">![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="2751b-154">ConServe la configuración predeterminada de todas las cuentas o especifique las cuentas que se van a incluir o excluir.</span><span class="sxs-lookup"><span data-stu-id="2751b-154">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="2751b-155">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="2751b-155">Click **Save**.</span></span>

<span data-ttu-id="2751b-156">Espere aproximadamente una hora para que los cambios funcionen en el centro de datos y sincronicen las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="2751b-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="2751b-157">Definir una nueva Directiva de DLP para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2751b-157">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="2751b-158">Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="2751b-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="2751b-159">Para obtener más información, [](data-loss-prevention-policies.md#permissions)consulte Permissions.</span><span class="sxs-lookup"><span data-stu-id="2751b-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="2751b-160">Vaya al centro de cumplimiento de & de seguridad de[https://protection.office.com](https://protection.office.com)Office 365 () e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2751b-160">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="2751b-161">Elegir \*\*\*\* > \*\*\*\* directiva > **de prevención de pérdida de datos + crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="2751b-161">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span> 

3. <span data-ttu-id="2751b-162">Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates)y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-162">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="2751b-163">En nuestro ejemplo, elegimos la plantilla de datos de información de identificación personal de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2751b-163">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="2751b-164">![Plantilla de privacidad para la Directiva DLP](media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-164">![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="2751b-165">En la pestaña Nombre de la **Directiva** , especifique un nombre y una descripción para la Directiva y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-165">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span> 

5. <span data-ttu-id="2751b-166">En la pestaña **elegir ubicaciones** , mantenga la configuración predeterminada de todas las ubicaciones o seleccione **permitirme elegir ubicaciones específicas**y, después, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-166">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="2751b-167">Si optó por elegir ubicaciones específicas, seleccione las ubicaciones de la Directiva DLP y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-167">If you opted to choose specific locations, select the locations for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="2751b-168">![Ubicaciones de directivas de DLP](media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-168">![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="2751b-169">Si desea asegurarse de que los documentos que contienen información confidencial no se compartan de manera inadecuada, asegúrese de que los **sitios de SharePoint** y **las cuentas de OneDrive** estén activados, junto con **los mensajes de chat y de canal**de Teams.</span><span class="sxs-lookup"><span data-stu-id="2751b-169">If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>
<br/>

6. <span data-ttu-id="2751b-170">En la **pestaña Configuración de directiva** , en **personalizar el tipo de contenido que quiere proteger**, mantenga la configuración sencilla predeterminada o elija **Usar configuración avanzada**y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-170">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="2751b-171">Si elige la configuración avanzada, puede crear o editar reglas para la Directiva.</span><span class="sxs-lookup"><span data-stu-id="2751b-171">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="2751b-172">(Para obtener ayuda, consulte [Configuración sencilla frente a configuración avanzada](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)).</span><span class="sxs-lookup"><span data-stu-id="2751b-172">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="2751b-173">En la pestaña **configuración de directiva** , en **¿qué desea hacer si se detecta información confidencial?**, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="2751b-173">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="2751b-174">(Aquí puede elegir mantener las [sugerencias de directiva y notificaciones de correo electrónico](use-notifications-and-policy-tips.md)predeterminadas o personalizarlas).</span><span class="sxs-lookup"><span data-stu-id="2751b-174">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="2751b-175">![Configuración de directivas de DLP con sugerencias y notificaciones](media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-175">![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="2751b-176">Cuando haya terminado de revisar o editar la configuración, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-176">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="2751b-177">En la **pestaña Configuración de directiva** , en **¿desea activar la Directiva o probar la primera?**, elija si desea activar la Directiva, [probarla primero](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)o dejarla desactivada por ahora y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2751b-177">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="2751b-178">![Especificar si se va a activar la Directiva](media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="2751b-178">![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="2751b-179">En la pestaña **revisar la configuración** , revise la configuración de la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="2751b-179">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="2751b-180">Elija **Editar** para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="2751b-180">Choose **Edit** to make changes.</span></span> <span data-ttu-id="2751b-181">Cuando haya terminado, elija **crear**.</span><span class="sxs-lookup"><span data-stu-id="2751b-181">When you're finished, choose **Create**.</span></span> 

<span data-ttu-id="2751b-182">Espere aproximadamente una hora para que la nueva Directiva funcione a través del centro de datos y sincronice las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="2751b-182">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2751b-183">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="2751b-183">Related articles</span></span>

[<span data-ttu-id="2751b-184">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="2751b-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="2751b-185">Enviar notificaciones de email y mostrar sugerencias para directivas DLP</span><span class="sxs-lookup"><span data-stu-id="2751b-185">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
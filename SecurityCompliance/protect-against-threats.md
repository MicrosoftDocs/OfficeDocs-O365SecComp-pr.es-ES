---
title: Protección contra amenazas en Office 365
ms.author: tracyp
author: msfttracyp
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Use este artículo como guía para configurar las características de protección contra amenazas ahora.
ms.openlocfilehash: 065071999130f209d63bcafc09ad72daceceac04
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261638"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="50a94-103">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="50a94-104">Office 365 incluye una variedad de características de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="50a94-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="50a94-105">Esta es una guía de inicio rápido que puede usar como una lista de comprobación para asegurarse de que las características de protección contra amenazas se configuran para su organización.</span><span class="sxs-lookup"><span data-stu-id="50a94-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="50a94-106">Si no está familiarizado con las características de protección contra amenazas de Office 365 o no está seguro de dónde empezar, use las siguientes instrucciones como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="50a94-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="50a94-107">**Se incluye la configuración recomendada inicial para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas de su organización**.</span><span class="sxs-lookup"><span data-stu-id="50a94-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="50a94-108">Espere unos 30 minutos para que las directivas o los cambios funcionen a través del centro de proceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="50a94-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="50a94-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50a94-109">Requirements</span></span>

### <a name="licenses"></a><span data-ttu-id="50a94-110">Licencias</span><span class="sxs-lookup"><span data-stu-id="50a94-110">Licenses</span></span>

<span data-ttu-id="50a94-111">Las características de protección contra amenazas se incluyen en todas las suscripciones de Office 365; sin embargo, algunas suscripciones incluyen características más avanzadas, como las de la protección contra amenazas avanzada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="50a94-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features, such as those in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="50a94-112">En este artículo se incluyen requisitos de suscripción para cada área de protección.</span><span class="sxs-lookup"><span data-stu-id="50a94-112">In this article we include subscription requirements for each protection area.</span></span>

<span data-ttu-id="50a94-113">Para obtener más información sobre las características y subsriptions de la protección contra amenazas, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="50a94-113">To learn more about threat protection features and subsriptions, see the following resources:</span></span>
- [<span data-ttu-id="50a94-114">Descripción del servicio de Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-114">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
- [<span data-ttu-id="50a94-115">Descripción del servicio Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="50a94-115">Exchange Online Protection Service Description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)
- [<span data-ttu-id="50a94-116">Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-116">Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

### <a name="roles-and-permissions"></a><span data-ttu-id="50a94-117">Roles y permisos</span><span class="sxs-lookup"><span data-stu-id="50a94-117">Roles and permissions</span></span>

<span data-ttu-id="50a94-118">Debe tener asignado un rol apropiado para configurar directivas en el [centro de seguridad _AMP_ cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="50a94-118">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="50a94-119">En la tabla siguiente se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="50a94-119">The following table includes some examples:</span></span> 

|<span data-ttu-id="50a94-120">Rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="50a94-120">Role or role group</span></span>  |<span data-ttu-id="50a94-121">Dónde obtener más información</span><span class="sxs-lookup"><span data-stu-id="50a94-121">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="50a94-122">Administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-122">Office 365 Global Administrator</span></span> |[<span data-ttu-id="50a94-123">Acerca de los roles de administrador de Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-123">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="50a94-124">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="50a94-124">Security Administrator</span></span> |[<span data-ttu-id="50a94-125">Permisos de rol de administrador en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="50a94-125">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="50a94-126">Administración de la organización de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="50a94-126">Exchange Online Organization Management</span></span> |[<span data-ttu-id="50a94-127">Permisos en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="50a94-127">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="50a94-128">y</span><span class="sxs-lookup"><span data-stu-id="50a94-128">and</span></span><br> [<span data-ttu-id="50a94-129">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="50a94-129">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="50a94-130">Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-130">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="50a94-131">Parte 1: anti-malware</span><span class="sxs-lookup"><span data-stu-id="50a94-131">Part 1 - Anti-malware</span></span>

<span data-ttu-id="50a94-132">La [protección contra malware](anti-malware-protection.md) está disponible en las suscripciones que incluyen [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span><span class="sxs-lookup"><span data-stu-id="50a94-132">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="50a94-133">En el [centro de seguridad & cumplimiento](https://protection.office.com), elija**anti-malware**de**Directiva** > de **Administración** > de amenazas.</span><span class="sxs-lookup"><span data-stu-id="50a94-133">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="50a94-134">Haga doble clic en la directiva **predeterminada** y, a continuación, elija **configuración**.</span><span class="sxs-lookup"><span data-stu-id="50a94-134">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="50a94-135">Especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="50a94-135">Specify the following settings:</span></span>
    
    - <span data-ttu-id="50a94-136">En la sección **respuesta de detección de malware** , mantenga el valor predeterminado de **no**.</span><span class="sxs-lookup"><span data-stu-id="50a94-136">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
   
    - <span data-ttu-id="50a94-137">En la sección **filtro de tipos de datos adjuntos comunes** , elija **activado**.</span><span class="sxs-lookup"><span data-stu-id="50a94-137">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="50a94-138">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="50a94-138">Click **Save**.</span></span>

<span data-ttu-id="50a94-139">Para obtener más información acerca de las opciones de directiva antimalware, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-139">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="50a94-140">Parte 2: protección de día cero</span><span class="sxs-lookup"><span data-stu-id="50a94-140">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="50a94-141">La protección de día cero está disponible en las suscripciones que incluyen la [protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) y se configuran mediante las directivas de [datos adjuntos seguros de ATP](atp-safe-attachments.md) y [vínculos seguros ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="50a94-141">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="50a94-142">Directivas de datos adJuntos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="50a94-142">ATP Safe Attachments policies</span></span>

<span data-ttu-id="50a94-143">Para configurar los [datos adjuntos seguros de ATP](atp-safe-attachments.md), debe definir al menos una directiva de datos adJuntos seguros ATP.</span><span class="sxs-lookup"><span data-stu-id="50a94-143">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="50a94-144">En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione la**Directiva** > de **Administración** > de amenazas datos adjuntos**seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="50a94-144">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="50a94-145">Seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="50a94-145">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="50a94-146">En la sección **proteger archivos adjuntos de correo electrónico** , haga**+** clic en el signo más ().</span><span class="sxs-lookup"><span data-stu-id="50a94-146">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="50a94-147">Especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="50a94-147">Specify the following settings:</span></span>

    - <span data-ttu-id="50a94-148">En el cuadro **nombre** , escriba `Block malware`.</span><span class="sxs-lookup"><span data-stu-id="50a94-148">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="50a94-149">En la sección respuesta, elija **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="50a94-149">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="50a94-150">En la sección **redirigir datos** adjuntos, seleccione la opción **Habilitar**redireccionamiento y, a continuación, especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización que va a revisar los archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="50a94-150">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="50a94-151">En la sección **aplicado a** , elija **el dominio del destinatario es**.</span><span class="sxs-lookup"><span data-stu-id="50a94-151">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="50a94-152">A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="50a94-152">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="50a94-153">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="50a94-153">Click **Save**.</span></span>

6. <span data-ttu-id="50a94-154">(**Paso adicional recomendado**) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true* para su entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="50a94-154">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="50a94-155">(Esto impide que los usuarios abran, muevan, copien o compartan archivos que se detectan como malintencionados.)</span><span class="sxs-lookup"><span data-stu-id="50a94-155">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="50a94-156">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="50a94-156">To learn more, see:</span></span> 
- [<span data-ttu-id="50a94-157">Configurar las directivas de datos adJuntos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="50a94-157">Set up Office 365 ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md)
- [<span data-ttu-id="50a94-158">Activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50a94-158">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a><span data-ttu-id="50a94-159">Directivas de vínculos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="50a94-159">ATP Safe Links policies</span></span>

<span data-ttu-id="50a94-160">Para configurar [vínculos seguros ATP](atp-safe-links.md), revise y edite su directiva predeterminada y agregue una directiva para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="50a94-160">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="50a94-161">En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**vínculos seguros ATP**de la**Directiva** > de **Administración** > de amenazas.</span><span class="sxs-lookup"><span data-stu-id="50a94-161">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="50a94-162">Haga doble clic en la directiva **predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="50a94-162">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="50a94-163">En la sección **usar vínculos seguros en** , seleccione la opción **Office 365 ProPlus, Office para iOS y Android**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="50a94-163">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="50a94-164">En la sección **directivas que se aplican a destinatarios específicos** , haga clic en**+** el signo más ().</span><span class="sxs-lookup"><span data-stu-id="50a94-164">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="50a94-165">Especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="50a94-165">Specify the following settings:</span></span>

    - <span data-ttu-id="50a94-166">En el cuadro **nombre** , escriba un nombre, como `Safe Links`.</span><span class="sxs-lookup"><span data-stu-id="50a94-166">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="50a94-167">En la sección **seleccionar la acción** , elija **activado**.</span><span class="sxs-lookup"><span data-stu-id="50a94-167">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="50a94-168">Seleccione estas opciones:</span><span class="sxs-lookup"><span data-stu-id="50a94-168">Select these options:</span></span>

        - <span data-ttu-id="50a94-169">**Usar datos adjuntos seguros para analizar contenido descargable**</span><span class="sxs-lookup"><span data-stu-id="50a94-169">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="50a94-170">**Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**</span><span class="sxs-lookup"><span data-stu-id="50a94-170">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="50a94-171">**No permitir que los usuarios hagan clic en los vínculos seguros a la dirección URL original**</span><span class="sxs-lookup"><span data-stu-id="50a94-171">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="50a94-172">En la sección **aplicado a** , elija **el dominio del destinatario es**.</span><span class="sxs-lookup"><span data-stu-id="50a94-172">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="50a94-173">A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="50a94-173">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="50a94-174">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="50a94-174">Click **Save**.</span></span>

<span data-ttu-id="50a94-175">Para obtener más información, consulte [configurar las directivas de vínculos seguros de Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-175">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="50a94-176">Parte 3: contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="50a94-176">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="50a94-177">[La protección contra suplantación de identidad (phishing)](anti-phishing-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="50a94-177">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="50a94-178">La protección contra suplantación de identidad avanzada está disponible en [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="50a94-178">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="50a94-179">El siguiente procedimiento describe cómo configurar una directiva contra la suplantación de identidad ATP.</span><span class="sxs-lookup"><span data-stu-id="50a94-179">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="50a94-180">Los pasos son similares a la configuración de una directiva contra la suplantación de identidad (sin ATP).</span><span class="sxs-lookup"><span data-stu-id="50a94-180">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="50a94-181">En el [centro de seguridad & cumplimiento](https://protection.office.com), elija la**Directiva** > de **Administración** > de amenazas**ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="50a94-181">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="50a94-182">Haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="50a94-182">Click **Default policy**.</span></span>

3. <span data-ttu-id="50a94-183">En la \*\*\*\* sección suplantación, haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="50a94-183">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    -  <span data-ttu-id="50a94-184">En la pestaña **Agregar usuarios a proteger** , desactive la protección.</span><span class="sxs-lookup"><span data-stu-id="50a94-184">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="50a94-185">A continuación, agregue usuarios, como los miembros del Consejo de su organización, su CEO, director financiero y otros líderes senior.</span><span class="sxs-lookup"><span data-stu-id="50a94-185">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="50a94-186">(Puede escribir una dirección de correo electrónico individual o hacer clic en para mostrar una lista).</span><span class="sxs-lookup"><span data-stu-id="50a94-186">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="50a94-187">En la pestaña **Agregar dominios para proteger** , Active **incluir automáticamente los dominios que posea**.</span><span class="sxs-lookup"><span data-stu-id="50a94-187">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="50a94-188">Si tiene dominios personalizados, agréguelos también.</span><span class="sxs-lookup"><span data-stu-id="50a94-188">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="50a94-189">En la ficha **acciones** , seleccione **mover mensaje a las carpetas de correo no deseado de los destinatarios para el** usuario suplantado y para el dominio suplantado, y active las sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="50a94-189">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="50a94-190">En la pestaña inteligencia de buzones de **correo** , asegúrese de que la inteligencia de buzones está activada.</span><span class="sxs-lookup"><span data-stu-id="50a94-190">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="50a94-191">En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="50a94-191">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="50a94-192">En la \*\*\*\* sección suplantación, haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="50a94-192">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="50a94-193">En la pestaña **configuración de filtro** de suplantaCión de identidad, asegúrese de que está activada la protección contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="50a94-193">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="50a94-194">En la ficha **acciones** , elija Mover mensaje a las carpetas de correo no deseado de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="50a94-194">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="50a94-195">En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="50a94-195">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="50a94-196">(Si no realizó ningún cambio, haga clic en **Cancelar**).</span><span class="sxs-lookup"><span data-stu-id="50a94-196">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="50a94-197">Cierre la página Configuración de directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="50a94-197">Close the default policy settings page.</span></span>

<span data-ttu-id="50a94-198">Para obtener más información sobre las opciones de la Directiva antiphishing, consulte [set up anti-phishing Policies](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-198">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="50a94-199">Parte 4: contra el correo no deseado</span><span class="sxs-lookup"><span data-stu-id="50a94-199">Part 4 - Anti-spam</span></span>

<span data-ttu-id="50a94-200">[La protección contra correo no deseado](anti-spam-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="50a94-200">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="50a94-201">En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**anti-spam**de la**Directiva** > de **Administración** > de amenazas.</span><span class="sxs-lookup"><span data-stu-id="50a94-201">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="50a94-202">En la ficha **personalizado** , active la **Configuración personalizada** .</span><span class="sxs-lookup"><span data-stu-id="50a94-202">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="50a94-203">ExPanda **directiva predeterminada de filtro de correo no deseado**, haga clic en **Editar Directiva**y especifique la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="50a94-203">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="50a94-204">En la sección **correo electrónico no deseado y acciones en masa** , establezca el umbral en un valor de 5 o 6.</span><span class="sxs-lookup"><span data-stu-id="50a94-204">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="50a94-205">En la sección **listas** de permitidos, revise (y, si es necesario, Edit) los remitentes y dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="50a94-205">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="50a94-206">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="50a94-206">Click **Save**.</span></span>

<span data-ttu-id="50a94-207">Para obtener más información sobre las opciones de la Directiva contra correo no deseado, consulte [configurar las directivas contra correo no deseado](configure-the-anti-spam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-207">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="50a94-208">Parte 5: configuración de todo el servicio</span><span class="sxs-lookup"><span data-stu-id="50a94-208">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="50a94-209">Purga automática de cero horas</span><span class="sxs-lookup"><span data-stu-id="50a94-209">Zero-hour auto purge</span></span>

<span data-ttu-id="50a94-210">[Purga automática de cero horas](zero-hour-auto-purge.md) (ZAP) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="50a94-210">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="50a94-211">Esta protección está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones para que la protección esté en vigor:</span><span class="sxs-lookup"><span data-stu-id="50a94-211">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="50a94-212">Las acciones de correo no deseado se establecen para **mover el mensaje a la carpeta correo no deseado** en [las directivas contra correo no deseado](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-212">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="50a94-213">Los usuarios han mantenido su [configuración](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="50a94-213">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="50a94-214">Para obtener más información, consulte depuración [automática de cero horas-protección contra correo no deseado y malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-214">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="50a94-215">Registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="50a94-215">Audit logging</span></span>

<span data-ttu-id="50a94-216">El registro de auditoría está disponible en las suscripciones que incluyen [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="50a94-216">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="50a94-217">Para poder ver los datos de los informes de protección contra amenazas, como el [Panel de seguridad](security-dashboard.md), los informes de [seguridad de correo electrónico](view-email-security-reports.md)y el [Explorador](use-explorer-in-security-and-compliance.md), el registro de auditoría debe estar activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="50a94-217">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="50a94-218">Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="50a94-218">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="50a94-219">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="50a94-219">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="50a94-220">Vea las nuevas características y actualizaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="50a94-220">Watch for new features and service updates</span></span>

- [<span data-ttu-id="50a94-221">Configurar las opciones estándar o de lanzamiento de destino</span><span class="sxs-lookup"><span data-stu-id="50a94-221">Set up the Standard or Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)

- [<span data-ttu-id="50a94-222">Ir a su centro de mensajes para ver anuncios de características</span><span class="sxs-lookup"><span data-stu-id="50a94-222">Go to your Message center to view feature announcements</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) 

- [<span data-ttu-id="50a94-223">Visite el plan de desarrollo de Microsoft 365 para ver el estado de las nuevas características</span><span class="sxs-lookup"><span data-stu-id="50a94-223">Visit the Microsoft 365 Roadmap to see status of new features</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="50a94-224">Revisión de las deScripciones del servicio de Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-224">Review the Office 365 Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)

### <a name="see-how-threat-protection-features-are-working-for-your-organization"></a><span data-ttu-id="50a94-225">Vea cómo funcionan las características de protección contra amenazas en su organización</span><span class="sxs-lookup"><span data-stu-id="50a94-225">See how threat protection features are working for your organization</span></span>

- [<span data-ttu-id="50a94-226">Visitar el panel de seguridad</span><span class="sxs-lookup"><span data-stu-id="50a94-226">Visit your security dashboard</span></span>](security-dashboard.md)

- <span data-ttu-id="50a94-227">[Ver los informes de Office 365 ATP](view-reports-for-atp.md), incluido el [Explorador](use-explorer-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="50a94-227">[View the reports for Office 365 ATP](view-reports-for-atp.md), including [Explorer](use-explorer-in-security-and-compliance.md)</span></span>

- [<span data-ttu-id="50a94-228">Ver los informes de seguridad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="50a94-228">View your email security reports</span></span>](view-email-security-reports.md)

### <a name="periodically-review-and-revise-your-threat-protection-policies"></a><span data-ttu-id="50a94-229">Revisar y revisar periódicamente las directivas de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="50a94-229">Periodically review and revise your threat protection policies</span></span>

- [<span data-ttu-id="50a94-230">Revisar la puntuación segura</span><span class="sxs-lookup"><span data-stu-id="50a94-230">Review your Secure Score</span></span>](microsoft-secure-score.md)

- [<span data-ttu-id="50a94-231">Usar los informes y la información inteligentes en el centro de &amp; seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="50a94-231">Use your smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 

- [<span data-ttu-id="50a94-232">Mantener a los usuarios seguros con las características de respuesta y investigación de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="50a94-232">Keep users safe with Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md) 
 
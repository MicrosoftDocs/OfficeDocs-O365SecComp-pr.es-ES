---
title: Activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo activar ATP para SharePoint, OneDrive y Teams, incluido cómo establecer alertas para los archivos detectados.
ms.openlocfilehash: f3be5b3cf73a04de10185428b84b5862906c3db7
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652673"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c49e4-103">Activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c49e4-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c49e4-104">Este artículo está destinado a los clientes empresariales que tienen la [protección contra amenazas avanzada de Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c49e4-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="c49e4-105">Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="c49e4-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c49e4-106">[Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) protege a su organización de archivos malintencionados que se comparten de forma inadvertida.</span><span class="sxs-lookup"><span data-stu-id="c49e4-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="c49e4-107">Cuando se detecta un archivo malintencionado, se bloquea el archivo para que nadie lo pueda abrir, copiar, mover ni compartir hasta que el equipo de seguridad de la organización haya realizado otras acciones.</span><span class="sxs-lookup"><span data-stu-id="c49e4-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="c49e4-108">Lea este artículo para activar ATP para SharePoint, OneDrive y Microsoft Teams, configurar alertas para que se notifiquen sobre los archivos detectados y realizar los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c49e4-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="c49e4-109">Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado.</span><span class="sxs-lookup"><span data-stu-id="c49e4-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="c49e4-110">En la tabla siguiente se describen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c49e4-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="c49e4-111">Role</span><span class="sxs-lookup"><span data-stu-id="c49e4-111">Role</span></span>  |<span data-ttu-id="c49e4-112">Dónde y cómo se asigna</span><span class="sxs-lookup"><span data-stu-id="c49e4-112">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="c49e4-113">Administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="c49e4-113">Office 365 Global Administrator</span></span> |<span data-ttu-id="c49e4-114">La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c49e4-114">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="c49e4-115">(Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="c49e4-115">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="c49e4-116">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="c49e4-116">Security Administrator</span></span> |<span data-ttu-id="c49e4-117">Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()</span><span class="sxs-lookup"><span data-stu-id="c49e4-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="c49e4-118">Administración de la organización de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c49e4-118">Exchange Online Organization Management</span></span> |<span data-ttu-id="c49e4-119">Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange ()</span><span class="sxs-lookup"><span data-stu-id="c49e4-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="c49e4-120">o</span><span class="sxs-lookup"><span data-stu-id="c49e4-120">or</span></span> <br>  <span data-ttu-id="c49e4-121">Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="c49e4-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c49e4-122">Activar ATP para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c49e4-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="c49e4-123">**Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya esté activado para su entorno de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="c49e4-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="c49e4-124">Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c49e4-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="c49e4-125">Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="c49e4-125">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="c49e4-126">Vaya a [https://protection.office.com](https://protection.office.com)e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c49e4-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="c49e4-127">En el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **Administración de amenazas**, seleccione **Directiva** \> de datos adjuntos **seguros**.</span><span class="sxs-lookup"><span data-stu-id="c49e4-127">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="c49e4-128">![En el centro &amp; de seguridad y cumplimiento, elija \> Directiva de administración de amenazas](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="c49e4-128">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="c49e4-129">Seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c49e4-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="c49e4-130">![Activar la protección contra amenazas avanzada para SharePoint Online, OneDrive para la empresa y Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="c49e4-130">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="c49e4-131">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="c49e4-131">Click **Save**.</span></span>
    
5. <span data-ttu-id="c49e4-132">Revise (y, según corresponda, Edit) las directivas de [datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) de su organización y [las directivas de vínculos a prueba](set-up-atp-safe-links-policies.md)de errores.</span><span class="sxs-lookup"><span data-stu-id="c49e4-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="c49e4-133">Recomenda Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true*.</span><span class="sxs-lookup"><span data-stu-id="c49e4-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="c49e4-134">Si se establece el parámetro en *true* , se bloquearán todas las acciones (excepto eliminar) de los archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="c49e4-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="c49e4-135">Los usuarios no pueden abrir, mover, copiar o compartir los archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="c49e4-135">People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="c49e4-136">Si el parámetro se establece en *false* , se bloquearán todas las acciones excepto eliminar y descargar.</span><span class="sxs-lookup"><span data-stu-id="c49e4-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="c49e4-137">Los usuarios pueden elegir entre aceptar el riesgo y descargar un archivo detectado.</span><span class="sxs-lookup"><span data-stu-id="c49e4-137">People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="c49e4-138">Espere hasta 30 minutos para que los cambios se extiendan a todos los centros de seguridad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c49e4-138">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="c49e4-139">Recomenda Proceda a configurar alertas para los archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="c49e4-139">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="c49e4-140">Para obtener más información sobre el uso de PowerShell con Office 365, consulte [administrar office 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c49e4-140">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="c49e4-141">Para obtener más información acerca de la experiencia del usuario cuando un archivo se ha detectado como malintencionado, consulte [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, en OneDrive o en Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="c49e4-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="c49e4-142">Configurar alertas para los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="c49e4-142">Set up alerts for detected files</span></span>

<span data-ttu-id="c49e4-143">Para recibir una notificación cuando se identificó un archivo en SharePoint Online, OneDrive para la empresa o Microsoft Teams como malintencionado, puede configurar una alerta.</span><span class="sxs-lookup"><span data-stu-id="c49e4-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="c49e4-144">En el [centro de seguridad &amp; y cumplimiento de Office 365](https://protection.office.com), elija **alertas** \> **Administrar alertas**.</span><span class="sxs-lookup"><span data-stu-id="c49e4-144">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="c49e4-145">Elija **nueva Directiva de alerta**.</span><span class="sxs-lookup"><span data-stu-id="c49e4-145">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="c49e4-146">Especifique un nombre para la alerta.</span><span class="sxs-lookup"><span data-stu-id="c49e4-146">Specify a name for the alert.</span></span> <span data-ttu-id="c49e4-147">Por ejemplo, podría escribir archivos malintencionados en bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="c49e4-147">For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="c49e4-148">Escriba una descripción de la alerta.</span><span class="sxs-lookup"><span data-stu-id="c49e4-148">Type a description for the alert.</span></span> <span data-ttu-id="c49e4-149">Por ejemplo, puede escribir notificar a los administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c49e4-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="c49e4-150">En la sección **enviar esta alerta cuando...** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c49e4-150">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="c49e4-151">a.</span><span class="sxs-lookup"><span data-stu-id="c49e4-151">a.</span></span> <span data-ttu-id="c49e4-152">En la lista **actividades** , seleccione **malware detectado en el archivo**.</span><span class="sxs-lookup"><span data-stu-id="c49e4-152">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="c49e4-153">b.</span><span class="sxs-lookup"><span data-stu-id="c49e4-153">b.</span></span> <span data-ttu-id="c49e4-154">Deje el campo **usuarios** vacío.</span><span class="sxs-lookup"><span data-stu-id="c49e4-154">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="c49e4-155">En la sección **enviar esta alerta a...** , seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecte un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="c49e4-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="c49e4-156">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="c49e4-156">Click **Save**.</span></span>
    
<span data-ttu-id="c49e4-157">Para obtener más información acerca de las alertas, consulte [crear alertas de actividad en &amp; el centro de seguridad y cumplimiento de Office 365](create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c49e4-157">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="c49e4-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c49e4-158">Next steps</span></span>

1. [<span data-ttu-id="c49e4-159">Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c49e4-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="c49e4-160">Administrar archivos y mensajes en cuarentena como un administrador en Office 365</span><span class="sxs-lookup"><span data-stu-id="c49e4-160">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  


---
title: Activar Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo activar ATP para SharePoint, OneDrive y equipos, incluido cómo establecer alertas para los archivos detectados.
ms.openlocfilehash: 8c63110baf391fd727e296f34361047b4b67b0cb
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995341"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c5f7e-103">Activar Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5f7e-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="c5f7e-p101">[Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) protege su organización de forma inadvertida uso compartido de archivos malintencionados. Cuando se detecta un archivo malintencionado, ese archivo se bloquea para que nadie puede abrir, copiar, mover o compártalo hasta que se toman más acciones por el equipo de seguridad de la organización. Lea este artículo para activar ATP para SharePoint, OneDrive y los equipos, configuración alertas para recibir una notificación acerca de los archivos detectados y lleve a cabo los pasos siguiente.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="c5f7e-107">Para definir las directivas de ATP (o editar), debe asignar uno de los roles que se describen en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="c5f7e-107">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="c5f7e-108">Rol</span><span class="sxs-lookup"><span data-stu-id="c5f7e-108">Role</span></span>  |<span data-ttu-id="c5f7e-109">Dónde y cómo asignado</span><span class="sxs-lookup"><span data-stu-id="c5f7e-109">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="c5f7e-110">Administrador Global de Office 365</span><span class="sxs-lookup"><span data-stu-id="c5f7e-110">Office 365 Global Administrator</span></span> |<span data-ttu-id="c5f7e-p102">La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p102">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="c5f7e-113">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="c5f7e-113">Security Administrator</span></span> |<span data-ttu-id="c5f7e-114">Centro de administración de Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="c5f7e-114">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="c5f7e-115">Administración de la organización en línea de Exchange</span><span class="sxs-lookup"><span data-stu-id="c5f7e-115">Exchange Online Organization Management</span></span> |<span data-ttu-id="c5f7e-116">Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="c5f7e-116">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="c5f7e-117">o</span><span class="sxs-lookup"><span data-stu-id="c5f7e-117">or</span></span> <br>  <span data-ttu-id="c5f7e-118">Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="c5f7e-118">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="c5f7e-119">Activar ATP para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-119">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="c5f7e-p103">**Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya está activado para el entorno de Office 365**. Normalmente, esto se realiza por una persona que tenga el rol de los registros de auditoría asignado en Exchange Online. Para obtener más información, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p103">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="c5f7e-123">Vaya a [https://protection.office.com](https://protection.office.com)y el inicio de sesión con la cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-123">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="c5f7e-124">En la seguridad de Office 365 &amp; centro de cumplimiento, en el panel de navegación izquierdo, en **administración de amenaza**, elija **Directiva** \> **Los datos adjuntos seguros**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-124">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="c5f7e-125">![En la seguridad &amp; centro de cumplimiento, elija Administración de amenaza \> directiva](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="c5f7e-125">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="c5f7e-126">Seleccione **Activar ATP para SharePoint, OneDrive y los equipos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-126">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="c5f7e-127">![Activar protección contra amenazas avanzadas para SharePoint Online, OneDrive para la empresa y los equipos de Microsoft](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="c5f7e-127">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="c5f7e-128">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-128">Click **Save**.</span></span>
    
5. <span data-ttu-id="c5f7e-129">Revise (y, según corresponda, edite) [las directivas de los datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) y [las directivas de vínculos seguros](set-up-atp-safe-links-policies.md)de su organización.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-129">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="c5f7e-130">(Recomendado) Como un administrador global o un administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true*.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-130">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="c5f7e-p104">Establecer el parámetro a *true* bloques todas las acciones (excepto eliminar) de los archivos detectados. Personas no se pueden abrir, mover, copiar o compartir archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p104">Setting the parameter to *true* blocks all actions (except Delete) for detected files. People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="c5f7e-p105">Si el parámetro se establece en *false* , bloquea todas las acciones excepto eliminar y la descarga. Personas pueden optar por aceptar el riesgo y descargar un archivo detectado.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p105">Setting the parameter to *false* blocks all actions except Delete and Download. People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="c5f7e-135">Permitir hasta 30 minutos para que los cambios propagar a todos los centros de datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-135">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="c5f7e-136">(Recomendado) Continúe con para configurar alertas para los archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-136">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="c5f7e-137">Para obtener más información acerca del uso de PowerShell con Office 365, vea [administrar Office 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5f7e-137">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="c5f7e-138">Para obtener más información acerca de la experiencia del usuario cuando se detecta un archivo como malintencionado, vea [qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o los equipos de Microsoft](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="c5f7e-138">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="c5f7e-139">Configurar alertas para archivos detectados</span><span class="sxs-lookup"><span data-stu-id="c5f7e-139">Set up alerts for detected files</span></span>

<span data-ttu-id="c5f7e-140">Para recibir una notificación cuando un archivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams se ha identificado como malintencionado, puede configurar una alerta.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-140">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="c5f7e-141">En la [Office 365 seguridad &amp; centro de cumplimiento](https://protection.office.com), elija **alertas** \> **Administrar alertas**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-141">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="c5f7e-142">Elija **nueva directiva de alerta**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-142">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="c5f7e-p106">Especifique un nombre para la alerta. Por ejemplo, puede escribir archivos malintencionados en bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p106">Specify a name for the alert. For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="c5f7e-p107">Escriba una descripción de la alerta. Por ejemplo, podría escribir notifica a administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p107">Type a description for the alert. For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="c5f7e-147">En la sección **Enviar esta alerta cuando...** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5f7e-147">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="c5f7e-p108">r. en la lista de **actividades** , elija **detectado malware en un archivo**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p108">a. In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="c5f7e-p109">b. deje en blanco el campo de **los usuarios** .</span><span class="sxs-lookup"><span data-stu-id="c5f7e-p109">b. Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="c5f7e-152">En la sección **Enviar esta alerta a...** , seleccione uno o varios de los administradores globales, los administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecta un archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-152">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="c5f7e-153">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c5f7e-153">Click **Save**.</span></span>
    
<span data-ttu-id="c5f7e-154">Para obtener más información acerca de las alertas, vea [crear alertas de actividad en la seguridad de Office 365 &amp; centro de cumplimiento](create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="c5f7e-154">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="c5f7e-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c5f7e-155">Next steps</span></span>

1. [<span data-ttu-id="c5f7e-156">Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5f7e-156">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="c5f7e-157">Administrar mensajes en cuarentena y los archivos como un administrador en Office 365</span><span class="sxs-lookup"><span data-stu-id="c5f7e-157">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  


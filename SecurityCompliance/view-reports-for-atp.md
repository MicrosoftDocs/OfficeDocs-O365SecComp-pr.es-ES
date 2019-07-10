---
title: Ver informes para la protección contra amenazas avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de la protección contra amenazas avanzada de Office &amp; 365 en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 418a836004995606fbeb492bf98b89e4474ab90c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598486"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="bbb92-103">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="bbb92-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="bbb92-104">Si la organización dispone de la [protección contra amenazas avanzada](office-365-atp.md) (ATP) de Office 365 y dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-the-atp-reports), puede usar varios informes de &amp; ATP en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="bbb92-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="bbb92-105">(Vaya a \*\*\*\* \> **Panel**de informes).</span><span class="sxs-lookup"><span data-stu-id="bbb92-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![El panel &amp; del centro de seguridad y cumplimiento puede ayudarle a ver dónde está funcionando la protección contra amenazas avanzada](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="bbb92-107">Los informes de ATP incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbb92-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="bbb92-108">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="bbb92-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="bbb92-109">Informe de tipos de archivo de ATP</span><span class="sxs-lookup"><span data-stu-id="bbb92-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="bbb92-110">Informe de disposición de mensajes ATP</span><span class="sxs-lookup"><span data-stu-id="bbb92-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="bbb92-111">[detección en tiempo real o explorador](threat-explorer.md) (en función de si tiene Office 365 ATP plan 1 o 2)</span><span class="sxs-lookup"><span data-stu-id="bbb92-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="bbb92-112">... [etc](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="bbb92-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="bbb92-113">Lea este artículo para obtener información general sobre los informes de ATP y cómo usarlos.</span><span class="sxs-lookup"><span data-stu-id="bbb92-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="bbb92-114">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="bbb92-114">Threat Protection Status report</span></span>

<span data-ttu-id="bbb92-115">El informe de **Estado de protección contra amenazas** es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) y [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="bbb92-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="bbb92-116">Este informe es útil para ver las detecciones a lo largo del tiempo (hasta 90 días) y permite a los administradores de seguridad identificar las tendencias o determinar si las directivas necesitan ajustes.</span><span class="sxs-lookup"><span data-stu-id="bbb92-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="bbb92-117">El informe de estado de protección contra amenazas proporciona un recuento agregado de mensajes de correo electrónico únicos con contenido malintencionado, como archivos o direcciones de sitios web (URL) bloqueados por el motor antimalware, la depuración [automática de cero horas (ZAP)](zero-hour-auto-purge.md)y las características de ATP como [Vínculos seguros ATP](atp-safe-links.md), [datos adjuntos seguros ATP](atp-safe-attachments.md)y [funcionalidades antiphishing de ATP](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="bbb92-117">The Threat Protection Status report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="bbb92-118">Un informe de estado de protección contra amenazas está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); sin embargo, la información que se muestra en el informe de estado de la protección contra amenazas para los clientes de ATP probablemente contendrá distintos datos de los que pueden ver los clientes de EOP.</span><span class="sxs-lookup"><span data-stu-id="bbb92-118">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="bbb92-119">Por ejemplo, el informe de estado de protección contra amenazas para los clientes de ATP contendrá información sobre [los archivos malintencionados detectados en SharePoint Online, OneDrive o Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bbb92-119">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="bbb92-120">Esta información es específica de ATP, por lo que los clientes que tengan EOP pero no ATP no verán los detalles en el informe de estado de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="bbb92-120">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="bbb92-121">Para ver el informe de estado de protección contra amenazas, en el [centro de seguridad &amp; y cumplimiento](https://protection.office.com), vaya al **Panel** \> **informes** \> **Estado de protección contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="bbb92-121">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Informe de estado de protección contra amenazas ATP](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="bbb92-123">Para obtener el estado detallado de un día, desplace el puntero sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="bbb92-123">To get detailed status for a day, hover over the graph.</span></span>
  
![Datos de estado de protección contra amenazas ATP para un día](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="bbb92-125">De forma predeterminada, el informe de estado de protección contra amenazas muestra datos de los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="bbb92-125">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="bbb92-126">Sin embargo, puede elegir **filtros** y cambiar el intervalo de fechas para ver los datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="bbb92-126">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="bbb92-127">(Si usa una suscripción de prueba, es posible que se limite a 30 días de datos).</span><span class="sxs-lookup"><span data-stu-id="bbb92-127">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Filtros de estado de protección contra amenazas ATP](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="bbb92-129">También puede usar el menú **ver datos por** para cambiar la información que se muestra en el informe.</span><span class="sxs-lookup"><span data-stu-id="bbb92-129">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Visualización de opciones del informe de estado de protección contra amenazas ATP](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="bbb92-131">Informe de tipos de archivo de ATP</span><span class="sxs-lookup"><span data-stu-id="bbb92-131">ATP File Types report</span></span>

<span data-ttu-id="bbb92-132">El informe de **tipos de archivo de ATP** muestra el tipo de archivos que los [datos adjuntos seguros de ATP](atp-safe-attachments.md)han detectado como malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bbb92-132">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="bbb92-133">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a los **tipos de archivo ATP**del **Panel** \> **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="bbb92-133">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Informe de tipos de archivo de ATP](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="bbb92-135">Al pasar el mouse sobre un día concreto, puede ver el desglose de los tipos de archivos malintencionados que ha detectado [ATP Safe Attachments](atp-safe-attachments.md) and [anti- &amp; spam Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bbb92-135">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Datos del informe de tipos de archivos ATP para un día](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="bbb92-137">Informe de disposición de mensajes ATP</span><span class="sxs-lookup"><span data-stu-id="bbb92-137">ATP Message Disposition report</span></span>

<span data-ttu-id="bbb92-138">El informe de **disposición de mensajes de ATP** muestra las acciones que se tomaron para los mensajes de correo electrónico que se detectaron con contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bbb92-138">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="bbb92-139">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a la **disposición de mensajes ATP**del **Panel** \> **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="bbb92-139">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Informe de disposición de mensajes ATP](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="bbb92-141">Cuando desplaza el puntero sobre una barra del gráfico, puede ver qué acciones se tomaron para el correo electrónico detectado durante ese día.</span><span class="sxs-lookup"><span data-stu-id="bbb92-141">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Datos del informe de disposición de mensajes ATP para un día](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="bbb92-143">Informes adicionales para ver</span><span class="sxs-lookup"><span data-stu-id="bbb92-143">Additional reports to view</span></span>

<span data-ttu-id="bbb92-144">Además de los informes de ATP descritos en este artículo, hay disponibles varios otros informes, como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbb92-144">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="bbb92-145">Informe (s)</span><span class="sxs-lookup"><span data-stu-id="bbb92-145">Report(s)</span></span>  |<span data-ttu-id="bbb92-146">Detalles</span><span class="sxs-lookup"><span data-stu-id="bbb92-146">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="bbb92-147">**Explorador** o **detecciones en tiempo real** (Office 365 ATP plan 2 los clientes tienen explorador; Office 365 ATP plan 1 los clientes tienen detecciones en tiempo real.)</span><span class="sxs-lookup"><span data-stu-id="bbb92-147">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="bbb92-148">Explorador de amenazas (y detecciones en tiempo real)</span><span class="sxs-lookup"><span data-stu-id="bbb92-148">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="bbb92-149">**Informes de seguridad de correo electrónico**, como un informe de remitentes y destinatarios principales, un informe de correo falsificado y un informe de detecciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbb92-149">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="bbb92-150">Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbb92-150">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="bbb92-151">**Seguimiento de dirección URL de vínculos seguros ATP** (Este es un informe que se genera con PowerShell). Este informe muestra los resultados de las acciones de vínculos seguros de ATP en los últimos siete (7) días.</span><span class="sxs-lookup"><span data-stu-id="bbb92-151">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="bbb92-152">Referencia del cmdlet Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="bbb92-152">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|<span data-ttu-id="bbb92-153">**Resultados de EOP y ATP** (Este es un informe personalizado que se genera mediante PowerShell).</span><span class="sxs-lookup"><span data-stu-id="bbb92-153">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="bbb92-154">Este informe contiene información como, por ejemplo, el dominio, la fecha, el tipo de evento, la dirección, la acción y el recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="bbb92-154">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="bbb92-155">Referencia del cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="bbb92-155">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="bbb92-156">**Detecciones de EOP y ATP** (Este es un informe personalizado que se genera mediante PowerShell).</span><span class="sxs-lookup"><span data-stu-id="bbb92-156">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="bbb92-157">Este informe contiene detalles sobre archivos malintencionados o direcciones URL, intentos de suplantación de identidad, suplantación y otras amenazas potenciales en los correos electrónicos o archivos.</span><span class="sxs-lookup"><span data-stu-id="bbb92-157">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="bbb92-158">Referencia del cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="bbb92-158">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="bbb92-159">¿Qué permisos se necesitan para ver los informes de ATP?</span><span class="sxs-lookup"><span data-stu-id="bbb92-159">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="bbb92-160">Para poder ver y usar los informes descritos en este artículo, **debe tener asignada una función adecuada para el centro de &amp; seguridad y cumplimiento y el centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="bbb92-160">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="bbb92-161">Para el centro &amp; de seguridad y cumplimiento, debe tener asignada una de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="bbb92-161">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="bbb92-162">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="bbb92-162">Organization Management</span></span>
    - <span data-ttu-id="bbb92-163">Administrador de seguridad (puede asignarse en el centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ())</span><span class="sxs-lookup"><span data-stu-id="bbb92-163">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="bbb92-164">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbb92-164">Security Reader</span></span>

- <span data-ttu-id="bbb92-165">Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="bbb92-165">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="bbb92-166">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="bbb92-166">Organization Management</span></span>
    - <span data-ttu-id="bbb92-167">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="bbb92-167">View-only Organization Management</span></span>
    - <span data-ttu-id="bbb92-168">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="bbb92-168">View-Only Recipients role</span></span>
    - <span data-ttu-id="bbb92-169">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbb92-169">Compliance Management</span></span>

<span data-ttu-id="bbb92-170">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="bbb92-170">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="bbb92-171">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bbb92-171">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="bbb92-172">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bbb92-172">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="bbb92-173">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="bbb92-173">What if the reports aren't showing data?</span></span>

<span data-ttu-id="bbb92-174">Si no ve datos en los informes de ATP, compruebe que las directivas estén correctamente configuradas.</span><span class="sxs-lookup"><span data-stu-id="bbb92-174">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="bbb92-175">La organización debe tener directivas de [vínculos seguros ATP](set-up-atp-safe-links-policies.md) y [directivas de datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md) definidas para que la protección de ATP esté en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bbb92-175">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="bbb92-176">Consulte también [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bbb92-176">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bbb92-177">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bbb92-177">Related topics</span></span>

[<span data-ttu-id="bbb92-178">Informes y opiniones en el centro de seguridad &amp; y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="bbb92-178">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="bbb92-179">Crear una programación para un informe en el centro &amp; de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbb92-179">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="bbb92-180">Configurar y descargar un informe personalizado en el centro de &amp; seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bbb92-180">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  


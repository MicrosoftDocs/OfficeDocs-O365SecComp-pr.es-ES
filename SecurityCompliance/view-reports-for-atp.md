---
title: Visualización de informes para la protección de amenaza avanzada de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: Obtenga información sobre cómo buscar y usar informes para Office 365 avanzada protección contra amenazas en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 1a0ecb9a6722deb50a491a15f720481a5bb7b0a4
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552338"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="de080-103">Visualización de informes para la protección de amenaza avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="de080-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="de080-p101">Si su organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP) y si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede usar varios informes de ATP en la seguridad &amp; centro de cumplimiento. (Vaya a **informes** \> **panel**.)</span><span class="sxs-lookup"><span data-stu-id="de080-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="de080-p102">Informes de ATP incluyen el [informe de estado de protección de amenaza](#threat-protection-status-report), el [informe de tipos de archivo de ATP](#atp-file-types-report)y el [informe de eliminación de mensaje de ATP](#atp-message-disposition-report). En este artículo se describe los informes de ATP e incluye vínculos a [informes adicionales para ver](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="de080-p102">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="de080-109">Informe de estado de protección de amenaza</span><span class="sxs-lookup"><span data-stu-id="de080-109">Threat Protection Status report</span></span>

<span data-ttu-id="de080-p103">El informe de **Estado de protección de amenaza** es una vista única que reúne información sobre malintencionado correo electrónico malintencionado y contenido detectados y bloqueados por [ATP de Office 365](office-365-atp.md)y [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP). El informe proporciona un recuento agregado de mensajes de correo electrónico único con contenido malintencionado (archivos o direcciones de sitios Web (URL)) bloqueados por el motor de antimalware, [cero horas automático purgar (ZAP)](zero-hour-auto-purge.md)y las características de ATP, como [Vínculos seguros ATP](atp-safe-links.md), [ATP seguras Datos adjuntos](atp-safe-attachments.md)y [las funciones de ATP contra suplantación de identidad](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="de080-p103">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md). The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="de080-p104">Un informe de estado de protección de amenaza está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Sin embargo, la información que se muestra en el informe de estado de protección de amenaza para los clientes de ATP probablemente contendrá datos distintos a lo que es posible que vea los clientes de EOP. Por ejemplo, el informe de estado de protección de amenaza para los clientes de ATP contendrá información sobre [archivos malintencionados detectan en SharePoint Online, OneDrive o los equipos de Microsoft](atp-for-spo-odb-and-teams.md). Dicha información es específica de ATP, por lo que los clientes que tienen EOP pero no ATP no verán los detalles de su informe de estado de protección de amenaza.</span><span class="sxs-lookup"><span data-stu-id="de080-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md). Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="de080-115">Para ver el informe de estado de protección de amenaza, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **Estado de protección de amenaza**.</span><span class="sxs-lookup"><span data-stu-id="de080-115">To view the Threat Protection Status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Informe de estado de protección de amenaza ATP](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="de080-117">Para obtener el estado detallado de un día, mantenga el mouse sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="de080-117">To get detailed status for a day, hover over the graph.</span></span>
  
![Datos de estado de protección de amenaza de ATP para un día](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="de080-p105">De forma predeterminada, el informe de estado de protección de amenaza muestra datos para los últimos siete días. Sin embargo, puede elegir **filtros** y cambiar el intervalo de fechas para ver los datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="de080-p105">By default, the Threat Protection Status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![Filtros de estado de protección de amenaza ATP](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="de080-122">También puede usar el menú **Ver datos por** para cambiar la información que se muestra en el informe.</span><span class="sxs-lookup"><span data-stu-id="de080-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opciones de visualización para el informe de estado de protección de amenaza ATP](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="de080-124">Informe de tipos de archivo de ATP</span><span class="sxs-lookup"><span data-stu-id="de080-124">ATP File Types report</span></span>

<span data-ttu-id="de080-125">El informe de **Tipos de archivo de ATP** muestra el tipo de archivos detectados como malintencionado por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="de080-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="de080-126">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **ATP tipos de archivo**.</span><span class="sxs-lookup"><span data-stu-id="de080-126">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Informe de tipos de archivo de ATP](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="de080-128">Cuando mantenga el mouse sobre un día determinado, puede ver el desglose de los tipos de archivos malintencionados que se detectaron por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md) y [contra correo no deseado &amp; protección antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="de080-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Datos de informe de tipos de archivo de ATP para un día](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="de080-130">Informe de eliminación de mensaje ATP</span><span class="sxs-lookup"><span data-stu-id="de080-130">ATP Message Disposition report</span></span>

<span data-ttu-id="de080-131">El informe de **Eliminación de mensaje de ATP** muestra las acciones que se tomaron para mensajes de correo electrónico que se detectaron como tener contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="de080-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="de080-132">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **ATP mensaje disposición**.</span><span class="sxs-lookup"><span data-stu-id="de080-132">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Informe de eliminación de mensajes de ATP](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="de080-134">Cuando mantenga el mouse sobre una barra en el gráfico, puede ver las acciones realizadas para el correo electrónico detectado para ese día.</span><span class="sxs-lookup"><span data-stu-id="de080-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Datos de informe de eliminación de mensajes de ATP para un día](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="de080-136">Para ver los informes adicionales</span><span class="sxs-lookup"><span data-stu-id="de080-136">Additional reports to view</span></span>

<span data-ttu-id="de080-137">Además de los informes de ATP que se describe en este artículo, varios otros informes están disponibles, tal como se describe en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="de080-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>


|<span data-ttu-id="de080-138">Tipo de informe</span><span class="sxs-lookup"><span data-stu-id="de080-138">Report type</span></span>  |<span data-ttu-id="de080-139">Más información</span><span class="sxs-lookup"><span data-stu-id="de080-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="de080-140">**Informes de seguridad de correo electrónico**, como una parte superior remitentes y destinatarios informe, un informe de correo de suplantación de la y un informe de detecciones de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="de080-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="de080-141">Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-141">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="de080-142">**Explorador** (se conoce también como el Explorador de amenaza, esto se incluye en [Office 365 amenaza inteligencia](office-365-ti.md))</span><span class="sxs-lookup"><span data-stu-id="de080-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Threat Intelligence](office-365-ti.md))</span></span>     | [<span data-ttu-id="de080-143">Use el explorador en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="de080-p106">**Resultados de la elevación de privilegios y ATP** (Esto es un informe personalizado que generar mediante el uso de PowerShell). Este informe contiene información, como el dominio, fecha, tipo de evento, dirección, acción y recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="de080-p106">**EOP and ATP results** (This is a custom report you generate by using PowerShell). This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="de080-146">Referencia del cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="de080-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="de080-p107">**Detecciones de elevación de privilegios y ATP** (Esto es un informe personalizado que generar mediante el uso de PowerShell). Este informe contiene detalles sobre archivos malintencionados o las direcciones URL, los intentos de suplantación de identidad, suplantación y otras posibles amenazas de correo electrónico o de archivos.</span><span class="sxs-lookup"><span data-stu-id="de080-p107">**EOP and ATP detections** (This is a custom report you generate by using PowerShell). This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="de080-149">Referencia del cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="de080-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="de080-150">¿Qué permisos son necesarios para ver los informes de ATP?</span><span class="sxs-lookup"><span data-stu-id="de080-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="de080-151">Para poder ver y usar los informes que se describen en este artículo, debe tener una función adecuada asignada en la seguridad &amp; centro de cumplimiento y en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="de080-151">In order to view and use the reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="de080-152">**Grupo de funciones**</span><span class="sxs-lookup"><span data-stu-id="de080-152">**Role group**</span></span>|<span data-ttu-id="de080-153">**Punto de asignación**</span><span class="sxs-lookup"><span data-stu-id="de080-153">**Where assigned**</span></span>|<span data-ttu-id="de080-154">**Obtener más información**</span><span class="sxs-lookup"><span data-stu-id="de080-154">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="de080-155">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="de080-155">One of the following:</span></span>  <br/><br/><span data-ttu-id="de080-156">: Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="de080-156">--Organization Management</span></span>  <br/><span data-ttu-id="de080-157">: Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="de080-157">--Security Administrator</span></span>  <br/><span data-ttu-id="de080-158">--Seguridad lector</span><span class="sxs-lookup"><span data-stu-id="de080-158">--Security Reader</span></span>  <br/> |<span data-ttu-id="de080-159">Seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-159">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="de080-160">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-160">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="de080-161">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="de080-161">One of the following:</span></span>  <br/><br/><span data-ttu-id="de080-162">: Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="de080-162">--Organization Management</span></span>  <br/><span data-ttu-id="de080-163">--Administración de la organización sólo vista</span><span class="sxs-lookup"><span data-stu-id="de080-163">--View-only Organization Management</span></span>  <br/><span data-ttu-id="de080-164">--Rol de los destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="de080-164">--View-Only Recipients role</span></span>  <br/><span data-ttu-id="de080-165">--Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-165">--Compliance Management</span></span>  <br/> |<span data-ttu-id="de080-166">Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="de080-166">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="de080-167">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de080-167">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="de080-168">¿Qué ocurre si los informes no muestran los datos?</span><span class="sxs-lookup"><span data-stu-id="de080-168">What if the reports aren't showing data?</span></span>

<span data-ttu-id="de080-p108">Si no está viendo datos en los informes de ATP, vuelva a comprobar que sus directivas están configuradas correctamente. Su organización debe tener [las directivas de ATP seguros vínculos](set-up-atp-safe-links-policies.md) y [datos adjuntos seguros de ATP directivas](set-up-atp-safe-attachments-policies.md) definidas en orden para la protección de ATP para estar en su lugar. Vea también la [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="de080-p108">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="de080-172">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="de080-172">Related topics</span></span>

[<span data-ttu-id="de080-173">Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-173">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="de080-174">Crear una programación para un informe en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-174">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="de080-175">Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="de080-175">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  


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
ms.openlocfilehash: 13b2a4c142a223a8a912c9017b6033b0b5a1548b
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782117"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="bee1f-103">Visualización de informes para la protección de amenaza avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="bee1f-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="bee1f-p101">Si su organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP) y tiene los permisos necesarios, puede usar varios informes de ATP en la seguridad &amp; centro de cumplimiento. (Vaya a **informes** \> **panel**.)</span><span class="sxs-lookup"><span data-stu-id="bee1f-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the necessary permissions, you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="bee1f-p102">Informes de ATP incluyen el informe de estado de protección de amenaza, el informe de tipos de archivo de ATP y el informe de eliminación de mensaje de ATP. En este artículo se describe los informes de ATP e incluye vínculos a informes adicionales para ver.</span><span class="sxs-lookup"><span data-stu-id="bee1f-p102">ATP reports include the Threat protection status report, the ATP File Types report, and the ATP Message Disposition report. This article describes the ATP reports and includes links to additional reports to view.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="bee1f-109">Informe de estado de protección de amenaza</span><span class="sxs-lookup"><span data-stu-id="bee1f-109">Threat protection status report</span></span>

<span data-ttu-id="bee1f-p103">El informe de **estado de protección de amenaza** es una vista única que reúne información sobre malintencionado correo electrónico malintencionado y contenido detectados y bloqueados por Exchange Online y avanzada de protección contra amenazas. El informe proporciona un recuento de mensajes de correo electrónico único con contenido malintencionado (archivos o direcciones URL) bloqueados por el motor de protección contra malware, [cero horas automático purgar (ZAP)](zero-hour-auto-purge.md)y las características de protección contra amenazas de avanzada, como [Vínculos seguros ATP](atp-safe-links.md), [ATP agregado Los datos adjuntos seguros](atp-safe-attachments.md)y [funciones de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="bee1f-p103">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).</span></span>
  
<span data-ttu-id="bee1f-112">Para ver el informe de estado de protección de amenaza, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **estado de protección de amenaza**.</span><span class="sxs-lookup"><span data-stu-id="bee1f-112">To view the Threat protection status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
  
![Informe de estado de protección de amenaza ATP](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="bee1f-114">Para obtener el estado detallado de un día, mantenga el mouse sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="bee1f-114">To get detailed status for a day, hover over the graph.</span></span>
  
![Datos de estado de protección de amenaza de ATP para un día](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="bee1f-p104">De forma predeterminada, el informe de estado de protección de amenaza muestra datos para los últimos siete días. Sin embargo, puede elegir **filtros** y cambiar el intervalo de fechas para ver los datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="bee1f-p104">By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![Filtros de estado de protección de amenaza ATP](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="bee1f-119">También puede usar el menú **Ver datos por** para cambiar la información que se muestra en el informe.</span><span class="sxs-lookup"><span data-stu-id="bee1f-119">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opciones de visualización para el informe de estado de protección de amenaza ATP](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="bee1f-121">Informe de tipos de archivo de ATP</span><span class="sxs-lookup"><span data-stu-id="bee1f-121">ATP File Types report</span></span>

<span data-ttu-id="bee1f-122">El informe de **Tipos de archivo de ATP** muestra el tipo de archivos detectados como malintencionado por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="bee1f-122">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="bee1f-123">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **ATP tipos de archivo**.</span><span class="sxs-lookup"><span data-stu-id="bee1f-123">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Informe de tipos de archivo de ATP](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="bee1f-125">Cuando mantenga el mouse sobre un día determinado, puede ver el desglose de los tipos de archivos malintencionados que se detectaron por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md) y [contra correo no deseado &amp; protección antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bee1f-125">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Datos de informe de tipos de archivo de ATP para un día](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="bee1f-127">Informe de eliminación de mensaje ATP</span><span class="sxs-lookup"><span data-stu-id="bee1f-127">ATP Message Disposition report</span></span>

<span data-ttu-id="bee1f-128">El informe de **Eliminación de mensaje de ATP** muestra las acciones que se tomaron para mensajes de correo electrónico que se detectaron como tener contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="bee1f-128">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="bee1f-129">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **ATP mensaje disposición**.</span><span class="sxs-lookup"><span data-stu-id="bee1f-129">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Informe de eliminación de mensajes de ATP](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="bee1f-131">Cuando mantenga el mouse sobre una barra en el gráfico, puede ver las acciones realizadas para el correo electrónico detectado para ese día.</span><span class="sxs-lookup"><span data-stu-id="bee1f-131">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Datos de informe de eliminación de mensajes de ATP para un día](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="bee1f-133">Para ver los informes adicionales</span><span class="sxs-lookup"><span data-stu-id="bee1f-133">Additional reports to view</span></span>

<span data-ttu-id="bee1f-p105">Además de los informes de ATP se describe en este artículo, [informes de seguridad de correo electrónico](view-email-security-reports.md) están disponibles en la seguridad &amp; centro de cumplimiento. Informes de seguridad de correo electrónico incluyen un [informe de los destinatarios y remitentes de la parte superior](view-email-security-reports.md#top-senders-and-recipients-report), un [informe de suplantación de correo](view-email-security-reports.md#spoof-mail-report), un [informe de detecciones de Spam](view-email-security-reports.md#spam-detections-report)y mucho más.</span><span class="sxs-lookup"><span data-stu-id="bee1f-p105">In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available in the Security &amp; Compliance Center. Email security reports include a [Top Senders and Recipients report](view-email-security-reports.md#top-senders-and-recipients-report), a [Spoof Mail report](view-email-security-reports.md#spoof-mail-report), a [Spam Detections report](view-email-security-reports.md#spam-detections-report), and more.</span></span>
  
<span data-ttu-id="bee1f-136">Y, si su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), también puede [Utilice el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="bee1f-136">And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).</span></span>
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="bee1f-137">¿Qué permisos son necesarios para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="bee1f-137">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="bee1f-138">Para poder ver y utilizar los informes de seguridad de correo electrónico que se describen en este artículo, debe tener una función adecuada asignada en la seguridad &amp; centro de cumplimiento y en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="bee1f-138">In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="bee1f-139">**Grupo de funciones**</span><span class="sxs-lookup"><span data-stu-id="bee1f-139">**Role group**</span></span>|<span data-ttu-id="bee1f-140">**Punto de asignación**</span><span class="sxs-lookup"><span data-stu-id="bee1f-140">**Where assigned**</span></span>|<span data-ttu-id="bee1f-141">**Obtener más información**</span><span class="sxs-lookup"><span data-stu-id="bee1f-141">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="bee1f-142">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bee1f-142">One of the following:</span></span>  <br/>  <span data-ttu-id="bee1f-143">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="bee1f-143">Organization Management</span></span>  <br/>  <span data-ttu-id="bee1f-144">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="bee1f-144">Security Administrator</span></span>  <br/>  <span data-ttu-id="bee1f-145">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="bee1f-145">Security Reader</span></span>  <br/> |<span data-ttu-id="bee1f-146">Seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bee1f-146">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="bee1f-147">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bee1f-147">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="bee1f-148">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bee1f-148">One of the following:</span></span>  <br/>  <span data-ttu-id="bee1f-149">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="bee1f-149">Organization Management</span></span>  <br/>  <span data-ttu-id="bee1f-150">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="bee1f-150">View-only Organization Management</span></span>  <br/>  <span data-ttu-id="bee1f-151">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="bee1f-151">View-Only Recipients role</span></span>  <br/>  <span data-ttu-id="bee1f-152">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bee1f-152">Compliance Management</span></span>  <br/> |<span data-ttu-id="bee1f-153">Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="bee1f-153">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="bee1f-154">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bee1f-154">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="bee1f-155">¿Qué ocurre si los informes no muestran los datos?</span><span class="sxs-lookup"><span data-stu-id="bee1f-155">What if the reports aren't showing data?</span></span>

<span data-ttu-id="bee1f-p106">Si no está viendo datos en los informes, vuelva a comprobar que sus directivas están configuradas correctamente. Su organización debe tener [las directivas de ATP seguros vínculos](set-up-atp-safe-links-policies.md) y [datos adjuntos seguros de ATP directivas](set-up-atp-safe-attachments-policies.md) definidas en orden para la protección de ATP para estar en su lugar. Vea también la [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bee1f-p106">If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bee1f-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bee1f-159">Related topics</span></span>

[<span data-ttu-id="bee1f-160">Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bee1f-160">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="bee1f-161">Crear una programación para un informe en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bee1f-161">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="bee1f-162">Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bee1f-162">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  


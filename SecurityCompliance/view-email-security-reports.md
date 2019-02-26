---
title: Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización con Office 365 Enterprise. Los informes de seguridad de correo electrónico están &amp; disponibles en el centro de seguridad y cumplimiento.
ms.openlocfilehash: fb9f8234f1febf98daf0382f2ad8ece3e3ecbbfe
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2019
ms.locfileid: "30242002"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="e2c4b-104">Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e2c4b-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="e2c4b-p102">Hay disponibles varios informes de seguridad de correo electrónico en [el &amp; centro de seguridad y cumplimiento](https://security.microsoft.com) para ayudarle a ver cómo las características contra correo electrónico no deseado y antimalware de Office 365 están protegiendo su organización. Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el centro de &amp; seguridad y cumplimiento desde el \*\*\*\* \> **Panel**de informes.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p102">A variety of email security reports are available in the [Security &amp; Compliance Center](https://security.microsoft.com) to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![El panel &amp; del centro de seguridad y cumplimiento puede ayudarle a ver dónde está funcionando la protección contra amenazas avanzada](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="e2c4b-108">Los informes de seguridad de correo electrónico incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2c4b-108">Your email security reports include the following:</span></span>
  
- [<span data-ttu-id="e2c4b-109">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="e2c4b-109">Threat Protection Status report</span></span>](view-email-security-reports.md#tps) 
    
- [<span data-ttu-id="e2c4b-110">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="e2c4b-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="e2c4b-111">Informe de malware principal</span><span class="sxs-lookup"><span data-stu-id="e2c4b-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="e2c4b-112">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="e2c4b-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="e2c4b-113">Informe de correo falsificado</span><span class="sxs-lookup"><span data-stu-id="e2c4b-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="e2c4b-114">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e2c4b-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="e2c4b-115">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="e2c4b-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="e2c4b-116">[Informe de mensajes notificados por el usuario](view-email-security-reports.md#userreported) (nueva)</span><span class="sxs-lookup"><span data-stu-id="e2c4b-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report"></a><span data-ttu-id="e2c4b-117">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="e2c4b-117">Threat Protection Status report</span></span>

<span data-ttu-id="e2c4b-p103">El nuevo informe de **Estado de protección contra amenazas** es un informe inteligente que muestra el correo electrónico malintencionado detectado y bloqueado por Exchange Online Protection. Este informe muestra información sobre el correo electrónico identificado como malware o como un intento de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="e2c4b-p104">Un informe de estado de protección contra amenazas está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); sin embargo, la información que se muestra en el informe de estado de la protección contra amenazas para los clientes de ATP probablemente contendrá distintos datos de los que pueden ver los clientes de EOP. Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre [los archivos malintencionados detectados en SharePoint Online, OneDrive o Microsoft Teams](atp-for-spo-odb-and-teams.md), una capacidad específica para ATP. ([Obtenga más información sobre los informes de ATP](view-reports-for-atp.md)).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="e2c4b-123">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya al **Panel** \> **informes** \> **Estado de protección contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-123">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Informe de estado de protección contra amenazas](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="e2c4b-p105">Al abrir por primera vez el informe de estado de protección contra amenazas, el informe muestra los datos de los últimos siete días de forma predeterminada; sin embargo, puede hacer clic en **filtros** y cambiar el intervalo de fechas de hasta 90 días de detalle. Este informe es útil para ver la eficacia y el impacto de las características de la protección de Exchange online de su organización, así como para las tendencias a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![Filtros del informe de estado de protección contra amenazas](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="e2c4b-128">También puede elegir si desea ver los datos de correo electrónico identificado como malintencionado, correo electrónico identificado como intentos de suplantación de identidad (phishing) o correo electrónico identificado como malware que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Opciones de vista del informe de estado de protección contra amenazas](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="e2c4b-130">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="e2c4b-130">Malware Detections report</span></span>

<span data-ttu-id="e2c4b-131">El informe de detecciones de **malware** muestra el número de mensajes entrantes y salientes que se detectaron que contenían malware para su organización.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="e2c4b-132">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a detecciones de **malware**del **Panel** \> de **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="e2c4b-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Ejemplo de informe de detecciones de malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="e2c4b-p106">De forma similar a otros informes, como el informe de estado de protección contra amenazas, el informe muestra los datos de los últimos siete días de manera predeterminada. Sin embargo, puede elegir **filtros** para cambiar el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="e2c4b-136">Informe de malware principal</span><span class="sxs-lookup"><span data-stu-id="e2c4b-136">Top Malware report</span></span>

<span data-ttu-id="e2c4b-137">El informe de **malware superior** muestra los distintos tipos de malware detectados por Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="e2c4b-138">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a **informes** \> de **malware superior**del **Panel** \> de informes.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-138">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-malware superior de EOP](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="e2c4b-140">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes que se detectaron como si tuvieran ese malware.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="e2c4b-141">Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Este informe muestra el malware principal detectado para su organización](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="e2c4b-143">Debajo del gráfico, verá una lista de malware detectado y el número de mensajes que se detectaron como si tuvieran ese malware.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e2c4b-144">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="e2c4b-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="e2c4b-145">El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los remitentes de correo electrónico principales.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="e2c4b-146">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a los **destinatarios y remitentes principales**del **Panel** \> de **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="e2c4b-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes de remitentes y destinatarios principales del panel de informes](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="e2c4b-148">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="e2c4b-149">Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="e2c4b-p107">Use la lista **Mostrar datos para** para elegir si desea ver los datos de los remitentes principales, los receptores, los destinatarios de correo no deseado y los destinatarios de malware. También puede ver quién recibió malware que se detectó con la protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![Usar la lista Mostrar datos para para ver información específica](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="e2c4b-153">Debajo del gráfico, verá quién eran los remitentes o destinatarios de correo electrónico principales, junto con un recuento de mensajes enviados o recibidos durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="e2c4b-154">Informe de correo falsificado</span><span class="sxs-lookup"><span data-stu-id="e2c4b-154">Spoof Mail report</span></span>

<span data-ttu-id="e2c4b-155">El informe de **correo falsificado** muestra cuántos mensajes de correo electrónico de falsificación se detectaron y cuáles se consideraron "buenos" (correo falsificado realizado por razones empresariales legítimas).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="e2c4b-156">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a **informes** \> de **correo falsificado**del **Panel** \> de informes.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes de correo falsificado del panel de informes](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="e2c4b-158">Cuando se mantiene el puntero sobre un día del gráfico, puede ver cuántos mensajes de correo falsificado llegaron.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="e2c4b-159">Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="e2c4b-160">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="e2c4b-160">Spam Detections report</span></span>

<span data-ttu-id="e2c4b-161">El informe de detecciones de **correo no deseado** muestra todo el contenido de correo no deseado bloqueado por Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="e2c4b-162">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a detecciones de **correo no deseado**del **Panel** \> de **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="e2c4b-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes de detección de correo no deseado de eop del panel informes](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="e2c4b-p108">Al pasar el mouse sobre un día del gráfico, puede ver cuántos elementos se bloquearon ese día, así como la forma en que esos elementos se clasifican. Por ejemplo, puede ver cuántos mensajes de correo no deseado se filtraron y cuántos elementos procedían de una dirección de protocolo de Internet (IP) bloqueada.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="e2c4b-166">Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![El informe de detecciones de correo no deseado indica el número de mensajes de correo no deseado bloqueados o filtrados](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="e2c4b-p109">Debajo del gráfico, verá una lista de elementos de correo no deseado que se detectaron. Seleccione un elemento para ver información adicional como, por ejemplo, si el elemento de correo no deseado era de entrada o de salida, su identificador de mensaje y su destinatario.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="e2c4b-170">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="e2c4b-170">Sent and received email report</span></span>

<span data-ttu-id="e2c4b-171">El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="e2c4b-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="e2c4b-172">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a **informes** \> **Panel** \> **enviados y recibidos**.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-172">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Para ver este informe, en el centro &amp; de seguridad y cumplimiento, vaya \> a \> informes panel enviados y recibidos](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="e2c4b-p110">Al pasar el mouse sobre un día del gráfico, puede ver cuántos mensajes se han recibido y cómo se clasifican los mensajes. Por ejemplo, puede ver cuántos mensajes se han detectado como que contienen malware y cuántos se identificaron como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="e2c4b-176">Haga clic (o puntee) en el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="e2c4b-177">Puede usar la lista **desglosar por** para ver la información por tipo o por dirección (entrante y saliente).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Use la lista desglosar por para ver la información por tipo o por dirección.](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="e2c4b-p111">Debajo del gráfico, verá una lista de categorías de correo electrónico, como **GoodMail**, **SpamContentFiltered**, etc. Seleccione una categoría para ver información adicional, como las acciones que se tomaron para malware y si el correo electrónico se ha entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Este informe le indica sobre antimalware, contra correo no deseado y otras detecciones de mensajes](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="e2c4b-182">Informe de mensajes notificados por el usuario (nuevo)</span><span class="sxs-lookup"><span data-stu-id="e2c4b-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="e2c4b-183">El informe de **mensajes de** informes de usuario muestra información sobre los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad (phishing) o correo correcto mediante el [complemento de mensajes de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="e2c4b-p112">Hay más detalles disponibles para cada mensaje, incluidos el motivo de la entrega, la excepción de la Directiva de correo no deseado o la regla de flujo de correo configurada para la organización. Para ver los detalles, seleccione un elemento de la lista de informes de usuarios y, a continuación, vea la información en las pestañas **Resumen** y **detalles** .</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![El informe de mensajes de informes de usuario muestra los usuarios etiquetados como correo no deseado, no deseado o intentos de suplantación de identidad.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="e2c4b-187">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="e2c4b-187">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="e2c4b-188">Vaya a **mensajes de los que ha informado el usuario del** **Panel** \> de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="e2c4b-189">Vaya a los mensajes de **revisión** \> de **Administración** \> de amenazas que ha **informado el usuario**.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![En el centro &amp; de seguridad y cumplimiento, elija \> mensajes \> de informe de usuario de revisión de administración de amenazas](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="e2c4b-p113">Para que el informe de mensajes notificados por el usuario funcione correctamente, el **registro de auditoría debe estar activado** para su entorno de Office 365. Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e2c4b-194">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="e2c4b-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e2c4b-195">Para poder ver y usar los informes descritos en este artículo, **debe tener asignada una función adecuada para el centro de &amp; seguridad y cumplimiento y el centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e2c4b-195">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="e2c4b-196">Para el centro &amp; de seguridad y cumplimiento, debe tener asignada una de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="e2c4b-196">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="e2c4b-197">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="e2c4b-197">Organization Management</span></span>
    - <span data-ttu-id="e2c4b-198">Administrador de seguridad (puede asignarse en el centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()</span><span class="sxs-lookup"><span data-stu-id="e2c4b-198">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="e2c4b-199">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="e2c4b-199">Security Reader</span></span>

- <span data-ttu-id="e2c4b-200">Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="e2c4b-200">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="e2c4b-201">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="e2c4b-201">Organization Management</span></span>
    - <span data-ttu-id="e2c4b-202">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="e2c4b-202">View-only Organization Management</span></span>
    - <span data-ttu-id="e2c4b-203">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="e2c4b-203">View-Only Recipients role</span></span>
    - <span data-ttu-id="e2c4b-204">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e2c4b-204">Compliance Management</span></span>

<span data-ttu-id="e2c4b-205">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="e2c4b-205">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="e2c4b-206">Permisos en el centro de seguridad &amp; y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="e2c4b-206">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="e2c4b-207">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e2c4b-207">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e2c4b-208">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="e2c4b-208">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e2c4b-p114">Si no ve datos en los informes, compruebe que las directivas estén correctamente configuradas. Para obtener más información, consulte [protección contra correo electrónico no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e2c4b-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2c4b-211">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e2c4b-211">Related topics</span></span>

[<span data-ttu-id="e2c4b-212">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="e2c4b-212">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="e2c4b-213">Informes y opiniones en el centro de seguridad &amp; y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="e2c4b-213">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="e2c4b-214">Crear una programación para un informe en el centro &amp; de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e2c4b-214">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="e2c4b-215">Configurar y descargar un informe personalizado en el centro de &amp; seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e2c4b-215">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  


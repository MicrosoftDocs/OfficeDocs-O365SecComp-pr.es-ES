---
title: Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para la organización con Office 365 Enterprise. Informes de seguridad de correo electrónico están disponibles en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 72039afd52cd6e9da7dfd05bb67aac2c7e7db001
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706424"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="2154a-104">Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2154a-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="2154a-p102">Una variedad de informes de seguridad de correo electrónico están disponibles en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com) que le ayudarán a ver cómo las características contra correo no deseado y antimalware en Office 365 protegen a la organización. Si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en la seguridad &amp; centro de cumplimiento yendo a los **informes** \> **panel**.</span><span class="sxs-lookup"><span data-stu-id="2154a-p102">A variety of email security reports are available in the [Security &amp; Compliance Center](https://security.microsoft.com) to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="2154a-108">Los informes de seguridad de correo electrónico son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2154a-108">Your email security reports include the following:</span></span>
  
- <span data-ttu-id="2154a-109">[Informe de estado de protección de amenaza](view-email-security-reports.md#tps) (nuevo)!</span><span class="sxs-lookup"><span data-stu-id="2154a-109">[Threat Protection Status report](view-email-security-reports.md#tps) (new!)</span></span> 
    
- [<span data-ttu-id="2154a-110">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="2154a-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="2154a-111">Informe de Malware superior</span><span class="sxs-lookup"><span data-stu-id="2154a-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="2154a-112">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="2154a-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="2154a-113">Informe de correo de suplantación</span><span class="sxs-lookup"><span data-stu-id="2154a-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="2154a-114">Informe de detecciones de correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="2154a-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="2154a-115">Informe de correo electrónico enviados y recibidos</span><span class="sxs-lookup"><span data-stu-id="2154a-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="2154a-116">[Informe de mensajes indicado por el usuario](view-email-security-reports.md#userreported) (nuevo)!</span><span class="sxs-lookup"><span data-stu-id="2154a-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report-new"></a><span data-ttu-id="2154a-117">Amenazas de informe de estado de protección (¡nuevo!)</span><span class="sxs-lookup"><span data-stu-id="2154a-117">Threat Protection Status report (new!)</span></span>

<span data-ttu-id="2154a-p103">El nuevo informe de **Estado de protección de amenaza** es un informe inteligente que se muestra el correo electrónico malintencionado que se ha detectado y bloqueado por Exchange Online Protection. Este informe muestra información acerca del correo electrónico identificado como malware o un intento de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="2154a-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="2154a-p104">Un informe de estado de protección de amenaza está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Sin embargo, la información que se muestra en el informe de estado de protección de amenaza para los clientes de ATP probablemente contendrá datos distintos a lo que es posible que vea los clientes de EOP. Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre [archivos malintencionados detectan en SharePoint Online, OneDrive o los equipos de Microsoft](atp-for-spo-odb-and-teams.md), una capacidad de ATP específicas. ([Más información acerca de los informes de ATP](view-reports-for-atp.md)).</span><span class="sxs-lookup"><span data-stu-id="2154a-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="2154a-123">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Estado de protección de amenaza**.</span><span class="sxs-lookup"><span data-stu-id="2154a-123">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Informe de estado de protección de amenaza](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="2154a-p105">La primera vez que se abre el informe de estado de protección de amenaza, el informe muestra datos de los últimos siete días de forma predeterminada; Sin embargo, puede haga clic en **filtros** y cambiar el intervalo de fechas de hasta 90 días de detalle. Este informe es útil para la visualización de la eficacia y el impacto de las características de protección en línea de Exchange de su organización y de tendencias a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="2154a-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![Filtros del informe de estado de protección de amenaza](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="2154a-128">También puede elegir si de forma para ver los datos de correo electrónico que se identificó como malintencionado, correo electrónico o correo electrónico identificado como los intentos de suplantación de una identidad identifica como que contiene el malware.</span><span class="sxs-lookup"><span data-stu-id="2154a-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Opciones de vista de informe de estado de protección de amenaza](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="2154a-130">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="2154a-130">Malware Detections report</span></span>

<span data-ttu-id="2154a-131">El informe de **Detecciones de Malware** muestra el número de mensajes entrante y saliente se detectaron como que contiene el malware para su organización.</span><span class="sxs-lookup"><span data-stu-id="2154a-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="2154a-132">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Detecciones de Malware**.</span><span class="sxs-lookup"><span data-stu-id="2154a-132">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Ejemplo de informe de detecciones de malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="2154a-p106">Similar a otros informes, como el informe de estado de protección de amenaza, el informe muestra datos de los últimos siete días de forma predeterminada. Sin embargo, puede elegir **filtros** para cambiar el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="2154a-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="2154a-136">Informe de Malware superior</span><span class="sxs-lookup"><span data-stu-id="2154a-136">Top Malware report</span></span>

<span data-ttu-id="2154a-137">El informe de **Malware de la parte superior** muestra los distintos tipos de malware que se detectó por Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2154a-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="2154a-138">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Malware de la parte superior**.</span><span class="sxs-lookup"><span data-stu-id="2154a-138">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC - principales de Malware de elevación de privilegios](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="2154a-140">Cuando mantenga el mouse sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes se detectaron como tener que el malware.</span><span class="sxs-lookup"><span data-stu-id="2154a-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="2154a-141">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="2154a-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Este informe muestra las principales de malware detectado para su organización](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="2154a-143">Debajo del gráfico, verá una lista de malware detectado y cuántos mensajes se detectaron como tener que el malware.</span><span class="sxs-lookup"><span data-stu-id="2154a-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="2154a-144">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="2154a-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="2154a-145">El informe **principales remitentes y destinatarios** es un gráfico circular que muestra la lista de remitentes de correo electrónico superior.</span><span class="sxs-lookup"><span data-stu-id="2154a-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="2154a-146">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **principales remitentes y destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="2154a-146">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> principales remitentes y destinatarios](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="2154a-148">Cuando mantenga el mouse sobre una cuña en el gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="2154a-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="2154a-149">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="2154a-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="2154a-p107">Utilice la lista **Mostrar datos para** elegir si desea ver los datos para remitentes principales, receptores, de correo no deseado y los destinatarios de malware. También puede ver que recibió el malware que se detectó por avanzada de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="2154a-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![Use la lista Mostrar datos para ver información específica](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="2154a-153">Debajo del gráfico, comprobará que los remitentes de correo electrónico superior o fueron de los destinatarios, junto con un recuento de los mensajes enviados o recibidos para el período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="2154a-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="2154a-154">Informe de correo de suplantación</span><span class="sxs-lookup"><span data-stu-id="2154a-154">Spoof Mail report</span></span>

<span data-ttu-id="2154a-155">El informe de **Correo de suplantación de la** muestra se detectaron ¿cuántos mensajes de correo de suplantación de la y, de ellas, cuáles se consideran "bueno" (correo de suplantación hecho por razones de negocio legítimo).</span><span class="sxs-lookup"><span data-stu-id="2154a-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="2154a-156">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Suplantación de correo**.</span><span class="sxs-lookup"><span data-stu-id="2154a-156">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> suplantación de correo](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="2154a-158">Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos mensajes de correo de suplantación de la suministrada a través de.</span><span class="sxs-lookup"><span data-stu-id="2154a-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="2154a-159">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="2154a-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="2154a-160">Informe de detecciones de correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="2154a-160">Spam Detections report</span></span>

<span data-ttu-id="2154a-161">El informe de **Detecciones de Spam** muestra todo el contenido de spam bloqueado por Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2154a-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="2154a-162">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **Detecciones de Spam**.</span><span class="sxs-lookup"><span data-stu-id="2154a-162">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> detecciones de correo electrónico no deseado de elevación de privilegios](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="2154a-p108">Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos elementos se han bloqueado ese día, así como el modo en esos elementos se clasifican. Por ejemplo, puede ver cuántos mensajes de spam se han filtrado y cuántos elementos proceden de una dirección de protocolo de Internet (IP) bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2154a-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="2154a-166">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="2154a-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![El informe de detecciones de correo electrónico no deseado le indica cuántos mensajes de spam se han bloqueado o filtran](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="2154a-p109">Debajo del gráfico, verá una lista de elementos de spam que se detectaron. Seleccione un elemento para ver información adicional, por ejemplo, si el elemento de spam fue entrante o saliente, su identificador de mensaje y su destinatario.</span><span class="sxs-lookup"><span data-stu-id="2154a-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="2154a-170">Informe de correo electrónico enviados y recibidos</span><span class="sxs-lookup"><span data-stu-id="2154a-170">Sent and received email report</span></span>

<span data-ttu-id="2154a-171">El informe **enviado y recibido de correo electrónico** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de spam, malware y correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="2154a-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="2154a-172">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), vaya a **informes** \> **panel** \> **enviado y recibido de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="2154a-172">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> enviados y correo electrónico recibido](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="2154a-p110">Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos mensajes procede y cómo se clasifican los mensajes. Por ejemplo, puede ver cuántos mensajes se detectaron como que contiene el malware y cuántos se han identificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="2154a-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="2154a-176">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="2154a-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="2154a-177">Puede usar la lista de **dividir por** para ver la información por tipo o por dirección (entrante y saliente).</span><span class="sxs-lookup"><span data-stu-id="2154a-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Use la lista de interrupción hacia abajo por para ver la información de tipo o la dirección](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="2154a-p111">Debajo del gráfico, verá una lista de categorías de correo electrónico, como **GoodMail**, **SpamContentFiltered**y así sucesivamente. Seleccione una categoría para ver información adicional, como las acciones que se tomaron de malware y de correo electrónico si fue entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="2154a-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Este informe le informa sobre anti-malware, contra correo no deseado y detecciones de otros mensajes](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="2154a-182">Informe de mensajes indicado por el usuario (¡nuevo!)</span><span class="sxs-lookup"><span data-stu-id="2154a-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="2154a-183">El informe de **mensajes indicado por el usuario** muestra información sobre los mensajes de correo electrónico que los usuarios han informado como correo no deseado, los intentos de suplantación de identidad o correo correcto mediante el [complemento en el mensaje de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="2154a-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="2154a-p112">Detalles están disponibles para cada mensaje, incluidos el motivo de la entrega, como una excepción de la directiva de spam o regla de flujo de correo de su organización. Para ver los detalles, seleccione un elemento en la lista de informes de usuario y, a continuación, ver la información en las fichas **Resumen** y **Detalles** .</span><span class="sxs-lookup"><span data-stu-id="2154a-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![El informe de los mensajes de User-Reported muestra a los usuarios de los mensajes etiquetados como no deseado, no correo no deseado o suplantación de identidad intentos.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="2154a-187">Para ver este informe, en la [seguridad &amp; centro de cumplimiento](https://security.microsoft.com), siga uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="2154a-187">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), do one of the following:</span></span>
  
- <span data-ttu-id="2154a-188">Vaya a **administración de amenaza** \> **panel** \> **mensajes indicado por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="2154a-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="2154a-189">Vaya a **administración de amenaza** \> **revisión** \> **mensajes indicado por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="2154a-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![En la seguridad &amp; centro de cumplimiento, elija Administración de amenaza \> revisión \> mensajes indicado por usuario](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="2154a-p113">En orden para que el informe de mensajes notificados por los usuarios para que funcione correctamente, **debe estar activado el registro de auditoría** para su entorno de Office 365. Normalmente, esto se realiza por una persona que tenga el rol de los registros de auditoría asignado en Exchange Online. Para obtener más información, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2154a-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="2154a-194">¿Qué permisos son necesarios para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="2154a-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="2154a-195">Para poder ver y usar los informes que se describen en este artículo, debe tener una función adecuada asignada en ambos la seguridad &amp; centro de cumplimiento y el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2154a-195">In order to view and use the reports described in this article, you must have an appropriate role assigned in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>

- <span data-ttu-id="2154a-196">Para la seguridad &amp; centro de cumplimiento, debe tener uno de los siguientes roles asignados:</span><span class="sxs-lookup"><span data-stu-id="2154a-196">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="2154a-197">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="2154a-197">Organization Management</span></span>
    - <span data-ttu-id="2154a-198">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="2154a-198">Security Administrator</span></span>
    - <span data-ttu-id="2154a-199">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="2154a-199">Security Reader</span></span>

- <span data-ttu-id="2154a-200">Para Exchange Online, debe tener uno de los siguientes roles asignados:</span><span class="sxs-lookup"><span data-stu-id="2154a-200">For Exchange Online, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="2154a-201">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="2154a-201">Organization Management</span></span>
    - <span data-ttu-id="2154a-202">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="2154a-202">View-only Organization Management</span></span>
    - <span data-ttu-id="2154a-203">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="2154a-203">View-Only Recipients role</span></span>
    - <span data-ttu-id="2154a-204">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2154a-204">Compliance Management</span></span>

<span data-ttu-id="2154a-205">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="2154a-205">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="2154a-206">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2154a-206">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="2154a-207">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2154a-207">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="2154a-208">¿Qué ocurre si los informes no muestran los datos?</span><span class="sxs-lookup"><span data-stu-id="2154a-208">What if the reports aren't showing data?</span></span>

<span data-ttu-id="2154a-p114">Si no está viendo datos en los informes, vuelva a comprobar que sus directivas están configuradas correctamente. Para obtener más información, consulte [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="2154a-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2154a-211">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2154a-211">Related topics</span></span>

[<span data-ttu-id="2154a-212">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2154a-212">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="2154a-213">Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2154a-213">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="2154a-214">Crear una programación para un informe en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2154a-214">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="2154a-215">Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="2154a-215">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  


---
title: Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento
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
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para la organización con Office 365 Enterprise. Informes de seguridad de correo electrónico están disponibles en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 0dd0c2ee7090e488d8619e71c6e4931f1934e9b0
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454347"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d0616-104">Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="d0616-p102">Informes de una gran variedad de seguridad de correo electrónico están disponibles en la seguridad &amp; centro de cumplimiento que le ayudarán a ver cómo las características contra correo no deseado y antimalware en Office 365 protegen a la organización. Si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en la seguridad &amp; centro de cumplimiento yendo a los **informes** \> **panel**.</span><span class="sxs-lookup"><span data-stu-id="d0616-p102">A variety of email security reports are available in the Security &amp; Compliance Center to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![La seguridad &amp; panel del centro de cumplimiento puede ayudarle a ver dónde está trabajando avanzada de protección contra amenazas](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="d0616-108">Los informes de seguridad de correo electrónico son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0616-108">Your email security reports include the following:</span></span>
  
- <span data-ttu-id="d0616-109">[Informe de estado de protección de amenaza](view-email-security-reports.md#tps) (nuevo)!</span><span class="sxs-lookup"><span data-stu-id="d0616-109">[Threat protection status report](view-email-security-reports.md#tps) (new!)</span></span> 
    
- [<span data-ttu-id="d0616-110">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="d0616-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="d0616-111">Informe de Malware superior</span><span class="sxs-lookup"><span data-stu-id="d0616-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="d0616-112">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="d0616-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="d0616-113">Informe de correo de suplantación</span><span class="sxs-lookup"><span data-stu-id="d0616-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="d0616-114">Informe de detecciones de correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="d0616-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="d0616-115">Informe de correo electrónico enviados y recibidos</span><span class="sxs-lookup"><span data-stu-id="d0616-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="d0616-116">[Informe de mensajes indicado por el usuario](view-email-security-reports.md#userreported) (nuevo)!</span><span class="sxs-lookup"><span data-stu-id="d0616-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report-new"></a><span data-ttu-id="d0616-117">Informe de estado de protección de amenaza (¡nuevo!)</span><span class="sxs-lookup"><span data-stu-id="d0616-117">Threat protection status report (new!)</span></span>

<span data-ttu-id="d0616-p103">El nuevo informe de **estado de protección de amenaza** es un informe inteligente que se muestra el correo electrónico malintencionado que se ha detectado y bloqueado por Exchange Online Protection. Este informe muestra información acerca del correo electrónico identificado como malware o un intento de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="d0616-p103">The new **Threat protection status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 
  
<span data-ttu-id="d0616-120">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **estado de protección de amenaza**.</span><span class="sxs-lookup"><span data-stu-id="d0616-120">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
  
![Informe de estado de protección de amenaza](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="d0616-p104">La primera vez que se abre el informe de estado de protección de amenaza, el informe muestra datos de los últimos siete días de forma predeterminada; Sin embargo, puede haga clic en **filtros** y cambiar el intervalo de fechas de hasta 90 días de detalle. Este informe es útil para la visualización de la eficacia y el impacto de las características de protección en línea de Exchange de su organización y de tendencias a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="d0616-p104">When you first open the Threat protection status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![Filtros del informe de estado de protección de amenaza](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="d0616-125">También puede elegir si de forma para ver los datos de correo electrónico que se identificó como malintencionado, correo electrónico o correo electrónico identificado como los intentos de suplantación de una identidad identifica como que contiene el malware.</span><span class="sxs-lookup"><span data-stu-id="d0616-125">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Opciones de vista de informe de estado de protección de amenaza](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="d0616-127">Informe de detecciones de malware</span><span class="sxs-lookup"><span data-stu-id="d0616-127">Malware Detections report</span></span>

<span data-ttu-id="d0616-128">El informe de **Detecciones de Malware** muestra el número de mensajes entrante y saliente se detectaron como que contiene el malware para su organización.</span><span class="sxs-lookup"><span data-stu-id="d0616-128">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="d0616-129">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **Detecciones de Malware**.</span><span class="sxs-lookup"><span data-stu-id="d0616-129">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Ejemplo de informe de detecciones de malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="d0616-p105">Similar a otros informes, como el informe de estado de protección de amenaza, el informe muestra datos de los últimos siete días de forma predeterminada. Sin embargo, puede elegir **filtros** para cambiar el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="d0616-p105">Similar to other reports, like the Threat protection status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="d0616-133">Informe de Malware superior</span><span class="sxs-lookup"><span data-stu-id="d0616-133">Top Malware report</span></span>

<span data-ttu-id="d0616-134">El informe de **Malware de la parte superior** muestra los distintos tipos de malware que se detectó por Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0616-134">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="d0616-135">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **Malware de la parte superior**.</span><span class="sxs-lookup"><span data-stu-id="d0616-135">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC - principales de Malware de elevación de privilegios](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="d0616-137">Cuando mantenga el mouse sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y el número de mensajes se detectaron como tener que el malware.</span><span class="sxs-lookup"><span data-stu-id="d0616-137">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="d0616-138">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="d0616-138">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Este informe muestra las principales de malware detectado para su organización](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="d0616-140">Debajo del gráfico, verá una lista de malware detectado y cuántos mensajes se detectaron como tener que el malware.</span><span class="sxs-lookup"><span data-stu-id="d0616-140">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="d0616-141">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="d0616-141">Top Senders and Recipients report</span></span>

<span data-ttu-id="d0616-142">El informe **principales remitentes y destinatarios** es un gráfico circular que muestra la lista de remitentes de correo electrónico superior.</span><span class="sxs-lookup"><span data-stu-id="d0616-142">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="d0616-143">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **principales remitentes y destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="d0616-143">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> principales remitentes y destinatarios](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="d0616-145">Cuando mantenga el mouse sobre una cuña en el gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="d0616-145">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="d0616-146">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="d0616-146">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="d0616-p106">Utilice la lista **Mostrar datos para** elegir si desea ver los datos para remitentes principales, receptores, de correo no deseado y los destinatarios de malware. También puede ver que recibió el malware que se detectó por avanzada de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="d0616-p106">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![Use la lista Mostrar datos para ver información específica](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="d0616-150">Debajo del gráfico, comprobará que los remitentes de correo electrónico superior o fueron de los destinatarios, junto con un recuento de los mensajes enviados o recibidos para el período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="d0616-150">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="d0616-151">Informe de correo de suplantación</span><span class="sxs-lookup"><span data-stu-id="d0616-151">Spoof Mail report</span></span>

<span data-ttu-id="d0616-152">El informe de **Correo de suplantación de la** muestra se detectaron ¿cuántos mensajes de correo de suplantación de la y, de ellas, cuáles se consideran "bueno" (correo de suplantación hecho por razones de negocio legítimo).</span><span class="sxs-lookup"><span data-stu-id="d0616-152">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="d0616-153">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **Suplantación de correo**.</span><span class="sxs-lookup"><span data-stu-id="d0616-153">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> suplantación de correo](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="d0616-155">Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos mensajes de correo de suplantación de la suministrada a través de.</span><span class="sxs-lookup"><span data-stu-id="d0616-155">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="d0616-156">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="d0616-156">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="d0616-157">Informe de detecciones de correo electrónico no deseado</span><span class="sxs-lookup"><span data-stu-id="d0616-157">Spam Detections report</span></span>

<span data-ttu-id="d0616-158">El informe de **Detecciones de Spam** muestra todo el contenido de spam bloqueado por Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0616-158">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="d0616-159">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **Detecciones de Spam**.</span><span class="sxs-lookup"><span data-stu-id="d0616-159">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> detecciones de correo electrónico no deseado de elevación de privilegios](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="d0616-p107">Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos elementos se han bloqueado ese día, así como el modo en esos elementos se clasifican. Por ejemplo, puede ver cuántos mensajes de spam se han filtrado y cuántos elementos proceden de una dirección de protocolo de Internet (IP) bloqueados.</span><span class="sxs-lookup"><span data-stu-id="d0616-p107">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="d0616-163">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="d0616-163">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![El informe de detecciones de correo electrónico no deseado le indica cuántos mensajes de spam se han bloqueado o filtran](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="d0616-p108">Debajo del gráfico, verá una lista de elementos de spam que se detectaron. Seleccione un elemento para ver información adicional, por ejemplo, si el elemento de spam fue entrante o saliente, su identificador de mensaje y su destinatario.</span><span class="sxs-lookup"><span data-stu-id="d0616-p108">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="d0616-167">Informe de correo electrónico enviados y recibidos</span><span class="sxs-lookup"><span data-stu-id="d0616-167">Sent and received email report</span></span>

<span data-ttu-id="d0616-168">El informe **enviado y recibido de correo electrónico** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de spam, malware y correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="d0616-168">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="d0616-169">Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a **informes** \> **panel** \> **enviado y recibido de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="d0616-169">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Para ver este informe, en la seguridad &amp; centro de cumplimiento, vaya a informes \> panel \> enviados y correo electrónico recibido](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="d0616-p109">Cuando mantenga el mouse sobre un día en el gráfico, puede ver cuántos mensajes procede y cómo se clasifican los mensajes. Por ejemplo, puede ver cuántos mensajes se detectaron como que contiene el malware y cuántos se han identificado como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="d0616-p109">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="d0616-173">Haga clic en (o puntee) el informe para abrirlo en una nueva ventana del explorador, donde puede obtener una vista más detallada del informe.</span><span class="sxs-lookup"><span data-stu-id="d0616-173">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="d0616-174">Puede usar la lista de **dividir por** para ver la información por tipo o por dirección (entrante y saliente).</span><span class="sxs-lookup"><span data-stu-id="d0616-174">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Use la lista de interrupción hacia abajo por para ver la información de tipo o la dirección](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="d0616-p110">Debajo del gráfico, verá una lista de categorías de correo electrónico, como **GoodMail**, **SpamContentFiltered**y así sucesivamente. Seleccione una categoría para ver información adicional, como las acciones que se tomaron de malware y de correo electrónico si fue entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="d0616-p110">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![Este informe le informa sobre anti-malware, contra correo no deseado y detecciones de otros mensajes](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="d0616-179">Informe de mensajes indicado por el usuario (¡nuevo!)</span><span class="sxs-lookup"><span data-stu-id="d0616-179">User-reported messages report (new!)</span></span>

<span data-ttu-id="d0616-180">El informe de **mensajes indicado por el usuario** muestra información sobre los mensajes de correo electrónico que los usuarios han informado como correo no deseado, los intentos de suplantación de identidad o correo correcto mediante el [complemento en el mensaje de informe](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="d0616-180">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="d0616-p111">Detalles están disponibles para cada mensaje, incluidos el motivo de la entrega, como una excepción de la directiva de spam o regla de flujo de correo de su organización. Para ver los detalles, seleccione un elemento en la lista de informes de usuario y, a continuación, ver la información en las fichas **Resumen** y **Detalles** .</span><span class="sxs-lookup"><span data-stu-id="d0616-p111">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![El informe de los mensajes de User-Reported muestra a los usuarios de los mensajes etiquetados como no deseado, no correo no deseado o suplantación de identidad intentos.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="d0616-184">Para ver este informe, en la seguridad &amp; centro de cumplimiento, realice uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0616-184">To view this report, in the Security &amp; Compliance Center, do one of the following:</span></span>
  
- <span data-ttu-id="d0616-185">Vaya a **administración de amenaza** \> **panel** \> **mensajes indicado por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="d0616-185">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="d0616-186">Vaya a **administración de amenaza** \> **revisión** \> **mensajes indicado por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="d0616-186">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![En la seguridad &amp; centro de cumplimiento, elija Administración de amenaza \> revisión \> mensajes indicado por usuario](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="d0616-p112">En orden para que el informe de mensajes notificados por los usuarios para que funcione correctamente, **debe estar activado el registro de auditoría** para su entorno de Office 365. Normalmente, esto se realiza por una persona que tenga el rol de los registros de auditoría asignado en Exchange Online. Para obtener más información, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="d0616-p112">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="d0616-191">¿Qué permisos son necesarios para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="d0616-191">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="d0616-192">Para poder ver y utilizar los informes de seguridad de correo electrónico que se describen en este artículo, debe tener una función adecuada asignada en la seguridad &amp; centro de cumplimiento y en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d0616-192">In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="d0616-193">**Grupo de funciones**</span><span class="sxs-lookup"><span data-stu-id="d0616-193">**Role group**</span></span>|<span data-ttu-id="d0616-194">**Punto de asignación**</span><span class="sxs-lookup"><span data-stu-id="d0616-194">**Where assigned**</span></span>|<span data-ttu-id="d0616-195">**Obtener más información**</span><span class="sxs-lookup"><span data-stu-id="d0616-195">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="d0616-196">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0616-196">One of the following:</span></span>  <br/>  <span data-ttu-id="d0616-197">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="d0616-197">Organization Management</span></span>  <br/>  <span data-ttu-id="d0616-198">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="d0616-198">Security Administrator</span></span>  <br/>  <span data-ttu-id="d0616-199">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="d0616-199">Security Reader</span></span>  <br/> |<span data-ttu-id="d0616-200">Seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-200">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="d0616-201">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-201">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="d0616-202">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0616-202">One of the following:</span></span>  <br/>  <span data-ttu-id="d0616-203">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="d0616-203">Organization Management</span></span>  <br/>  <span data-ttu-id="d0616-204">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="d0616-204">View-only Organization Management</span></span>  <br/>  <span data-ttu-id="d0616-205">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="d0616-205">View-Only Recipients role</span></span>  <br/>  <span data-ttu-id="d0616-206">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-206">Compliance Management</span></span>  <br/> |<span data-ttu-id="d0616-207">Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="d0616-207">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="d0616-208">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d0616-208">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d0616-209">¿Qué ocurre si los informes no muestran los datos?</span><span class="sxs-lookup"><span data-stu-id="d0616-209">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d0616-p113">Si no está viendo datos en los informes, vuelva a comprobar que sus directivas están configuradas correctamente. Para obtener más información, consulte [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d0616-p113">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d0616-212">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d0616-212">Related topics</span></span>

[<span data-ttu-id="d0616-213">Protección contra correo no deseado de Office 365</span><span class="sxs-lookup"><span data-stu-id="d0616-213">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="d0616-214">Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-214">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d0616-215">Crear una programación para un informe en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-215">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="d0616-216">Configurar y descargar un informe personalizado en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d0616-216">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  


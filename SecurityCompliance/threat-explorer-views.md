---
title: Vistas del explorador de amenazas
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre los distintos tipos de vistas disponibles en el explorador (también denominado explorador de amenazas) como parte de Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: bcfa044db6844d9459b3dd62d9ced1cd37a999ec
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736503"
---
# <a name="threat-explorer-views"></a><span data-ttu-id="e5629-103">Vistas del explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="e5629-103">Threat Explorer views</span></span>

<span data-ttu-id="e5629-104">[Threat Explorer](use-explorer-in-security-and-compliance.md) es una herramienta eficaz, casi en tiempo real, que ayuda a los equipos de operaciones de seguridad a investigar y &amp; responder a amenazas en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e5629-104">[Threat Explorer](use-explorer-in-security-and-compliance.md) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="e5629-105">El explorador muestra información sobre el malware y el phish sospechoso en el correo electrónico y los archivos de Office 365, así como otras amenazas de seguridad y riesgos para la organización.</span><span class="sxs-lookup"><span data-stu-id="e5629-105">Explorer displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

<span data-ttu-id="e5629-106">La primera vez que se abre el explorador, la vista predeterminada muestra las detecciones de malware de correo electrónico de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="e5629-106">When you first open Explorer, the default view shows email malware detections for the past 7 days.</span></span> 

![Explorador de amenazas](media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="e5629-108">El explorador también puede mostrar características de protección de seguridad en Office 365, incluidos [vínculos seguros](atp-safe-links.md) y [datos adjuntos seguros](atp-safe-attachments.md) , y se puede modificar para mostrar los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e5629-108">Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5629-109">Si tiene una suscripción de prueba de Office 365 Advanced Threat Protection Plan 2 u Office 365 E5, solo verá las detecciones y los datos de correo electrónico de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="e5629-109">If you have a trial subscription for Office 365 Advanced Threat Protection Plan 2 or Office 365 E5, you will only see detections and email data for the past 7 days.</span></span>
  
<span data-ttu-id="e5629-110">Use el menú **Ver** para cambiar la información que se muestra.</span><span class="sxs-lookup"><span data-stu-id="e5629-110">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="e5629-111">La información sobre herramientas ayuda a determinar la vista que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e5629-111">Tooltips help you determine which view to use.</span></span>
  
![Menú Ver del explorador de amenazas](media/ThreatExplorerViewMenu.png)

<span data-ttu-id="e5629-113">Una vez que haya seleccionado una vista, puede aplicar filtros y configurar consultas para realizar más análisis.</span><span class="sxs-lookup"><span data-stu-id="e5629-113">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="e5629-114">En las siguientes secciones se proporciona una breve introducción a las distintas vistas disponibles en el explorador.</span><span class="sxs-lookup"><span data-stu-id="e5629-114">The following sections provide a brief overview of the various views available in Explorer.</span></span>  

## <a name="email--malware"></a><span data-ttu-id="e5629-115">Correo electrónico > malware</span><span class="sxs-lookup"><span data-stu-id="e5629-115">Email > Malware</span></span>

<span data-ttu-id="e5629-116">Para ver este informe, en el explorador, elija **Ver** > **malware**de**correo electrónico** > .</span><span class="sxs-lookup"><span data-stu-id="e5629-116">To view this report, in Explorer, choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="e5629-117">Esta vista muestra información sobre los mensajes de correo electrónico que se identificaron como que contenían malware.</span><span class="sxs-lookup"><span data-stu-id="e5629-117">This view shows information about email messages that were identified as containing malware.</span></span>  

![Ver datos sobre el correo electrónico identificado como malware](media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="e5629-119">Haga clic en **remitente** para abrir la lista de opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="e5629-119">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="e5629-120">Use esta lista para ver los datos del remitente, los destinatarios, el dominio del remitente, el asunto, la tecnología de detección, el estado de protección y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e5629-120">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="e5629-121">Por ejemplo, para ver qué acciones se han realizado en los mensajes de correo electrónico detectados, elija **Estado de protección** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e5629-121">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="e5629-122">Seleccione una opción y, a continuación, haga clic en el botón actualizar para aplicar ese filtro al informe.</span><span class="sxs-lookup"><span data-stu-id="e5629-122">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opciones de estado de la protección contra amenazas para el explorador de amenazas](media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="e5629-124">Debajo del gráfico, vea más detalles sobre mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="e5629-124">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="e5629-125">Al seleccionar un elemento de la lista, se abre un panel emergente en el que puede obtener más información sobre el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5629-125">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Explorador de amenazas con FLYOUT abierto](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="e5629-127">Correo electrónico > phish</span><span class="sxs-lookup"><span data-stu-id="e5629-127">Email > Phish</span></span>

<span data-ttu-id="e5629-128">Para ver este informe, en el explorador, elija **Ver** > **phishing**de**correo electrónico** > .</span><span class="sxs-lookup"><span data-stu-id="e5629-128">To view this report, in Explorer, choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="e5629-129">Esta vista muestra los mensajes de correo electrónico identificados como intentos de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e5629-129">This view shows email messages identified as phishing attempts.</span></span>  

![Ver datos sobre correo electrónico identificado como intentos de suplantación de identidad](media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="e5629-131">Haga clic en **remitente** para abrir la lista de opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="e5629-131">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="e5629-132">Use esta lista para ver los datos por remitente, destinatarios, dominio de remitente, IP del remitente, dominio de dirección URL, haga clic en veredicto, etc.</span><span class="sxs-lookup"><span data-stu-id="e5629-132">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="e5629-133">Por ejemplo, para ver las acciones que se realizaron cuando los usuarios hicieron clic en las direcciones URL que se identificaron como intentos de suplantación de identidad, elija **hacer clic** en el veredicto de la lista, seleccione una o más opciones y, a continuación, haga clic en el botón actualizar.</span><span class="sxs-lookup"><span data-stu-id="e5629-133">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Haga clic en opciones de veredicto del informe de phish](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="e5629-135">Debajo del gráfico, vea más detalles sobre mensajes específicos, clics de direcciones URL, URL y origen de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e5629-135">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![Direcciones URL detectadas como phish en los mensajes de correo electrónico](media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="e5629-137">Cuando se selecciona un elemento de la lista, como una dirección URL detectada, se abre un panel emergente en el que puede obtener más información sobre el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5629-137">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Detalles sobre una dirección URL detectada](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--user-reported"></a><span data-ttu-id="e5629-139">_GT_ de correo electrónico notificado por el usuario</span><span class="sxs-lookup"><span data-stu-id="e5629-139">Email > User-reported</span></span>

<span data-ttu-id="e5629-140">Para ver este informe, en el explorador, elija **Ver** > **correo electrónico** > **del usuario notificado**.</span><span class="sxs-lookup"><span data-stu-id="e5629-140">To view this report, in Explorer, choose **View** > **Email** > **User-reported**.</span></span> <span data-ttu-id="e5629-141">Esta vista muestra el correo electrónico que los usuarios han notificado como correo electrónico no deseado, no deseado o de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e5629-141">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![Mensajes de correo electrónico notificados por los usuarios](media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="e5629-143">Haga clic en **remitente** para abrir la lista de opciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="e5629-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="e5629-144">Use esta lista para ver información por remitente, destinatarios, tipo de informe (la determinación del usuario de que el correo electrónico era correo no deseado, correo deseado o phish), entre otros.</span><span class="sxs-lookup"><span data-stu-id="e5629-144">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="e5629-145">Por ejemplo, para ver información sobre los mensajes de correo electrónico que se han notificado como intentos de suplantación de identidad, haga clic en**tipo de informe**de **remitente** > , seleccione **phish**y, a continuación, haga clic en el botón actualizar.</span><span class="sxs-lookup"><span data-stu-id="e5629-145">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish seleccionado para filtro de tipo de informe](media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="e5629-147">Debajo del gráfico, vea más detalles sobre los mensajes de correo electrónico específicos, como la línea de asunto, la dirección IP del remitente, el usuario que notificó el mensaje como correo no deseado, correo deseado o phish, entre otros.</span><span class="sxs-lookup"><span data-stu-id="e5629-147">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![Mensajes que se notificaron como intentos de suplantación de identidad](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="e5629-149">Seleccione un elemento de la lista para ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="e5629-149">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="e5629-150">Correo electrónico > todo el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e5629-150">Email > All email</span></span>

<span data-ttu-id="e5629-151">Para ver este informe, en el explorador, elija **Ver** > \*\*\*\* > **todos los correos**electrónicos.</span><span class="sxs-lookup"><span data-stu-id="e5629-151">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="e5629-152">En esta vista se muestra una vista general de la actividad de correo electrónico, incluido el correo electrónico identificado como malintencionado debido a suplantación de identidad (phishing) o malware, así como a todo el correo no malintencionado (correo electrónico normal, correo no deseado y correo masivo).</span><span class="sxs-lookup"><span data-stu-id="e5629-152">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="e5629-153">Si recibe un error que lee **demasiados datos para mostrar**, agregue un filtro y, si es necesario, restrinja el intervalo de fechas que está viendo.</span><span class="sxs-lookup"><span data-stu-id="e5629-153">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="e5629-154">Para aplicar un filtro, elija **remitente**, seleccione un elemento de la lista y, a continuación, haga clic en el botón actualizar.</span><span class="sxs-lookup"><span data-stu-id="e5629-154">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="e5629-155">En nuestro ejemplo, utilizamos la **tecnología de detección** como filtro (hay varias opciones disponibles).</span><span class="sxs-lookup"><span data-stu-id="e5629-155">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="e5629-156">Ver información por remitente, dominio del remitente, destinatarios, asunto, nombre de archivo de datos adjuntos, familia de malware, estado de protección (acciones llevadas a cabo por las directivas y características de protección contra amenazas en Office 365), la tecnología de detección (cómo se detectó el malware) y adicional.</span><span class="sxs-lookup"><span data-stu-id="e5629-156">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Ver los datos sobre el correo electrónico detectado mediante la tecnología de detección](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="e5629-158">Debajo del gráfico, vea más detalles sobre los mensajes de correo electrónico específicos, como la línea de asunto, el destinatario, el remitente, el estado, etc.</span><span class="sxs-lookup"><span data-stu-id="e5629-158">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="e5629-159">Malware > de contenido</span><span class="sxs-lookup"><span data-stu-id="e5629-159">Content > Malware</span></span>

<span data-ttu-id="e5629-160">Para ver este informe, en el explorador, elija **Ver** > \*\*\*\* > **malware**de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5629-160">To view this report, in Explorer, choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="e5629-161">Esta vista muestra los archivos que se identificaron como malintencionados con la [protección contra amenazas avanzada de Office 365 en SharePoint Online, OneDrive para la empresa y Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e5629-161">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="e5629-162">Ver información por familia de malware, tecnología de detección (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o Teams).</span><span class="sxs-lookup"><span data-stu-id="e5629-162">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="e5629-164">Debajo del gráfico, vea más detalles sobre archivos específicos, como nombre de archivo de datos adjuntos, carga de trabajo, tamaño de archivo, quién modificó el archivo por última vez, etc.</span><span class="sxs-lookup"><span data-stu-id="e5629-164">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="e5629-165">Capacidades de hacer clic y filtrar</span><span class="sxs-lookup"><span data-stu-id="e5629-165">Click-to-filter capabilities</span></span>

<span data-ttu-id="e5629-166">Con el explorador, puede aplicar un filtro en un clic.</span><span class="sxs-lookup"><span data-stu-id="e5629-166">With Explorer, you can apply a filter in a click.</span></span> <span data-ttu-id="e5629-167">Haga clic en un elemento de la leyenda y ese elemento se convertirá en un filtro para el informe.</span><span class="sxs-lookup"><span data-stu-id="e5629-167">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="e5629-168">Por ejemplo, supongamos que estamos viendo la vista de malware en el explorador:</span><span class="sxs-lookup"><span data-stu-id="e5629-168">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="e5629-170">Al hacer clic en **detonaCiones ATP** en este gráfico, se obtiene una vista similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5629-170">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![El explorador está filtrado para mostrar solo los resultados de detonaciones de ATP](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="e5629-172">En esta vista, ahora miramos los datos de los archivos que se han enumerado con datos adJuntos [seguros de ATP de Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="e5629-172">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="e5629-173">Debajo del gráfico, podemos ver los detalles sobre los mensajes de correo electrónico específicos que tienen datos adjuntos detectados por los datos adJuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="e5629-173">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Detalles específicos sobre los mensajes de correo electrónico con datos adjuntos detectados](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="e5629-175">Al seleccionar uno o más elementos, se activa el menú **acciones** , que ofrece varias opciones entre las que elegir para los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="e5629-175">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Al seleccionar un elemento, se activa el menú acciones](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="e5629-177">La capacidad de filtrar en un clic y navegar a detalles específicos puede ahorrarle mucho tiempo para la investigación de las amenazas.</span><span class="sxs-lookup"><span data-stu-id="e5629-177">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="e5629-178">Consultas y filtros</span><span class="sxs-lookup"><span data-stu-id="e5629-178">Queries and filters</span></span>

<span data-ttu-id="e5629-179">Explorer tiene varios filtros y capacidades de consulta eficaces que le permiten profundizar en los detalles, como los usuarios de destino más importantes, las familias de malware principales, la tecnología de detección y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e5629-179">Explorer has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="e5629-180">Cada tipo de informe ofrece varias formas de ver y explorar los datos.</span><span class="sxs-lookup"><span data-stu-id="e5629-180">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5629-181">No use caracteres comodín, como un asterisco (\*) o un signo de interrogación (?), en la barra de consulta para Explorer.</span><span class="sxs-lookup"><span data-stu-id="e5629-181">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), in the query bar for Explorer.</span></span> <span data-ttu-id="e5629-182">Al buscar mensajes de correo electrónico en el campo asunto, el explorador realizará una coincidencia parcial y obtendrá resultados similares a una búsqueda con caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="e5629-182">When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

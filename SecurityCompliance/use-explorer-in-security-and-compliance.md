---
title: Use el explorador en la seguridad &amp; centro de cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: Obtenga información sobre el explorador (también denominado Explorador de amenaza) en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: c5b6273120c605cb4233f62b5c52c6a794e554eb
ms.sourcegitcommit: 0cc6083bd8cb2f7bbf18847149c6d5239f2a6403
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699933"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="d13c1-103">Use el explorador en la seguridad &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d13c1-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="d13c1-p101">Si su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), y tiene los permisos necesarios, puede usar el explorador para identificar y analizar las amenazas. Por ejemplo, puede identificar y eliminar el correo electrónico malintencionado que se entregó o vea malware que se capturó mediante las características de seguridad de Office 365. Explorer (también denominada Explorador de amenaza) es un potente cerca de informe en tiempo real en la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d13c1-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![Vaya a administración de amenaza \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="d13c1-108">Para usar el explorador, en la seguridad &amp; centro de cumplimiento, vaya a **administración de amenazas** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d13c1-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="d13c1-109">Introducción al explorador</span><span class="sxs-lookup"><span data-stu-id="d13c1-109">Explorer overview</span></span>

<span data-ttu-id="d13c1-p102">El explorador muestra información sobre malware sospechoso en el correo electrónico y los archivos de Office 365, así como otras amenazas de seguridad y riesgos para la organización. La primera vez que se abre el explorador, la vista predeterminada muestra las detecciones de malware de antivirus para los últimos 7 días. El explorador también puede mostrar seguridad características de protección en Office 365, incluidos [Vínculos seguros](atp-safe-links.md) y [Los datos adjuntos seguros](atp-safe-attachments.md) y se puede modificar para mostrar los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="d13c1-p102">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![El explorador muestra información acerca de los principales de malware y los usuarios de destino](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="d13c1-114">Use el menú Ver para cambiar la información que se muestra.</span><span class="sxs-lookup"><span data-stu-id="d13c1-114">Use the View menu to change what information is displayed.</span></span>
  
![El menú Ver para el explorador](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="d13c1-p103">El explorador tiene varias filtrado y consultar las funcionalidades que permiten explorar en profundidad detalles, como la parte superior había destinada a los usuarios, las familias de malware superior y más. Cada tipo de informe ofrece una variedad de posibilidades para ver y explorar datos.</span><span class="sxs-lookup"><span data-stu-id="d13c1-p103">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d13c1-p104">No utilice caracteres comodín, como un asterisco (\*) o un signo de interrogación (?), con el explorador. Al buscar en el campo Asunto de los mensajes de correo electrónico, el explorador realizará parciales resultados de coincidencia y rendimiento similares a una búsqueda con caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="d13c1-p104">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="d13c1-120">Correo electrónico \> Malware</span><span class="sxs-lookup"><span data-stu-id="d13c1-120">Email \> Malware</span></span>

<span data-ttu-id="d13c1-121">Esta vista muestra los mensajes de correo electrónico identificados como que contiene el malware.</span><span class="sxs-lookup"><span data-stu-id="d13c1-121">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="d13c1-122">Ver la información en el gráfico por familia de código malintencionado, dominio del remitente, IP del remitente, el estado de protección (acciones realizadas por sus características de protección de amenaza y directivas en Office 365) y tecnología de detección (cómo se detectó el malware).</span><span class="sxs-lookup"><span data-stu-id="d13c1-122">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="d13c1-124">Debajo del gráfico, ver detalles acerca de las familias de malware superior, parte superior había destinada a los usuarios y obtener más detalles acerca de los mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="d13c1-124">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="d13c1-125">Correo electrónico \> phishing</span><span class="sxs-lookup"><span data-stu-id="d13c1-125">Email \> Phish</span></span>

<span data-ttu-id="d13c1-126">Esta vista muestra los mensajes de correo electrónico identificados como los intentos de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="d13c1-126">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="d13c1-127">Ver la información de dominio del remitente, IP del remitente y el estado de protección (acciones realizadas por sus características de protección de amenaza y directivas en Office 365).</span><span class="sxs-lookup"><span data-stu-id="d13c1-127">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![Ver los datos de correo electrónico que se identificó como intentos de suplantación de identidad](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="d13c1-129">Debajo del gráfico, ver más detalles acerca de los mensajes específicos.</span><span class="sxs-lookup"><span data-stu-id="d13c1-129">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="d13c1-130">Correo electrónico \> indicado por el usuario</span><span class="sxs-lookup"><span data-stu-id="d13c1-130">Email \> User-reported</span></span>

<span data-ttu-id="d13c1-131">Esta vista muestra el correo electrónico que los usuarios han informado como no deseado, no correo no deseado o correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="d13c1-131">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="d13c1-132">Ver la información por tipo de informe (determinación de la del usuario que el correo electrónico es correo no deseado, no no deseado o phishing) y por el motivo de la entrega (motivos de por qué salió el correo electrónico a una ubicación específica, como una directiva de filtro de spam, una regla de flujo de correo, una lista de remitentes bloqueados, una lista de remitentes seguros, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="d13c1-132">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![Datos de vista acerca de los usuarios de correo electrónico enviados como correo no deseado, no no deseado o suplantación de identidad](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="d13c1-134">Debajo del gráfico, ver más detalles acerca de los mensajes de correo electrónico específica, como la línea de asunto, la dirección IP del remitente, el usuario que envió el mensaje como correo no deseado, no no deseado, o phishing y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d13c1-134">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="d13c1-135">Correo electrónico \> todo el correo</span><span class="sxs-lookup"><span data-stu-id="d13c1-135">Email \> All mail</span></span>

<span data-ttu-id="d13c1-136">Este vistas muestra una vista de total de actividad de correo electrónico, correo electrónico, con identificado como malintencionados de vencimiento para la suplantación de identidad o malware, además de todo el correo que no sean malintencionado (correo electrónico normal, correo no deseado y correo masivo).</span><span class="sxs-lookup"><span data-stu-id="d13c1-136">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="d13c1-137">Si recibe un error que lee **demasiado cantidad de datos para mostrar**, agregue un filtro y, si es necesario, restringir el intervalo de fechas que se está viendo.</span><span class="sxs-lookup"><span data-stu-id="d13c1-137">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="d13c1-p105">Para aplicar un filtro, elija **remitente**, seleccione un elemento en la lista y, a continuación, haga clic en el botón Actualizar. En nuestro ejemplo, hemos usado la **tecnología de detección** como un filtro (hay varias opciones disponibles). Ver la información de remitente, dominio del remitente, los destinatarios, asunto, nombre de archivo de datos adjuntos, familia de código malintencionado, el estado de protección (acciones realizadas por sus características de protección de amenaza y directivas en Office 365), tecnología de detección (cómo se detectó el malware), y más.</span><span class="sxs-lookup"><span data-stu-id="d13c1-p105">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Ver los datos de correo electrónico detectado por tecnología de detección](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="d13c1-142">Debajo del gráfico, ver más detalles acerca de los mensajes de correo electrónico específica, por ejemplo, la línea de asunto, destinatario, remitente, estado y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d13c1-142">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="d13c1-143">Contenido \> Malware</span><span class="sxs-lookup"><span data-stu-id="d13c1-143">Content \> Malware</span></span>

<span data-ttu-id="d13c1-144">Esta vista muestra los archivos que se han identificado como malintencionados en SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d13c1-144">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="d13c1-145">Ver la información por malware, detección tecnología de la familia (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o equipos).</span><span class="sxs-lookup"><span data-stu-id="d13c1-145">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="d13c1-147">Debajo del gráfico, ver más detalles acerca de los archivos específicos, como el nombre del archivo adjunto, carga de trabajo, el tamaño de archivo que se modificó por última vez el archivo y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d13c1-147">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="d13c1-148">(Nuevo)! Haga clic en para filtrar capacidades</span><span class="sxs-lookup"><span data-stu-id="d13c1-148">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="d13c1-p106">El explorador es la capacidad de hacer clic para filtrar. A partir de las últimas de 2018 mayo, al hacer clic en un elemento de la leyenda, que el elemento se convierte en un filtro para el informe. Por ejemplo, suponga que buscamos en la vista de Malware en el explorador:</span><span class="sxs-lookup"><span data-stu-id="d13c1-p106">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Vaya a administración de amenaza \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="d13c1-153">Al hacer clic en **Detonación ATP** en los resultados de este gráfico en una vista como esta:</span><span class="sxs-lookup"><span data-stu-id="d13c1-153">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Explorador de filtrado para mostrar sólo los resultados de detonación ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="d13c1-p107">En esta vista, ahora observamos datos para los archivos que se han detonated por [Office 365 ATP los datos adjuntos seguros](atp-safe-attachments.md). Debajo del gráfico, podemos ver detalles acerca de los mensajes de correo electrónico específica que tenían datos adjuntos que se han detectado por los datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="d13c1-p107">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Detalles específicos acerca de los mensajes de correo electrónico con datos adjuntos detectados](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="d13c1-158">Al seleccionar uno o varios elementos, activa el menú **acciones** , que ofrece varias opciones desde el que se elija para los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d13c1-158">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Al seleccionar un elemento, activa el menú Acciones](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="d13c1-160">La capacidad de filtrar en un clic y desplazarse por los detalles específicos puede guardar una gran cantidad de tiempo en investigar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="d13c1-160">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="d13c1-161">¿Cómo se puede obtener el explorador?</span><span class="sxs-lookup"><span data-stu-id="d13c1-161">How do I get Explorer?</span></span>

<span data-ttu-id="d13c1-162">El explorador se incluye en la [Información sobre amenazas de Office 365](office-365-ti.md).</span><span class="sxs-lookup"><span data-stu-id="d13c1-162">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="d13c1-p108">Debe tener los permisos adecuados, como los concedidos a un administrador de seguridad o el lector de seguridad, a fin de ver y usar el explorador. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d13c1-p108">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d13c1-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d13c1-165">Related topics</span></span>

[<span data-ttu-id="d13c1-166">Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d13c1-166">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d13c1-167">Buscar e investigar el correo electrónico malintencionado que se entregó (Office 365 información sobre amenazas)</span><span class="sxs-lookup"><span data-stu-id="d13c1-167">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="d13c1-168">Protección contra correo electrónico no deseado y antimalware en Office 365</span><span class="sxs-lookup"><span data-stu-id="d13c1-168">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  


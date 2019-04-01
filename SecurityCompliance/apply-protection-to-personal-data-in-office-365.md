---
title: Aplicar protección a los datos personales de Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Obtenga información sobre cómo usar las directivas DLP para proteger datos personales en Office 365.
ms.openlocfilehash: 97a8c584cd010ae10a0416e47d8184c84f1e1ab9
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001003"
---
# <a name="apply-protection-to-personal-data-in-office-365"></a><span data-ttu-id="94b12-103">Aplicar protección a los datos personales de Office 365</span><span class="sxs-lookup"><span data-stu-id="94b12-103">Apply protection to personal data in Office 365</span></span>

<span data-ttu-id="94b12-104">La protección de información personal en Office 365 implica el uso de funciones de prevención de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-104">Protection of personal information in Office 365 includes using data loss prevention capabilities.</span></span> <span data-ttu-id="94b12-105">Con una directiva de prevención de pérdida de datos (DLP) del centro cumplimiento puede identificar, supervisar y proteger automáticamente información confidencial en todo Office 365.</span><span class="sxs-lookup"><span data-stu-id="94b12-105">With a data loss prevention (DLP) policy, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="94b12-p102">En este tema se describe cómo se usan las DLP para proteger los datos personales. Este tema también muestra otras capacidades de protección que pueden usarse para cumplir el RGPD, incluyendo la configuración de permisos en bibliotecas de SharePoint y el uso de directivas de acceso de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="94b12-p102">This topic describes how to use DLP to protect personal data. This topic also lists other protection capabilities that can be used to achieve GDPR compliance, including setting permissions in SharePoint libraries and using device access policies.</span></span>

## <a name="apply-protection-using-data-loss-prevention-in-office-365"></a><span data-ttu-id="94b12-108">Aplicar protección mediante la prevención de pérdida de datos en Office 365</span><span class="sxs-lookup"><span data-stu-id="94b12-108">Apply protection using data loss prevention in Office 365</span></span>

<span data-ttu-id="94b12-109">Con la DLP, puede:</span><span class="sxs-lookup"><span data-stu-id="94b12-109">With DLP, you can:</span></span>

-   <span data-ttu-id="94b12-110">Identificar información confidencial en varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="94b12-110">Identify sensitive information across many locations.</span></span>

-   <span data-ttu-id="94b12-111">Evitar el uso compartido accidental de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="94b12-111">Prevent accidental sharing of sensitive information.</span></span>

-   <span data-ttu-id="94b12-112">Ayudar a los usuarios a aprender a cumplir sin interrumpir el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="94b12-112">Help users learn how to stay compliant without interrupting their workflow.</span></span>

-   <span data-ttu-id="94b12-113">Ver informes de DLP con contenido que coincida con las directivas DLP de su organización.</span><span class="sxs-lookup"><span data-stu-id="94b12-113">View DLP reports showing content that matches your organization’s DLP policies.</span></span>

<span data-ttu-id="94b12-114">Para obtener más información, consulte [Información general sobre directivas de prevención de pérdida de datos](https://support.office.com/es-ES/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span><span class="sxs-lookup"><span data-stu-id="94b12-114">For more information, see [Overview of data loss prevention policies](https://support.office.com/es-ES/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span></span>

![Opciones para crear una directiva de prevención de pérdida de datos](Media/Apply-protection-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="94b12-116">Esta ilustración muestra las opciones para crear una directiva DLP:</span><span class="sxs-lookup"><span data-stu-id="94b12-116">This illustration shows the options for creating a DLP policy:</span></span>

-   <span data-ttu-id="94b12-p103">Elija la protección que se aplicará. La protección puede incluir:</span><span class="sxs-lookup"><span data-stu-id="94b12-p103">Choose the protection to apply. Protection can include:</span></span>

    -   <span data-ttu-id="94b12-119">Sugerencias de directiva para los usuarios</span><span class="sxs-lookup"><span data-stu-id="94b12-119">Policy tips for users</span></span>

    -   <span data-ttu-id="94b12-120">Informes de correo electrónico para los administradores</span><span class="sxs-lookup"><span data-stu-id="94b12-120">Email report for admins</span></span>

    -   <span data-ttu-id="94b12-121">Impedir el uso compartido externamente, internamente, o ambos</span><span class="sxs-lookup"><span data-stu-id="94b12-121">Prevent sharing externally, internally, or both</span></span>

-   <span data-ttu-id="94b12-p104">Elija los criterios para aplicar la protección. Aplique la protección a los documentos con este tipo de contenido: puede configurar la directiva para usar tipos de información confidencial o etiquetas.</span><span class="sxs-lookup"><span data-stu-id="94b12-p104">Choose the criteria for applying the protection. Apply the protection to documents with this type of content: you can configure the policy to use sensitive information types and/or labels.</span></span>

### <a name="using-dlp-for-gdpr-compliance"></a><span data-ttu-id="94b12-124">Uso de DLP para el cumplimiento de RGPD</span><span class="sxs-lookup"><span data-stu-id="94b12-124">Using DLP for GDPR compliance</span></span>

<span data-ttu-id="94b12-p105">Uno de los usos principales de DLP de Office 365 es identificar datos personales relacionados con temas de datos de la UE en su entorno de Office 365. DLP de Office 365 puede notificar a sus equipos de cumplimiento dónde se almacena información personal en SharePoint Online y OneDrive para la Empresa o cuándo los usuarios envían correo electrónico con información personal. DLP puede proporcionar sugerencias de directiva a sus empleados cuando trabajan con información personal de residentes de la UE.</span><span class="sxs-lookup"><span data-stu-id="94b12-p105">One of the primary uses of Office 365 DLP is to identify personal data related to EU data subjects in your Office 365 environment. Office 365 DLP can notify your compliance teams of where personal information is stored in SharePoint Online and OneDrive for Business, or when users send email containing personal information. DLP can also provide policy tips to your employees when working with personal information related to EU residents.</span></span>

<span data-ttu-id="94b12-p106">Instruir y aumentar el conocimiento sobre dónde se almacenan los datos de residentes de la UE en su entorno y cómo sus empleados pueden administrarlos representa un nivel de protección de información con DLP de Office 365. A menudo, los empleados que ya tengan acceso a este tipo de información requieren este acceso para realizar su trabajo diario. Al aplicar directivas DLP para ayudar a cumplir con el RGPD no necesitará restringir el acceso.</span><span class="sxs-lookup"><span data-stu-id="94b12-p106">Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP. Often, employees who already have access to this type of information require this access to perform their day to day work. Enforcing DLP policies to help comply with GDPR may not require restricting access.</span></span>

<span data-ttu-id="94b12-p107">Sin embargo, el cumplimiento del RGPD normalmente implica una evaluación de riesgos de la organización desde la perspectiva de la seguridad de la información y legal, la identificación de qué tipo de información personal se almacena y dónde, así como si hay una justificación legal para almacenar y procesar la información. Con esta evaluación, implementar directivas para proteger la organización y cumplir con el RGPD puede hacer necesario quitar el acceso de los empleados a los documentos que contengan información personal para temas de datos de la UE. En los casos donde se requiera protección adicional, puede configurar protección adicional de DLP.</span><span class="sxs-lookup"><span data-stu-id="94b12-p107">However, complying with GDPR typically involves a risk based assessment of the organization from both a legal and information security perspective, identification of what type and where personal information is stored, as well as if there is a legal justification to store and process that information. Based on this assessment, implementing policies to protect the organization and comply with GDPR might require removing access for employees to documents that contain personal information for EU data subjects. In cases where further protection is required, additional DLP protection can be configured.</span></span>

<span data-ttu-id="94b12-p108">En la siguiente tabla se muestran tres configuraciones para incrementar la protección mediante DLP. La primera configuración, reconocimiento, puede usarse como punto mínimo inicial y nivel de protección para RGPD.</span><span class="sxs-lookup"><span data-stu-id="94b12-p108">The following table lists three configurations of increasing protection using DLP. The first configuration, awareness, can be used as a starting point and minimum level of protection for GDPR.</span></span>

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a><span data-ttu-id="94b12-136">Ejemplo de niveles de protección que pueden configurarse con directivas DLP y utilizarse para el cumplimiento de RGPD</span><span class="sxs-lookup"><span data-stu-id="94b12-136">Example protection levels that can be configured with DLP policies and used for GDPR compliance</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94b12-137"><strong>Nivel de protección</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-137"><strong>Protection level</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-138"><strong>Configuración de DLP para documentos con información personal relacionada con datos de la UE</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-138"><strong>DLP configuration for documents with personal information related to EU data subjects</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-139"><strong>Beneficios y riesgos</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-139"><strong>Benefits and risks</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-140">Reconocimiento</span><span class="sxs-lookup"><span data-stu-id="94b12-140">Awareness</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-141">Envíe notificaciones por correo electrónico a equipos de cumplimiento cuando estos datos se encuentren en documentos de SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="94b12-141">Send email notifications to compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business.</span></span></p>
<p><span data-ttu-id="94b12-142">Personalice y muestre sugerencias de directiva a los empleados en SharePoint y OneDrive para la Empresa al acceder a documentos que contienen datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-142">Customize and display Policy Tips to employees in SharePoint and OneDrive for Business when accessing documents containing this data.</span></span></p>
<p><span data-ttu-id="94b12-143">Detecte y notifique cuándo se comparten datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-143">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94b12-144">Informe al personal con equipos de cumplimiento, así como mediante los empleados, sobre dónde se almacenan los datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-144">Raise awareness with compliance teams as well as employees regarding where this data is stored.</span></span></p>
<p><span data-ttu-id="94b12-145">Forme a los empleados sobre la directiva corporativa para controlar documentos que contienen este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-145">Educate employees on corporate policy for handling documents containing this data.</span></span></p>
<p><span data-ttu-id="94b12-146">Impida que los empleados compartan datos de forma interna o externa.</span><span class="sxs-lookup"><span data-stu-id="94b12-146">Does not prevent employees from sharing this data internally or externally.</span></span></p>
<p><span data-ttu-id="94b12-147">Puede revisar los informes DLP de datos compartidos y decidir si quiere aumentar la protección.</span><span class="sxs-lookup"><span data-stu-id="94b12-147">You can review DLP reports for shared data and decide if you need to increase the protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-148">Evitar el uso compartido externo</span><span class="sxs-lookup"><span data-stu-id="94b12-148">Prevent external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-149">Restrinja el acceso a documentos que contienen estos datos en SharePoint Online y OneDrive para la Empresa cuando ese contenido se comparta con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="94b12-149">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared with external users.</span></span></p>
<p><span data-ttu-id="94b12-150">Evite el envío de correos electrónicos con documentos que contienen datos a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="94b12-150">Prevent sending emails with documents that contain this data to external recipients.</span></span></p>
<p><span data-ttu-id="94b12-151">Detecte y notifique cuándo se comparten datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-151">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94b12-152">Evite el uso compartido externo de datos y permita a los empleados trabajar con esos datos de forma interna.</span><span class="sxs-lookup"><span data-stu-id="94b12-152">Prevents external sharing of this data while allowing for employees to work with this data internally.</span></span></p>
<p><span data-ttu-id="94b12-153">Puede revisar los informes DLP de datos compartidos de forma interna y decidir si quiere aumentar la protección.</span><span class="sxs-lookup"><span data-stu-id="94b12-153">You can review DLP reports for internally shared data and decide if you need to increase this protection.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-154">Evitar el uso compartido interno y externo</span><span class="sxs-lookup"><span data-stu-id="94b12-154">Prevent internal and external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-155">Restrinja el acceso a documentos que contienen datos en SharePoint Online y OneDrive para la Empresa cuando ese contenido se comparta de forma interna o externa.</span><span class="sxs-lookup"><span data-stu-id="94b12-155">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared internally or externally.</span></span></p>
<p><span data-ttu-id="94b12-156">Evite enviar correos electrónicos que contienen datos a destinatarios internos o externos.</span><span class="sxs-lookup"><span data-stu-id="94b12-156">Prevent sending emails which contain this data to both internal and external recipients.</span></span></p></td>
<td align="left"><p><span data-ttu-id="94b12-157">Evita el uso compartido interno y externo de estos datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-157">Prevents internal and external sharing of this data.</span></span></p>
<p><span data-ttu-id="94b12-158">Es posible que los empleados puedan completar tareas que requieran el uso de estos datos.</span><span class="sxs-lookup"><span data-stu-id="94b12-158">Employees might not be able to complete tasks that require working with this data.</span></span></p>
<p><span data-ttu-id="94b12-159">Puede revisar los informes DLP de datos compartidos de forma interna o externa y decidir si es necesario entrenamiento para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="94b12-159">You can review DLP reports for internally or externally shared data and decide if end user training is needed.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-p109">Nota: A medida que aumentan los niveles de protección, la capacidad de los usuarios de acceder a información disminuirá en algunos casos y podría afectar a su productividad o capacidad para completar las tareas del día a día. Aumentar los niveles de protección implementando directivas que afectan a los empleados normalmente viene acompañado de aprendizaje para usuarios finales para instruirlos sobre las directivas de seguridad y procedimientos y ayudarles a seguir siendo productivos en un entorno más seguro.</span><span class="sxs-lookup"><span data-stu-id="94b12-p109">Note: As the levels of protection increase, the ability of users to access information will decrease in some cases, and could potentially impact their productivity or ability to complete day to day tasks. Increasing protection levels by implementing policies that impact employees is typically accompanied by end user training, educating users on new security policies and procedures to help them continue to be productive in a more secure environment.</span></span>

### <a name="example-dlp-policy-for-gdpr--awareness"></a><span data-ttu-id="94b12-162">Ejemplo de directiva DLP para RGPD: reconocimiento</span><span class="sxs-lookup"><span data-stu-id="94b12-162">Example DLP policy for GDPR — Awareness</span></span> 

<span data-ttu-id="94b12-163">Nombre: Reconocimiento de datos personales sujetos a RGPD.</span><span class="sxs-lookup"><span data-stu-id="94b12-163">Name: Awareness for personal data that is subject to GDPR.</span></span>

<span data-ttu-id="94b12-164">Descripción: muestre sugerencias de directiva a los empleados, notifique a los equipos de cumplimiento cuando se encuentran estos datos en documentos de SharePoint Online y OneDrive para la Empresa, detecte y notifique cuando estos datos se comparten fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="94b12-164">Description: Display policy tips to employees, notify compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business, detect and report when this data is being shared outside your organization.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94b12-165"><strong>Control</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-165"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-166"><strong>Configuración</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-166"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-167">Elegir qué información quiere proteger</span><span class="sxs-lookup"><span data-stu-id="94b12-167">Choose information to protect</span></span></td>
<td align="left"><span data-ttu-id="94b12-168">Seleccione una plantilla de directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="94b12-168">Select a Custom policy template.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-169">Ubicaciones</span><span class="sxs-lookup"><span data-stu-id="94b12-169">Locations</span></span></td>
<td align="left"><span data-ttu-id="94b12-170">Todas las ubicaciones en Office 365</span><span class="sxs-lookup"><span data-stu-id="94b12-170">All locations in Office 365</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-171">Encontrar contenido que incluya</span><span class="sxs-lookup"><span data-stu-id="94b12-171">Find content that contains</span></span></td>
<td align="left"><span data-ttu-id="94b12-172">Haga clic en "Editar" y agregue todos los tipos de información confidencial creados en su entorno.</span><span class="sxs-lookup"><span data-stu-id="94b12-172">Click ‘Edit’ and add all the sensitive information types you curated for your environment.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-173">Detectar si este contenido se comparte</span><span class="sxs-lookup"><span data-stu-id="94b12-173">Detect when this content is shared</span></span></td>
<td align="left"><span data-ttu-id="94b12-174">Active esta casilla y seleccione "con usuarios externos a la organización".</span><span class="sxs-lookup"><span data-stu-id="94b12-174">Check this box and select ‘with people outside my organization.’</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-175">Notificar a los usuarios cuando el contenido coincide con la configuración de directiva</span><span class="sxs-lookup"><span data-stu-id="94b12-175">Notify users when content matches the policy settings</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-176">Active esta casilla ("Mostrar sugerencias de directiva a los usuarios y enviarles una notificación por correo electrónico".)</span><span class="sxs-lookup"><span data-stu-id="94b12-176">Check this box (“Show policy tips to users and send them an email notification.”)</span></span></p>
<p><span data-ttu-id="94b12-p110">Haga clic en "Personalizar la información y el correo electrónico" y adáptelos a su entorno. Consulte las notificaciones predeterminadas en este artículo: <a href="https://support.office.com/en-us/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Enviar notificaciones de correo electrónico y mostrar las sugerencias de directiva de directivas DLP</a>.</span><span class="sxs-lookup"><span data-stu-id="94b12-p110">Click ‘Customize the tip and email’ and update these for your environment. See the default notifications in this article: <a href="https://support.office.com/en-us/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Send email notifications and show policy tips for DLP policies</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-179">Detectar si se está compartiendo una cantidad determinada de información confidencial a la vez</span><span class="sxs-lookup"><span data-stu-id="94b12-179">Detect when a specific amount of sensitive info is being shared at one time</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-180">"Detectar el contenido que se está compartiendo que incluye: un mínimo de ___ instancias del mismo tipo de información confidencial": establézcalo en 1.</span><span class="sxs-lookup"><span data-stu-id="94b12-180">‘Detect when content that’s being shared contains: At least ____ instances of the same sensitive info type’ — Set this to 1.</span></span></p>
<p><span data-ttu-id="94b12-p111">"Enviar informes de incidentes por correo electrónico": active esta casilla. Haga clic en "Elegir qué incluir en el informe y quién lo recibe". Asegúrese de agregar al equipo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="94b12-p111">‘Send incident reports in email’ — check this box. Click ‘Choose what to include in the report and who receives it.’ Be sure to add your compliance team.</span></span></p>
<p><span data-ttu-id="94b12-184">"Restringir quién puede acceder al contenido e invalidar la directiva": desactive esta casilla para recibir notificaciones sobre información confidencial sin impedir que los usuarios accedan a esa información.</span><span class="sxs-lookup"><span data-stu-id="94b12-184">‘Restrict who can access the content and override the policy’ — clear this checkbox to receive notifications about sensitive information without preventing users from access that information.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-185">“Todas las ubicaciones” incluye:</span><span class="sxs-lookup"><span data-stu-id="94b12-185">All locations includes:</span></span>

-   <span data-ttu-id="94b12-186">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="94b12-186">SharePoint Online</span></span>

-   <span data-ttu-id="94b12-187">Cuentas de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="94b12-187">OneDrive for Business accounts</span></span>

-   <span data-ttu-id="94b12-188">Buzones de Exchange</span><span class="sxs-lookup"><span data-stu-id="94b12-188">Exchange mailboxes</span></span>

<span data-ttu-id="94b12-189">Dado que la búsqueda de contenido actualmente no permite comprobar los tipos de información confidencial con el correo electrónico, considere la posibilidad de crear directivas independientes de Exchange con un subconjunto de tipos de información confidencial de cada directiva y supervisar la implementación de estas directivas.</span><span class="sxs-lookup"><span data-stu-id="94b12-189">Because Content Search doesn’t currently let you test sensitive information types with email,consider creating separate policies for Exchange with a subset of sensitive information types in each policy and monitoring the rollout of these policies.</span></span>

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-office-365"></a><span data-ttu-id="94b12-190">Protección adicional que puede aplicar para proteger los datos personales de Office 365</span><span class="sxs-lookup"><span data-stu-id="94b12-190">Additional protection you can apply to protect personal data in Office 365</span></span>

<span data-ttu-id="94b12-p112">Las directivas de protección de pérdida de datos, las etiquetas y los tipos de información confidencial le ayudan a identificar los documentos que contienen datos específicos y a aplicar la protección. Sin embargo, estas protecciones dependen de que se configuren los permisos adecuados para el acceso a datos, de que las cuentas de usuario no estén en peligro y de que los dispositivos estén en buen estado.</span><span class="sxs-lookup"><span data-stu-id="94b12-p112">Sensitive information types, labels, and data loss protection policies help you identify documents containing specific data and apply protection. However, these protections depend on appropriate permissions being set for access to data, users with accounts that are not compromised, and devices that are healthy.</span></span>

<span data-ttu-id="94b12-193">En la siguiente ilustración se detalla protección adicional que puede aplicar para proteger el acceso a datos personales.</span><span class="sxs-lookup"><span data-stu-id="94b12-193">The following illustration details additional protection you can apply to protect access to personal data.</span></span>

![Protección adicional para proteger el acceso a datos personales](Media/Apply-protection-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="94b12-195">Para la accesibilidad, la siguiente tabla contiene la misma información que la ilustración.</span><span class="sxs-lookup"><span data-stu-id="94b12-195">For accessibility, the following table provides the same information in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94b12-196"><strong>Ámbito de protección</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-196"><strong>Scope of protection</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-197"><strong>Capacidades</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-197"><strong>Capabilities</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-198">Protección de documentos y de correo electrónico (incluye el correo en tránsito, pero no los buzones en reposo actualmente)</span><span class="sxs-lookup"><span data-stu-id="94b12-198">Document and email-level protection (includes mail in transit, but not currently mailboxes at rest)</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-199">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="94b12-199">Sensitive information types</span></span></p>
<p><span data-ttu-id="94b12-200">Etiquetas de Office</span><span class="sxs-lookup"><span data-stu-id="94b12-200">Office labels</span></span></p>
<p><span data-ttu-id="94b12-201">Directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="94b12-201">Data loss prevention policies</span></span></p>
<p><span data-ttu-id="94b12-202">Preguntas más frecuentes sobre el cifrado de mensajes para correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="94b12-202">Office 365 Message Encryption for email</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-203">Protección de sitios y bibliotecas (incluye SharePoint Online y OneDrive para la Empresa)</span><span class="sxs-lookup"><span data-stu-id="94b12-203">Site and library-level protection (includes SharePoint Online and OneDrive for Business sites)</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-204">Permisos para bibliotecas y sitios de SharePoint Online y OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="94b12-204">Permissions for SharePoint Online and OneDrive for Business sites and libraries</span></span></p>
<p><span data-ttu-id="94b12-205">Directivas de uso compartido externo para SharePoint Online y OneDrive para la Empresa (nivel de sitio)</span><span class="sxs-lookup"><span data-stu-id="94b12-205">External sharing policies for SharePoint Online and OneDrive for Business (site-level)</span></span></p>
<p><span data-ttu-id="94b12-206">Directivas de acceso a dispositivos de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="94b12-206">Site-level device access policies</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-207">Protección de acceso de servicio (incluye el acceso a todos los servicios de Office 365)</span><span class="sxs-lookup"><span data-stu-id="94b12-207">Service access protection (includes access to all services in Office 365)</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-208">Protección de acceso a dispositivo e identidad en el conjunto de aplicaciones Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="94b12-208">Identity and device access protection in Enterprise Mobility + Security (EMS) suite</span></span></p>
<p><span data-ttu-id="94b12-209">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="94b12-209">Privileged access management</span></span></p>
<p><span data-ttu-id="94b12-210">Funciones de seguridad de Windows 10</span><span class="sxs-lookup"><span data-stu-id="94b12-210">Windows 10 security capabilities</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-211">En el resto de este artículo se proporciona más información sobre cada una de estas categorías de protección.</span><span class="sxs-lookup"><span data-stu-id="94b12-211">The rest of this article provides more information on each of these categories of protection.</span></span>

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a><span data-ttu-id="94b12-212">Funcionalidades que puede usar con RGPD</span><span class="sxs-lookup"><span data-stu-id="94b12-212">Capabilities that are OK to use with GDPR</span></span>

<span data-ttu-id="94b12-p113">Puede usar las siguientes funcionalidades en un entorno configurado para el cumplimiento del RGPD. Estas funcionalidades no son necesarias para el cumplimiento del RGPD, pero se pueden usar sin afectar negativamente a su capacidad para descubrir, proteger, supervisar e informar sobre los datos relacionados con el cumplimiento del RGPD.</span><span class="sxs-lookup"><span data-stu-id="94b12-p113">You can use the following capabilities in an environment configured for GDPR compliance. These capabilities are not necessary for GDPR compliance, but they can be used without adversely affecting your ability to discover, protect, monitor, and report on data related to GDPR compliance.</span></span>

<span data-ttu-id="94b12-p114">Clave de cliente: permite a los clientes proporcionar y mantener el control sobre las claves de cifrado que se usan para cifrar los datos almacenados en Office 365. Se recomienda solo para los clientes con una necesidad normativa de administrar sus propias claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="94b12-p114">Customer Key — Allows customers to provide and retain control over the encryption keys that are used to encrypt data at rest within Office 365. Recommended only for customers with a regulatory need to manage their own encryption keys.</span></span>

<span data-ttu-id="94b12-p115">Caja de seguridad del cliente: la Caja de seguridad del cliente le permite controlar cómo un ingeniero de soporte técnico de Microsoft accede a los datos, si es necesario, para solucionar un problema técnico de forma individual. Puede controlar si quiere permitir que el ingeniero de soporte técnico acceda a los datos o no. Se proporciona una fecha de expiración con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="94b12-p115">Customer Lockbox — Customer lockbox allows you to control how a Microsoft support engineer accesses your data, if needed, to fix a technical issue on a case by case basis. You can control whether to give the support engineer access to your data or not. An expiration time is provided with each request.</span></span>

## <a name="site-and-library-level-protection"></a><span data-ttu-id="94b12-220">Protección de bibliotecas y sitios</span><span class="sxs-lookup"><span data-stu-id="94b12-220">Site and library-level protection</span></span>

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="94b12-221">Permisos para bibliotecas de SharePoint y OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="94b12-221">Permissions for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="94b12-p116">Use los permisos de SharePoint para proporcionar o restringir el acceso de usuarios al sitio o a su contenido. Agregue usuarios individuales o grupos de Azure Active Directory a los grupos de SharePoint predeterminados, o bien cree un grupo personalizado para obtener un control más preciso.</span><span class="sxs-lookup"><span data-stu-id="94b12-p116">Use permissions in SharePoint to provide or restrict user access to the site or its contents. Add individual users or Azure Active Directory groups to the default SharePoint groups. Or, create a custom group for finer-grain control.</span></span>

![Niveles de permisos de control total a solo vista](Media/Apply-protection-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="94b12-p117">La ilustración indica los niveles de permisos de control total a solo vista. La siguiente tabla contiene la misma información.</span><span class="sxs-lookup"><span data-stu-id="94b12-p117">The illustration plots permission levels from Full control to View Only. The following table includes the same information.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94b12-228"><strong>Control total</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-228"><strong>Full Control</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-229"><strong>Diseño</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-229"><strong>Design</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-230"><strong>Editar</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-230"><strong>Edit</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-231"><strong>Colaborar</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-231"><strong>Contribute</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-232"><strong>Lectura</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-232"><strong>Read</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-233"><strong>Solo vista</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-233"><strong>View Only</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="94b12-234">Colaborar, aprobar y personalizar</span><span class="sxs-lookup"><span data-stu-id="94b12-234">Contribute + approve and customize</span></span></td>
<td align="left"><span data-ttu-id="94b12-235">Colaborar, agregar, editar y eliminar listas (no solo elementos)</span><span class="sxs-lookup"><span data-stu-id="94b12-235">Contribute + add, edit and delete lists (not just list items)</span></span></td>
<td align="left"><span data-ttu-id="94b12-236">Ver, agregar, actualizar y eliminar elementos de lista y documentos</span><span class="sxs-lookup"><span data-stu-id="94b12-236">View, add, update, delete list items and documents</span></span></td>
<td align="left"><span data-ttu-id="94b12-237">Ver y descargar</span><span class="sxs-lookup"><span data-stu-id="94b12-237">View and download</span></span></td>
<td align="left"><span data-ttu-id="94b12-238">Ver sin descargar</span><span class="sxs-lookup"><span data-stu-id="94b12-238">View, no download</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-239">Más información:</span><span class="sxs-lookup"><span data-stu-id="94b12-239">More information:</span></span>

-   [<span data-ttu-id="94b12-240">Información sobre los niveles de permisos en SharePoint</span><span class="sxs-lookup"><span data-stu-id="94b12-240">Understanding permission levels in SharePoint</span></span>](https://support.office.com/es-ES/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [<span data-ttu-id="94b12-241">Información sobre los grupos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="94b12-241">Understanding SharePoint groups</span></span>](https://support.office.com/es-ES/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="94b12-242">Directivas de uso compartido externo para las bibliotecas de SharePoint y OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="94b12-242">External sharing policies for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="94b12-p118">Muchas organizaciones permiten el uso compartido para admitir la colaboración. Descubra cómo se configuran las opciones aplicables a todo el inquilino. Después, revise la configuración de uso compartido externo para los sitios que contienen datos personales.</span><span class="sxs-lookup"><span data-stu-id="94b12-p118">Many organizations allow external sharing to support collaboration. Find out how your tenant-wide settings are configured. Then review the external sharing settings for sites that contain personal data.</span></span>

<span data-ttu-id="94b12-246">Un usuario externo es alguien de fuera de la organización que está invitado para acceder a sus sitios y documentos de SharePoint Online pero no tiene una licencia para su suscripción a SharePoint Online o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="94b12-246">An external user is someone outside of your organization who is invited to access your SharePoint Online sites and documents but does not have a license for your SharePoint Online or Microsoft Office 365 subscription.</span></span>

<span data-ttu-id="94b12-247">Las directivas de uso compartido externo se aplican a SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="94b12-247">External sharing policies apply to both SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="94b12-248">Debe ser administrador de SharePoint Online para configurar las directivas de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="94b12-248">You must be a SharePoint Online admin to configure sharing policies.</span></span>

-   <span data-ttu-id="94b12-249">Debe ser propietario del sitio o tener permisos de control total para compartir un sitio o documentos con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="94b12-249">You must be a Site Owner or have full control permissions to share a site or document with external users.</span></span>

<span data-ttu-id="94b12-250">En la siguiente tabla se resumen los controles que puede configurar.</span><span class="sxs-lookup"><span data-stu-id="94b12-250">The following table summarizes the controls you can configure.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94b12-251"><strong>Categoría de control</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-251"><strong>Control category</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-252"><strong>Opciones</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-252"><strong>Options</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-253">Tipo de uso compartido</span><span class="sxs-lookup"><span data-stu-id="94b12-253">Type of sharing</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-254">No permitir el uso compartido fuera de su organización (puede establecerse para colecciones de sitios individuales)</span><span class="sxs-lookup"><span data-stu-id="94b12-254">Don’t allow sharing outside your organization (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="94b12-255">Permitir el uso compartido solo para usuarios externos autenticados (permitir nuevos o limitar existentes, puede establecerse para colecciones de sitios individuales)\*</span><span class="sxs-lookup"><span data-stu-id="94b12-255">Allow sharing to authenticated external users only (allow new or limit to existing, can be set for individual site collections)\*</span></span></p>
<p><span data-ttu-id="94b12-256">Permitir el uso compartido con usuarios externos con un vínculo de acceso anónimo (puede establecerse para colecciones de sitios individuales)</span><span class="sxs-lookup"><span data-stu-id="94b12-256">Allow sharing to external users with an anonymous access link (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="94b12-257">Limitar el uso compartido externo mediante dominios (lista de permitidos y denegados)</span><span class="sxs-lookup"><span data-stu-id="94b12-257">Limit external sharing using domains (allow and deny list)</span></span></p>
<p><span data-ttu-id="94b12-258">Elegir el tipo de vínculo predeterminado (anónimo, para compartir en la empresa o restringido)</span><span class="sxs-lookup"><span data-stu-id="94b12-258">Choose the default link type (anonymous, company shareable, or restricted)</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-259">Qué pueden hacer los usuarios externos</span><span class="sxs-lookup"><span data-stu-id="94b12-259">What external users can do</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-260">Evitar que los usuarios externos puedan compartir archivos, carpetas, o sitios de los que no son propietarios</span><span class="sxs-lookup"><span data-stu-id="94b12-260">Prevent external users from sharing files, folders, sites they don’t own</span></span></p>
<p><span data-ttu-id="94b12-261">Requerir que los usuarios externos acepten invitaciones de uso compartido con la misma cuenta a la que se envió la invitación</span><span class="sxs-lookup"><span data-stu-id="94b12-261">Require external users to accept sharing invitations with the same account the invitation was sent to</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-262">Notificaciones</span><span class="sxs-lookup"><span data-stu-id="94b12-262">Notifications</span></span></td>
<td align="left"><p><span data-ttu-id="94b12-p119">Actualmente, solo está disponible en OneDrive para la Empresa. Envíe una notificación a los propietarios cuando:</span><span class="sxs-lookup"><span data-stu-id="94b12-p119">Currently only available in OneDrive for Business. Notify owners when:</span></span></p>
- <p><span data-ttu-id="94b12-265">Los usuarios invitan a otros usuarios externos a los archivos compartidos</span><span class="sxs-lookup"><span data-stu-id="94b12-265">Users invite additional external users to shared files</span></span></p>
- <p><span data-ttu-id="94b12-266">Los usuarios externos aceptan invitaciones de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="94b12-266">External users accept invitations to access files</span></span></p>
- <p><span data-ttu-id="94b12-267">Se crea o modifica un vínculo de acceso anónimo</span><span class="sxs-lookup"><span data-stu-id="94b12-267">An anonymous access link is created or changed</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-268">Más información:</span><span class="sxs-lookup"><span data-stu-id="94b12-268">More information:</span></span>

-   <span data-ttu-id="94b12-269">
  [Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="94b12-269">[Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)</span></span>

-   [<span data-ttu-id="94b12-270">Compartir documentos o sitios con personas fuera de su organización</span><span class="sxs-lookup"><span data-stu-id="94b12-270">Share sites or documents with people outside your organization</span></span>](https://support.office.com/es-ES/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a><span data-ttu-id="94b12-271">Directivas de acceso a dispositivos de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="94b12-271">Site-level device access policies</span></span>

<span data-ttu-id="94b12-p120">SharePoint Online y OneDrive para la Empresa le permiten configurar directivas de acceso de dispositivo a nivel de sitio. Esto le permite configurar más protección para sitios con datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="94b12-p120">SharePoint Online and OneDrive for Business let you configure device access policies at the site level. This lets you configure more protection for sites with sensitive data.</span></span>

<span data-ttu-id="94b12-274">Si configura directivas de acceso de dispositivo de nivel de sitio, no olvide coordinarlas con directivas de nivel de inquilino y con las directivas de acceso que se configuran en Azure Active Directory, Intune e Intune App Management.</span><span class="sxs-lookup"><span data-stu-id="94b12-274">If you configure site-level device access policies, be sure to coordinate these with tenant-level policies and also with access policies that are configured in Azure Active Directory, Intune, and Intune App Management.</span></span>

<span data-ttu-id="94b12-p121">Las directivas de acceso de dispositivo para SharePoint y OneDrive para la empresa la compatibilidad con directivas en Azure Active Directory y Microsoft Intune según el escenario que va a implementar. En la siguiente tabla se resumen los objetivos que puede conseguir con las directivas de acceso de dispositivo y se indica qué productos requieren la compatibilidad con directivas.</span><span class="sxs-lookup"><span data-stu-id="94b12-p121">Device access policies for SharePoint and OneDrive for Business require supporting policies in Azure Active Directory and Microsoft Intune depending on the scenario you are implementing. The following table summarizes objectives you can achieve with device access policies and indicates which products require supporting policies.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="94b12-277">Solo permitir el acceso desde ubicaciones de direcciones IP específicas</span><span class="sxs-lookup"><span data-stu-id="94b12-277">Only allow access from specific IP address locations</span></span></th>
<th align="left"><span data-ttu-id="94b12-278">Impedir que los usuarios descarguen archivos en dispositivos de dominios no combinados</span><span class="sxs-lookup"><span data-stu-id="94b12-278">Prevent users from downloading files to non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="94b12-279">Bloquear el acceso en los dispositivos sin dominios combinados</span><span class="sxs-lookup"><span data-stu-id="94b12-279">Block access on non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="94b12-280">Impedir que los usuarios descarguen archivos en dispositivos no compatibles</span><span class="sxs-lookup"><span data-stu-id="94b12-280">Prevent users from downloading files to non-compliant devices</span></span></th>
<th align="left"><span data-ttu-id="94b12-281">Bloquear el acceso de dispositivos no compatibles</span><span class="sxs-lookup"><span data-stu-id="94b12-281">Block access on non-compliant devices</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-282">Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="94b12-282">SharePoint admin center</span></span></td>
<td align="left"><span data-ttu-id="94b12-283">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-283">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-284">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-284">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-285">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-285">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-286">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-286">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-287">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-287">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-288">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="94b12-288">Azure Active Directory</span></span></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="94b12-289">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-289">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-290">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-290">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-291">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-291">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-292">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-292">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-293">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="94b12-293">Microsoft Intune</span></span></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="94b12-294">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-294">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-295">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-295">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-296">Más información: [Centro de administración de SharePoint Online: Controlar el acceso desde dispositivos no administrados](https://support.office.com/en-us/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="94b12-296">More information: [SharePoint Online admin center: Control access from unmanaged devices](https://support.office.com/en-us/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="service-access-protection-for-identities-and-devices"></a><span data-ttu-id="94b12-297">Protección de acceso a servicios de identidades y dispositivos</span><span class="sxs-lookup"><span data-stu-id="94b12-297">Service access protection for identities and devices</span></span>

<span data-ttu-id="94b12-p122">Microsoft le recomienda que configure la protección de identidades y dispositivos que acceden al servicio. El esfuerzo de proteger el acceso a servicios de Office 365 también puede usarse para proteger el acceso a otros servicios SaaS, servicios PaaS e incluso aplicaciones de otros proveedores de nube.</span><span class="sxs-lookup"><span data-stu-id="94b12-p122">Microsoft recommends you configure protection for identities and devices that access the service. The work you put into protecting access to Office 365 services can also be used to protect access to other SaaS services, PaaS services, and even apps in other cloud providers.</span></span>

<span data-ttu-id="94b12-300">La protección de acceso para identidades y dispositivos proporciona una línea base de protección para asegurarse de que las identidades no están en peligro, los dispositivos son seguros y los datos de la organización a los que se acceden desde dispositivos están aislados y protegidos.</span><span class="sxs-lookup"><span data-stu-id="94b12-300">Access protection for identities and devices provides a baseline of protection to ensure that identities are not compromised, devices are safe, and organization data that is accessed on devices is isolated and protected.</span></span>

<span data-ttu-id="94b12-301">Para ver recomendaciones para comenzar e instrucciones de configuración, consulte [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](https://docs.microsoft.com/es-ES/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="94b12-301">For starting point recommendations and configuration guidance, see [Microsoft security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/es-ES/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="94b12-302">Para entornos de identidad híbridos con AD FS, consulte [Opciones y directivas de seguridad recomendadas](https://docs.microsoft.com/es-ES/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="94b12-302">For hybrid identity environments with AD FS, see [Recommended security policies and configurations](https://docs.microsoft.com/es-ES/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="94b12-p123">En la siguiente ilustración se describe cómo se relacionan los servicios en la nube (SaaS, PaaS), los tipos de cuenta (cuentas de dominio de inquilino y cuentas B2B) y las funciones de acceso de servicio. Es importante que tenga en cuenta qué funciones pueden usarse con cuentas B2B.</span><span class="sxs-lookup"><span data-stu-id="94b12-p123">The following illustration describes how cloud services (SaaS, PaaS), account types (tenant domain accounts vs. B2B accounts) and service access capabilities relate. It’s important to note which capabilities can be used with B2B accounts.</span></span>

![Servicios en la nube, tipos de cuenta y las funciones de acceso](Media/Apply-protection-to-personal-data-in-Office-365-image4.png)

<span data-ttu-id="94b12-306">Para la accesibilidad, el resto de esta sección describe esta ilustración.</span><span class="sxs-lookup"><span data-stu-id="94b12-306">For accessibility, the rest of this section describes this illustration.</span></span>

### <a name="cloud-services"></a><span data-ttu-id="94b12-307">Servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="94b12-307">Cloud services</span></span>

<span data-ttu-id="94b12-p124">Azure Active Directory proporciona acceso de identidad a cualquier servicio de nube, incluidos los proveedores que no son de Microsoft como Amazon Web Services. La ilustración muestra Office 365, "Otras aplicaciones SaaS" y "Aplicación PaaS". Las flechas apuntan de Azure Active Directory a cada uno de estos servicios, lo que muestra que puede usarse Azure Active Directory para la autenticación de todos estos tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="94b12-p124">Azure Active Directory provides identity access to any cloud service, including non-Microsoft providers such as Amazon Web Services. The illustration shows Office 365, “Other SaaS app,” and “PaaS app.” Arrows point from Azure Active Directory to each of these services, showing that Azure Active Directory can be used for authentication to all of these app types.</span></span>

### <a name="types-of-accounts"></a><span data-ttu-id="94b12-311">Tipos de cuentas</span><span class="sxs-lookup"><span data-stu-id="94b12-311">Types of accounts</span></span>

<span data-ttu-id="94b12-p125">Las cuentas de dominio de inquilino son cuentas que agrega a su inquilino y administra directamente. Las cuentas B2B son cuentas de usuarios fuera de la organización a los que invita a colaborar. Pueden ser otras cuentas de Office 365, otras cuentas de la organización o cuentas de consumidor (como Gmail). En la ilustración se muestran dos tipos de cuenta en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94b12-p125">Tenant domain accounts are account you add to your tenant and manage directly. B2B accounts are accounts for users outside your organization you invite to collaborate with. These can be other Office 365 accounts, other organization accounts, or consumer accounts (such as Gmail). The illustration shows both account types within Azure Active Directory.</span></span>

### <a name="capabilities"></a><span data-ttu-id="94b12-316">Capacidades</span><span class="sxs-lookup"><span data-stu-id="94b12-316">Capabilities</span></span>

<span data-ttu-id="94b12-p126">Las capacidades de la siguiente tabla protegen las identidades y dispositivos. La tabla indica qué funcionalidades pueden usarse también con cuentas B2B, como en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="94b12-p126">The capabilities in the following table protect identities and devices. The table indicates which capabilities can also be used with B2B accounts, similar to the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="94b12-319"><strong>Función</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-319"><strong>Capability</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-320"><strong>Funciona con cuentas de dominio de inquilino</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-320"><strong>Works with tenant domain accounts</strong></span></span></th>
<th align="left"><span data-ttu-id="94b12-321"><strong>Funciona con cuentas B2B de Azure (sin licencia adicional)</strong></span><span class="sxs-lookup"><span data-stu-id="94b12-321"><strong>Works with Azure B2B accounts (without additional licensing)</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-322">Autenticación multifactor y acceso condicional</span><span class="sxs-lookup"><span data-stu-id="94b12-322">Multi-factor authentication and conditional access</span></span></td>
<td align="left"><span data-ttu-id="94b12-323">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-323">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-324">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-324">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-325">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="94b12-325">Azure AD Identity Protection</span></span></td>
<td align="left"><span data-ttu-id="94b12-326">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-326">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-327">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-327">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-328">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="94b12-328">Azure AD Privileged Identity Management</span></span></td>
<td align="left"><span data-ttu-id="94b12-329">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-329">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-330">Administración de aplicaciones (MAM)</span><span class="sxs-lookup"><span data-stu-id="94b12-330">Mobile Application Management (MAM)</span></span></td>
<td align="left"><span data-ttu-id="94b12-331">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-331">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="94b12-332">Inscripción y administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="94b12-332">Device enrollment and management</span></span></td>
<td align="left"><span data-ttu-id="94b12-333">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-333">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-334">Solo una organización puede administrar un dispositivo</span><span class="sxs-lookup"><span data-stu-id="94b12-334">Only one organization can manage a device</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="94b12-335">Funciones de seguridad de Windows 10 (el acceso condicional basado en el cumplimiento de dispositivo requiere la administración de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="94b12-335">Windows 10 security capabilities (conditional access based on device compliance requires device management)</span></span></td>
<td align="left"><span data-ttu-id="94b12-336">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-336">Yes</span></span></td>
<td align="left"><span data-ttu-id="94b12-337">Sí</span><span class="sxs-lookup"><span data-stu-id="94b12-337">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="94b12-338">Puede agregar licencias a cuentas B2B para conceder a estos usuarios funciones adicionales, si es necesario, para proteger el acceso a datos personales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="94b12-338">You can add licenses to B2B accounts to give these users additional capabilities, if needed, to protect access to personal data in your environment.</span></span>

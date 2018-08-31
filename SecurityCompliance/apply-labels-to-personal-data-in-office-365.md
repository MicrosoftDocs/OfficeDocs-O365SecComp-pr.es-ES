---
title: Aplicar etiquetas a datos personales en Office 365
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
ms.service: o365-solutions
localization_priority: Priority
ms.custom: ''
ms.assetid: ''
search.appverid:
- MET150
description: Aprenda a usar etiquetas de Office como parte de su plan de protección RGPD.
ms.openlocfilehash: 35fc3be6f2c98d6b7f6c4d6f6150eeef6d552437
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272345"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="b8763-103">Aplicar etiquetas a datos personales en Office 365</span><span class="sxs-lookup"><span data-stu-id="b8763-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="b8763-p101">Este tema puede serle útil si utiliza etiquetas de Office como parte de su plan de protección RGPD. Actualmente puede crear etiquetas en el Centro de seguridad y cumplimiento de Office 365 y en Azure Information Protection. Con el tiempo estas tecnologías se unirán en una experiencia de etiquetado y clasificación unificada y podrá hacer mucho más.</span><span class="sxs-lookup"><span data-stu-id="b8763-p101">Use this topic if you are using Office labels as part of your GDPR protection plan. Today labels can be created in the Office 365 Security & Compliance Center and in Azure Information Protection. Over time these technologies will converge into a unified labeling and classification experience and you will be able to achieve even more.</span></span>

<span data-ttu-id="b8763-p102">Si utiliza etiquetas para la protección de datos personales de Office 365, Microsoft le recomienda que empiece con las etiquetas de Office. Puede usar Gobierno de datos avanzado para aplicar automáticamente etiquetas basándose en tipos de información confidencial u otros criterios. También puede usar etiquetas de Office con la prevención de pérdida de datos para aplicar protección, y usarlas con eDiscovery y Búsqueda de contenido. Pronto podrá usar las etiquetas y tipos de información confidencial con Cloud App Security para supervisar datos personales en otras aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="b8763-p102">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with Office labels. You can use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria. You can use Office labels with data loss prevention to apply protection. You can also use labels with eDiscovery and Content Search. You’ll soon be able to use both labels and sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="b8763-p103">Las etiquetas de Azure Information Protection actualmente se recomiendan para aplicar etiquetas a archivos locales, y en otros proveedores y servicios en la nube. También se recomiendan para los archivos de Office 365 que requieren el cifrado de Azure Rights Management (Azure RMS) para proteger datos, como archivos de secreto empresarial.</span><span class="sxs-lookup"><span data-stu-id="b8763-p103">Azure Information Protection labels are currently recommended for applying labels to files on premises and in other cloud services and providers. These are also recommended for files in Office 365 that require Azure Rights Management (Azure RMS) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="b8763-p104">En este momento, no se recomienda usar Azure Information Protection para aplicar el cifrado de Azure RMS a archivos de Office 365 con datos que están sujetos al RGPD. Los servicios de Office 365 actualmente no pueden leer archivos cifrados de RMS. Por lo tanto, el servicio no puede encontrar los datos confidenciales en estos archivos.</span><span class="sxs-lookup"><span data-stu-id="b8763-p104">At this time, using Azure Information Protection to apply Azure RMS encryption is not recommended for files in Office 365 with data that is subject to the GDPR. Office 365 services currently cannot read into RMS-encrypted files. Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="b8763-p105">Pueden aplicarse las etiquetas de Azure Information Protection al correo en Exchange Online y estas son compatibles con la prevención de pérdida de datos de Office 365. Próximamente, la clasificación unificada y el motor de etiquetas permitirán usar las mismas etiquetas para correo electrónico y archivos, incluyendo etiquetar y proteger el correo electrónico en tránsito automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b8763-p105">Azure Information Protection labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention. Coming soon with the unified classification and labeling engine you will be able to use the same labels for email and files, including automatically labeling and protecting email in transit.</span></span>

![Etiquetas de Office 365 y de Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="b8763-120">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="b8763-120">In the illustration:</span></span>

-   <span data-ttu-id="b8763-121">Use las etiquetas de Office 365 para los datos personales y archivos secretos empresariales muy regulados en SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="b8763-121">Use Office 365 labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="b8763-122">Use las etiquetas de Azure Information Protection (AIP) para archivos secretos empresariales muy regulados, correo electrónico de Exchange Online, archivos en otros servicios SaaS, archivos en centros de datos locales y archivos de otros proveedores en la nube.</span><span class="sxs-lookup"><span data-stu-id="b8763-122">Use Azure Information Protection (AIP) labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>

-   <span data-ttu-id="b8763-123">Próximamente: ambos tipos de etiquetas convergerán en una experiencia de clasificación y etiquetado unificada.</span><span class="sxs-lookup"><span data-stu-id="b8763-123">Coming soon: both types of labels will converge into a unified classification and labeling experience.</span></span>

## <a name="use-office-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="b8763-124">Uso de etiquetas y tipos de información confidencial de Office en Microsoft 365 para la protección de información</span><span class="sxs-lookup"><span data-stu-id="b8763-124">Use Office labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="b8763-125">En la ilustración siguiente se muestra cómo pueden aprovecharse las etiquetas y los tipos de información confidencial de Office en las directivas de etiquetas, de prevención de pérdida de datos y de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b8763-125">The following illustration shows how Office labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Etiquetas y tipos de información confidencial de Office](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="b8763-127">Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="b8763-127">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8763-128"><strong>Elementos de clasificación</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-128"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="b8763-129"><strong>Directivas de etiqueta: 2 ejemplos</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-129"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="b8763-130"><strong>Directivas de prevención de pérdida de datos: 2 ejemplos</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-130"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="b8763-131"><strong>Directivas de Cloud App Security para todas las aplicaciones SaaS: 1 ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-131"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="b8763-p106">Etiquetas de Office. Ejemplos: personal, público, datos de clientes, datos de recursos humanos, confidencial, extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="b8763-p106">Office labels. Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="b8763-p107">Aplicar automáticamente esta etiqueta...</span><span class="sxs-lookup"><span data-stu-id="b8763-p107">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="b8763-137">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="b8763-137">Customer data</span></span></p>
<p><span data-ttu-id="b8763-p108">...a documentos que coincidan con estos tipos de información confidencial...</span><span class="sxs-lookup"><span data-stu-id="b8763-p108">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="b8763-144">&lt;lista de ejemplos de información confidencial disponibles&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-144">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8763-p109">Aplicar esta protección...</span><span class="sxs-lookup"><span data-stu-id="b8763-p109">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="b8763-148">&lt;definir la protección&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-148">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="b8763-p110">...a documentos con esta etiqueta...</span><span class="sxs-lookup"><span data-stu-id="b8763-p110">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="b8763-155">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="b8763-155">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8763-p111">Enviar alerta cuando los archivos con estos atributos...</span><span class="sxs-lookup"><span data-stu-id="b8763-p111">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="b8763-159">&lt;atributo DCP predefinido o expresión personalizada&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-159">&lt;predefined PII attribute -or- custom expression&gt;</span></span></p>
<p><span data-ttu-id="b8763-p112">...en cualquier aplicación de SaaS autorizada que se comparte fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="b8763-p112">. . . in any sanctioned SaaS app are shared outside the organization</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8763-p113">Tipos de información confidencial. Ejemplos: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="b8763-p113">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="b8763-p114">Publicar estas etiquetas para los usuarios para aplicar manualmente...</span><span class="sxs-lookup"><span data-stu-id="b8763-p114">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="b8763-169">&lt;seleccionar etiquetas&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-169">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="b8763-p115">...a estas ubicaciones...</span><span class="sxs-lookup"><span data-stu-id="b8763-p115">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="b8763-176">&lt;todas las ubicaciones o elegir ubicaciones específicas&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-176">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8763-p116">Aplicar esta protección...</span><span class="sxs-lookup"><span data-stu-id="b8763-p116">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="b8763-180">&lt;definir la protección&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-180">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="b8763-p117">...a documentos que coincidan con estos tipos de información confidencial&gt;</span><span class="sxs-lookup"><span data-stu-id="b8763-p117">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"><span data-ttu-id="b8763-185">Nota: Los atributos que estarán disponibles próximamente para Cloud App Security incluyen los tipos de información confidencial y las etiquetas unificadas de Office 365 en Office 365 y Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="b8763-185">Note: Attributes coming soon to Cloud App Security include Office 365 sensitive information types and Unified labels across Office 365 and Azure Information Protection.</span></span></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="b8763-186">Asignar prioridades a las directivas de etiqueta de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="b8763-186">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="b8763-p118">Para los datos personales que están sujetos a RGPD, Microsoft recomienda aplicar etiquetas automáticamente mediante tipos de información confidencial que gestione en su entorno. Es importante que las directivas de aplicación automática de etiquetas estén bien diseñadas y probadas para asegurar que se produce el comportamiento esperado.</span><span class="sxs-lookup"><span data-stu-id="b8763-p118">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="b8763-p119">El orden en que las directivas de aplicación automática se crean y si los usuarios también aplican estas etiquetas afectan al resultado. Por lo tanto, es importante planear cuidadosamente la distribución. Esto es lo que necesita saber.</span><span class="sxs-lookup"><span data-stu-id="b8763-p119">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="b8763-191">Una etiqueta de cada vez</span><span class="sxs-lookup"><span data-stu-id="b8763-191">One label at a time</span></span>

<span data-ttu-id="b8763-192">Solo puede aplicar una etiqueta a un documento.</span><span class="sxs-lookup"><span data-stu-id="b8763-192">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="b8763-193">Las directivas de aplicación automática antiguas tienen prioridad</span><span class="sxs-lookup"><span data-stu-id="b8763-193">Older auto-apply policies win</span></span>

<span data-ttu-id="b8763-p120">Si hay varias reglas que asignan una etiqueta de aplicación automática y el contenido cumple las condiciones de varias reglas, se asigna la etiqueta de la regla más antigua. Por este motivo, es importante planear minuciosamente las directivas de etiqueta antes de configurarlas. Si una organización necesita un cambio en la prioridad de las directivas de etiqueta, tendrá que eliminarlas y volver a crearlas.</span><span class="sxs-lookup"><span data-stu-id="b8763-p120">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="b8763-197">Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente</span><span class="sxs-lookup"><span data-stu-id="b8763-197">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="b8763-p121">Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente. Las directivas de aplicación automática no pueden reemplazar una etiqueta que ya ha aplicado un usuario. Los usuarios pueden reemplazar las etiquetas que se aplican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b8763-p121">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="b8763-201">Las etiquetas asignadas automáticamente pueden actualizarse</span><span class="sxs-lookup"><span data-stu-id="b8763-201">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="b8763-202">Las directivas de etiqueta más recientes o las actualizaciones de directivas existentes pueden actualizar etiquetas asignadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b8763-202">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="b8763-203">Asegúrese de que su plan para implementar etiquetas incluye:</span><span class="sxs-lookup"><span data-stu-id="b8763-203">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="b8763-204">Dar prioridad al orden en que se crean las directivas de aplicación automática.</span><span class="sxs-lookup"><span data-stu-id="b8763-204">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="b8763-p122">Permita el tiempo suficiente para que las etiquetas se apliquen automáticamente antes de implementarlas para que los usuarios las apliquen manualmente. Pueden ser necesarios hasta siete días para que las etiquetas se apliquen a todo el contenido que coincida con las condiciones.</span><span class="sxs-lookup"><span data-stu-id="b8763-p122">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="b8763-207">Prioridad de ejemplo para crear directivas de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="b8763-207">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8763-208"><strong>Etiquetas</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-208"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="b8763-209"><strong>Orden de prioridad para crear directivas de aplicación automática</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-209"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="b8763-210">Recursos humanos: datos de empleado</span><span class="sxs-lookup"><span data-stu-id="b8763-210">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="b8763-211">1</span><span class="sxs-lookup"><span data-stu-id="b8763-211">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8763-212">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="b8763-212">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="b8763-213">2</span><span class="sxs-lookup"><span data-stu-id="b8763-213">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b8763-214">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="b8763-214">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="b8763-215">3</span><span class="sxs-lookup"><span data-stu-id="b8763-215">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8763-216">Recursos humanos: datos de sueldo</span><span class="sxs-lookup"><span data-stu-id="b8763-216">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="b8763-217">4</span><span class="sxs-lookup"><span data-stu-id="b8763-217">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b8763-218">Confidencial</span><span class="sxs-lookup"><span data-stu-id="b8763-218">Confidential</span></span></td>
<td align="left"><span data-ttu-id="b8763-219">5</span><span class="sxs-lookup"><span data-stu-id="b8763-219">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="b8763-220">Público</span><span class="sxs-lookup"><span data-stu-id="b8763-220">Public</span></span></td>
<td align="left"><span data-ttu-id="b8763-221">6</span><span class="sxs-lookup"><span data-stu-id="b8763-221">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="b8763-222">Personal</span><span class="sxs-lookup"><span data-stu-id="b8763-222">Personal</span></span></td>
<td align="left"><span data-ttu-id="b8763-223">Directiva que no es de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="b8763-223">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="b8763-224">Crear etiquetas y aplicar directivas de etiqueta automáticamente</span><span class="sxs-lookup"><span data-stu-id="b8763-224">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="b8763-225">Cree etiquetas y directivas en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8763-225">Create labels and policies in the Security & Compliance Center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8763-226"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-226"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="b8763-227"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="b8763-227"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8763-228">Conceda permisos a los miembros de su equipo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8763-228">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8763-p123">Los miembros de su equipo de cumplimiento que vayan a crear etiquetas necesitan permisos para usar el Centro de seguridad y cumplimiento. Vaya a los permisos en el Centro de seguridad y cumplimiento y modifique los miembros del grupo Administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8763-p123">Members of your compliance team who will create labels need permissions to use the Security &amp; Compliance Center. Go to Permissions in Security and Compliance Center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="b8763-231">Consulte <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="b8763-231">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8763-232">Cree etiquetas de Office.</span><span class="sxs-lookup"><span data-stu-id="b8763-232">Create Office labels.</span></span></p></td>
<td align="left"><span data-ttu-id="b8763-233">Vaya a Clasificaciones en el Centro de seguridad y cumplimiento, elija Etiquetas y cree las etiquetas en su entorno.</span><span class="sxs-lookup"><span data-stu-id="b8763-233">Go to Classifications in Security and Compliance Center, choose Labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8763-234">Cree directivas de aplicación automática para etiquetas.</span><span class="sxs-lookup"><span data-stu-id="b8763-234">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="b8763-p124">Vaya a Clasificación en el Centro de seguridad y cumplimiento, elija Directivas de etiqueta y cree las directivas de aplicación automática de etiquetas. Asegúrese de crear estas directivas en el orden de la prioridad.</span><span class="sxs-lookup"><span data-stu-id="b8763-p124">Go to Classification in Security and Compliance Center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b8763-237">La siguiente ilustración muestra cómo crear una etiqueta de aplicación automática para la etiqueta Datos de cliente.</span><span class="sxs-lookup"><span data-stu-id="b8763-237">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Crear y aplicar una etiqueta de datos de cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="b8763-239">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="b8763-239">In the illustration:</span></span>

-   <span data-ttu-id="b8763-240">Se crea la etiqueta "Datos de cliente".</span><span class="sxs-lookup"><span data-stu-id="b8763-240">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="b8763-241">Se listan los tipos de información confidencial deseados para RGPD: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="b8763-241">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="b8763-242">Crear una directiva de aplicación automática asigna la etiqueta "Datos de cliente" a cualquier archivo que contenga uno de los tipos de información confidencial que agregue a la directiva.</span><span class="sxs-lookup"><span data-stu-id="b8763-242">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>

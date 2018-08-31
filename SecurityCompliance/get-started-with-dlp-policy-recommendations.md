---
title: Introducción a las recomendaciones de la directiva DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2ea4459b-cb13-4ce2-b9d1-0619316df88c
description: Esta recomendación controlados por insight ayuda a su organización a mantener segura la contenido confidencial cuando se almacena y se comparten en Office 365 para informar cuando hay una posible brecha en la cobertura de la directiva DLP. Verá esta recomendación en la página principal de la seguridad &amp; centro de cumplimiento, si los documentos contienen cualquiera de los tipos más comunes de cinco de la parte superior de la información confidencial, pero no están protegidos por una directiva de DLP.
ms.openlocfilehash: 842387397b9b95d236660c5809174c2b356cf14a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536741"
---
# <a name="get-started-with-dlp-policy-recommendations"></a><span data-ttu-id="a56e9-104">Introducción a las recomendaciones de la directiva DLP</span><span class="sxs-lookup"><span data-stu-id="a56e9-104">Get started with DLP policy recommendations</span></span>

<span data-ttu-id="a56e9-p102">Esta recomendación controlados por insight ayuda a su organización a mantener segura la contenido confidencial cuando se almacena y se comparten en Office 365 para informar cuando hay una posible brecha en la cobertura de la directiva DLP. Verá esta recomendación en la página **principal** de la seguridad &amp; centro de cumplimiento, si los documentos contienen cualquiera de los tipos más comunes de cinco de la parte superior de la información confidencial, pero no están protegidos por una directiva de (DLP) de prevención de pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="a56e9-p102">This insight-driven recommendation helps your organization keep sensitive content secure when it's stored and shared in Office 365 by informing you when there's a possible gap in your DLP policy coverage. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center, if your documents contain any of the top-five most common types of sensitive information but aren't protected by a data loss prevention (DLP) policy.</span></span> 
  
<span data-ttu-id="a56e9-p103">Puede usar este widget para crear rápidamente una directiva de DLP personalizada en un clic o dos y, después de crear esta directiva DLP, es totalmente personalizable. Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendado para usted** .</span><span class="sxs-lookup"><span data-stu-id="a56e9-p103">You can use this widget to quickly create a customized DLP policy in just a click or two, and after you create this DLP policy, it's fully customizable. Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget con nombre de información confidencial desprotegida](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a><span data-ttu-id="a56e9-110">Crear la directiva DLP recomendada</span><span class="sxs-lookup"><span data-stu-id="a56e9-110">Create the recommended DLP policy</span></span>

<span data-ttu-id="a56e9-111">Cuando se muestra en el widget desprotegido información confidencial, elija **empezar a trabajar** en la parte inferior para crear rápidamente una directiva de DLP.</span><span class="sxs-lookup"><span data-stu-id="a56e9-111">When the widget shows you unprotected sensitive information, choose **Get started** at the bottom to quickly create a DLP policy.</span></span> 
  
<span data-ttu-id="a56e9-112">Para ayudar a proteger la información confidencial, esta directiva DLP:</span><span class="sxs-lookup"><span data-stu-id="a56e9-112">To help protect the sensitive information, this DLP policy:</span></span>
  
- <span data-ttu-id="a56e9-113">Detecta cuando el contenido de Exchange, SharePoint y OneDrive que contiene uno de los tipos de información confidencial desprotegidos se comparte con personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a56e9-113">Detects when content in Exchange, SharePoint, and OneDrive that contains one of the unprotected types of sensitive information is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="a56e9-p104">Genera informes de actividad detallada de modo que puede realizar un seguimiento de cosas como el contenido que compartido con personas fuera de la organización y cuando lo hacían. Puede usar los [informes DLP](view-the-dlp-reports.md) y los [datos de registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **actividad** = **DLP**) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="a56e9-p104">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it. You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="a56e9-116">También puede elegir que tengan la directiva DLP:</span><span class="sxs-lookup"><span data-stu-id="a56e9-116">You can also choose to have the DLP policy:</span></span>
  
- <span data-ttu-id="a56e9-117">Enviará un correo electrónico de informe del incidente cuando los usuarios compartir una gran cantidad de información confidencial con personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a56e9-117">Send you an incident report email when users share a lot of this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="a56e9-118">Agregar otros usuarios al informe de incidentes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a56e9-118">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="a56e9-p105">Mostrar una sugerencia de directiva y enviar una notificación de correo electrónico a los usuarios cuando intenten compartir esta información confidencial con personas fuera de la organización. Para obtener más información acerca de estas opciones, vea [Enviar notificaciones por correo electrónico y mostrar sugerencias de directivas para las directivas DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="a56e9-p105">Show a policy tip and send an email notification to users when they attempt to share this sensitive information with people outside your organization. For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
<span data-ttu-id="a56e9-p106">Si desea cambiar estas opciones más adelante, puede editar la directiva DLP después de crearla. Por ejemplo, puede realizar la directiva más restrictiva por personas incluso bloqueo de uso compartido de contenido que contiene información confidencial en primer lugar - vea la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="a56e9-p106">If you want to change these options later, you can edit the DLP policy after it's created. For example, you can make the policy more restrictive by even blocking people from sharing content that contains sensitive information in the first place - see the next section.</span></span>
  
![Configuración para el widget con nombre de información confidencial desprotegida](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a><span data-ttu-id="a56e9-124">Editar la directiva DLP recomendada</span><span class="sxs-lookup"><span data-stu-id="a56e9-124">Edit the recommended DLP policy</span></span>

<span data-ttu-id="a56e9-125">Después de usar el widget para crear una directiva de DLP, la directiva aparece bajo la **prevención de pérdida de datos** en la página **Directiva** de la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a56e9-125">After you use the widget to create a DLP policy, the policy appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="a56e9-p107">De forma predeterminada, la directiva se denomina **Directiva del sistema se recomienda para el uso compartido de información confidencial**. Esta directiva es totalmente personalizable, igual que cualquier directiva DLP crear usted mismo desde el principio. Por ejemplo, si ha decidido no activar informes de incidentes y sugerencias de directiva cuando se utiliza el widget, siempre puede editar la directiva y activar estas opciones en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a56e9-p107">By default, the policy is named **System Recommended Policy for Sharing Sensitive Information**. This policy is fully customizable, the same as any DLP policy that you create yourself from scratch. For example, if you decided not to turn on incident reports and policy tips when you used the widget, you can always edit the policy and turn on those options at any time.</span></span>
  
![Sistema recomendado directiva para uso compartido de información confidencial](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="a56e9-130">Cuando el widget y no aparece</span><span class="sxs-lookup"><span data-stu-id="a56e9-130">When the widget does and does not appear</span></span>

<span data-ttu-id="a56e9-131">El widget con nombre de **Información confidencial desprotegida** aparece en la sección de **recomendado para usted** de la página **principal** de la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a56e9-131">The widget named **Unprotected Sensitive Information** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="a56e9-132">Este widget aparece sólo cuando:</span><span class="sxs-lookup"><span data-stu-id="a56e9-132">This widget appears only when:</span></span>
  
- <span data-ttu-id="a56e9-133">Se detectan nuevos documentos que contengan cualquiera de los cinco tipos más comunes de información confidencial en SharePoint o OneDrive durante los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="a56e9-133">New documents containing any of the five most common types of sensitive information are detected in SharePoint or OneDrive over the past 30 days.</span></span>
    
- <span data-ttu-id="a56e9-134">Esa información confidencial ya no está protegida por una directiva DLP existente.</span><span class="sxs-lookup"><span data-stu-id="a56e9-134">That sensitive information is not already protected by an existing DLP policy.</span></span>
    
<span data-ttu-id="a56e9-135">A diferencia de las directivas de DLP que constantemente se están analizando los datos, esta recomendación examina para los vacíos en la cobertura de la directiva DLP aproximadamente cada 48 horas, por lo que después de carga el nuevo contenido, puede tardar hasta dos días para la recomendación que aparezca.</span><span class="sxs-lookup"><span data-stu-id="a56e9-135">Unlike DLP policies that are constantly scanning your data, this recommendation scans for gaps in your DLP policy coverage roughly every 48 hours, so after new content is uploaded, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="a56e9-136">Por último, después de usar el widget para crear una directiva DLP recomendada, el widget desaparece de la página **principal** .</span><span class="sxs-lookup"><span data-stu-id="a56e9-136">Finally, after you use the widget to create a recommended DLP policy, the widget disappears from the **Home** page.</span></span> 
  


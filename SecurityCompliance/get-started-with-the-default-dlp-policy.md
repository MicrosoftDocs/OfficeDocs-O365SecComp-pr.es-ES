---
title: Introducción a la directiva predeterminada de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: Antes de crear la primera directiva de prevención (DLP) de pérdida de datos incluso, DLP es ayudar a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su mantener de ayuda recomendación (que se muestra a continuación), el contenido confidencial seguro y se lo comunica al número de tarjeta de correo electrónico o documentos que contengan un crédito se comparte con alguien de fuera de la organización.
ms.openlocfilehash: 1b522a2c04e72353970ef5dfcd62183023a01994
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536859"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="84f54-104">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="84f54-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="84f54-p102">Antes de crear la primera directiva de prevención (DLP) de pérdida de datos incluso, DLP es ayudar a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su mantener de ayuda recomendación (que se muestra a continuación), el contenido confidencial seguro y se lo comunica al número de tarjeta de correo electrónico o documentos que contengan un crédito se comparte con alguien de fuera de la organización. Verá esta recomendación en la página **principal** de la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84f54-p102">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy. This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="84f54-p103">Puede usar este widget para ver rápidamente cuándo y la cantidad de información confidencial se ha compartido y, a continuación, refinar la directiva DLP predeterminada en un clic o un doble. También puede editar la directiva DLP predeterminado en cualquier momento porque es totalmente personalizable. Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendado para usted** .</span><span class="sxs-lookup"><span data-stu-id="84f54-p103">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two. You can also edit the default DLP policy at any time because it's fully customizable. Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominado más proteger contenido compartido](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="84f54-112">Ver el informe y refinar la directiva DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="84f54-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="84f54-113">Cuando el widget muestra que los usuarios comparte información confidencial con personas fuera de la organización, seleccione **Directiva de DLP refinar** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="84f54-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="84f54-p104">El informe detallado muestra cuándo y cómo se ha compartido la cantidad de contenido que contiene los números de tarjeta de crédito en los últimos 30 días. Tenga en cuenta que coincide con la regla puede tardar hasta 48 horas aparezca en el widget.</span><span class="sxs-lookup"><span data-stu-id="84f54-p104">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days. Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="84f54-116">Para ayudar a proteger la información confidencial, la directiva DLP predeterminada:</span><span class="sxs-lookup"><span data-stu-id="84f54-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="84f54-117">Detecta cuando el contenido de Exchange, SharePoint y OneDrive que contiene al menos una tarjeta de crédito se comparte con personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="84f54-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="84f54-p105">Muestra una sugerencia de directiva y envía una notificación de correo electrónico a los usuarios cuando intenten compartir esta información confidencial con personas fuera de la organización. Para obtener más información acerca de estas opciones, vea [Enviar notificaciones por correo electrónico y mostrar sugerencias de directivas para las directivas DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="84f54-p105">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization. For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="84f54-p106">Genera informes de actividad detallada de modo que puede realizar un seguimiento de cosas como el contenido que compartido con personas fuera de la organización y cuando lo hacían. Puede usar los [informes DLP](view-the-dlp-reports.md) y los [datos de registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde **actividad** = **DLP**) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="84f54-p106">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it. You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="84f54-122">Para refinar rápidamente la directiva DLP de forma predeterminada, puede elegir para que:</span><span class="sxs-lookup"><span data-stu-id="84f54-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="84f54-123">Enviará un correo electrónico de informe del incidente cuando los usuarios compartir esta información confidencial con personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="84f54-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="84f54-124">Agregar otros usuarios al informe de incidentes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="84f54-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="84f54-125">Bloquee el acceso al contenido que contiene la información confidencial, pero permitir que el usuario invalidar y compartir o enviar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="84f54-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="84f54-126">Para obtener más información sobre los informes de incidentes o restringir el acceso, vea [información general de las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="84f54-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="84f54-127">Si desea cambiar estas opciones más adelante, puede editar el valor predeterminado directiva DLP en cualquier momento - vea la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="84f54-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Configuración de widget denominado más protege contenido compartido](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="84f54-129">Editar la directiva DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="84f54-129">Edit the default DLP policy</span></span>

<span data-ttu-id="84f54-130">Esta directiva se denomina **directiva predeterminada Office 365 DLP** y aparece bajo la **prevención de pérdida de datos** en la página **Directiva** de la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84f54-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="84f54-p107">Esta directiva es totalmente personalizable, igual que cualquier directiva DLP crear usted mismo desde el principio. También puede desactivar o eliminar la directiva, de modo que los usuarios ya no reciben sugerencias de directiva o notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="84f54-p107">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch. You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Directiva DLP denominada directiva predeterminada DLP de Office 365](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="84f54-134">Cuando el widget y no aparece</span><span class="sxs-lookup"><span data-stu-id="84f54-134">When the widget does and does not appear</span></span>

<span data-ttu-id="84f54-135">El widget denominado **proteger más el contenido compartido** aparece en la sección de **recomendado para usted** de la página **principal** de la seguridad &amp; centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84f54-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="84f54-136">Este widget aparece sólo cuando:</span><span class="sxs-lookup"><span data-stu-id="84f54-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="84f54-p108">No hay ningún directivas de prevención de pérdida de datos en la seguridad &amp; centro de cumplimiento o centro de administración de Exchange. Este widget está pensada para ayudarle a empezar a trabajar con DLP, para que no aparezca si ya dispone de las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="84f54-p108">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange Admin Center. This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="84f54-139">Contenido que contenga menos una tarjeta de crédito se ha compartido con alguien de fuera de la organización en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="84f54-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="84f54-140">Tenga en cuenta que coincide con la regla puede tardar hasta 48 horas esté disponible para el widget, por lo que una vez que se detecta información confidencial shared externamente, puede tardar hasta dos días para la recomendación que aparezca.</span><span class="sxs-lookup"><span data-stu-id="84f54-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="84f54-141">Por último, después de usar el widget para refinar la directiva DLP de forma predeterminada, el widget desaparece de la página **principal** .</span><span class="sxs-lookup"><span data-stu-id="84f54-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  


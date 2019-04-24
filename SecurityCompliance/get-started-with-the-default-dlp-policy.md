---
title: Introducción a la directiva predeterminada de DLP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: Antes de crear la primera Directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada. Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a mantener seguro el contenido confidencial mediante una notificación cuando el correo electrónico o los documentos que contienen un número de tarjeta de crédito se han compartido con alguien ajeno a la organización.
ms.openlocfilehash: fa48025a7b979ad69c600b21a10fbb62567234c3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256738"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="4dbfb-104">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="4dbfb-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="4dbfb-105">Antes de crear la primera Directiva de prevención de pérdida de datos (DLP), DLP ayuda a proteger la información confidencial con una directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="4dbfb-106">Esta directiva predeterminada y su recomendación (que se muestra a continuación) ayudan a mantener seguro el contenido confidencial mediante una notificación cuando el correo electrónico o los documentos que contienen un número de tarjeta de crédito se han compartido con alguien ajeno a la organización.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="4dbfb-107">Verá esta recomendación en la página **principal** del centro de seguridad &amp; y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4dbfb-108">Puede usar este widget para ver rápidamente cuándo y cuánto se ha compartido la información confidencial y, a continuación, refinar la Directiva de DLP predeterminada en solo un clic o dos.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="4dbfb-109">También puede editar la Directiva DLP predeterminada en cualquier momento, ya que es totalmente personalizable.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="4dbfb-110">Tenga en cuenta que si no ve la recomendación en primer lugar, intente hacer clic en **+ más** en la parte inferior de la sección **recomendada para usted** .</span><span class="sxs-lookup"><span data-stu-id="4dbfb-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominado protección de contenido compartido adicional](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="4dbfb-112">Ver el informe y refinar la Directiva de DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="4dbfb-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="4dbfb-113">Cuando el widget muestre que los usuarios comparten información confidencial con personas de fuera de la organización, elija refinar la **Directiva DLP** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="4dbfb-114">El informe detallado muestra Cuándo y cuánto contenido que contiene los números de las tarjetas de crédito se ha compartido en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="4dbfb-115">Tenga en cuenta que las coincidencias de regla pueden tardar hasta 48 horas en mostrarse en el widget.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="4dbfb-116">Para ayudar a proteger la información confidencial, la Directiva de DLP predeterminada:</span><span class="sxs-lookup"><span data-stu-id="4dbfb-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="4dbfb-117">Detecta si el contenido de Exchange, SharePoint y OneDrive que contiene al menos un número de tarjeta de crédito se comparte con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="4dbfb-118">Muestra una sugerencia de directiva y envía una notificación por correo electrónico a los usuarios cuando intentan compartir esta información confidencial con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="4dbfb-119">Para obtener más información sobre estas opciones, vea [enviar notificaciones de correo electrónico y Mostrar sugerencias de directiva para directivas de DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="4dbfb-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="4dbfb-120">Genera informes de actividad detallados para que pueda realizar un seguimiento de cosas como quién ha compartido el contenido con personas de fuera de la organización y cuándo lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="4dbfb-121">Puede usar los [informes de DLP](view-the-dlp-reports.md) y los datos del [registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (donde**DLP**de **actividad** = ) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="4dbfb-122">Para refinar rápidamente la Directiva DLP predeterminada, puede elegir que:</span><span class="sxs-lookup"><span data-stu-id="4dbfb-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="4dbfb-123">Envíe un informe de correo electrónico de incidentes cuando los usuarios compartan esta información confidencial con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="4dbfb-124">Agregar otros usuarios al informe de incidentes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="4dbfb-125">Bloquee el acceso al contenido que contiene la información confidencial, pero permita al usuario reemplazar y compartir o enviar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="4dbfb-126">Para obtener más información sobre los informes de incidentes o restringir el acceso, consulte [información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4dbfb-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="4dbfb-127">Si desea cambiar estas opciones más adelante, puede editar la Directiva DLP predeterminada en cualquier momento (consulte la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="4dbfb-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Configuración del widget con el nombre protección de contenido compartido adicional](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="4dbfb-129">Edición de la Directiva de DLP predeterminada</span><span class="sxs-lookup"><span data-stu-id="4dbfb-129">Edit the default DLP policy</span></span>

<span data-ttu-id="4dbfb-130">Esta Directiva se denomina **Directiva DLP predeterminada de Office 365** y aparece en **prevención de pérdida de datos** en la página de la **Directiva** del centro de seguridad &amp; y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4dbfb-131">Esta directiva es totalmente personalizable, igual que cualquier directiva DLP que se cree a partir de cero.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="4dbfb-132">También puede desactivar o eliminar la Directiva para que los usuarios dejen de recibir sugerencias de directiva o notificaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Directiva DLP denominada Directiva DLP predeterminada de Office 365](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="4dbfb-134">Cuando el widget no aparece</span><span class="sxs-lookup"><span data-stu-id="4dbfb-134">When the widget does and does not appear</span></span>

<span data-ttu-id="4dbfb-135">El widget denominado **protección de contenido compartido adicional** aparece en la sección **recomendada para usted** de la página **principal** del centro &amp; de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4dbfb-136">Este widget solo aparece cuando:</span><span class="sxs-lookup"><span data-stu-id="4dbfb-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="4dbfb-137">No hay directivas de prevención de pérdida de datos en &amp; el centro de seguridad y cumplimiento o en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="4dbfb-138">Este widget está pensado para ayudarle a empezar a usar DLP, por lo que no aparece si ya tiene directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="4dbfb-139">En los últimos 30 días se ha compartido el contenido que contiene menos una tarjeta de crédito con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="4dbfb-140">Tenga en cuenta que las coincidencias de regla pueden tardar hasta 48 horas en estar disponibles para el widget, por lo que, una vez detectada la información confidencial compartida de forma externa, puede tardar hasta dos días en aparecer la recomendación.</span><span class="sxs-lookup"><span data-stu-id="4dbfb-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="4dbfb-141">Por último, después de usar el widget para refinar la Directiva de DLP predeterminada, el widget desaparecerá de la página **principal** .</span><span class="sxs-lookup"><span data-stu-id="4dbfb-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  


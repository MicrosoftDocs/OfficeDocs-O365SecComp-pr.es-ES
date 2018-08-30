---
title: Informes de supervisión
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: Usar informes de supervisión para ver qué mensajes de correo electrónico necesita cumplimiento revisar y que debe realizar.
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535794"
---
# <a name="supervision-reports"></a><span data-ttu-id="f2cca-103">Informes de supervisión</span><span class="sxs-lookup"><span data-stu-id="f2cca-103">Supervision reports</span></span>

<span data-ttu-id="f2cca-p101">Definición las directivas de supervisión que las comunicaciones de la organización deben revisar para el cumplimiento y quién llevará a cabo las revisiones. Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada directiva, también puede ver las estadísticas de live en el estado actual de la actividad de revisión. [Obtenga más información acerca de las directivas de supervisión](configure-supervision-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="f2cca-p101">Supervision policies define which communications in your organization need review for compliance, and who will perform those reviews. Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. [Learn more about supervision policies ](configure-supervision-policies.md) .</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f2cca-p102">Uso de directivas de supervisión requiere una suscripción a Office 365 E5 para su organización. Si no tiene ese plan y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f2cca-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f2cca-110">Puede usar los informes de supervisión para:</span><span class="sxs-lookup"><span data-stu-id="f2cca-110">You can use the supervision reports to:</span></span>
  
- <span data-ttu-id="f2cca-111">Compruebe que las directivas se funcionan según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="f2cca-111">Verify that your policies are working as you intended.</span></span> 
    
- <span data-ttu-id="f2cca-112">Averigüe cuántos mensajes de correo electrónico que se identifican para su revisión.</span><span class="sxs-lookup"><span data-stu-id="f2cca-112">Find out how many emails are being identified for review.</span></span>
    
- <span data-ttu-id="f2cca-p103">Averigüe cuántos mensajes de correo electrónico no son compatibles y cuáles están pasando la revisión. Esta información puede ayudarle a decidir si se debe ajustar con precisión las directivas o cambiar el número de revisores.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p103">Find out how many emails aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.</span></span>
    
## <a name="view-the-supervision-report"></a><span data-ttu-id="f2cca-115">Ver el informe de supervisión</span><span class="sxs-lookup"><span data-stu-id="f2cca-115">View the Supervision report</span></span>

1. <span data-ttu-id="f2cca-116">Inicie sesión en la [seguridad &amp; centro de cumplimiento](https://protection.office.com/) con las credenciales para una cuenta de administrador de la organización de Office 365 que tiene permisos para ver informes de supervisión..</span><span class="sxs-lookup"><span data-stu-id="f2cca-116">Sign into the [Security &amp; Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports..</span></span> 
    
2. <span data-ttu-id="f2cca-p104">Vaya a **informes** \> **panel**. Verá un widget de informes de supervisión y otros informes tiene acceso a.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p104">Go to **Reports** \> **Dashboard**. You'll see a reporting widget for supervision and other reports you have access to.</span></span>
    
3. <span data-ttu-id="f2cca-119">Haga clic en el widget de **supervisión** para abrir la página de informe detallado.</span><span class="sxs-lookup"><span data-stu-id="f2cca-119">Click the **Supervision** widget to open the detailed report page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="f2cca-p105">Si no puede tener acceso a la página de **informes** , compruebe que se encuentra un miembro del grupo de roles de revisión de supervisión, tal como se describe en [realizar supervisión disponible en su organización](configure-supervision-policies.md#SRavailable). Que se incluye en este rol grupo le permite crea y administrar supervisión directivas y ejecuta el informe.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p105">If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md#SRavailable). Being included in this role group lets you create and manage supervision polices and run the report.</span></span> 
  
## <a name="how-to-use-the-report"></a><span data-ttu-id="f2cca-122">Cómo usar el informe</span><span class="sxs-lookup"><span data-stu-id="f2cca-122">How to use the report</span></span>

<span data-ttu-id="f2cca-p106">Cuando una directiva de supervisión identifica un correo electrónico para su revisión, el correo electrónico se entrega en la carpeta de supervisión del revisor en Outlook y Outlook web app. Este informe muestra el nombre de la directiva y el número de comunicaciones en cada etapa del proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p106">When a supervision policy identifies an email for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.</span></span>
  
<span data-ttu-id="f2cca-125">Utilice el informe para:</span><span class="sxs-lookup"><span data-stu-id="f2cca-125">Use the report to:</span></span>
  
- <span data-ttu-id="f2cca-126">Ver los datos para todas o directivas específicas.</span><span class="sxs-lookup"><span data-stu-id="f2cca-126">View data for all or specific policies.</span></span>
    
- <span data-ttu-id="f2cca-127">Ver los datos agrupados por tipo de etiqueta (como compatible, Questionable, etc.), el revisor o el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f2cca-127">View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.</span></span>
    
- <span data-ttu-id="f2cca-128">Exportar datos a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f2cca-128">Export data to a CSV file.</span></span>
    
- <span data-ttu-id="f2cca-129">Filtrar los datos según la fecha de actividad de revisión, tipo de etiqueta, revisor, tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f2cca-129">Filter data based on review activity date, tag type, reviewer, message type.</span></span>
    
<span data-ttu-id="f2cca-130">Éste es un desglose de los valores que aparecen en la columna **tipo de etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="f2cca-130">Here's a breakdown of the values you might see in the **Tag type** column.</span></span> 
  
|<span data-ttu-id="f2cca-131">**Tipo de etiqueta**</span><span class="sxs-lookup"><span data-stu-id="f2cca-131">**Tag type**</span></span>|<span data-ttu-id="f2cca-132">**¿Qué significa**</span><span class="sxs-lookup"><span data-stu-id="f2cca-132">**What it means**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2cca-133">No se ha revisado</span><span class="sxs-lookup"><span data-stu-id="f2cca-133">Not Reviewed</span></span>  <br/> |<span data-ttu-id="f2cca-p107">El número de mensajes de correo electrónico que no se han revisado todavía. Estos mensajes de correo electrónico están en espera de revisión en la carpeta de supervisión del revisor de Outlook.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p107">The number of emails that have not been reviewed yet. These emails are awaiting review in the reviewer's supervision folder in Outlook.</span></span>  <br/> |
|<span data-ttu-id="f2cca-136">Compatible con</span><span class="sxs-lookup"><span data-stu-id="f2cca-136">Compliant</span></span>  <br/> |<span data-ttu-id="f2cca-p108">El número de mensajes de correo electrónico revisado y marcado como compatible. No es necesario realizar ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p108">The number of emails reviewed and marked as compliant. No further action is needed.</span></span>  <br/> |
|<span data-ttu-id="f2cca-139">Dudosos</span><span class="sxs-lookup"><span data-stu-id="f2cca-139">Questionable</span></span>  <br/> |<span data-ttu-id="f2cca-p109">El número de mensajes de correo electrónico revisado y marca dudoso. Esto actúa como un indicador; otros revisores pueden ayudar a comprobar si un correo electrónico necesita investigación para cumplimiento de normas.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p109">The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance.</span></span>  <br/> |
|<span data-ttu-id="f2cca-142">No compatible (activo)</span><span class="sxs-lookup"><span data-stu-id="f2cca-142">Non-Compliant (Active)</span></span>  <br/> |<span data-ttu-id="f2cca-143">El número de mensajes de correo electrónico que no son compatibles con que actualmente están investigar los revisores.</span><span class="sxs-lookup"><span data-stu-id="f2cca-143">The number of non-compliant emails that reviewers are currently investigating.</span></span>  <br/> |
|<span data-ttu-id="f2cca-144">No compatible (resuelto)</span><span class="sxs-lookup"><span data-stu-id="f2cca-144">Non-Compliant (Resolved)</span></span>  <br/> |<span data-ttu-id="f2cca-145">El número de mensajes de correo electrónico que no son compatibles con que investigar y resuelven los revisores.</span><span class="sxs-lookup"><span data-stu-id="f2cca-145">The number of non-compliant emails that reviewers investigated and resolved.</span></span>  <br/> |
   
## <a name="more-details"></a><span data-ttu-id="f2cca-146">Obtener más detalles</span><span class="sxs-lookup"><span data-stu-id="f2cca-146">More details</span></span>

- <span data-ttu-id="f2cca-147">En primer lugar se deben aprovisionar las directivas de supervisión antes de que aparecen en este informe.</span><span class="sxs-lookup"><span data-stu-id="f2cca-147">Supervision policies must first be provisioned before they will appear in this report.</span></span>
    
- <span data-ttu-id="f2cca-p110">Si se eliminan las directivas, aún se muestran datos históricos. Sin embargo, están indicados como "directiva inexistente", y no está disponible la función **de exportación** .</span><span class="sxs-lookup"><span data-stu-id="f2cca-p110">If policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy", and the **Export** function isn't available.</span></span> 
    
- <span data-ttu-id="f2cca-p111">Si el informe no muestra los datos de forma predeterminada, podría ser debido a que el intervalo de fechas actual no tiene ningún dato que mostrar. En estos casos, utilice el control de **filtros** para cambiar el intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="f2cca-p111">If the report doesn't show any data by default, it might be because the current date range doesn't have any data to show. In these cases, use the **Filters** control to change the date range.</span></span> 
    


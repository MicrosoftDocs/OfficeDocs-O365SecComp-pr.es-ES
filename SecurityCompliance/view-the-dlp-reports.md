---
title: Ver los informes de prevención de pérdida de datos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Con los informes de DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas de DLP, invalidaciones o falsos positivos; ver si las tendencias están arriba o abajo con el tiempo; filtrar el informe de diferentes formas; y ver detalles adicionales seleccionando un punto en una línea del gráfico.
ms.openlocfilehash: bd2bc63fa3e2ea08f44ddb3923786010c59e829f
ms.sourcegitcommit: 173936324ea015d788703440924ec8a9fb0db88b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "30510227"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="b8c24-103">Ver los informes de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="b8c24-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="b8c24-104">Después de crear las directivas de prevención de pérdida de datos (DLP), querrá comprobar que funcionan según lo previsto y ayudarle a mantener la conformidad.</span><span class="sxs-lookup"><span data-stu-id="b8c24-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="b8c24-105">Con los informes de DLP en el centro de &amp; seguridad y cumplimiento de Office 365, puede ver rápidamente:</span><span class="sxs-lookup"><span data-stu-id="b8c24-105">With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="b8c24-106">Coincidencias de **directivas DLP** Este informe muestra el número de coincidencias de directivas de DLP a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="b8c24-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="b8c24-107">Puede filtrar el informe por fecha, ubicación, Directiva o acción.</span><span class="sxs-lookup"><span data-stu-id="b8c24-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="b8c24-108">Puede usar este informe para:</span><span class="sxs-lookup"><span data-stu-id="b8c24-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="b8c24-109">Ajustar o refinar las directivas de DLP a medida que las ejecuta en modo de prueba.</span><span class="sxs-lookup"><span data-stu-id="b8c24-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="b8c24-110">Puede ver la regla específica que coincide con el contenido.</span><span class="sxs-lookup"><span data-stu-id="b8c24-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="b8c24-111">Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="b8c24-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="b8c24-112">Descubra los procesos de negocio que infringen las directivas DLP de su organización.</span><span class="sxs-lookup"><span data-stu-id="b8c24-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="b8c24-113">Comprenda cualquier impacto empresarial de las directivas DLP mediante la visualización de las acciones que se aplican al contenido.</span><span class="sxs-lookup"><span data-stu-id="b8c24-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="b8c24-114">Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="b8c24-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="b8c24-115">Ver una lista de los usuarios principales y repetir los usuarios que están contribuyendo a incidentes de la organización.</span><span class="sxs-lookup"><span data-stu-id="b8c24-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="b8c24-116">Ver una lista de los principales tipos de información confidencial de la organización.</span><span class="sxs-lookup"><span data-stu-id="b8c24-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="b8c24-117">**Incidentes de DLP** Este informe también muestra las coincidencias de directivas a lo largo del tiempo, como la Directiva coincide con el informe.</span><span class="sxs-lookup"><span data-stu-id="b8c24-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="b8c24-118">Sin embargo, el informe de coincidencias de directivas muestra coincidencias en un nivel de regla; por ejemplo, si un correo electrónico coincide con tres reglas distintas, la Directiva coincide con el informe muestra tres elementos de línea diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8c24-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="b8c24-119">Por el contrario, el informe de incidentes muestra coincidencias en un nivel de elemento; por ejemplo, si un correo electrónico coincide con tres reglas distintas, el informe de incidentes muestra un elemento de línea único para esa parte de contenido.</span><span class="sxs-lookup"><span data-stu-id="b8c24-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="b8c24-120">Dado que el número de informes se agrega de forma diferente, el informe de coincidencias de directiva es mejor para identificar coincidencias con reglas específicas y ajustar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="b8c24-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="b8c24-121">El informe de incidentes es mejor para identificar fragmentos específicos de contenido que son problemáticos para sus directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="b8c24-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="b8c24-122">**Falsos positivos y reemplazos de DLP** Si su Directiva DLP permite a los usuarios invalidarla o informar de un falso positivo, este informe muestra un recuento de esas instancias a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="b8c24-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="b8c24-123">Puede filtrar el informe por fecha, ubicación o Directiva.</span><span class="sxs-lookup"><span data-stu-id="b8c24-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="b8c24-124">Puede usar este informe para:</span><span class="sxs-lookup"><span data-stu-id="b8c24-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="b8c24-125">Para ajustar o refinar las directivas de DLP, vea las directivas que incurren en un gran número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="b8c24-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="b8c24-126">Ver las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva reemplazando la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b8c24-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="b8c24-127">Descubra dónde entran en conflicto las directivas de DLP con procesos de negocio válidos al incurrir en un gran número de invalidaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="b8c24-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="b8c24-128">Todos los informes de DLP pueden mostrar datos del período de tiempo de cuatro meses más reciente.</span><span class="sxs-lookup"><span data-stu-id="b8c24-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="b8c24-129">Los datos más recientes pueden tardar hasta 24 horas en aparecer en los informes.</span><span class="sxs-lookup"><span data-stu-id="b8c24-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="b8c24-130">Puede encontrar estos informes en el **Panel**de &amp; \> **informes** \> del centro de cumplimiento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8c24-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Informe de coincidencias de directivas de DLP](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="b8c24-132">Ver la justificación enviada por un usuario para una invalidación</span><span class="sxs-lookup"><span data-stu-id="b8c24-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="b8c24-133">Si su Directiva DLP permite a los usuarios invalidarla, puede usar el informe de anulación y de falso positivo para ver el texto enviado por los usuarios en la sugerencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="b8c24-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo de justificación en detalles del informe de reemplazo y falso positivo de DLP](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="b8c24-135">Realizar acciones en información y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b8c24-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="b8c24-136">Los informes pueden mostrar información y recomendaciones en las que puede hacer clic en el icono rojo de advertencia para ver los detalles de los posibles problemas y realizar posibles acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="b8c24-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Hacer clic en un icono de información para ver los detalles y las acciones que se deben realizar](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="b8c24-138">Permisos para informes de DLP</span><span class="sxs-lookup"><span data-stu-id="b8c24-138">Permissions for DLP reports</span></span>

<span data-ttu-id="b8c24-139">Para ver los informes de DLP en el centro de seguridad & cumplimiento, debe tener asignado el:</span><span class="sxs-lookup"><span data-stu-id="b8c24-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="b8c24-140">Rol de **lector de seguridad** en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8c24-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="b8c24-141">De forma predeterminada, este rol se asigna a los grupos de roles administración de la organización y lector de seguridad en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8c24-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="b8c24-142">**View-Only DLP Compliance Management** role en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8c24-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="b8c24-143">De forma predeterminada, este rol se asigna a los grupos de roles administrador de cumplimiento, administración de la organización, administrador de seguridad y lector de seguridad en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8c24-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="b8c24-144">Rol **destinatarios con permiso de vista** en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8c24-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="b8c24-145">De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento, administración de la organización y administración de la organización de solo vista en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b8c24-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="b8c24-146">Buscar los cmdlets para los informes de DLP</span><span class="sxs-lookup"><span data-stu-id="b8c24-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="b8c24-147">Para usar la mayoría de los cmdlets del centro &amp; de seguridad y cumplimiento, debe:</span><span class="sxs-lookup"><span data-stu-id="b8c24-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="b8c24-148">Conectarse al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b8c24-148">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="b8c24-149">Use cualquiera de estos [cmdlets del &amp; centro de seguridad y cumplimiento de Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="b8c24-149">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="b8c24-150">Sin embargo, los informes DLP necesitan extraer datos de toda la oficina 365, incluido Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b8c24-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="b8c24-151">Por este motivo, los cmdlets para los informes de DLP están disponibles en Exchange Online PowerShell, no en &amp; PowerShell del centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8c24-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="b8c24-152">Por lo tanto, para usar los cmdlets para los informes de DLP, debe:</span><span class="sxs-lookup"><span data-stu-id="b8c24-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="b8c24-153">Conectarse a Exchange Online con el PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="b8c24-153">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="b8c24-154">Use cualquiera de estos cmdlets para los informes de DLP:</span><span class="sxs-lookup"><span data-stu-id="b8c24-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="b8c24-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="b8c24-155">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="b8c24-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="b8c24-156">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    


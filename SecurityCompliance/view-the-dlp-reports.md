---
title: Ver los informes de prevención de pérdida de datos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: Con los informes DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas de DLP, invalidaciones o falsos positivos; vea si está tendencias de arriba o abajo en el tiempo; filtrar el informe de diferentes maneras; y ver detalles adicionales mediante la selección de un punto en una línea en el gráfico.
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013914"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="03000-103">Ver los informes de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="03000-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="03000-p101">Después de crear las directivas de prevención (DLP) la pérdida de datos, desea comprobar que trabaja como pensado y le ayuda a cumplir. Con la DLP informes en la seguridad de Office 365 &amp; centro de cumplimiento, puede ver rápidamente:</span><span class="sxs-lookup"><span data-stu-id="03000-p101">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="03000-p102">**Coincidencias de directivas de DLP** Este informe muestra el recuento de coincidencias de directivas de DLP a través del tiempo. Puede filtrar el informe por fecha, la ubicación, la directiva o la acción. Puede usar este informe para:</span><span class="sxs-lookup"><span data-stu-id="03000-p102">**DLP policy matches** This report shows the count of DLP policy matches over time. You can filter the report by date, location, policy, or action. You can use this report to:</span></span> 
    
  - <span data-ttu-id="03000-p103">Ajustar o restringir sus directivas de DLP, tal y como se ejecuta en modo de prueba. Puede ver la regla específica que coincidieron con el contenido.</span><span class="sxs-lookup"><span data-stu-id="03000-p103">Tune or refine your DLP policies as you run them in test mode. You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="03000-111">Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="03000-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="03000-112">Descubra los procesos de negocio que infringen las directivas DLP de su organización.</span><span class="sxs-lookup"><span data-stu-id="03000-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="03000-113">Para comprender cualquier impacto en el negocio de las directivas de DLP, vean qué acciones se aplican al contenido.</span><span class="sxs-lookup"><span data-stu-id="03000-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="03000-114">Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="03000-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="03000-115">Ver una lista de los principales usuarios y repita los usuarios que contribuyen a los incidentes en la organización.</span><span class="sxs-lookup"><span data-stu-id="03000-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="03000-116">Ver una lista de los principales tipos de información confidencial de la organización.</span><span class="sxs-lookup"><span data-stu-id="03000-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="03000-p104">**Incidentes DLP** Este informe muestra también coincidencias de directivas con el tiempo, como el informe de coincide con la directiva. Sin embargo, la directiva coincide con informe muestra las coincidencias en un nivel de la regla; Por ejemplo, si un correo electrónico, coincidió con tres reglas diferentes, la directiva coincide con informe muestra tres diferentes elementos de línea. Por el contrario, el informe de incidentes muestra las coincidencias en un nivel de elemento; Por ejemplo, si un correo electrónico, coincidió con tres reglas diferentes, el informe de incidentes muestra un elemento de línea única para esa parte del contenido.</span><span class="sxs-lookup"><span data-stu-id="03000-p104">**DLP incidents** This report also shows policy matches over time, like the policy matches report. However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items. By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="03000-p105">Debido a que los recuentos de informe se agregan de forma diferente, el informe de coincidencias de directiva es mejor para identificar las coincidencias con las reglas específicas y realizar ajustes en las directivas de DLP. El informe de incidentes es mejor para la identificación de partes específicas del contenido que son problemáticas para las directivas de DLP.</span><span class="sxs-lookup"><span data-stu-id="03000-p105">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies. The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="03000-p106">**Invalidaciones y falsos positivos DLP** Si la directiva de DLP permite a los usuarios invalidarla o notificar un falso positivo, este informe muestra un recuento de esas instancias a través del tiempo. Puede filtrar el informe por fecha, la ubicación o la directiva. Puede usar este informe para:</span><span class="sxs-lookup"><span data-stu-id="03000-p106">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time. You can filter the report by date, location, or policy. You can use this report to:</span></span> 
    
  - <span data-ttu-id="03000-125">Ajustar o restringir sus directivas de DLP por vean qué directivas provocar una gran cantidad de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="03000-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="03000-126">Ver la justificación presentada por los usuarios cuando resuelvan una sugerencia de directiva mediante el reemplazo de la directiva.</span><span class="sxs-lookup"><span data-stu-id="03000-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="03000-127">Descubrir donde invalida el conflicto de directivas DLP con los procesos de negocio válido por incurrir en un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="03000-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="03000-p107">Todos los informes DLP pueden mostrar los datos desde el período de tiempo de cuatro meses más reciente. Los datos más recientes pueden tardar hasta 24 horas que aparezca en los informes.</span><span class="sxs-lookup"><span data-stu-id="03000-p107">All DLP reports can show data from the most recent four-month time period. The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="03000-130">Puede encontrar estos informes en la seguridad &amp; centro de cumplimiento \> **informes** \> **panel**.</span><span class="sxs-lookup"><span data-stu-id="03000-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Informe de coincidencias de directivas DLP](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="03000-132">Ver la justificación presentada por un usuario para un reemplazo</span><span class="sxs-lookup"><span data-stu-id="03000-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="03000-133">Si la directiva de DLP permite a los usuarios invalidarla, puede usar el falso positivo y reemplazar el informe para ver el texto enviado por los usuarios en la sugerencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="03000-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo de justificación de detalles del informe de reemplazo y falso positivo DLP](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="03000-135">Tomar medidas en conocimientos y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="03000-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="03000-136">Pueden mostrar informes de conocimientos y recomendaciones donde puede hacer clic en el icono de advertencia de color rojo para ver más detalles sobre posibles problemas y tomar medidas correctivas posibles.</span><span class="sxs-lookup"><span data-stu-id="03000-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Al hacer clic en un icono de conocimientos para ver detalles y acciones que se realizarán](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="03000-138">Busque los cmdlets para los informes DLP</span><span class="sxs-lookup"><span data-stu-id="03000-138">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="03000-139">Para utilizar la mayoría de los cmdlets para la seguridad &amp; centro de cumplimiento, necesita:</span><span class="sxs-lookup"><span data-stu-id="03000-139">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="03000-140">Conectarse a la seguridad de Office 365 &amp; centro de cumplimiento de normas mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="03000-140">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="03000-141">Use cualquiera de estas [Office 365 seguridad &amp; centro de cumplimiento cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="03000-141">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="03000-p108">Sin embargo, los informes de DLP necesitan extraer datos de a través de Office 365, como Exchange Online. Por este motivo, los cmdlets de para los informes DLP están disponibles en Exchange Online Powershell, no en seguridad &amp; Powershell de centro de cumplimiento. Por lo tanto, para usar los cmdlets de para los informes DLP, necesitará:</span><span class="sxs-lookup"><span data-stu-id="03000-p108">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="03000-145">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="03000-145">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="03000-146">Use cualquiera de estos cmdlets para los informes DLP:</span><span class="sxs-lookup"><span data-stu-id="03000-146">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="03000-147">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="03000-147">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="03000-148">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="03000-148">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    


---
title: Ver el uso de etiquetas con el análisis de etiquetas
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Después de crear sus etiquetas de retención y de confidencialidad, le interesará ver cómo se utilizan en el espacio empresarial. Con el análisis de etiquetas en el Centro de cumplimiento de Microsoft 365 y el Centro de seguridad de Microsoft 365, puede ver rápidamente las etiquetas que más se usan y dónde se aplican
ms.openlocfilehash: d0289eb79dca04262ef61d58a8e622ae6d7cbe93
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254598"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="73068-104">Ver el uso de etiquetas con el análisis de etiquetas</span><span class="sxs-lookup"><span data-stu-id="73068-104">View label usage with label analytics</span></span>

<span data-ttu-id="73068-105">Después de crear sus etiquetas de retención y de confidencialidad, le interesará ver cómo se utilizan en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="73068-105">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="73068-106">Con el análisis de etiquetas en el Centro de cumplimiento de Microsoft 365 y el Centro de seguridad de Microsoft 365, puede ver rápidamente las etiquetas que más se usan y dónde se aplican</span><span class="sxs-lookup"><span data-stu-id="73068-106">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="73068-107">Por ejemplo, con el análisis de etiquetas, puede ver:</span><span class="sxs-lookup"><span data-stu-id="73068-107">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="73068-108">El número total de etiquetas de retención y etiquetas de confidencialidad aplicadas al contenido.</span><span class="sxs-lookup"><span data-stu-id="73068-108">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="73068-109">Las etiquetas principales y el número de veces que se ha aplicado cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="73068-109">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="73068-110">Las ubicaciones en las que se aplican las etiquetas y el número de veces en cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="73068-110">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="73068-111">El número de archivos y carpetas cuya etiqueta de retención se ha cambiado o eliminado.</span><span class="sxs-lookup"><span data-stu-id="73068-111">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="73068-112">Puede encontrar el análisis de etiquetas en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/labelanalytics) o [Centro de seguridad de Microsoft 365](https://security.microsoft.com/labelanalytics) > **Clasificación**  >  **Análisis de etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="73068-112">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![Página de análisis de etiquetas](media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="73068-114">Uso de etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="73068-114">Sensitivity label usage</span></span>

<span data-ttu-id="73068-115">Los datos sobre el uso de las etiqueta de confidencialidad se extraen de los informes de Azure Information Protection: para obtener más información, vea [Informes centrales de Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/reports-aip).</span><span class="sxs-lookup"><span data-stu-id="73068-115">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="73068-116">Tenga en cuenta que los informes de Azure Information Protection tienen [requisitos previos](https://docs.microsoft.com/es-ES/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics) que también se aplican a los análisis de etiquetas en las etiquetas de confidencialidad en el Centro de seguridad de Microsoft 365 y el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73068-116">Note that the Azure Information Protection reports have [prerequisites](https://docs.microsoft.com/es-ES/azure/information-protection/reports-aip#prerequisites-for-azure-information-protection-analytics) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="73068-117">Por ejemplo, necesita una suscripción de Azure que incluya Log Analytics porque estos informes son el resultado de enviar eventos de auditoría de protección de información de clientes de Azure Information Protection y escáneres a una ubicación centralizada basada en el servicio Log Analytics de Azure.</span><span class="sxs-lookup"><span data-stu-id="73068-117">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="73068-118">Para el uso de etiquetas de confidencialidad:</span><span class="sxs-lookup"><span data-stu-id="73068-118">For sensitivity label usage:</span></span>

- <span data-ttu-id="73068-119">No hay ninguna latencia en los datos.</span><span class="sxs-lookup"><span data-stu-id="73068-119">There is no latency in the data.</span></span> <span data-ttu-id="73068-120">Se trata de un informe en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="73068-120">This is a real-time report.</span></span>
- <span data-ttu-id="73068-121">Para ver la cantidad de cada etiqueta principal, seleccione el gráfico de barras y lea la información sobre herramientas que aparece.</span><span class="sxs-lookup"><span data-stu-id="73068-121">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="73068-122">El informe muestra dónde se aplican las etiquetas de confidencialidad por aplicación (mientras que las etiquetas de retención se muestran por ubicación).</span><span class="sxs-lookup"><span data-stu-id="73068-122">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![Informe de uso de etiquetas de confidencialidad](media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="73068-124">Uso de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="73068-124">Retention label usage</span></span>

<span data-ttu-id="73068-125">Este informe muestra una vista rápida de cuáles son las etiquetas principales y dónde se aplican.</span><span class="sxs-lookup"><span data-stu-id="73068-125">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="73068-126">Para obtener más información sobre cómo se etiqueta contenido en SharePoint y OneDrive, vea [Ver la actividad de etiqueta de documentos](view-label-activity-for-documents.md).</span><span class="sxs-lookup"><span data-stu-id="73068-126">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="73068-127">Para el uso de etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="73068-127">For retention label usage:</span></span>

- <span data-ttu-id="73068-128">Los datos se agregan semanalmente, por lo que pueden tardar hasta siete días en aparecer en el informe.</span><span class="sxs-lookup"><span data-stu-id="73068-128">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="73068-129">Para ver la cantidad de cada etiqueta principal, seleccione el gráfico de barras y lea la información sobre herramientas que aparece.</span><span class="sxs-lookup"><span data-stu-id="73068-129">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="73068-130">El informe muestra dónde se aplican las etiquetas de retención por ubicación (mientras que las etiquetas de confidencialidad se muestran por aplicación).</span><span class="sxs-lookup"><span data-stu-id="73068-130">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="73068-131">Para las etiquetas de retención, este es un resumen de todos los datos del espacio empresarial; no se filtra para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="73068-131">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="73068-132">Por el contrario, el [Explorador de actividad de etiquetas](view-label-activity-for-documents.md) muestra los datos de solo los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="73068-132">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![Informe de uso de etiquetas de retención](media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="73068-134">Ver todo el contenido con una etiqueta de retención específica</span><span class="sxs-lookup"><span data-stu-id="73068-134">View all content with a specific retention label</span></span>

<span data-ttu-id="73068-135">En el informe de uso de etiquetas de retención, puede explorar rápidamente todo el contenido con esa etiqueta aplicada.</span><span class="sxs-lookup"><span data-stu-id="73068-135">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="73068-136">(Tenga en cuenta que estamos trabajando actualmente en esta característica, por lo que requerirá menos pasos para ver todo el contenido con la etiqueta).</span><span class="sxs-lookup"><span data-stu-id="73068-136">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="73068-137">Primero, elija **Ver detalles** en la parte inferior del informe.</span><span class="sxs-lookup"><span data-stu-id="73068-137">First, choose **View Details** at the bottom of the report.</span></span>

![Opción de Ver detalles en la parte inferior del informe de uso de etiquetas de retención](media/retention-label-usage-view-details.png)

<span data-ttu-id="73068-139">Después elija una etiqueta de retención > **Explorar elementos** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="73068-139">Then choose a retention label > **Explore items** in the right pane.</span></span>

![Opción Explorar los elementos en el panel derecho](media/retention-label-usage-explore-items.png)

<span data-ttu-id="73068-141">Para esa etiqueta, puede elegir la ficha **Actividad** para ver el número de elementos con esa etiqueta según la ubicación.</span><span class="sxs-lookup"><span data-stu-id="73068-141">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![Ficha actividad para una etiqueta de retención](media/retention-label-usage-activity-tab.png)

<span data-ttu-id="73068-143">También puede elegir la ficha **Elementos con esta etiqueta**. Después, puede explorar ubicaciones específicas:</span><span class="sxs-lookup"><span data-stu-id="73068-143">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="73068-144">Para Exchange Online, verá una lista de buzones con el número de elementos con la etiqueta en cada buzón.</span><span class="sxs-lookup"><span data-stu-id="73068-144">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="73068-145">En SharePoint Online y OneDrive para la Empresa, verá una lista de colecciones de sitios y cuentas de OneDrive con el número de elementos etiquetados en cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="73068-145">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="73068-146">Al elegir una colección de sitios o un buzón, puede ver una lista de los elementos con esa etiqueta de retención en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="73068-146">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![Ficha Elementos con esta etiqueta que muestra todos los elementos con esa etiqueta de retención](media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="73068-148">Permisos</span><span class="sxs-lookup"><span data-stu-id="73068-148">Permissions</span></span>

<span data-ttu-id="73068-149">Para ver el análisis de etiquetas, debe tener asignado uno de los roles siguientes de Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="73068-149">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="73068-150">Administrador global</span><span class="sxs-lookup"><span data-stu-id="73068-150">Global administrator</span></span>
- <span data-ttu-id="73068-151">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="73068-151">Compliance administrator</span></span>
- <span data-ttu-id="73068-152">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="73068-152">Security administrator</span></span>
- <span data-ttu-id="73068-153">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="73068-153">Security reader</span></span>

<span data-ttu-id="73068-154">Además, tenga en cuenta que estos informes usan Azure Monitor para almacenar los datos en un área de trabajo de Log Analytics que pertenezca a su organización.</span><span class="sxs-lookup"><span data-stu-id="73068-154">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="73068-155">Por lo tanto, el usuario debería agregarse como un lector para el espacio de trabajo de supervisión de Azure que contiene los datos. Para obtener más información, vea [Permisos necesarios para los análisis de Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span><span class="sxs-lookup"><span data-stu-id="73068-155">Therefore, the user should be added as a reader to the Azure Monitoring worksapce that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/es-ES/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>


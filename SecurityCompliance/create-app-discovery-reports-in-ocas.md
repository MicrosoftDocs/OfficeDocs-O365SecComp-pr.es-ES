---
title: Crear informes de detección de aplicaciones con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Cree informes con Office 365 Cloud App Security que le permita conocer cómo los usuarios de su organización usan Office 365 y otras aplicaciones.
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220300"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="c9c61-103">Crear informes de detección de aplicaciones con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c9c61-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="c9c61-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c9c61-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="c9c61-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c9c61-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="c9c61-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c9c61-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="c9c61-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="c9c61-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="c9c61-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="c9c61-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="c9c61-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="c9c61-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="c9c61-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="c9c61-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="c9c61-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="c9c61-111">You are here!</span></span>  <br/> [<span data-ttu-id="c9c61-112">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c9c61-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="c9c61-p101">Office 365 Cloud App Security ayuda a los administradores globales, a los administradores de seguridad y a los lectores de seguridad a obtener información sobre los servicios de nube que usan los usuarios de una organización. Por ejemplo, puede ver dónde los usuarios almacenan y colaboran en documentos y cuántos datos se cargan en aplicaciones o servicios que se encuentran fuera de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9c61-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="c9c61-115">Para generar un informe de detección de aplicaciones, cargue manualmente los archivos de registro de tráfico web desde sus firewalls y servidores proxy y, a continuación, Office 365 Cloud App Security analiza y analiza estos archivos para el informe.</span><span class="sxs-lookup"><span data-stu-id="c9c61-115">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9c61-p102">Debe ser un administrador global, un administrador de seguridad o un lector de seguridad para realizar las tareas descritas en este artículo. Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c9c61-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="c9c61-118">Crear un informe con detección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c9c61-118">Create a report with app discovery</span></span>

<span data-ttu-id="c9c61-119">Para crear un informe de detección de aplicaciones, identifique el origen de datos del proveedor para los archivos de registro que desee analizar, seleccione los archivos de registro y, a continuación, solicite el informe.</span><span class="sxs-lookup"><span data-stu-id="c9c61-119">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9c61-120">Use los archivos de registro de tráfico web que incluyan períodos de tráfico máximos para obtener la mejor representación del uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="c9c61-120">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="c9c61-121">Recopilar los [registros de tráfico y los orígenes de datos Web para Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="c9c61-121">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="c9c61-122">Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="c9c61-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="c9c61-123">Elija **descubrir** \> **crear nuevo informe**.</span><span class="sxs-lookup"><span data-stu-id="c9c61-123">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="c9c61-124">![En el portal de Office 365 CAS, elija descubrir](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="c9c61-124">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="c9c61-125">Especifique un nombre y una descripción para el informe y, a continuación, seleccione el origen de datos para los registros de tráfico web en la lista **origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="c9c61-125">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="c9c61-126">![En entidades de certificación de O365 \> , elija descubrir crear nuevo informe.](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="c9c61-126">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="c9c61-p103">Si no aparece un origen de datos que le gustaría usar, puede solicitar que se agregue. Seleccione **otro** para **origen de datos**y, a continuación, escriba el nombre del origen de datos que está intentando cargar. Revisaremos el registro y le indicaremos si se agrega compatibilidad para el origen de datos que lo generó.</span><span class="sxs-lookup"><span data-stu-id="c9c61-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="c9c61-p104">Vaya a la ubicación de los archivos de registro que recopiló y seleccione los archivos. Los archivos de registro deben haber sido generados por el origen de datos elegido para el informe.</span><span class="sxs-lookup"><span data-stu-id="c9c61-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="c9c61-132">Haga clic en **crear** para iniciar el proceso de creación de informes.</span><span class="sxs-lookup"><span data-stu-id="c9c61-132">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="c9c61-p105">Para ver el estado del informe, haga clic en **administrar informes**de instantáneas. Cuando un informe esté listo, verá la opción **Ver informe** .</span><span class="sxs-lookup"><span data-stu-id="c9c61-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="c9c61-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c9c61-135">Next steps</span></span>

- [<span data-ttu-id="c9c61-136">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="c9c61-136">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="c9c61-137">Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c9c61-137">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="c9c61-138">Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="c9c61-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


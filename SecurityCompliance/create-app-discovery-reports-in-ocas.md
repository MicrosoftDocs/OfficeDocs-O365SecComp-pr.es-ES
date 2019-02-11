---
title: Crear informes de detección de aplicaciones con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Crear informes con Office 365 en la nube seguridad de la aplicación que permiten a comprender cómo las personas de su organización están usando Office 365 y otras aplicaciones.
ms.openlocfilehash: 543a194ec9d441a4feea97b8ad49022094565d7a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603721"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a><span data-ttu-id="bdb39-103">Crear informes de detección de aplicaciones con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bdb39-103">Create app discovery reports using Office 365 Cloud App Security</span></span>

<span data-ttu-id="bdb39-104">Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bdb39-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="bdb39-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="bdb39-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="bdb39-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="bdb39-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="bdb39-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="bdb39-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="bdb39-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="bdb39-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="bdb39-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="bdb39-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="bdb39-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="bdb39-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="bdb39-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="bdb39-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="bdb39-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="bdb39-112">You are here!</span></span>  <br/> [<span data-ttu-id="bdb39-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bdb39-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="bdb39-p101">Seguridad de la aplicación en la nube Office 365 ayuda a los administradores globales, los administradores de seguridad y obtenga información sobre los servicios de nube de personas en una organización de lectores de seguridad. Por ejemplo, puede ver donde los usuarios se almacenar y colaborar en los documentos y la cantidad de datos se está cargando en aplicaciones o servicios que están fuera de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bdb39-p101">Office 365 Cloud App Security helps global administrators, security administrators, and security readers gain insight into the cloud services people in an organization are using. For example, you can see where users are storing and collaborating on documents and how much data is being uploaded to apps or services that are outside of Office 365.</span></span>
  
<span data-ttu-id="bdb39-116">Para generar un informe de detección de aplicaciones, cargar manualmente los archivos de registro del tráfico web desde los servidores de seguridad y los servidores proxy y, a continuación, la seguridad de la aplicación de nube de Office 365 analiza y analiza los archivos para el informe.</span><span class="sxs-lookup"><span data-stu-id="bdb39-116">To generate an app discovery report, you manually upload your web traffic log files from your firewalls and proxies, and then Office 365 Cloud App Security parses and analyzes those files for your report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdb39-p102">Debe ser un administrador global, Administrador de seguridad o lector de seguridad para llevar a cabo las tareas descritas en este artículo. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bdb39-p102">You must be a global administrator, security administrator, or security reader to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="create-a-report-with-app-discovery"></a><span data-ttu-id="bdb39-119">Crear un informe con la detección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="bdb39-119">Create a report with app discovery</span></span>

<span data-ttu-id="bdb39-120">Para crear un informe de detección de aplicaciones, identifique el origen de datos del proveedor para los archivos de registro que se desean analizado, seleccione los archivos de registro y, a continuación, solicitar el informe.</span><span class="sxs-lookup"><span data-stu-id="bdb39-120">To create an app discovery report, you identify the vendor data source for the log files that you want to have analyzed, select the log files, and then request the report.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdb39-121">Use los archivos de registro de tráfico web que incluyen los períodos de tráfico para obtener la mejor representación de uso en su organización.</span><span class="sxs-lookup"><span data-stu-id="bdb39-121">Use web traffic log files that include peak traffic periods to get the best representation of usage in your organization.</span></span> 
  
1. <span data-ttu-id="bdb39-122">Recopilar los [registros de tráfico web y orígenes de datos de seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="bdb39-122">Collect your [web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md).</span></span>
    
2. <span data-ttu-id="bdb39-123">Vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="bdb39-123">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> 
       
3. <span data-ttu-id="bdb39-124">Elija **detección** \> **crear un nuevo informe**.</span><span class="sxs-lookup"><span data-stu-id="bdb39-124">Choose **Discover** \> **Create new report**.</span></span> <br><span data-ttu-id="bdb39-125">![En el portal de Office 365 CAS, elija detectar](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span><span class="sxs-lookup"><span data-stu-id="bdb39-125">![In the Office 365 CAS portal, choose Discover](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)</span></span><br>
  
4. <span data-ttu-id="bdb39-126">Especifique un nombre y una descripción para el informe y, a continuación, seleccione el origen de datos de sus registros de tráfico web en la lista de **origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="bdb39-126">Specify a name and description for your report, and then select the data source for your web traffic logs in the **Data source** list.</span></span> <br><span data-ttu-id="bdb39-127">![En Office 365 CAS, elija detectar \> crear nuevo informe](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span><span class="sxs-lookup"><span data-stu-id="bdb39-127">![In O365 CAS, choose Discover \> Create new report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)</span></span><br><span data-ttu-id="bdb39-p103">Si un origen de datos que desea usar no aparece, puede solicitar que se agrega. Seleccione **otro** origen de **datos**y, a continuación, escriba el nombre del origen de datos que está intentando cargar. Se podrá revisar el registro de y le permiten conocer si se agrega compatibilidad para el origen de datos que lo generó.</span><span class="sxs-lookup"><span data-stu-id="bdb39-p103">If a data source that you'd like to use is not listed, you can request that it be added. Select **Other** for **Data source**, and then type the name of the data source that you're trying to upload. We'll review the log, and let you know if we add support for the data source that generated it.</span></span> 
  
5. <span data-ttu-id="bdb39-p104">Vaya a la ubicación de los archivos de registro que recopilan y seleccione los archivos. Los archivos de registro deben haberse generados por el origen de datos que haya elegido para el informe.</span><span class="sxs-lookup"><span data-stu-id="bdb39-p104">Browse to the location of the log files you collected and select the files. The log files must have been generated by the data source that you chose for the report.</span></span>
    
6. <span data-ttu-id="bdb39-133">Haga clic en **crear** para iniciar el proceso de creación de informes.</span><span class="sxs-lookup"><span data-stu-id="bdb39-133">Click **Create** to start the report creation process.</span></span> 
    
7. <span data-ttu-id="bdb39-p105">Para ver el estado del informe, haga clic en **administrar los informes de instantáneas**. Cuando el informe está listo, verá la opción de **Ver el informe** .</span><span class="sxs-lookup"><span data-stu-id="bdb39-p105">To see the status of the report, click **Manage snapshot reports**. When a report is ready, you'll see the **View report** option.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="bdb39-136">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bdb39-136">Next steps</span></span>

- [<span data-ttu-id="bdb39-137">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="bdb39-137">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="bdb39-138">Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bdb39-138">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="bdb39-139">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="bdb39-139">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


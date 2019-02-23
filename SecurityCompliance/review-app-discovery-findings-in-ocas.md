---
title: Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Revisar los informes de detección de aplicaciones en Office 365 Cloud App Security puede ayudarle a obtener más información sobre cómo los usuarios de su organización usan aplicaciones en la nube. Una vez que haya creado los informes de detección de aplicaciones con archivos de registro de los firewalls y servidores proxy, revise los resultados en el panel de detección de aplicaciones.
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216260"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="bdc2f-104">Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bdc2f-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="bdc2f-105">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bdc2f-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="bdc2f-106">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bdc2f-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="bdc2f-107">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bdc2f-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="bdc2f-108">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="bdc2f-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="bdc2f-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="bdc2f-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="bdc2f-110">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="bdc2f-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="bdc2f-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="bdc2f-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="bdc2f-112">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-112">You are here!</span></span>  <br/> [<span data-ttu-id="bdc2f-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bdc2f-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="bdc2f-p102">El panel de detección en la nube funciona con los registros de tráfico web de la organización para proporcionar información detallada sobre el uso de aplicaciones en la nube. Si es administrador global, administrador de seguridad o lector de seguridad y su organización ha [creado informes de detección de aplicaciones en Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), puede usar el panel de detección en la nube para conocer la forma en que los usuarios de su organización usan Office 365 y otras aplicaciones en la nube. (El panel de detección en la nube también se conoce como detección de aplicaciones de productividad).</span><span class="sxs-lookup"><span data-stu-id="bdc2f-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="bdc2f-117">El panel de detección en la nube le permite ver información detallada sobre la forma en que los usuarios de su organización usan Office 365 y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-117">The Cloud Discovery dashboard enables you to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![Se ha actualizado el panel de detección en la nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="bdc2f-119">Ir al panel de detección en la nube</span><span class="sxs-lookup"><span data-stu-id="bdc2f-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="bdc2f-120">Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-120">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="bdc2f-121">Vaya al panel **Descubra** \> **detección en la nube**.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-121">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="bdc2f-122">Ver los usuarios principales, las direcciones IP, las aplicaciones y los niveles de riesgo</span><span class="sxs-lookup"><span data-stu-id="bdc2f-122">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="bdc2f-123">El panel de detección en la nube le ofrece una visión general de las aplicaciones que se usan con Office 365 en su organización, las alertas abiertas, los usuarios principales y los niveles de riesgo.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-123">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![Detección en la nube dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="bdc2f-125">En la pestaña **Panel** , mire el uso general de la aplicación de nube en su organización en la sección información general en la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-125">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="bdc2f-126">Vea las **categorías de Office 365** para las aplicaciones que se usan en su organización.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-126">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="bdc2f-127">Mire el widget **aplicaciones** descubiertas para ver el uso de Office 365 y otras aplicaciones en esta vista.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-127">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="bdc2f-128">Mire el widget **principales usuarios** y **direcciones IP principales** para identificar a los usuarios de Office 365 y de la nube la mayor parte de su organización.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-128">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="bdc2f-129">Vea dónde las aplicaciones que usan los usuarios se encuentran en la ubicación geográfica con el mapa de ubicación de las **oficinas centrales de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="bdc2f-129">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="bdc2f-p103">Por encima del área mapas, eche un vistazo a la puntuación de riesgo de las aplicaciones detectadas en la introducción a **los niveles de riesgo** . Puede ver los riesgos en los mismos grupos y categorías que usó en el área de **aplicaciones detectadas** . Por ejemplo, puede ver la cantidad de tráfico de cada agrupación de aplicaciones de riesgo alta, media o baja.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-p103">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="bdc2f-133">Profundizar más en la información</span><span class="sxs-lookup"><span data-stu-id="bdc2f-133">Dive deeper into the information</span></span>

<span data-ttu-id="bdc2f-134">Puede usar detección en la nube para profundizar en las aplicaciones, subdominios, direcciones IP y usuarios.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-134">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="bdc2f-135">En el panel detección en la nube, elija la pestaña **aplicaciones detectadas** .</span><span class="sxs-lookup"><span data-stu-id="bdc2f-135">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="bdc2f-136">Use la sección Filtros para ver las aplicaciones por nombre, categoría, nivel de uso o fecha de última visualización.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-136">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="bdc2f-137">En la lista de resultados, mantenga el mouse por un nombre de aplicación para mostrar el vínculo **Ver** subdominios.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-137">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="bdc2f-138">![Mantener el mouse junto a una aplicación para mostrar un vínculo para ver los detalles de subdominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="bdc2f-138">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="bdc2f-139">Se mostrará información detallada sobre la aplicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-139">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="bdc2f-140">Para ver los detalles de las direcciones IP, seleccione la pestaña **direcciones IP** .</span><span class="sxs-lookup"><span data-stu-id="bdc2f-140">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="bdc2f-141">![Detección en la nube muestra información detallada sobre las direcciones IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="bdc2f-141">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="bdc2f-142">En la lista de resultados, seleccione una dirección IP individual para ver información más detallada.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-142">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="bdc2f-143">Para ver información detallada sobre los usuarios de Office 365 dentro de su organización, elija la pestaña **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="bdc2f-143">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="bdc2f-144">![Detección en la nube: información de los usuarios](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="bdc2f-144">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="bdc2f-145">Excluir entidades</span><span class="sxs-lookup"><span data-stu-id="bdc2f-145">Exclude entities</span></span>

<span data-ttu-id="bdc2f-146">Puede excluir determinados usuarios del sistema o direcciones IP para poder centrarse en información más específica.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-146">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="bdc2f-147">Elija Configuración de **detección en la nube**. \*\*\*\* \></span><span class="sxs-lookup"><span data-stu-id="bdc2f-147">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="bdc2f-148">Elija **excluir entidades**.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-148">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="bdc2f-149">Elija **usuarios excluidos** o **direcciones IP excluidas**.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-149">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="bdc2f-150">Especifique los usuarios o las direcciones IP y, en el cuadro **comentarios** , escriba información sobre los motivos por los que se excluyen los usuarios o las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-150">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="bdc2f-151">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bdc2f-151">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="bdc2f-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bdc2f-152">Next steps</span></span>

- [<span data-ttu-id="bdc2f-153">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="bdc2f-153">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="bdc2f-154">Crear informes de detección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="bdc2f-154">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="bdc2f-155">Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="bdc2f-155">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


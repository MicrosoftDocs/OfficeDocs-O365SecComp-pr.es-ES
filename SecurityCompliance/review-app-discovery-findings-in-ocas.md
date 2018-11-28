---
title: Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Revisión de informes de detección de aplicaciones en administración avanzada de seguridad le ayudarán a obtener más información acerca de cómo las personas de su organización utilizan aplicaciones de nube. Después de crear informes de detección de aplicación con archivos de registro de los firewalls y servidores proxy, revise los resultados en el panel de la detección de la aplicación.
ms.openlocfilehash: ddf3826f5aac9d3c837cf66f1b97b4650df70f32
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706264"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a><span data-ttu-id="3be1f-104">Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3be1f-104">Review app discovery findings in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="3be1f-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="3be1f-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="3be1f-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="3be1f-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="3be1f-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="3be1f-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="3be1f-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="3be1f-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="3be1f-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="3be1f-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="3be1f-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="3be1f-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="3be1f-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="3be1f-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="3be1f-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="3be1f-112">You are here!</span></span>  <br/> [<span data-ttu-id="3be1f-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3be1f-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="3be1f-p102">El panel de detección de la nube funciona con registros de tráfico web de la organización para proporcionar información detallada sobre el uso de la aplicación en la nube. Si usted es un administrador global, Administrador de seguridad o lector de seguridad y su organización tiene [creado informes de detección de aplicaciones en la seguridad de la aplicación de nube de Office 365](create-app-discovery-reports-in-ocas.md), puede usar el panel de detección en la nube para comprender mejor cómo de personas en su organización está usando Office 365 y otras aplicaciones en la nube. (El panel de detección de la nube también conocido como está detección de aplicaciones de productividad).</span><span class="sxs-lookup"><span data-stu-id="3be1f-p102">The Cloud Discovery dashboard works with your organization's web traffic logs to provide detailed information about cloud app usage. If you're a global administrator, security administrator, or security reader, and your organization has [created app discovery reports in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), you can use the Cloud Discovery dashboard to gain insight into how people in your organization are using Office 365 and other cloud apps. (The Cloud Discovery dashboard is also known as Productivity App Discovery.)</span></span>
  
 <span data-ttu-id="3be1f-117">**A partir de marzo 2018, el panel de detección de la nube tiene nuevas características** que hacen que sea más fácil ver información detallada acerca de cómo las personas de su organización están usando Office 365 y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3be1f-117">**As of March 2018, the Cloud Discovery dashboard has new features** that make it easier to view detailed information about how people in your organization are using Office 365 and other apps.</span></span> 
  
![Se ha actualizado el panel detección de nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a><span data-ttu-id="3be1f-119">Vaya al panel de detección de la nube</span><span class="sxs-lookup"><span data-stu-id="3be1f-119">Go to the Cloud Discovery dashboard</span></span>

1. <span data-ttu-id="3be1f-p103">Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)</span><span class="sxs-lookup"><span data-stu-id="3be1f-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="3be1f-122">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span><br/><span data-ttu-id="3be1f-123">(Si no está habilitado aún seguridad de la aplicación de nube de Office 365, y debe ser un administrador global, [activar la seguridad de la aplicación de nube de Office 365](turn-on-office-365-cas.md).)</span><span class="sxs-lookup"><span data-stu-id="3be1f-123">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="3be1f-124">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-124">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="3be1f-125">Vaya a **descubrir** \> **panel de detección de la nube**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-125">Go to **Discover** \> **Cloud Discovery dashboard**.</span></span>
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a><span data-ttu-id="3be1f-126">Vea sus usuarios principales, direcciones IP, aplicaciones y niveles de riesgo</span><span class="sxs-lookup"><span data-stu-id="3be1f-126">See your top users, IP addresses, apps, and risk levels</span></span>

<span data-ttu-id="3be1f-127">El panel de detección de la nube le ofrece una introducción de un vistazo a las aplicaciones que se usan con Office 365 en su organización, cualquier alertas abiertas, superior a los usuarios y niveles de riesgo.</span><span class="sxs-lookup"><span data-stu-id="3be1f-127">The Cloud Discovery dashboard gives you an at-a-glance overview of apps that are used with Office 365 in your organization, any open alerts, top users, and risk levels.</span></span>
  
![Dashboaard de detección de la nube](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. <span data-ttu-id="3be1f-129">En la ficha de **panel** , examine el uso de aplicación en la nube global en la organización en la sección información general en la parte superior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="3be1f-129">On the **Dashboard** tab, look at the overall cloud app use in your organization in the overview section across the top of the screen.</span></span> 
    
2. <span data-ttu-id="3be1f-130">Ver las **categorías de Office 365** para las aplicaciones que se usan en su organización.</span><span class="sxs-lookup"><span data-stu-id="3be1f-130">See the **Office 365 categories** for apps that are used in your organization.</span></span> 
    
3. <span data-ttu-id="3be1f-131">Examine el widget **Discovered aplicaciones** para ver el uso de Office 365 y otras aplicaciones en esta vista.</span><span class="sxs-lookup"><span data-stu-id="3be1f-131">Look at the **Discovered apps** widget to see usage of Office 365 and other apps in this view.</span></span> 
    
4. <span data-ttu-id="3be1f-132">Examine el widget **superior a los usuarios** y **las direcciones IP de la parte superior** para identificar aquellos que usar Office 365 y en la nube de aplicaciones en la mayor parte de la organización.</span><span class="sxs-lookup"><span data-stu-id="3be1f-132">Look at the **Top users** and **Top IP addresses** widget to identify those who use Office 365 and cloud apps the most in your organization.</span></span> 
    
5. <span data-ttu-id="3be1f-133">Vea dónde están las aplicaciones que usan las personas por ubicación geográfica mediante el uso de la asignación de **ubicación de sedes centrales de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="3be1f-133">See where the apps people are using are by geographical location by using the **Apps headquarters location** map.</span></span> 
    
6. <span data-ttu-id="3be1f-p104">Sobre el área de mapas, eche un vistazo en la puntuación de riesgo de las aplicaciones descubiertas en la información general de **los niveles de riesgo** . Puede mirar los riesgos por los mismos grupos y categorías que se usaron en el área de **aplicaciones Discovered** . Por ejemplo, puede ver es la cantidad de tráfico en cada agrupación de aplicaciones de riesgo alto, medio o bajo.</span><span class="sxs-lookup"><span data-stu-id="3be1f-p104">Above the maps area, take a look at the risk score of the discovered apps in the **Risk levels** overview. You can look at risks by the same groups and categories that you used in the **Discovered apps** area. For example, you can see how much traffic in each grouping is from high, medium, or low risk apps.</span></span> 
    
## <a name="dive-deeper-into-the-information"></a><span data-ttu-id="3be1f-137">Profundizan en la información</span><span class="sxs-lookup"><span data-stu-id="3be1f-137">Dive deeper into the information</span></span>

<span data-ttu-id="3be1f-138">Puede usar la detección en la nube para Eche un vistazo más profundo de aplicaciones, subdominios, direcciones IP y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3be1f-138">You can use Cloud Discovery to take a deeper look at apps, subdomains, IP addresses, and users.</span></span>
  
1. <span data-ttu-id="3be1f-139">En el panel de la detección de la nube, elija la ficha **Discovered aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="3be1f-139">In the Cloud Discovery dashboard, choose the **Discovered apps** tab.</span></span> 
    
2. <span data-ttu-id="3be1f-140">Use la sección filtros para ver aplicaciones por nombre, categoría, el nivel de uso o última fecha visto.</span><span class="sxs-lookup"><span data-stu-id="3be1f-140">Use the filters section to view apps by name, category, usage level, or last seen date.</span></span>
    
3. <span data-ttu-id="3be1f-141">En la lista de resultados, pase el ratón por un nombre de la aplicación para mostrar el vínculo **Ver subdominios** .</span><span class="sxs-lookup"><span data-stu-id="3be1f-141">In the list of results, hover by an app name to reveal the **View sub-domains** link.</span></span><br/> <span data-ttu-id="3be1f-142">![Mantenga el mouse junto a una aplicación para mostrar un vínculo para ver los detalles de subdominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span><span class="sxs-lookup"><span data-stu-id="3be1f-142">![Hover next to an app to reveal a link to view subdomain details](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)</span></span><br/><span data-ttu-id="3be1f-143">Aparecerá información detallada sobre la aplicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3be1f-143">Detailed information about the selected app will appear.</span></span>
    
4. <span data-ttu-id="3be1f-144">Para ver detalles acerca de las direcciones IP, elija la pestaña **direcciones IP** .</span><span class="sxs-lookup"><span data-stu-id="3be1f-144">To view details about IP addresses, choose the **IP addresses** tab.</span></span><br/><span data-ttu-id="3be1f-145">![Detección de la nube muestra información detallada acerca de las direcciones IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span><span class="sxs-lookup"><span data-stu-id="3be1f-145">![Cloud Discovery shows detailed information about IP addresses](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)</span></span><br/><span data-ttu-id="3be1f-146">En la lista de resultados, seleccione una dirección IP individual para ver información más detallada.</span><span class="sxs-lookup"><span data-stu-id="3be1f-146">In the list of results, select an individual IP address to view more detailed information.</span></span>
    
5. <span data-ttu-id="3be1f-147">Para ver detalles acerca de los usuarios de Office 365 dentro de la organización, elija la pestaña de **los usuarios** .</span><span class="sxs-lookup"><span data-stu-id="3be1f-147">To view details about Office 365 users within your organization, choose the **Users** tab.</span></span><br/><span data-ttu-id="3be1f-148">![Detección de nube - información de los usuarios](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span><span class="sxs-lookup"><span data-stu-id="3be1f-148">![Cloud Discovery - users info](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)</span></span>
  
## <a name="exclude-entities"></a><span data-ttu-id="3be1f-149">Excluir las entidades</span><span class="sxs-lookup"><span data-stu-id="3be1f-149">Exclude entities</span></span>

<span data-ttu-id="3be1f-150">Puede excluir determinados usuarios del sistema o las direcciones IP con el fin de centrarse en información más específica.</span><span class="sxs-lookup"><span data-stu-id="3be1f-150">You can exclude certain system users or IP addresses in order to focus on more specific information.</span></span>
  
1. <span data-ttu-id="3be1f-151">Elija **configuración** \> **configuración de detección de la nube**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-151">Choose **Settings** \> **Cloud Discovery settings**.</span></span>
    
2. <span data-ttu-id="3be1f-152">Elija **excluir las entidades**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-152">Choose **Exclude entities**.</span></span>
    
3. <span data-ttu-id="3be1f-153">Elija **los usuarios excluidos** o **direcciones IP excluidos**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-153">Choose either **Excluded users** or **Excluded IP addresses**.</span></span>
    
4. <span data-ttu-id="3be1f-154">Especificar los usuarios o las direcciones IP y, en el cuadro **comentarios** , escriba información acerca de por qué se van a excluir los usuarios o direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="3be1f-154">Specify the users or IP addresses, and in the **Comments** box, type information about why you are excluding those users or IP addresses.</span></span> 
    
5. <span data-ttu-id="3be1f-155">Elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3be1f-155">Choose **Add**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="3be1f-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3be1f-156">Next steps</span></span>

- [<span data-ttu-id="3be1f-157">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="3be1f-157">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="3be1f-158">Crear informes de detección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3be1f-158">Create app discovery reports</span></span>](create-app-discovery-reports-in-ocas.md)
    
- <span data-ttu-id="3be1f-159">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="3be1f-159">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


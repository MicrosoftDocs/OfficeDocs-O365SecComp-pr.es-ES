---
title: Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: Para identificar fácilmente los conjuntos de direcciones IP que usará en la seguridad de la aplicación de nube de Office 365, como las direcciones IP de oficina física, puede configurar grupos de intervalos de direcciones IP.
ms.openlocfilehash: 76cb9625a46d1f5eceaab696de5dcbb72f4d2b47
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535617"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="db7d9-103">Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="db7d9-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="db7d9-104">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="db7d9-104">****Evaluation** \>**</span></span>|<span data-ttu-id="db7d9-105">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="db7d9-105">****Planning** \>**</span></span>|<span data-ttu-id="db7d9-106">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="db7d9-106">****Deployment** \>**</span></span>|<span data-ttu-id="db7d9-107">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="db7d9-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="db7d9-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="db7d9-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="db7d9-109">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="db7d9-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="db7d9-110">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="db7d9-110">You are here!</span></span>  <br/> [<span data-ttu-id="db7d9-111">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="db7d9-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="db7d9-112">Iniciar utilizando</span><span class="sxs-lookup"><span data-stu-id="db7d9-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="db7d9-p101">Para identificar fácilmente los conjuntos de direcciones IP que usará en la seguridad de la aplicación de nube de Office 365, como las direcciones IP de oficina física, puede configurar grupos de intervalos de direcciones IP. Definición de estos intervalos permite etiquetar y clasificar y, a continuación, puede usar etiquetas y categorías para personalizar la forma en que la actividad de los registros y las alertas se muestren e investigarse.</span><span class="sxs-lookup"><span data-stu-id="db7d9-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="db7d9-p102">Cada grupo de intervalos de IP se puede etiquetar con nombres de etiqueta que elija y, a continuación, las etiquetas se pueden clasificar en función de una lista predeterminada de categorías IP (por ejemplo, Corporate, administrativas, Risky y VPN). Se admiten las direcciones IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="db7d9-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db7d9-p103">Debe ser un administrador global o administrador de seguridad para llevar a cabo los procedimientos descritos en este artículo. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="db7d9-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="db7d9-119">Para configurar un intervalo de direcciones IP en la seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="db7d9-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="db7d9-p104">Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)</span><span class="sxs-lookup"><span data-stu-id="db7d9-p104">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="db7d9-122">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="db7d9-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="db7d9-123">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="db7d9-123">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="db7d9-125">En la esquina superior derecha de la página, haga clic en **configuración de** \> **intervalos de direcciones IP**.</span><span class="sxs-lookup"><span data-stu-id="db7d9-125">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span>
    
    ![En seguridad de la aplicación de nube de Office 365, elija Configuración para tener acceso a la configuración del sistema y de datos](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. <span data-ttu-id="db7d9-127">Haga clic en el botón nuevo, que se parece a un signo más ( **+**).</span><span class="sxs-lookup"><span data-stu-id="db7d9-127">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
6. <span data-ttu-id="db7d9-128">En la ventana de **intervalo de direcciones IP de nuevo** , especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db7d9-128">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="db7d9-129">**Campo o lista**</span><span class="sxs-lookup"><span data-stu-id="db7d9-129">**Field or list**</span></span>|<span data-ttu-id="db7d9-130">**Qué hacer**</span><span class="sxs-lookup"><span data-stu-id="db7d9-130">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db7d9-131">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="db7d9-131">**Name**</span></span> <br/> |<span data-ttu-id="db7d9-p105">Use este campo para administrar la configuración y el intervalo de direcciones IP. (No verá este valor en los registros de actividades.)</span><span class="sxs-lookup"><span data-stu-id="db7d9-p105">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="db7d9-134">**Intervalos de direcciones IP**</span><span class="sxs-lookup"><span data-stu-id="db7d9-134">**IP address ranges**</span></span> <br/> |<span data-ttu-id="db7d9-p106">Especifique un rango, con la notación de prefijo de red (también conocido como notación CIDR). Por ejemplo, 192.168.1.0/27 incluye el intervalo de valores 192.168.1.0 a través de 192.168.1.31 (ambos inclusive).</span><span class="sxs-lookup"><span data-stu-id="db7d9-p106">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="db7d9-137">**Ubicación** y **registrado ISP**</span><span class="sxs-lookup"><span data-stu-id="db7d9-137">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="db7d9-p107">Especifique la ubicación y el proveedor de servicios de Internet (ISP) para el intervalo de direcciones IP. Esto invalida los campos públicos definidos para las direcciones, lo que resulta útil para los casos, como una dirección IP es la que se considera como públicamente en Irlanda, pero es realmente en los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="db7d9-p107">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="db7d9-140">**Tags**</span><span class="sxs-lookup"><span data-stu-id="db7d9-140">**Tags**</span></span> <br/> |<span data-ttu-id="db7d9-p108">Usar etiquetas para el nombre de los grupos de direcciones IP. (A diferencia del campo nombre, verá las etiquetas en los registros de actividad.) Escriba una palabra o frase que desea usar para una etiqueta. Puede agregar tantas etiquetas como desee para cada intervalo de direcciones IP. Y, si ya ha configurado una etiqueta y que desea agregar este intervalo de direcciones IP, elija de la lista de etiquetas actuales que aparecen como comience a escribir.</span><span class="sxs-lookup"><span data-stu-id="db7d9-p108">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="db7d9-145">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="db7d9-145">**Category**</span></span> <br/> | <span data-ttu-id="db7d9-p109">Asignar categorías a las etiquetas para que sea más fácil reconocer las actividades que provienen de determinadas direcciones IP. Elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="db7d9-p109">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="db7d9-148">**Administrativas** Todas las direcciones IP de los administradores.</span><span class="sxs-lookup"><span data-stu-id="db7d9-148">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="db7d9-149">**Proveedor de nube** La dirección IP de su servidor proxy en la nube.</span><span class="sxs-lookup"><span data-stu-id="db7d9-149">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="db7d9-150">**Corporativo** Todas las direcciones IP en la red interna, las sucursales y las direcciones móviles Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="db7d9-150">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="db7d9-p110">**Arriesgar** Todas las direcciones IP que considere la posibilidad de ser arriesgado, tales como las direcciones IP sospechoso han visto en el pasado, las direcciones IP en las redes de sus competidores y así sucesivamente. De forma predeterminada, las categorías arriesgadas incluye dos etiquetas IP: **proxy anónimo** y los **términos de referencia**</span><span class="sxs-lookup"><span data-stu-id="db7d9-p110">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="db7d9-153">**VPN** Las direcciones IP que usan los trabajadores remotos.</span><span class="sxs-lookup"><span data-stu-id="db7d9-153">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="db7d9-154">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="db7d9-154">Choose **Save**.</span></span>
    
<span data-ttu-id="db7d9-155">Después de configurar los intervalos de direcciones IP, tenga en cuenta que eventos futuros sólo se ven afectados por estos cambios.</span><span class="sxs-lookup"><span data-stu-id="db7d9-155">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="db7d9-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="db7d9-156">Next steps</span></span>

- [<span data-ttu-id="db7d9-157">Las alertas y las directivas de actividad</span><span class="sxs-lookup"><span data-stu-id="db7d9-157">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="db7d9-158">Directivas de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="db7d9-158">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="db7d9-159">Integrar su servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="db7d9-159">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="db7d9-160">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="db7d9-160">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    


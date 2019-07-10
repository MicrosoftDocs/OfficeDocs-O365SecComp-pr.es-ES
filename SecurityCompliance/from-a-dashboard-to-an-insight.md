---
title: 'Tutorial: desde un panel o a un reporte'
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/04/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
ms.collection:
- M365-security-compliance
description: Obtenga información acerca de cómo puede ir de un panel a un conocimiento de las acciones recomendadas en el centro de seguridad &amp; y cumplimiento.
ms.openlocfilehash: e4ff0491e767fd4ffcf14a5ce8b5014447f80238
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599316"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="06ee4-103">Tutorial: desde un panel o a un reporte</span><span class="sxs-lookup"><span data-stu-id="06ee4-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="06ee4-104">Si no está familiarizado con [los informes y la información del centro de seguridad &amp; y cumplimiento de Office 365](reports-and-insights-in-security-and-compliance.md), es posible que le resulte útil ver cómo puede navegar fácilmente desde un panel hasta una perspectiva y las acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="06ee4-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="06ee4-105">Este es uno de los diversos tutoriales del centro &amp; de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="06ee4-105">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="06ee4-106">Para ver Tutoriales adicionales, consulte la sección [temas relacionados](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="06ee4-106">To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="06ee4-107">Tutorial: desde un panel a un conocimiento</span><span class="sxs-lookup"><span data-stu-id="06ee4-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="06ee4-108">Vamos a recorrer el flujo de un panel a un informe de una visión y una acción.</span><span class="sxs-lookup"><span data-stu-id="06ee4-108">Let's walk through the flow from a dashboard to a report to an insight and action.</span></span> <span data-ttu-id="06ee4-109">(Este es un breve ejemplo de inteligencia de suplantación de [identidad](learn-about-spoof-intelligence.md) ).</span><span class="sxs-lookup"><span data-stu-id="06ee4-109">(This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="06ee4-110">Comenzamos con el panel de seguridad en [el &amp; centro de seguridad y cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="06ee4-110">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="06ee4-111">(Vaya al \*\*\*\* \> **Panel**de administración de amenazas).</span><span class="sxs-lookup"><span data-stu-id="06ee4-111">(Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="06ee4-112">![En el centro &amp; de seguridad y cumplimiento, elija \> panel de administración de amenazas](media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="06ee4-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="06ee4-113">En la \*\*\*\* fila Insights, se observa una información que indica que es necesario revisar algunos dominios que podrían ser sospechosos.</span><span class="sxs-lookup"><span data-stu-id="06ee4-113">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious.</span></span> <span data-ttu-id="06ee4-114">(En la fila **información** , haga clic en **pares de dominios**).</span><span class="sxs-lookup"><span data-stu-id="06ee4-114">(In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="06ee4-115">![La fila Insights menciona los posibles problemas de suplantación](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="06ee4-115">![The Insights row mentions potential spoofing concerns](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="06ee4-116">Obtenemos una lista de las actividades relacionadas con la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="06ee4-116">We get a list of activities related to spoof intelligence.</span></span> <span data-ttu-id="06ee4-117">Son instancias en las que se enviaron los mensajes de correo electrónico que parecen de nuestra organización pero, de hecho, se enviaron desde otra organización.</span><span class="sxs-lookup"><span data-stu-id="06ee4-117">These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization.</span></span> <span data-ttu-id="06ee4-118">El objetivo es determinar si los mensajes suplantados están autorizados o no.</span><span class="sxs-lookup"><span data-stu-id="06ee4-118">The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="06ee4-119">![Información de inteligencia de falsificación](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="06ee4-119">![Spoof intelligence insights](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="06ee4-120">En esta lista, podemos ordenar la información por número de mensajes, fecha en la que se detectó por última vez la suplantación, etc.</span><span class="sxs-lookup"><span data-stu-id="06ee4-120">In this list, we can sort the information by message count, date the spoofing was last detected, and more.</span></span> <span data-ttu-id="06ee4-121">(Haga clic en los encabezados de columna, como **número de mensajes** o **último visto** para ver cómo funciona la ordenación.)</span><span class="sxs-lookup"><span data-stu-id="06ee4-121">(Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="06ee4-122">Al seleccionar un elemento de la lista, se abre un panel de detalles en el que se puede ver información adicional, incluidos los mensajes de correo electrónico similares que se detectaron.</span><span class="sxs-lookup"><span data-stu-id="06ee4-122">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected.</span></span> <span data-ttu-id="06ee4-123">(Haga clic en un elemento de la lista y revise la información y las recomendaciones).</span><span class="sxs-lookup"><span data-stu-id="06ee4-123">(Click an item in the list, and review the information and recommendations.)</span></span><br>![Al seleccionar un elemento se abre un panel de detalles.](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="06ee4-125">Observe que en la parte superior del panel, tenemos la opción de agregar el remitente a la lista de remitentes permitidos de la organización.</span><span class="sxs-lookup"><span data-stu-id="06ee4-125">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list.</span></span> <span data-ttu-id="06ee4-126">(No seleccione **Agregar a la lista de remitentes permitidos de ' AllowedtoSpoof '** hasta que esté seguro de que desea hacerlo.</span><span class="sxs-lookup"><span data-stu-id="06ee4-126">(Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this.</span></span> <span data-ttu-id="06ee4-127">[Obtenga más información sobre la inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).)</span><span class="sxs-lookup"><span data-stu-id="06ee4-127">[Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="06ee4-128">![Puede autorizar a un remitente](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="06ee4-128">![You can authorize a sender](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="06ee4-129">De esta forma, podemos pasar de un panel a información y acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="06ee4-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="06ee4-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="06ee4-130">Related topics</span></span>

[<span data-ttu-id="06ee4-131">Tutorial: desde una perspectiva a un informe detallado</span><span class="sxs-lookup"><span data-stu-id="06ee4-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="06ee4-132">Tutorial: desde un informe detallado a un conocimiento</span><span class="sxs-lookup"><span data-stu-id="06ee4-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  


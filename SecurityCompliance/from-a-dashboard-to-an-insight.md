---
title: 'Tutorial: desde un panel o a un reporte'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
description: Obtenga información sobre cómo puede ir desde un panel a un entendimiento con acciones recomendadas en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 9245d26a98bac34836772cb1d895c638ed5e5564
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536584"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="86d14-103">Tutorial: desde un panel o a un reporte</span><span class="sxs-lookup"><span data-stu-id="86d14-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="86d14-104">Si está familiarizado con [informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento de normas](reports-and-insights-in-security-and-compliance.md), que puede resultar útil para ver cómo puede navegar fácilmente desde un panel a un entendimiento y acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="86d14-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="86d14-p101">Se trata de uno de varios tutoriales para la seguridad &amp; centro de cumplimiento. Para ver tutoriales adicionales, vea la sección [temas relacionados](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="86d14-p101">This is one of several walkthroughs for the Security &amp; Compliance Center. To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="86d14-107">Tutorial: desde un panel para un entendimiento</span><span class="sxs-lookup"><span data-stu-id="86d14-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="86d14-p102">Examinemos el flujo de un panel a un informe a un entendimiento y la acción. (Esto es un ejemplo de [suplantación de la inteligencia](learn-about-spoof-intelligence.md) de breve).</span><span class="sxs-lookup"><span data-stu-id="86d14-p102">Let's walk through the flow from a dashboard to a report to an insight and action. (This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="86d14-p103">Empezamos con el panel de la seguridad en la seguridad &amp; centro de cumplimiento. (Vaya a **administración de amenaza** \> **panel**.)</span><span class="sxs-lookup"><span data-stu-id="86d14-p103">We begin with the Security dashboard in the Security &amp; Compliance Center. (Go to **Threat management** \> **Dashboard**.)</span></span>
    
    ![En la seguridad &amp; centro de cumplimiento, elija Administración de amenaza \> panel](media/05a38660-eb13-4960-a266-11809c453d95.png)
  
2. <span data-ttu-id="86d14-p104">En la fila de **conocimientos** , se observe un entendimiento que indica que es necesario revisar algunos dominios que podrían ser sospechosos. (En la fila de **datos** , haga clic en **pares de dominio**).</span><span class="sxs-lookup"><span data-stu-id="86d14-p104">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious. (In the **Insights** row, click **Domain pairs**.)</span></span>
    
    ![La fila de perspectivas menciones posibles problemas de suplantación de identidad](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)
  
3. <span data-ttu-id="86d14-p105">Se obtiene una lista de las actividades relacionadas con suplantación de inteligencia. Estos son instancias donde se han enviado mensajes de correo electrónico que parecen proceden de nuestra organización pero, de hecho, enviados desde otra organización. El objetivo es determinar si están autorizados los mensajes falsos o no.</span><span class="sxs-lookup"><span data-stu-id="86d14-p105">We get a list of activities related to spoof intelligence. These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization. The goal is to determine whether the spoofed messages are authorized or not.</span></span>
    
    ![Suplantación de la inteligencia insights](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)
  
    <span data-ttu-id="86d14-p106">En esta lista, podemos ordenar la información por recuento de mensajes, la fecha de que la suplantación de identidad se detectó por última vez y mucho más. (Haga clic en los encabezados de columna, como **recuento de mensaje** o **visto por última vez** para ver cómo ordenación funciona).</span><span class="sxs-lookup"><span data-stu-id="86d14-p106">In this list, we can sort the information by message count, date the spoofing was last detected, and more. (Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="86d14-p107">Al seleccionar un elemento en la lista, abrirá un panel de detalles donde podemos ver información adicional, incluidos los mensajes de correo electrónico similar que se detectaron. (Haga clic en un elemento en la lista y revise la información y recomendaciones).</span><span class="sxs-lookup"><span data-stu-id="86d14-p107">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected. (Click an item in the list, and review the information and recommendations.)</span></span>
    
    ![Al seleccionar un elemento abrirá un panel de detalles](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)
  
5. <span data-ttu-id="86d14-p108">Observe que en la parte superior del panel, tenemos la opción para agregar el remitente a la lista de remitentes permitidos de nuestra organización. (No seleccione **lista de permitidos de agregar al remitente 'AllowedtoSpoof'** hasta que esté seguro de que desea hacerlo. [Obtenga más información sobre inteligencia de réplicas](learn-about-spoof-intelligence.md).)</span><span class="sxs-lookup"><span data-stu-id="86d14-p108">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list. (Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this. [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span>
    
    ![Puede autorizar un remitente](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)
  
<span data-ttu-id="86d14-129">De este modo, se puede mover de un panel a conocimientos y acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="86d14-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="86d14-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="86d14-130">Related topics</span></span>

[<span data-ttu-id="86d14-131">Tutorial: desde una perspectiva con respecto a un informe detallado</span><span class="sxs-lookup"><span data-stu-id="86d14-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="86d14-132">Tutorial: desde un informe detallado a un entendimiento</span><span class="sxs-lookup"><span data-stu-id="86d14-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  


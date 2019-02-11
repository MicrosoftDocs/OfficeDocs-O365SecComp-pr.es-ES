---
title: Puntuación segura de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: ¿Se ha preguntado cómo proteger su organización es realmente en Office 365? Puntuación seguro está aquí para ayudar a. Puntuación seguro analiza la seguridad de su organización en función de sus actividades normales y la configuración de seguridad en Office 365 y asigna una puntuación.
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559093"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="4bb7f-105">Puntuación segura de Office 365</span><span class="sxs-lookup"><span data-stu-id="4bb7f-105">Office 365 Secure Score</span></span>

<span data-ttu-id="4bb7f-p102">**Resumen** ¿Se ha preguntado cómo proteger su organización es realmente en Office 365? Puntuación seguro está aquí para ayudar a. Puntuación seguro analiza la seguridad de su organización en función de sus actividades normales y la configuración de seguridad en Office 365 y asigna una puntuación. Lea este artículo para obtener una visión general de puntuación de seguro y cómo puede usarlo.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p102">**Summary** Ever wonder how secure your organization really is in Office 365? Secure Score is here to help. Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score. Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="4bb7f-110">Cómo llegar a la puntuación de seguro</span><span class="sxs-lookup"><span data-stu-id="4bb7f-110">How to get to Secure Score</span></span>

<span data-ttu-id="4bb7f-111">Si su organización tiene una suscripción que incluye [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/)o Premium de negocio de Office 365 y, si tiene los [permisos necesarios](#required-permissions), puede ver la puntuación seguro de su organización visitando [https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="4bb7f-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="4bb7f-112">Como alternativa, puede visitar el centro de cumplimiento de seguridad & ([https://protection.office.com](https://protection.office.com)), donde encontrará un widget de puntuación seguro que se proporciona con su calificación actual.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![Widget de puntuación seguro](media/SecureScoreWidget-o365.png)

<span data-ttu-id="4bb7f-114">El widget incluye un vínculo al panel puntuación seguro.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-114">The widget includes a link to your Secure Score dashboard.</span></span>

![Panel de puntuación seguro](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="4bb7f-116">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="4bb7f-116">How it works</span></span>

<span data-ttu-id="4bb7f-p103">Puntuación seguro determina qué servicios de Office 365 está usando (por ejemplo, OneDrive, SharePoint y Exchange), a continuación, se comparan las configuraciones y las actividades de una línea de base establecida por Microsoft. Obtendrá una puntuación en función de cómo bien alineada a la organización es con procedimientos recomendados de seguridad. También obtendrá recomendaciones en los pasos que puede realizar para mejorar la puntuación de su organización.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p103">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft. You'll get a score based on how well aligned your organization is with security best practices. You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![Cola de acciones de la herramienta de Office 365 seguro puntuación](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="4bb7f-p104">Puntuación de seguro calcula la puntuación basada en los servicios que ha comprado. Por ejemplo, si ha comprado solo un plan de Exchange Online, no se tuvo para características de seguridad de SharePoint Online. El denominador de la puntuación es la suma de todas las líneas de base para los controles que se aplican a los productos que ha comprado. El numerador es la suma de todos los controles para los que completado o parcialmente completado, las acciones para cumplir con ese control.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p104">Secure Score calculates your score based on the services you purchased. For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features. The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased. The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="4bb7f-125">Expanda una acción para obtener información sobre qué pasos que deben seguirse, protegen las amenazas que le ayudará desde y el número de puntos que aumentará su puntuación una vez seguir la recomendación.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![Acción expandida en la herramienta de Office 365 seguro puntuación](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="4bb7f-127">Para ver el impacto de sus acciones en la seguridad de su organización, seleccione la ficha **Del analizador de puntuación** y revisar el historial.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Ficha de puntuación del analizador de la herramienta de Office 365 seguro puntuación](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="4bb7f-129">Debajo del gráfico, verá una lista de acciones y las puntuaciones por categoría.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![En la ficha del analizador de puntuación que muestra un punto de datos seleccionado de gráfico](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="4bb7f-131">Acciones que están etiquetadas como **[No una puntuación]** son los que se puede realizar para su organización, pero debido a que no están conectados a la puntuación de seguro, no se cuentan.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="4bb7f-p105">En la página **Analizador de puntuación** , haga clic en un punto de datos para un día específico, a continuación, desplácese hacia abajo para ver las acciones completadas e incompletas para ese día para averiguar qué ha cambiado. La puntuación se calcula una vez al día (aproximadamente 1:00 AM PST). Si realiza un cambio en una acción medida, la puntuación actualizará automáticamente el día siguiente. Se tardan hasta 48 horas para que un cambio se refleja en su puntuación.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p105">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed. The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="4bb7f-p106">Puntuación seguro no express una medida absoluta de cómo es probable que van a obtener tipo de brecha. Expresa la medida a la que han adoptado las características que pueden desplazar el riesgo de que se pueda infringir. No hay ningún servicio puede garantizar que va a no ser tipo de brecha y la puntuación de seguro no se debe interpretar como una garantía de ninguna forma.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p106">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted features that can offset the risk of being breached. No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="4bb7f-139">Cómo ayuda proteger puntuación</span><span class="sxs-lookup"><span data-stu-id="4bb7f-139">How Secure Score helps</span></span>

<span data-ttu-id="4bb7f-p107">Con la puntuación de seguro, puede ayudar a mejorar la posición de seguridad de su organización mediante el uso de las características de seguridad integradas en Office 365 (muchas de las cuales ya adquirido pero es posible que no tenga). Aprender más acerca de estas características puede ayudar a su tranquilidad de que va a llevar los pasos adecuados para proteger su organización contra las amenazas.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p107">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of). Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="4bb7f-p108">Pero no sólo nuestra palabra de él. Los clientes que usen puntuación seguro han visto sus puntuación aumentar cinco veces mayor que los clientes que no son lo utilizan. (El aumento en su puntuación se corresponde con las características de seguridad que se usan en las organizaciones).</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p108">But don't just take our word for it. Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it. (The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="4bb7f-p109">Puntuación seguro no express una medida absoluta de cómo es probable que van a obtener tipo de brecha. Expresa la medida a la que han adoptado los controles que pueden desplazar el riesgo de que se pueda infringir. Ningún servicio puede garantizar que no se pueda infringir y puntuación seguro no se debe interpretar como una garantía de ninguna forma.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-p109">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted controls which can offset the risk of being breached. No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="4bb7f-148">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="4bb7f-148">Required permissions</span></span>

<span data-ttu-id="4bb7f-149">Para poder ver y usar el panel de puntuación seguro, debe asignar uno de los siguientes roles en Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="4bb7f-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in Azure Active Directory:</span></span>
- <span data-ttu-id="4bb7f-150">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4bb7f-150">Global Administrator</span></span>
- <span data-ttu-id="4bb7f-151">Administrador de facturación</span><span class="sxs-lookup"><span data-stu-id="4bb7f-151">Billing Administrator</span></span>
- <span data-ttu-id="4bb7f-152">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="4bb7f-152">User Administrator</span></span>
- <span data-ttu-id="4bb7f-153">Administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="4bb7f-153">Password Administrator</span></span>
- <span data-ttu-id="4bb7f-154">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="4bb7f-154">Security Administrator</span></span>
- <span data-ttu-id="4bb7f-155">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="4bb7f-155">Security Reader</span></span>
- <span data-ttu-id="4bb7f-156">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="4bb7f-156">Exchange Administrator</span></span>
- <span data-ttu-id="4bb7f-157">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="4bb7f-157">SharePoint Administrator</span></span>

 <span data-ttu-id="4bb7f-158">Los usuarios que no están asignados a un rol de administrador no podrán tener acceso a la puntuación de seguro.</span><span class="sxs-lookup"><span data-stu-id="4bb7f-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4bb7f-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4bb7f-159">Related topics</span></span>

[<span data-ttu-id="4bb7f-160">Información general del panel de seguridad</span><span class="sxs-lookup"><span data-stu-id="4bb7f-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="4bb7f-161">¿Qué suscripción tengo?</span><span class="sxs-lookup"><span data-stu-id="4bb7f-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
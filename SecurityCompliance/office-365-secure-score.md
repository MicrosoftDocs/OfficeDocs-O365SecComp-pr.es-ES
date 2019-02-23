---
title: Puntuación segura de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: ¿Alguna vez se ha preguntado cómo proteger su organización realmente en Office 365? La puntuación segura está aquí para ayudar. La puntuación segura analiza la seguridad de la organización en función de las actividades habituales y la configuración de seguridad de Office 365 y asigna una puntuación.
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220360"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="ed3fa-105">Puntuación segura de Office 365</span><span class="sxs-lookup"><span data-stu-id="ed3fa-105">Office 365 Secure Score</span></span>

<span data-ttu-id="ed3fa-p102">**Resumen** ¿Alguna vez se ha preguntado cómo proteger su organización realmente en Office 365? La puntuación segura está aquí para ayudar. La puntuación segura analiza la seguridad de la organización en función de las actividades habituales y la configuración de seguridad de Office 365 y asigna una puntuación. Lea este artículo para obtener información general sobre la puntuación segura y cómo usarla.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p102">**Summary** Ever wonder how secure your organization really is in Office 365? Secure Score is here to help. Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score. Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="ed3fa-110">Cómo obtener una puntuación segura</span><span class="sxs-lookup"><span data-stu-id="ed3fa-110">How to get to Secure Score</span></span>

<span data-ttu-id="ed3fa-111">Si su organización tiene una suscripción que incluye [office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 business](https://docs.microsoft.com/microsoft-365/business/)o Office 365 Business Premium, y tiene los [permisos necesarios](#required-permissions), puede ver la puntuación segura de su organización visitando [https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="ed3fa-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="ed3fa-112">Como alternativa, puede visitar el centro de seguridad & cumplimiento ([https://protection.office.com](https://protection.office.com)), donde encontrará un widget de puntuación segura que le proporcionará el resultado actual.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![Widget de calificación segura](media/SecureScoreWidget-o365.png)

<span data-ttu-id="ed3fa-114">El widget incluye un vínculo a su panel de calificaciones seguras.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-114">The widget includes a link to your Secure Score dashboard.</span></span>

![Panel de calificaciones seguras](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="ed3fa-116">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="ed3fa-116">How it works</span></span>

<span data-ttu-id="ed3fa-p103">La puntuación segura determina qué servicios de Office 365 está usando (como OneDrive, SharePoint y Exchange), a continuación, compara la configuración y las actividades con una línea base establecida por Microsoft. Obtendrá una puntuación según el grado de alineación de la organización con los procedimientos recomendados de seguridad. También obtendrá recomendaciones sobre los pasos que puede realizar para mejorar la puntuación de su organización.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p103">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft. You'll get a score based on how well aligned your organization is with security best practices. You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![Cola de acciones en la herramienta de puntuación segura de Office 365](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="ed3fa-p104">Puntuación segura calcula la puntuación en función de los servicios adquiridos. Por ejemplo, si solo compró un plan de Exchange Online, no recibirá ninguna de las características de seguridad de SharePoint Online. El denominador de la puntuación es la suma de todas las líneas de base de los controles que se aplican a los productos adquiridos. El numerador es la suma de todos los controles para los que ha completado, o parcialmente, las acciones para completar ese control.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p104">Secure Score calculates your score based on the services you purchased. For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features. The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased. The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="ed3fa-125">ExPanda una acción para obtener información sobre los pasos que se deben seguir, las amenazas a las que se va a proteger y cuántos puntos aumentará la puntuación una vez que se sigue la recomendación.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![Acción expandida en la herramienta de puntuación segura de Office 365](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="ed3fa-127">Para ver el impacto de las acciones en la seguridad de la organización, seleccione la ficha **analizador de puntuación** y revise el historial.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Ficha analizador de puntuación de la herramienta de puntuación segura de Office 365](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="ed3fa-129">Debajo del gráfico, verá una lista de calificaciones y acciones por categoría.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![Gráfico en la ficha analizador de puntuaciones que muestra un punto de datos seleccionado](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="ed3fa-131">Las acciones etiquetadas como **[no puntuadas]** son las que se pueden realizar para la organización, pero porque no están conectadas a la puntuación segura, no se puntuan.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="ed3fa-p105">En la página **analizador de puntuación** , haga clic en un punto de datos para un día específico y, a continuación, desplácese hacia abajo para ver las acciones completadas y incompletas de ese día para averiguar qué ha cambiado. La puntuación se calcula una vez al día (alrededor de 1:00 A.M. PST). Si realiza un cambio en una acción medida, la puntuación se actualizará automáticamente el día siguiente. Tarda hasta 48 horas en reflejarse un cambio en su puntuación.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p105">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed. The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="ed3fa-p106">La puntuación segura no expresa una medida absoluta de la probabilidad de que se infrinja. Expresa en qué medida ha adoptado características que pueden compensar el riesgo de infringirse. Ningún servicio puede garantizar que no se infrinja y la calificación segura no se debe interpretar como garantía de ningún modo.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p106">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted features that can offset the risk of being breached. No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="ed3fa-139">Cómo ayuda la puntuación segura</span><span class="sxs-lookup"><span data-stu-id="ed3fa-139">How Secure Score helps</span></span>

<span data-ttu-id="ed3fa-p107">Con la puntuación segura, puede ayudar a mejorar la postura de seguridad de su organización mediante las características de seguridad integradas en Office 365 (muchas de las cuales ya compró pero podrían no tener en cuenta). Obtener más información sobre estas características puede ayudarle a tener la tranquilidad de que está llevando a cabo los pasos correctos para proteger su organización de las amenazas.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p107">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of). Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="ed3fa-p108">Pero no solo tiene que tomar nuestra palabra. Los clientes que usan la puntuación segura han observado su puntuación en cinco veces mayor que los clientes que no la usan. (El aumento de la puntuación se corresponde con las características de seguridad que se usan en sus organizaciones).</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p108">But don't just take our word for it. Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it. (The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed3fa-p109">La puntuación segura no expresa una medida absoluta de la probabilidad de que se infrinja. Expresa la medida en que ha adoptado los controles que pueden compensar el riesgo de infringirse. Ningún servicio puede garantizar que no se infrinja y la puntuación segura no se debe interpretar como garantía de ningún modo.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-p109">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted controls which can offset the risk of being breached. No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="ed3fa-148">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ed3fa-148">Required permissions</span></span>

<span data-ttu-id="ed3fa-149">Para poder ver y usar el panel de calificaciones seguras, debe tener asignado uno de los siguientes roles en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span><span class="sxs-lookup"><span data-stu-id="ed3fa-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span></span>
- <span data-ttu-id="ed3fa-150">Administrador global</span><span class="sxs-lookup"><span data-stu-id="ed3fa-150">Global Administrator</span></span>
- <span data-ttu-id="ed3fa-151">Administrador de facturación</span><span class="sxs-lookup"><span data-stu-id="ed3fa-151">Billing Administrator</span></span>
- <span data-ttu-id="ed3fa-152">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="ed3fa-152">User Administrator</span></span>
- <span data-ttu-id="ed3fa-153">Administrador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="ed3fa-153">Password Administrator</span></span>
- <span data-ttu-id="ed3fa-154">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="ed3fa-154">Security Administrator</span></span>
- <span data-ttu-id="ed3fa-155">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="ed3fa-155">Security Reader</span></span>
- <span data-ttu-id="ed3fa-156">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="ed3fa-156">Exchange Administrator</span></span>
- <span data-ttu-id="ed3fa-157">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ed3fa-157">SharePoint Administrator</span></span>

 <span data-ttu-id="ed3fa-158">Los usuarios a los que no se les ha asignado un rol de administrador no podrán tener acceso a la puntuación segura.</span><span class="sxs-lookup"><span data-stu-id="ed3fa-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed3fa-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ed3fa-159">Related topics</span></span>

[<span data-ttu-id="ed3fa-160">Introducción al panel de seguridad</span><span class="sxs-lookup"><span data-stu-id="ed3fa-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="ed3fa-161">¿Qué suscripción tengo?</span><span class="sxs-lookup"><span data-stu-id="ed3fa-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)

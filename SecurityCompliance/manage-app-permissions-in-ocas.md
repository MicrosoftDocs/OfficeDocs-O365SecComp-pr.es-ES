---
title: Administrar aplicaciones de OAuth con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Las aplicaciones de OAuth en Office 365 Cloud App Security ayudan a administrar las aplicaciones que los usuarios descargan para usar con datos de Office 365
ms.openlocfilehash: 510cb64f2267c99b783f86a69f7b7a84db8d84dd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219830"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="b4b6d-103">Administrar aplicaciones de OAuth con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b4b6d-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="b4b6d-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b4b6d-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b4b6d-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b4b6d-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b4b6d-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b4b6d-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b4b6d-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b4b6d-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b4b6d-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="b4b6d-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b4b6d-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="b4b6d-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="b4b6d-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="b4b6d-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="b4b6d-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-111">You are here!</span></span>  <br/> [<span data-ttu-id="b4b6d-112">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b4b6d-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="b4b6d-p101">Las personas adoran aplicaciones y las descargan con frecuencia, especialmente las aplicaciones que los usuarios creen que ahorrarán tiempo al facilitar la obtención de información profesional o educativa. Sin embargo, algunas aplicaciones podrían ser un riesgo para la seguridad de la organización, en función de la información a la que tengan acceso y de cómo controlan dicha información. Con [Office 365 Cloud App Security](office-365-cas-overview.md), si es un administrador global o de seguridad, puede administrar las aplicaciones de OAuth para su organización. Puede ver las aplicaciones que usan los usuarios con datos de Office 365, los permisos que tienen las aplicaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="b4b6d-117">En este artículo se describe dónde dirigirse a administrar aplicaciones de OAuth, cómo aprobar, prohibir o informar de una aplicación y cómo crear una consulta de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="b4b6d-118">Cómo encontrar la página Administrar aplicaciones de OAuth</span><span class="sxs-lookup"><span data-stu-id="b4b6d-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="b4b6d-p102">Las aplicaciones de OAuth se administran en el portal de seguridad de aplicaciones de nube de Office 365. Debe ser administrador global o administrador de seguridad para realizar la siguiente tarea. Para obtener más información, vea [permisos en el centro &amp; de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="b4b6d-122">Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="b4b6d-123">Elija **investigar** \> **aplicaciones de OAuth**.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="b4b6d-124">![En el portal de CAS de O365, elija investigar.](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="b4b6d-125">Lo que verá en la página Administrar aplicaciones de OAuth</span><span class="sxs-lookup"><span data-stu-id="b4b6d-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="b4b6d-126">En la tabla siguiente se describen los controles y las opciones disponibles en la página Administrar aplicaciones de OAuth.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="b4b6d-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="b4b6d-127">**Item**</span></span>|<span data-ttu-id="b4b6d-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b4b6d-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4b6d-129">Icono básico en la barra de consulta de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b4b6d-129">Basic icon in the app query bar</span></span>  <br/> ![Icono que indica la vista de consulta básica para la consulta](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="b4b6d-131">Seleccione esta opción para cambiar a la vista avanzada.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="b4b6d-132">(Si ve **Basic**, está usando la vista avanzada)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="b4b6d-133">Icono avanzado en la barra de consulta de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b4b6d-133">Advanced icon in the app query bar</span></span>  <br/> ![Icono que indica la vista de consulta avanzada para la consulta](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="b4b6d-135">Seleccione esta opción para cambiar a la vista básica.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="b4b6d-136">(Si ve **avanzado**, está usando la vista básica).</span><span class="sxs-lookup"><span data-stu-id="b4b6d-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="b4b6d-137">Icono de abrir o cerrar todos los detalles en la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b4b6d-137">Open or close all details icon in the app list</span></span>  <br/> ![Haga clic en este icono para abrir o cerrar todos los detalles de todas las aplicaciones](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="b4b6d-139">Seleccione este icono para ver más o menos detalles sobre cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="b4b6d-140">Icono exportar en la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b4b6d-140">Export icon in the app list</span></span>  <br/> ![Haga clic en este icono para exportar un archivo CSV de todas las aplicaciones](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="b4b6d-142">Seleccione este icono para exportar un archivo CSV que contenga una lista de aplicaciones, el número de usuarios de cada aplicación, los permisos asociados con la aplicación, el nivel de permisos, el estado de la aplicación y el nivel de uso de la comunidad.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="b4b6d-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="b4b6d-143">Name</span></span>  <br/> |<span data-ttu-id="b4b6d-p103">Use esta para ver el nombre de una aplicación. Seleccione el nombre para ver más información, como su descripción, el sitio web de la aplicación y el identificador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p103">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="b4b6d-146">Autorizado por</span><span class="sxs-lookup"><span data-stu-id="b4b6d-146">Authorized by</span></span>  <br/> |<span data-ttu-id="b4b6d-p104">Use esta para ver cuántos usuarios han autorizado una aplicación para tener acceso a su cuenta de Office 365. Seleccione el número para ver más información, como una lista de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p104">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="b4b6d-149">Nivel de permisos</span><span class="sxs-lookup"><span data-stu-id="b4b6d-149">Permissions Level</span></span>  <br/> ![Icono que indica el nivel de permisiions de una aplicación](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="b4b6d-p105">Use esta para ver cuánto acceso tiene una aplicación con los datos de Office 365. Los niveles de permisos indican **bajo**, **medio**o **alto**, donde **bajo** puede indicar que la aplicación solo tiene acceso al perfil y el nombre de un usuario. Seleccione el nivel para ver más información, como los permisos concedidos a la aplicación, el uso de la comunidad y la actividad relacionada en el [registro de gobierno](suspend-or-restore-an-account-in-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p105">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="b4b6d-154">Última autorización</span><span class="sxs-lookup"><span data-stu-id="b4b6d-154">Last authorized</span></span> <br/> |<span data-ttu-id="b4b6d-155">Use esta para ver la fecha y la hora en que una aplicación de OAuth recibió la última autorización para obtener acceso a los datos de Office 365 de la organización.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="b4b6d-156">Acciones</span><span class="sxs-lookup"><span data-stu-id="b4b6d-156">Actions</span></span><br/>![Aplicaciones de OAuth](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="b4b6d-158">Use esta opción para ver o marcar una aplicación como aprobada o prohibida, informar de una aplicación de OAuth a Microsoft o dejarla como indeterminada.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="b4b6d-159">Marcar una aplicación como aprobada</span><span class="sxs-lookup"><span data-stu-id="b4b6d-159">Mark an app as approved</span></span>

<span data-ttu-id="b4b6d-160">En la página **Administrar aplicaciones de OAuth** , busque la aplicación que quiera aprobar y elija el icono **marcar la aplicación como aprobada** .</span><span class="sxs-lookup"><span data-stu-id="b4b6d-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![Elija el icono marcar aplicación como aprobada](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="b4b6d-162">El icono se vuelve de color verde y la aplicación se aprueba para todos los usuarios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4b6d-p106">Al marcar una aplicación como aprobada, no tiene efecto en el usuario final. Marcar visualmente las aplicaciones aprobadas ayuda a separarlas de las aplicaciones que todavía no se han revisado.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p106">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="b4b6d-165">Prohibir una aplicación</span><span class="sxs-lookup"><span data-stu-id="b4b6d-165">Ban an app</span></span>

1. <span data-ttu-id="b4b6d-166">En la página **Administrar aplicaciones de OAuth** , busque la aplicación que quiera prohibir y elija el icono **marcar la aplicación como prohibida** .</span><span class="sxs-lookup"><span data-stu-id="b4b6d-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="b4b6d-167">![Elija el icono marcar aplicación como prohibida](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="b4b6d-p107">En el cuadro mensaje de notificación, mantenga el texto existente como está o personalice el texto. Elige si deseas que los usuarios sepan que la aplicación se ha vetado.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p107">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![La plantilla de correo para una aplicación prohibida](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="b4b6d-171">Elija **prohibición de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="b4b6d-172">Informar de una aplicación de OAuth a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4b6d-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="b4b6d-173">Si quiere enviar una aplicación de OAuth a Microsoft para su análisis, puede informar de esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="b4b6d-174">En la página **Administrar aplicaciones de OAuth** , busque la aplicación que quiera enviar para su análisis.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="b4b6d-175">Elija los puntos suspensivos verticales y, a continuación, elija **aplicación de informes...**.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="b4b6d-176">![Informar de una aplicación de OAuth](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="b4b6d-p108">En el cuadro de diálogo **informar de esta aplicación** , use la lista desplegable para indicar su preocupación. De forma predeterminada, **esta aplicación está** seleccionada como malintencionada. Sin embargo, puede elegir una de las otras opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p108">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="b4b6d-180">![Informar de una aplicación de OAuth](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="b4b6d-181">Recomenda Mantenga la opción de ponerse en contacto con usted seleccionado y confirme (o modifique) la dirección de correo electrónico que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="b4b6d-182">Elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="b4b6d-183">Crear una consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="b4b6d-183">Create an app query</span></span>

<span data-ttu-id="b4b6d-184">Se recomienda usar la vista avanzada, que tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b4b6d-184">We recommend using the Advanced view, which looks like this:</span></span> 

![Vista avanzada](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="b4b6d-p109">En la barra de consulta de la aplicación, si ve **avanzadas**, está usando la vista básica. Haga clic en (o puntee) **avanzada** para ir a la vista avanzada.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-p109">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![Vista básica](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="b4b6d-189">En la barra de consulta, use la lista **seleccionar un filtro** para elegir una opción.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="b4b6d-190">**Aplicación** Aplicaciones con determinados nombres</span><span class="sxs-lookup"><span data-stu-id="b4b6d-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="b4b6d-191">**Estado** de la aplicación Aplicaciones basadas en su estado (aprobada, prohibida o no determinada)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="b4b6d-192">**Uso** de la comunidad Aplicaciones basadas en los niveles de uso de la comunidad (inusual, poco frecuente o común)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="b4b6d-193">**Nivel de permisos** Aplicaciones basadas en determinados niveles de permisos</span><span class="sxs-lookup"><span data-stu-id="b4b6d-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="b4b6d-194">**Permisos** Aplicaciones que requieren determinados permisos</span><span class="sxs-lookup"><span data-stu-id="b4b6d-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="b4b6d-195">**Publicador**  Aplicaciones de determinados editores</span><span class="sxs-lookup"><span data-stu-id="b4b6d-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="b4b6d-196">**Usuario** Aplicaciones que un usuario concreto ha autorizado</span><span class="sxs-lookup"><span data-stu-id="b4b6d-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="b4b6d-197">Seleccione **es igual** a o no **es igual**a y, a continuación, especifique un valor para el filtro.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="b4b6d-198">Para agregar más filtros, seleccione el signo más (</span><span class="sxs-lookup"><span data-stu-id="b4b6d-198">To add more filters, select the plus sign (</span></span>![Agregar un icono de filtro para consultar aplicaciones](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="b4b6d-200">) y, a continuación, repita los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="b4b6d-201">Para quitar un filtro, seleccione la x (</span><span class="sxs-lookup"><span data-stu-id="b4b6d-201">To remove a filter, select the x (</span></span>![Quitar un icono de filtro para consultar aplicaciones](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="b4b6d-203">) que se encuentra junto a un nombre de filtro.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-203">) next to a filter name.</span></span>
    
<span data-ttu-id="b4b6d-204">Los filtros se aplican automáticamente y la lista de aplicaciones se actualiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b4b6d-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b4b6d-205">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b4b6d-205">Next steps</span></span>

- [<span data-ttu-id="b4b6d-206">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="b4b6d-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="b4b6d-207">Revisar los [orígenes de datos y los registros de tráfico web para Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="b4b6d-208">Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b4b6d-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


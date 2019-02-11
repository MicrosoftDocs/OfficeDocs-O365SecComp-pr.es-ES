---
title: Administrar aplicaciones de OAuth con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Aplicaciones de OAuth de seguridad de la aplicación de nube de Office 365 le ayudan a administrar las aplicaciones de que los usuarios descargar para su uso con datos de Office 365
ms.openlocfilehash: ae32e3c6b15f4ad4794a3dd08c3992adaeba655c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603691"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="186ce-103">Administrar aplicaciones de OAuth con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="186ce-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="186ce-104">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="186ce-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="186ce-105">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="186ce-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="186ce-106">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="186ce-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="186ce-107">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="186ce-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="186ce-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="186ce-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="186ce-109">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="186ce-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="186ce-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="186ce-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="186ce-111">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="186ce-111">You are here!</span></span>  <br/> [<span data-ttu-id="186ce-112">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="186ce-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="186ce-p101">Personas love aplicaciones y descargue con frecuencia, especialmente las aplicaciones que la gente piense va a ahorrar tiempo al hacer que sea más fácil obtener en su trabajo o escuela información. Sin embargo, algunas aplicaciones potencialmente podrían ser un riesgo de seguridad para la organización, dependiendo de qué información tienen acceso a y cómo tratar esa información. Con la [Seguridad de la aplicación de nube de Office 365](office-365-cas-overview.md), si es un administrador global o de seguridad, puede administrar aplicaciones de OAuth para su organización. Puede ver las personas de aplicaciones están usando con datos de Office 365, ¿qué permisos de esas aplicaciones tienen y mucho más.</span><span class="sxs-lookup"><span data-stu-id="186ce-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="186ce-117">En este artículo se describe dónde ir a la administración de aplicaciones de OAuth, cómo aprobar, prohibir o informar de una aplicación y cómo crear una consulta de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="186ce-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="186ce-118">Cómo encontrar la página de aplicaciones de administración de OAuth</span><span class="sxs-lookup"><span data-stu-id="186ce-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="186ce-p102">Aplicaciones de OAuth se administran en el portal de seguridad de la aplicación de nube de Office 365. Debe ser un administrador global o administrador de seguridad para llevar a cabo la siguiente tarea. Para obtener más información vea más [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="186ce-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="186ce-122">Vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="186ce-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="186ce-123">Elija **investigar** \> **aplicaciones de OAuth**.</span><span class="sxs-lookup"><span data-stu-id="186ce-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="186ce-124">![En el portal de O365 CAS, elija investigar.](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="186ce-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="186ce-125">Lo que verá en la página de aplicaciones de administración de OAuth</span><span class="sxs-lookup"><span data-stu-id="186ce-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="186ce-126">En la siguiente tabla se describe los controles y las opciones disponibles en la página de aplicaciones de administración de OAuth.</span><span class="sxs-lookup"><span data-stu-id="186ce-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="186ce-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="186ce-127">**Item**</span></span>|<span data-ttu-id="186ce-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="186ce-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="186ce-129">Icono básica en la barra de consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="186ce-129">Basic icon in the app query bar</span></span>  <br/> ![Icono que indica la vista de consulta básica para consultar](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="186ce-131">Seleccione esta opción para cambiar a la vista avanzada.</span><span class="sxs-lookup"><span data-stu-id="186ce-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="186ce-132">(Si ve **básica**, está usando la vista avanzada)</span><span class="sxs-lookup"><span data-stu-id="186ce-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="186ce-133">Icono avanzadas en la barra de consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="186ce-133">Advanced icon in the app query bar</span></span>  <br/> ![Icono que indica la vista de consulta avanzada para consultar](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="186ce-135">Seleccione esta opción para cambiar a la vista básica.</span><span class="sxs-lookup"><span data-stu-id="186ce-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="186ce-136">(Si ve **Opciones avanzadas**, se utiliza la vista básica).</span><span class="sxs-lookup"><span data-stu-id="186ce-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="186ce-137">Abrir o cerrar todos los iconos de detalles en la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="186ce-137">Open or close all details icon in the app list</span></span>  <br/> ![Haga clic en este icono para abrir o cerrar todos los detalles de todas las aplicaciones](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="186ce-139">Seleccione este icono para ver más o menos detalles acerca de cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="186ce-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="186ce-140">Icono de exportación en la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="186ce-140">Export icon in the app list</span></span>  <br/> ![Haga clic en este icono para exportar un archivo csv de todas las aplicaciones](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="186ce-142">Seleccione este icono para exportar un archivo CSV que contiene una lista de aplicaciones, el número de usuarios para cada aplicación, los permisos asociados con la aplicación, nivel de permisos, estado de la aplicación y usar nivel de la Comunidad.</span><span class="sxs-lookup"><span data-stu-id="186ce-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="186ce-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="186ce-143">Name</span></span>  <br/> |<span data-ttu-id="186ce-p103">Utilícelo para ver el nombre de una aplicación, seleccione el nombre para ver más información, como su descripción, publisher, sitio Web de la aplicación e identificador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="186ce-p103">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="186ce-146">Autorizado por</span><span class="sxs-lookup"><span data-stu-id="186ce-146">Authorized by</span></span>  <br/> |<span data-ttu-id="186ce-p104">Se usa para ver el número de usuarios ha autorizado una aplicación para tener acceso a su cuenta de Office 365. Seleccione el número para ver más información, como una lista de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="186ce-p104">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="186ce-149">Nivel de permisos</span><span class="sxs-lookup"><span data-stu-id="186ce-149">Permissions Level</span></span>  <br/> ![Icono que indica el nivel de permisiions para una aplicación](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="186ce-p105">Se usa para ver el nivel de acceso una aplicación tiene a los datos de Office 365. Los niveles de permisos indican **bajo**, **medio**o **alto**, donde **bajo** podría indicar que la aplicación sólo tiene acceso a perfiles y el nombre de un usuario. Seleccione el nivel para ver más información, como los permisos concedidos a la aplicación, el uso de la Comunidad y la actividad relacionada en el [registro de gobierno](suspend-or-restore-an-account-in-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="186ce-p105">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="186ce-154">Autorizado por última vez</span><span class="sxs-lookup"><span data-stu-id="186ce-154">Last authorized</span></span> <br/> |<span data-ttu-id="186ce-155">Se usa para ver la fecha y hora de que una aplicación de OAuth por última vez se ha autorizado para tener acceso a datos de Office 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="186ce-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="186ce-156">Acciones</span><span class="sxs-lookup"><span data-stu-id="186ce-156">Actions</span></span><br/>![Aplicaciones de OAuth](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="186ce-158">Use esta opción para ver o para marcar una aplicación como aprobado o expulsados, informar de una aplicación de OAuth a Microsoft, o deje como indeterminado.</span><span class="sxs-lookup"><span data-stu-id="186ce-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="186ce-159">Marcar una aplicación como aprobados</span><span class="sxs-lookup"><span data-stu-id="186ce-159">Mark an app as approved</span></span>

<span data-ttu-id="186ce-160">En la página **aplicaciones de administración de OAuth** , busque la aplicación que desee aprobar y elija el icono **aplicación marca como aprobada** .</span><span class="sxs-lookup"><span data-stu-id="186ce-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![Elija la aplicación de marca como icono aprobada](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="186ce-162">El icono se vuelve verde y la aplicación está aprobada para todos los usuarios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="186ce-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="186ce-p106">Cuando una aplicación se marca como aprobados, no hay ningún efecto en el usuario final. Marcar visualmente las aplicaciones que están aprobadas ayuda a separarlas desde aplicaciones que aún no se han revisado todavía.</span><span class="sxs-lookup"><span data-stu-id="186ce-p106">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="186ce-165">Expulsar a una aplicación</span><span class="sxs-lookup"><span data-stu-id="186ce-165">Ban an app</span></span>

1. <span data-ttu-id="186ce-166">En la página **aplicaciones de administración de OAuth** , busque la aplicación que desea prohibir y elija el icono **aplicación marcar como no permitidas** .</span><span class="sxs-lookup"><span data-stu-id="186ce-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="186ce-167">![Elija la aplicación de marca como icono prohibido](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="186ce-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="186ce-p107">En el cuadro de mensaje de notificación, mantener el texto existente tal cual o personalizar el texto. Elija si desea que los usuarios sepan que se ha prohibido su aplicación.</span><span class="sxs-lookup"><span data-stu-id="186ce-p107">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![La plantilla de correo para una aplicación no permitida](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="186ce-171">Elija la **aplicación de prohibición**.</span><span class="sxs-lookup"><span data-stu-id="186ce-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="186ce-172">Informar a Microsoft de una aplicación de OAuth</span><span class="sxs-lookup"><span data-stu-id="186ce-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="186ce-173">Si desea enviar una aplicación de OAuth a Microsoft para su análisis, puede informar de esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="186ce-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="186ce-174">En la página **aplicaciones de administración de OAuth** , busque la aplicación que desea enviar para su análisis.</span><span class="sxs-lookup"><span data-stu-id="186ce-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="186ce-175">Elija el botón de puntos suspensivos vertical y, a continuación, elija **informe App...**.</span><span class="sxs-lookup"><span data-stu-id="186ce-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="186ce-176">![Notificar a una aplicación de OAuth](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="186ce-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="186ce-p108">En el cuadro de diálogo **informe de esta aplicación** , use la lista desplegable para indicar su preocupación. De forma predeterminada, está seleccionada **esta aplicación es malintencionada** . Sin embargo, puede elegir en una de las otras opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="186ce-p108">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="186ce-180">![Notificar a una aplicación de OAuth](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="186ce-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="186ce-181">(Recomendado) Mantenga la opción ponerse en contacto con el que ha seleccionado, y confirme la dirección de correo electrónico que aparecen (o editar).</span><span class="sxs-lookup"><span data-stu-id="186ce-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="186ce-182">Elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="186ce-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="186ce-183">Crear una consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="186ce-183">Create an app query</span></span>

<span data-ttu-id="186ce-184">Se recomienda usar la vista avanzada, que tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="186ce-184">We recommend using the Advanced view, which looks like this:</span></span> 

![Vista avanzada](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="186ce-p109">En la barra de consulta de la aplicación, si ve **Opciones avanzadas**, está utilizando la vista básica. Haga clic en **Avanzadas** para ir a la vista avanzada (o puntee).</span><span class="sxs-lookup"><span data-stu-id="186ce-p109">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![Vista básica](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="186ce-189">En la barra de la consulta, use la lista **Seleccione un filtro** para elegir una opción.</span><span class="sxs-lookup"><span data-stu-id="186ce-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="186ce-190">**Aplicación** Aplicaciones con algunos nombres</span><span class="sxs-lookup"><span data-stu-id="186ce-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="186ce-191">**Estado de la aplicación** Aplicaciones en función de su estado (aprobado, expulsados o sin determinar)</span><span class="sxs-lookup"><span data-stu-id="186ce-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="186ce-192">**Use la Comunidad** En función de la Comunidad de aplicaciones utilizan niveles (raras, Uncommon o común)</span><span class="sxs-lookup"><span data-stu-id="186ce-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="186ce-193">**Nivel de permisos** En función de determinados niveles de permisos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="186ce-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="186ce-194">**Permisos** Aplicaciones que requieren determinados permisos</span><span class="sxs-lookup"><span data-stu-id="186ce-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="186ce-195">**Publisher**  Aplicaciones de ciertos editores</span><span class="sxs-lookup"><span data-stu-id="186ce-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="186ce-196">**Usuario** Aplicaciones que un usuario determinado autorizado</span><span class="sxs-lookup"><span data-stu-id="186ce-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="186ce-197">Seleccione **es igual a** o **no es igual a**y, a continuación, especifique un valor para el filtro.</span><span class="sxs-lookup"><span data-stu-id="186ce-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="186ce-198">Para agregar más filtros, seleccione el signo más)</span><span class="sxs-lookup"><span data-stu-id="186ce-198">To add more filters, select the plus sign (</span></span>![Agregar un icono de filtro para consultar aplicaciones](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="186ce-200">) y, a continuación, repita los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="186ce-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="186ce-201">Para quitar un filtro, seleccione la x (</span><span class="sxs-lookup"><span data-stu-id="186ce-201">To remove a filter, select the x (</span></span>![Quitar un icono de filtro para consultar aplicaciones](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="186ce-203">) junto a un nombre de filtro.</span><span class="sxs-lookup"><span data-stu-id="186ce-203">) next to a filter name.</span></span>
    
<span data-ttu-id="186ce-204">Los filtros se aplican automáticamente, y la lista de aplicaciones se actualiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="186ce-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="186ce-205">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="186ce-205">Next steps</span></span>

- [<span data-ttu-id="186ce-206">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="186ce-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="186ce-207">Revise los [registros de tráfico Web y orígenes de datos de seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="186ce-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="186ce-208">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="186ce-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


---
title: Administrar permisos de aplicación con Office 365 Cloud App Security
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
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Permisos de aplicación de seguridad de la aplicación de nube de Office 365 le ayudan a administrar las aplicaciones de que los usuarios descargar para su uso con datos de Office 365
ms.openlocfilehash: 7bda35bbbf3a16cd1d386adcb03b1c7c4176913a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536587"
---
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a><span data-ttu-id="1b628-103">Administrar permisos de aplicación con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1b628-103">Manage app permissions using Office 365 Cloud App Security</span></span>

<span data-ttu-id="1b628-104">Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b628-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="1b628-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="1b628-105">****Evaluation** \>**</span></span>|<span data-ttu-id="1b628-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="1b628-106">****Planning** \>**</span></span>|<span data-ttu-id="1b628-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="1b628-107">****Deployment** \>**</span></span>|<span data-ttu-id="1b628-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="1b628-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="1b628-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="1b628-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="1b628-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="1b628-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="1b628-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="1b628-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="1b628-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="1b628-112">You are here!</span></span>  <br/> [<span data-ttu-id="1b628-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1b628-113">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="1b628-p101">Personas love aplicaciones y descargue con frecuencia, especialmente las aplicaciones que la gente piense va a ahorrar tiempo al hacer que sea más fácil obtener en su trabajo o escuela información. Sin embargo, algunas aplicaciones potencialmente podrían ser un riesgo de seguridad para la organización, dependiendo de qué información tienen acceso a y cómo tratar esa información. Con la [Seguridad de la aplicación de nube de Office 365](office-365-cas-overview.md), si es un administrador global o de seguridad, puede administrar los permisos de aplicación para su organización. Puede ver las personas de aplicaciones están usando con datos de Office 365, ¿qué permisos de esas aplicaciones tienen y mucho más.</span><span class="sxs-lookup"><span data-stu-id="1b628-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage app permissions for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="1b628-118">En este artículo se describe dónde debe acudir para administrar los permisos de la aplicación, cómo aprobar o prohibir una aplicación y cómo crear una consulta de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b628-118">This article describes where to go to manage app permissions, how to approve or ban an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-app-permissions-page"></a><span data-ttu-id="1b628-119">Cómo encontrar la página de permisos de aplicación de administrar</span><span class="sxs-lookup"><span data-stu-id="1b628-119">How to find the Manage app permissions page</span></span>
<span data-ttu-id="1b628-120"><a name="findappperms"> </a></span><span class="sxs-lookup"><span data-stu-id="1b628-120"></span></span>

> [!NOTE]
> <span data-ttu-id="1b628-p102">Permisos de aplicación se administran en el portal de seguridad de la aplicación de nube de Office 365. Debe ser un administrador global o administrador de seguridad para llevar a cabo la siguiente tarea. Para obtener más información vea más [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1b628-p102">App permissions are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="1b628-p103">Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)</span><span class="sxs-lookup"><span data-stu-id="1b628-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="1b628-126">Vaya a **las alertas de** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="1b628-126">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="1b628-127">Haga clic en (o puntee) **vaya a la seguridad de la aplicación de nube de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="1b628-127">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span>
    
    ![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > <span data-ttu-id="1b628-p104">Si la seguridad de la aplicación de nube de Office 365 no está activado todavía, puede hacer en esta página. Vea [prepararse para la seguridad de la aplicación de nube de Office 365](get-ready-for-office-365-cas.md).</span><span class="sxs-lookup"><span data-stu-id="1b628-p104">If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="1b628-131">Elija **investigar** \> **permisos de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="1b628-131">Choose **Investigate** \> **App permissions**.</span></span>
    
    ![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a><span data-ttu-id="1b628-133">Lo que verá en la página de permisos de aplicación de administrar</span><span class="sxs-lookup"><span data-stu-id="1b628-133">What you'll see on the Manage app permissions page</span></span>
<span data-ttu-id="1b628-134"><a name="whatsonpage"> </a></span><span class="sxs-lookup"><span data-stu-id="1b628-134"></span></span>

<span data-ttu-id="1b628-135">En la siguiente tabla se describe los controles y las opciones disponibles en la página de permisos de aplicación de administrar.</span><span class="sxs-lookup"><span data-stu-id="1b628-135">The following table describes the controls and options available on the Manage app permissions page.</span></span>
  
|<span data-ttu-id="1b628-136">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1b628-136">**Item**</span></span>|<span data-ttu-id="1b628-137">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1b628-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b628-138">Icono básica en la barra de consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="1b628-138">Basic icon in the app query bar</span></span>  <br/> ![Icono que indica la vista de consulta básica para consultar los permisos de aplicación](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="1b628-140">Seleccione esta opción para cambiar a la vista avanzada.</span><span class="sxs-lookup"><span data-stu-id="1b628-140">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="1b628-141">(Si ve **básica**, está usando la vista avanzada)</span><span class="sxs-lookup"><span data-stu-id="1b628-141">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="1b628-142">Icono avanzadas en la barra de consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="1b628-142">Advanced icon in the app query bar</span></span>  <br/> ![Icono que indica la vista de consulta para consultar los permisos de aplicación avanzada](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="1b628-144">Seleccione esta opción para cambiar a la vista básica.</span><span class="sxs-lookup"><span data-stu-id="1b628-144">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="1b628-145">(Si ve **Opciones avanzadas**, se utiliza la vista básica).</span><span class="sxs-lookup"><span data-stu-id="1b628-145">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="1b628-146">Abrir o cerrar todos los iconos de detalles en la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1b628-146">Open or close all details icon in the app list</span></span>  <br/> ![Haga clic en este icono para abrir o cerrar todos los detalles de todas las aplicaciones](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="1b628-148">Seleccione este icono para ver más o menos detalles acerca de cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b628-148">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="1b628-149">Icono de exportación en la lista de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1b628-149">Export icon in the app list</span></span>  <br/> ![Haga clic en este icono para exportar un archivo csv de todas las aplicaciones](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="1b628-151">Seleccione este icono para exportar un archivo CSV que contiene una lista de aplicaciones, el número de usuarios para cada aplicación, los permisos asociados con la aplicación, nivel de permisos, estado de la aplicación y usar nivel de la Comunidad.</span><span class="sxs-lookup"><span data-stu-id="1b628-151">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="1b628-152">Name</span><span class="sxs-lookup"><span data-stu-id="1b628-152">Name</span></span>  <br/> |<span data-ttu-id="1b628-p105">Utilícelo para ver el nombre de una aplicación, seleccione el nombre para ver más información, como su descripción, publisher, sitio Web de la aplicación e identificador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b628-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="1b628-155">Autorizado por</span><span class="sxs-lookup"><span data-stu-id="1b628-155">Authorized by</span></span>  <br/> |<span data-ttu-id="1b628-p106">Se usa para ver el número de usuarios ha autorizado una aplicación para tener acceso a su cuenta de Office 365. Seleccione el número para ver más información, como una lista de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="1b628-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="1b628-158">Nivel de permisos</span><span class="sxs-lookup"><span data-stu-id="1b628-158">Permissions Level</span></span>  <br/> ![Icono que indica el nivel de permisiions para una aplicación](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="1b628-p107">Se usa para ver el nivel de acceso una aplicación tiene a los datos de Office 365. Los niveles de permisos indican **bajo**, **medio**o **alto**, donde **bajo** podría indicar que la aplicación sólo tiene acceso a perfiles y el nombre de un usuario. Seleccione el nivel para ver más información, como los permisos concedidos a la aplicación, el uso de la Comunidad y la actividad relacionada en el [registro de gobierno](suspend-or-restore-an-account-in-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="1b628-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="1b628-163">Estado de la aplicación ( **expulsados**, **aprobado**o **sin determinar**)</span><span class="sxs-lookup"><span data-stu-id="1b628-163">App state ( **Banned**, **Approved**, or **Undetermined**)</span></span>  <br/> <span data-ttu-id="1b628-164">![Iconos de permisos de aplicación después de que se está permitido, bloqueado o ninguna acción ha sido tomado por un administrador](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span><span class="sxs-lookup"><span data-stu-id="1b628-164">![App permissions icons after being allowed, blocked, or no action has been taken by an admin](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span></span>|<span data-ttu-id="1b628-165">Use esta opción para marcar una aplicación como aprobado o expulsados o deje como indeterminado.</span><span class="sxs-lookup"><span data-stu-id="1b628-165">Use this to mark an app as Approved or Banned, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="1b628-166">Marcar una aplicación como aprobados</span><span class="sxs-lookup"><span data-stu-id="1b628-166">Mark an app as approved</span></span>
<span data-ttu-id="1b628-167"><a name="approveapp"> </a></span><span class="sxs-lookup"><span data-stu-id="1b628-167"></span></span>

<span data-ttu-id="1b628-168">En la página **Administrar permisos de aplicación** , busque la aplicación que desee aprobar y elija el icono **aplicación marca como aprobada** .</span><span class="sxs-lookup"><span data-stu-id="1b628-168">On the **Manage app permissions** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![Elija la aplicación de marca como icono aprobada](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
<span data-ttu-id="1b628-170">El icono se vuelve verde y la aplicación está aprobada para todos los usuarios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b628-170">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b628-p108">Cuando una aplicación se marca como aprobados, no hay ningún efecto en el usuario final. Marcar visualmente las aplicaciones que están aprobadas ayuda a separarlas desde aplicaciones que aún no se han revisado todavía.</span><span class="sxs-lookup"><span data-stu-id="1b628-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="1b628-173">Expulsar a una aplicación</span><span class="sxs-lookup"><span data-stu-id="1b628-173">Ban an app</span></span>
<span data-ttu-id="1b628-174"><a name="banapp"> </a></span><span class="sxs-lookup"><span data-stu-id="1b628-174"></span></span>

1. <span data-ttu-id="1b628-175">En la página **Administrar permisos de aplicación** , busque la aplicación que desea prohibir y elija el icono **aplicación marcar como no permitidas** .</span><span class="sxs-lookup"><span data-stu-id="1b628-175">On the **Manage app permissions** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span> 
    
    ![Elija la aplicación de marca como icono prohibido](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. <span data-ttu-id="1b628-177">Elija si desea que los usuarios sepan que se ha prohibido su aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b628-177">Choose whether to let users know that their app has been banned.</span></span>
    
    <span data-ttu-id="1b628-178">(Recomendado) Para permitir que los usuarios sepan, seleccione **los usuarios de notificar quién conceden acceso a esta aplicación prohibido**y agregar o editar un mensaje de notificación personalizado.</span><span class="sxs-lookup"><span data-stu-id="1b628-178">(Recommended) To let users know, select **Notify users who granted access to this banned app**, and add or edit a custom notification message.</span></span>
    
    <span data-ttu-id="1b628-179">Para no permitir que los usuarios sepan, desactive **los usuarios de notificar quién conceden acceso a esta aplicación no permitida**.</span><span class="sxs-lookup"><span data-stu-id="1b628-179">To not let users know, clear **Notify users who granted access to this banned app**.</span></span>
    
    ![La plantilla de correo para una aplicación no permitida](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. <span data-ttu-id="1b628-181">Elija la **aplicación de prohibición**.</span><span class="sxs-lookup"><span data-stu-id="1b628-181">Choose **Ban app**.</span></span>
    
## <a name="create-an-app-query"></a><span data-ttu-id="1b628-182">Crear una consulta de aplicación</span><span class="sxs-lookup"><span data-stu-id="1b628-182">Create an app query</span></span>
<span data-ttu-id="1b628-183"><a name="createapp"> </a></span><span class="sxs-lookup"><span data-stu-id="1b628-183"></span></span>

1. <span data-ttu-id="1b628-p109">En la barra de consulta de aplicación, si ve **Opciones avanzadas**, haga clic en (o puntee) que vaya a la vista avanzada. (Si ve Basic, está utilizando la vista avanzada; mantener su vista como está).</span><span class="sxs-lookup"><span data-stu-id="1b628-p109">In the app query bar, if you see **Advanced**, click (or tap) it to go to the Advanced view. (If you see Basic, you are using the Advanced view; keep your view as it is.)</span></span>
    
2. <span data-ttu-id="1b628-p110">Use la lista **Seleccione un filtro** para elegir una opción. En la siguiente tabla se resume las opciones de filtrado disponibles.</span><span class="sxs-lookup"><span data-stu-id="1b628-p110">Use the **Select a filter** list to choose an option. The following table summarizes your available filter options.</span></span> 
    
|<span data-ttu-id="1b628-188">**Use este filtro**</span><span class="sxs-lookup"><span data-stu-id="1b628-188">**Use this filter**</span></span>|<span data-ttu-id="1b628-189">**Para mostrar**</span><span class="sxs-lookup"><span data-stu-id="1b628-189">**To display**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b628-190">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="1b628-190">**App**</span></span> <br/> |<span data-ttu-id="1b628-191">Aplicaciones con algunos nombres</span><span class="sxs-lookup"><span data-stu-id="1b628-191">Apps with certain names</span></span>  <br/> |
|<span data-ttu-id="1b628-192">**Estado de la aplicación**</span><span class="sxs-lookup"><span data-stu-id="1b628-192">**App state**</span></span> <br/> |<span data-ttu-id="1b628-193">Aplicaciones en función de su estado (aprobado, expulsados o sin determinar)</span><span class="sxs-lookup"><span data-stu-id="1b628-193">Apps based on their state (Approved, Banned, or Undetermined)</span></span>  <br/> |
|<span data-ttu-id="1b628-194">**Uso de la Comunidad**</span><span class="sxs-lookup"><span data-stu-id="1b628-194">**Community use**</span></span> <br/> |<span data-ttu-id="1b628-195">En función de la Comunidad de aplicaciones utilizan niveles (raras, Uncommon o común)</span><span class="sxs-lookup"><span data-stu-id="1b628-195">Apps based on community use levels (Rare, Uncommon, or Common)</span></span>  <br/> |
|<span data-ttu-id="1b628-196">**Nivel de permisos**</span><span class="sxs-lookup"><span data-stu-id="1b628-196">**Permission level**</span></span> <br/> |<span data-ttu-id="1b628-197">En función de determinados niveles de permisos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1b628-197">Apps based on certain permission levels</span></span>  <br/> |
|<span data-ttu-id="1b628-198">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="1b628-198">**Permissions**</span></span> <br/> |<span data-ttu-id="1b628-199">Aplicaciones que requieren determinados permisos</span><span class="sxs-lookup"><span data-stu-id="1b628-199">Apps that require certain permissions</span></span>  <br/> |
|<span data-ttu-id="1b628-200">**Publicador**</span><span class="sxs-lookup"><span data-stu-id="1b628-200">**Publisher**</span></span> <br/> |<span data-ttu-id="1b628-201">Aplicaciones de ciertos editores</span><span class="sxs-lookup"><span data-stu-id="1b628-201">Apps from certain publishers</span></span>  <br/> |
|<span data-ttu-id="1b628-202">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="1b628-202">**User**</span></span> <br/> |<span data-ttu-id="1b628-203">Aplicaciones que un usuario determinado autorizado</span><span class="sxs-lookup"><span data-stu-id="1b628-203">Apps that a certain user authorized</span></span>  <br/> |
   
3. <span data-ttu-id="1b628-204">Seleccione **es igual a** o **no es igual a**y, a continuación, especifique un valor para el filtro.</span><span class="sxs-lookup"><span data-stu-id="1b628-204">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
4. <span data-ttu-id="1b628-205">Para agregar más filtros, seleccione el signo más)</span><span class="sxs-lookup"><span data-stu-id="1b628-205">To add more filters, select the plus sign (</span></span>![Agregar un icono de filtro para consultar aplicaciones](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="1b628-207">) y, a continuación, repita los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="1b628-207">), and then repeat steps 2 and 3.</span></span>
    
5. <span data-ttu-id="1b628-208">Para quitar un filtro, seleccione la x (</span><span class="sxs-lookup"><span data-stu-id="1b628-208">To remove a filter, select the x (</span></span>![Quitar un icono de filtro para consultar aplicaciones](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="1b628-210">) junto a un nombre de filtro.</span><span class="sxs-lookup"><span data-stu-id="1b628-210">) next to a filter name.</span></span>
    
<span data-ttu-id="1b628-211">Los filtros se aplican automáticamente, y la lista de aplicaciones se actualiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="1b628-211">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1b628-212">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1b628-212">Next steps</span></span>
<span data-ttu-id="1b628-213"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="1b628-213"></span></span>

- [<span data-ttu-id="1b628-214">Revisar y realizar acciones en las alertas</span><span class="sxs-lookup"><span data-stu-id="1b628-214">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="1b628-215">Revise los [registros de tráfico Web y orígenes de datos de seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="1b628-215">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="1b628-216">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="1b628-216">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


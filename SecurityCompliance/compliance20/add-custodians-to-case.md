---
title: Agregar custodios a un caso de eDiscovery avanzado (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fe208f4a9f7927d8481d5c6ec8b901baafb98626
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243598"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="5b71d-102">Agregar custodios a un caso de eDiscovery avanzado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5b71d-102">Add custodians to an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="5b71d-103">Mediante eDiscovery avanzado (versión preliminar), puede aprovechar la herramienta de administración de custodios incorporada para coordinar sus flujos de trabajo en la administración de custodios y para identificar los orígenes de datos relevantes y relevantes dentro de un caso.</span><span class="sxs-lookup"><span data-stu-id="5b71d-103">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case.</span></span> <span data-ttu-id="5b71d-104">Cuando se agrega un custodio, el sistema puede identificar automáticamente y realizar suspensiones en el buzón principal de Exchange y en el sitio de OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="5b71d-104">When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site.</span></span> <span data-ttu-id="5b71d-105">Al realizar la detección, también puede descubrir y asignar los sitios o buzones de correo adicionales que un custodio haya accediendo en el pasado o Teams de los que un custodio es miembro de hoy.</span><span class="sxs-lookup"><span data-stu-id="5b71d-105">As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="5b71d-106">Use el siguiente flujo de trabajo para agregar y administrar custodios en escenarios de eDiscovery avanzado (vista previa) en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5b71d-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

![Pestaña de administración de custodios](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="5b71d-108">Paso 1: identificar custodios potenciales</span><span class="sxs-lookup"><span data-stu-id="5b71d-108">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="5b71d-109">El primer paso es identificar los custodios adecuados para su caso.</span><span class="sxs-lookup"><span data-stu-id="5b71d-109">The first step is to identify the appropriate custodians for your matter.</span></span> <span data-ttu-id="5b71d-110">Para agregar custodios a un caso, debe ser miembro del grupo de roles de administradores de eDiscovery o administradores de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5b71d-110">To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

![Identificar custodios potenciales](../media/AddCustodianStep1.png)

<span data-ttu-id="5b71d-112">Para agregar custodios a un caso existente de eDiscovery avanzado (versión preliminar):</span><span class="sxs-lookup"><span data-stu-id="5b71d-112">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="5b71d-113">En la página exhibición avanzada de documentos electrónicos **(vista previa)** , vaya a su caso.</span><span class="sxs-lookup"><span data-stu-id="5b71d-113">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="5b71d-114">Una vez que haya seleccionado un caso, vaya a \*\*\*\* la pestaña custodios y haga clic en **+ Agregar custodio**.</span><span class="sxs-lookup"><span data-stu-id="5b71d-114">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="5b71d-115">Elija los custodios que desea agregar al caso.</span><span class="sxs-lookup"><span data-stu-id="5b71d-115">Choose the custodians that you want to add to the case.</span></span> <span data-ttu-id="5b71d-116">Puede empezar a escribir para buscar y seleccionar los usuarios de Azure Active Directory de su organización.</span><span class="sxs-lookup"><span data-stu-id="5b71d-116">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="5b71d-117">Una vez que haya finalizado la lista de custodios, haga clic en **siguiente** para identificar los posibles orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="5b71d-117">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
  
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="5b71d-118">Opcional Paso 2: seleccionar orígenes de datos custodios</span><span class="sxs-lookup"><span data-stu-id="5b71d-118">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="5b71d-119">Una vez que haya agregado custodios a un caso, puede aprovechar Office 365 para ayudarle a identificar y preservar los principales orígenes de datos de custodios.</span><span class="sxs-lookup"><span data-stu-id="5b71d-119">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources.</span></span> <span data-ttu-id="5b71d-120">El siguiente paso de este flujo de trabajo es seleccionar los orígenes de datos que pertenecen a los custodios especificados en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="5b71d-120">The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

![Seleccionar orígenes de datos de Private](../media/AddCustodianStep2.png)

<span data-ttu-id="5b71d-122">Para identificar los orígenes de datos de custodios:</span><span class="sxs-lookup"><span data-stu-id="5b71d-122">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="5b71d-123">Para cada custodio, seleccione **Exchange** si desea que el sistema identifique y agregue automáticamente el buzón de correo principal de Exchange del custodio.</span><span class="sxs-lookup"><span data-stu-id="5b71d-123">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="5b71d-124">Para cada custodio, seleccione **onedrive** si desea que el sistema identifique y agregue automáticamente la dirección URL principal de onedrive del custodio.</span><span class="sxs-lookup"><span data-stu-id="5b71d-124">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="5b71d-125">Después de realizar las selecciones, el sistema intentará identificar los orígenes de datos automáticamente y agregarlos a su caso.</span><span class="sxs-lookup"><span data-stu-id="5b71d-125">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="5b71d-126">Haga clic en **siguiente** para comenzar a asignar orígenes de datos adicionales a su custodio.</span><span class="sxs-lookup"><span data-stu-id="5b71d-126">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="5b71d-127">Opcional Paso 3: asignar orígenes de datos adicionales</span><span class="sxs-lookup"><span data-stu-id="5b71d-127">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="5b71d-128">Según el caso, es posible que también desee agregar buzones que un custodio dado puede haber usado anteriormente, grupos en los que un custodio es actualmente miembro o sitios a los que un custodio tenía acceso en el pasado.</span><span class="sxs-lookup"><span data-stu-id="5b71d-128">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past.</span></span> <span data-ttu-id="5b71d-129">Además de los orígenes de datos de custodios principales, puede Agregar orígenes de datos de Office 365 adicionales a un custodio o aprovechar Office 365 para ayudarle a identificar también los orígenes de datos potencialmente relevantes.</span><span class="sxs-lookup"><span data-stu-id="5b71d-129">In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

![Asignar orígenes de datos adicionales](../media/AddCustodianStep3.PNG)

<span data-ttu-id="5b71d-131">Para asignar buzones de correo, sitios o equipos a un custodio específico:</span><span class="sxs-lookup"><span data-stu-id="5b71d-131">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="5b71d-132">Seleccione **Agregar** para asignar ubicaciones de contenido, como buzones de correo, sitios y equipos, a un custodio específico.</span><span class="sxs-lookup"><span data-stu-id="5b71d-132">Select **Add** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="5b71d-133">En el control flotante, especifique lo siguiente ![: asignar orígenes de datos](../media/AddCustodianStep4.PNG)</span><span class="sxs-lookup"><span data-stu-id="5b71d-133">In the flyout, specify the following: ![Map Data Sources](../media/AddCustodianStep4.PNG)</span></span>
  -  <span data-ttu-id="5b71d-134">**Buzones de Exchange** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o equipos** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5b71d-134">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="5b71d-135">Para especificar los buzones que se asignarán al custodio seleccionado, use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="5b71d-135">To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="5b71d-136">También puede asignar el buzón asociado para un grupo de Office 365 o un equipo de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b71d-136">You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="5b71d-137">Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="5b71d-137">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5b71d-138">Al hacer clic en elegir usuarios, grupos o equipos para especificar los buzones, el selector de buzones que se muestra está vacío.</span><span class="sxs-lookup"><span data-stu-id="5b71d-138">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="5b71d-139">Esto se ha diseñado así para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5b71d-139">This is by design to enhance performance.</span></span> <span data-ttu-id="5b71d-140">Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5b71d-140">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="5b71d-141">**Sitios de SharePoint** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para especificar sitios de SharePoint y OneDrive para la empresa adicionales que quiera asignar al custodio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5b71d-141">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian.</span></span> <span data-ttu-id="5b71d-142">También puede Agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un equipo de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b71d-142">You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="5b71d-143">Escriba la dirección URL de cada sitio que quiera asignar.</span><span class="sxs-lookup"><span data-stu-id="5b71d-143">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="5b71d-144">Haga clic en **elegir**y, a continuación, en **listo**.</span><span class="sxs-lookup"><span data-stu-id="5b71d-144">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="5b71d-145">**Microsoft Teams** : haga clic en **elegir Teams** y, a continuación, haga clic en **elegir Teams** de nuevo para ver una lista de los grupos de Microsoft Teams de los que el custodio es miembro de hoy.</span><span class="sxs-lookup"><span data-stu-id="5b71d-145">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today.</span></span> <span data-ttu-id="5b71d-146">Seleccione los equipos que quiera agregar a su custodio.</span><span class="sxs-lookup"><span data-stu-id="5b71d-146">Select the Teams that you would like to add to your custodian.</span></span> <span data-ttu-id="5b71d-147">Una vez seleccionado, el sistema identificará automáticamente & seleccionar el sitio de SharePoint y el buzón de grupo asociados a ese equipo de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b71d-147">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="5b71d-148">Haga clic en **elegir**y, a continuación, en **listo**.</span><span class="sxs-lookup"><span data-stu-id="5b71d-148">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="5b71d-149">Para agregar Microsoft Teams, tendrá que agregar por separado el buzón de correo y el sitio de SharePoint, como se muestra más arriba.</span><span class="sxs-lookup"><span data-stu-id="5b71d-149">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="5b71d-150">Una vez que haya terminado de asignar sus orígenes, puede ver los buzones de correo totales, los sitios y los equipos de los custodios que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="5b71d-150">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added.</span></span> <span data-ttu-id="5b71d-151">Cuando haya finalizado los orígenes de datos relevantes para un custodio específico, esta asignación se mantendrá y se extenderá a los flujos de trabajo de recopilación, procesamiento y revisión de la exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5b71d-151">When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="5b71d-152">Opcional Paso 4: poner los custodios en espera</span><span class="sxs-lookup"><span data-stu-id="5b71d-152">(Optional) Step 4: Place custodians on hold</span></span>

![ReTenciones de posición](../media/AddCustodianStep5.PNG)

<span data-ttu-id="5b71d-154">Una vez que haya finalizado los custodios y los orígenes de datos que desea agregar a su caso, puede, de manera opcional, poner algunos o todos los custodios en retención.</span><span class="sxs-lookup"><span data-stu-id="5b71d-154">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold.</span></span> <span data-ttu-id="5b71d-155">Cuando se pone un custodio en espera, el contenido asignado a ese usuario se conserva hasta que se libere el custodio del caso o hasta que se elimine la retención.</span><span class="sxs-lookup"><span data-stu-id="5b71d-155">When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold.</span></span> <span data-ttu-id="5b71d-156">En algunos casos, es posible que quiera agregar custodios a un caso sin ponerlos en retención.</span><span class="sxs-lookup"><span data-stu-id="5b71d-156">In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="5b71d-157">Para poner los custodios y los orígenes de datos seleccionados en espera:</span><span class="sxs-lookup"><span data-stu-id="5b71d-157">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="5b71d-158">Compruebe las selecciones de custodios y seleccione la casilla para poner cada custodio en espera.</span><span class="sxs-lookup"><span data-stu-id="5b71d-158">Verify your custodian selections and select the checkbox to place each custodian on hold.</span></span> <span data-ttu-id="5b71d-159">Una vez que un custodio se coloca en retención, se creará automáticamente una directiva de retención de custodios que contiene todas las fuentes de la Private.</span><span class="sxs-lookup"><span data-stu-id="5b71d-159">After a custodian is placed on hold, a custodian hold policy containing all custodial sources will be automatically created.</span></span> <span data-ttu-id="5b71d-160">Si la opción no está seleccionada, el custodio y los orígenes de datos seleccionados se agregarán al caso, pero el contenido no se conservará.</span><span class="sxs-lookup"><span data-stu-id="5b71d-160">If the option is not checked, the custodian and selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="5b71d-161">Vaya a la \*\*\*\* pestaña suspensiones y seleccione la **Directiva de retención**de custodios.</span><span class="sxs-lookup"><span data-stu-id="5b71d-161">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="5b71d-162">Haga clic en **Editar** para ver todos los orígenes de datos de custodios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5b71d-162">Click **Edit** to view all the selected custodian data sources.</span></span>

   

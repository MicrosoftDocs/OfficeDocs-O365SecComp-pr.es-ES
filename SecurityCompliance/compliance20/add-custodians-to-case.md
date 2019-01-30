---
title: Agregar a custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9a7dc6b1c2eeffdcd49be64d1d09d4a2bda782b
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608375"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="f18f4-102">Agregar custodia a una exhibición de documentos electrónicos avanzada (vista previa) caso</span><span class="sxs-lookup"><span data-stu-id="f18f4-102">Add custodians to an Advanced eDiscovery (Preview) Case</span></span>

<span data-ttu-id="f18f4-p101">Uso de exhibición de documentos electrónicos avanzada (vista previa), puede aprovechar la herramienta de administración integrada de custodia para coordinar los flujos de trabajo alrededor de administración de custodia y la identificación de los orígenes de datos relevantes, custodia dentro de un caso. Cuando se agrega una custodia, puede identificar automáticamente el sistema y realizar suspensiones en su buzón de Exchange principal y OneDrive para el sitio de negocio. Como dirigir la detección, también es posible que descubrir y asignar los buzones de correo adicionales o sitios que una custodia tener acceso en el pasado o los equipos que una custodia es un miembro de hoy.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p101">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case. When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site. As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="f18f4-106">Use el siguiente flujo de trabajo para agregar y administrar a custodia en los casos de exhibición de documentos electrónicos avanzada (vista previa) en el centro de cumplimiento de seguridad &.</span><span class="sxs-lookup"><span data-stu-id="f18f4-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="f18f4-107">Paso 1: Identificar posible custodia</span><span class="sxs-lookup"><span data-stu-id="f18f4-107">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="f18f4-p102">El primer paso es identificar a la custodia adecuada para su caso. Para agregar a custodia a un caso, debe ser un miembro de la exhibición de documentos electrónicos los administradores o el grupo de roles de administradores de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p102">The first step is to identify the appropriate custodians for your matter. To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

<span data-ttu-id="f18f4-110">Para agregar a custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa) existente:</span><span class="sxs-lookup"><span data-stu-id="f18f4-110">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="f18f4-111">Desde la página de **exhibición de documentos electrónicos avanzada (vista previa)** , vaya a su caso.</span><span class="sxs-lookup"><span data-stu-id="f18f4-111">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="f18f4-112">Después de haber seleccionado un caso, vaya a la ficha de **custodia** y haga clic en **+ custodia de agregar**.</span><span class="sxs-lookup"><span data-stu-id="f18f4-112">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="f18f4-p103">Elija a la custodia que desea agregar a las mayúsculas y minúsculas. Puede iniciar escribiendo para buscar y seleccionar los usuarios de Azure Active Directory su organización.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p103">Choose the custodians that you want to add to the case. You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="f18f4-115">Tras finalizar la lista de custodia, haga clic en **siguiente** para comenzar a identificar los posibles orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="f18f4-115">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
   
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="f18f4-116">(Opcional) Paso 2: Seleccione orígenes de datos de custodia</span><span class="sxs-lookup"><span data-stu-id="f18f4-116">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="f18f4-p104">Después de agregar a un caso de custodia, puede sacar provecho de Office 365 para ayudarle a identificar y conservar los orígenes de datos de custodia principal. Es el paso siguiente de este flujo de trabajo seleccionar los orígenes de datos que pertenecen a la custodia especificado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p104">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources. The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

<span data-ttu-id="f18f4-119">Para identificar los orígenes de datos de custodia:</span><span class="sxs-lookup"><span data-stu-id="f18f4-119">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="f18f4-120">Para cada custodia, seleccione **Exchange** si le gustaría que el sistema para identificar y agregar el buzón principal de la custodia de automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f18f4-120">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="f18f4-121">Para cada custodia, seleccione **OneDrive** si le gustaría que el sistema para identificar automáticamente y agregar principal OneDrive para la dirección URL de la custodia.</span><span class="sxs-lookup"><span data-stu-id="f18f4-121">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="f18f4-122">Una vez haya realizado las selecciones, sistema intentará automáticamente identificar los orígenes de datos y agregarlos a su caso.</span><span class="sxs-lookup"><span data-stu-id="f18f4-122">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="f18f4-123">Haga clic en **siguiente** para comenzar la asignación de orígenes de datos adicionales a su custodia.</span><span class="sxs-lookup"><span data-stu-id="f18f4-123">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="f18f4-124">(Opcional) Paso 3: Asignar orígenes de datos adicionales</span><span class="sxs-lookup"><span data-stu-id="f18f4-124">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="f18f4-p105">Dependiendo del caso, es posible que desee agregar buzones de correo que es posible que ha usado la custodia determinada en el pasado, grupos donde actualmente es un miembro de custodia o sitios que una custodia tenía acceso a en el pasado. Además de los orígenes de datos principal de custodia, puede agregar otros orígenes de datos de Office 365 a custodia o sacar provecho de Office 365 para ayudar a identificar los orígenes de datos potencialmente relevantes así como.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p105">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past. In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

<span data-ttu-id="f18f4-127">Para asignar los buzones de correo, sitios o los equipos a custodia específica:</span><span class="sxs-lookup"><span data-stu-id="f18f4-127">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="f18f4-128">Seleccione la **actualización** para asignar las ubicaciones de contenido, como los buzones de correo, los sitios y de los equipos, a una custodia específica.</span><span class="sxs-lookup"><span data-stu-id="f18f4-128">Select **Update** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="f18f4-129">En el menú desplegable, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f18f4-129">In the flyout, specify the following:</span></span>
   
  -  <span data-ttu-id="f18f4-p106">**Los buzones de Exchange** - haga clic en **Elegir usuarios, grupos o equipos** y, a continuación, haga clic en **Elegir usuarios, grupos o equipos de** nuevo. Para especificar los buzones de correo para asignar a la custodia seleccionada, use el cuadro de búsqueda para encontrar buzones de usuario y grupos de distribución. También puede asignar el buzón asociado para un grupo de Office 365 o un Microsoft Team. Seleccione el usuario, el grupo, la casilla de verificación de equipo, haga clic en **Elegir**y, a continuación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p106">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again. To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups. You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="f18f4-p107">Al hacer clic en Elegir usuarios, grupos o equipos para especificar los buzones de correo, el selector de buzón de correo que se muestra está vacío. Este comportamiento está diseñado para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p107">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
   - <span data-ttu-id="f18f4-p108">**Sitios de SharePoint** : haga clic en **Elegir sitios** y, a continuación, haga clic en **sitios de elija** nuevo para especificar SharePoint y OneDrive adicionales para sitios de negocio que le gustaría usar para asignar a la custodia seleccionada. También puede agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un Microsoft Team. Escriba la dirección URL para cada sitio que desee asignar. Haga clic en **Elegir**y, a continuación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p108">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Type the URL for each site that you want to assign. Click **Choose**, and then click **Done**.</span></span>
   - <span data-ttu-id="f18f4-p109">**Los equipos de Microsoft** : haga clic en **Elegir los equipos** y, a continuación, haga clic en **Elegir los equipos** de nuevo para ver una lista de grupos de Microsoft Team que la custodia es un miembro de hoy. Seleccione los equipos que le gustaría usar para agregar a su custodia. Una vez seleccionado, el sistema automáticamente identificará seleccionar & que el sitio de SharePoint y el buzón de grupo asociado asociado a ese Microsoft Team. Haga clic en **Elegir**y, a continuación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p109">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today. Select the Teams that you would like to add to your custodian. Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="f18f4-145">Para agregar adicionales Teams Microsoft, debe agregar por separado el buzón de correo y el sitio de SharePoint como se indicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f18f4-145">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="f18f4-p110">Cuando haya terminado de asignación de los orígenes, puede ver el totales buzones, sitios y los equipos para la custodia que acaba de agregar. Cuando haya finalizado los orígenes de datos relevantes de custodia específica, esta asignación se mantiene y extendida para la colección de exhibición de documentos electrónicos, procesamiento y los flujos de trabajo de revisión.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p110">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added. When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="f18f4-148">(Opcional) Paso 4: Lugar custodia en espera</span><span class="sxs-lookup"><span data-stu-id="f18f4-148">(Optional) Step 4: Place custodians on hold</span></span>

 <span data-ttu-id="f18f4-p111">Tras finalizar la custodia y orígenes de datos que desea agregar a su caso, opcionalmente puede colocar algunos o todos los de su custodia en espera. Cuando se realiza una custodia en espera, el contenido asignado a ese usuario se mantiene hasta que se suelte a la custodia desde las mayúsculas y minúsculas o hasta que se elimine la suspensión. En algunos casos, es posible que desee agregar a custodia a un caso sin colocarlos en suspensión.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p111">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold. When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold. In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="f18f4-152">Para colocar el seleccionado custodia y orígenes de datos en espera:</span><span class="sxs-lookup"><span data-stu-id="f18f4-152">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="f18f4-p112">Compruebe las selecciones de custodia y seleccione el checkox para realizar a cada custodia en espera. Una vez que una custodia se pondrá en espera, se creará automáticamente una directiva de retención de custodia que contiene custodia todos los orígenes. Si la opción no está activada, los orígenes de datos de custodia & seleccionado se agregará a las mayúsculas y minúsculas, pero no se conservará el contenido.</span><span class="sxs-lookup"><span data-stu-id="f18f4-p112">Verify your custodian selections and select the checkox to place each custodian on hold.Once a custodian is placed on hold, a custodian hold policy containing all custodial sources will automatically be created. If the option is not checked, the custodian & selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="f18f4-155">Vaya a la ficha **contiene** y seleccione la **Directiva de retención de custodia**.</span><span class="sxs-lookup"><span data-stu-id="f18f4-155">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="f18f4-156">Haga clic en **Editar** para ver todos los orígenes de datos de custodia seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f18f4-156">Click **Edit** to view all the selected custodian data sources.</span></span>

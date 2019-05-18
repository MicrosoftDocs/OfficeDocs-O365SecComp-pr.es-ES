---
title: Administrar los custodios en un caso de eDiscovery avanzado
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9806ecbc23f46ee2d39f8d7e6be07af0d6a83e8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151622"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="5a4b8-102">Administrar los custodios en un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="5a4b8-102">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="5a4b8-103">La ficha custodios de eDiscovery avanzado contiene una lista de todos los custodios que se han agregado al caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-103">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="5a4b8-104">Después de agregar custodios a un caso, los detalles de cada custodio se recopilan automáticamente desde Azure Active Directory y se pueden ver en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-104">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Administrar custodios](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="5a4b8-106">Ver detalles del custodio</span><span class="sxs-lookup"><span data-stu-id="5a4b8-106">View custodian details</span></span>

<span data-ttu-id="5a4b8-107">Para ver los detalles sobre un custodio, haga clic en el custodio en la lista \*\*\*\* de la ficha custodios. Se muestra una página de control flotante que contiene la siguiente información sobre el custodio:</span><span class="sxs-lookup"><span data-stu-id="5a4b8-107">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="5a4b8-108">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="5a4b8-108">Contact information</span></span>

  - <span data-ttu-id="5a4b8-109">**Nombre para mostrar** : nombre que se muestra en la libreta de direcciones del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-109">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="5a4b8-110">Suele ser la combinación del nombre del custodio, la inicial del segundo nombre y el apellido.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-110">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="5a4b8-111">**Correo/SMTP** : la dirección SMTP principal para el custodio, por ejemplo, brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-111">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="5a4b8-112">Tenga en cuenta que también se muestra el nombre principal del usuario (UPN) del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-112">Note that the custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="5a4b8-113">**Título** : el puesto del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-113">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="5a4b8-114">**Department** : el nombre del Departamento en el que trabaja el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-114">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="5a4b8-115">**Administrador** : el administrador del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-115">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="5a4b8-116">El administrador designado recibirá todas las comunicaciones de escalado para este custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-116">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="5a4b8-117">Información de ubicación</span><span class="sxs-lookup"><span data-stu-id="5a4b8-117">Location information</span></span>

  - <span data-ttu-id="5a4b8-118">**City** : la ciudad en la que se encuentra el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-118">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="5a4b8-119">**State** -estado o provincia en la dirección del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-119">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="5a4b8-120">**País/región** : el país o la región donde se encuentra el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-120">**Country/Region** - The country/region where the custodian’s is located.</span></span>

  - <span data-ttu-id="5a4b8-121">**Oficina** : la ubicación de la oficina en el lugar de trabajo del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-121">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="5a4b8-122">Información del caso</span><span class="sxs-lookup"><span data-stu-id="5a4b8-122">Case information</span></span>

  - <span data-ttu-id="5a4b8-123">**Estado de retención** : indica si el custodio se ha puesto en retención.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-123">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="5a4b8-124">**Estado de comunicación**: indica si el custodio ha emitido un aviso de retenciones.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="5a4b8-125">Si se ha emitido un aviso al custodio, se **publica**este valor de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-125">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="5a4b8-126">Si no se ha emitido un aviso al custodio, el estado no se **publica**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-126">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="5a4b8-127">**Estado** : el estado del custodio en el caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-127">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="5a4b8-128">Un estado de **activo** indica que el custodio forma parte del caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-128">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="5a4b8-129">Si se ha lanzado un custodio desde un caso, el estado cambia a **lanzado**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-129">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="5a4b8-130">Orígenes de datos e información de indización</span><span class="sxs-lookup"><span data-stu-id="5a4b8-130">Data sources and indexing information</span></span>

    - <span data-ttu-id="5a4b8-131">**Orígenes de datos** : muestra el recuento y el tipo de orígenes de datos (buzones, sitios y equipos) que están asociados con el custodio y forman parte del caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-131">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="5a4b8-132">**Tiempo de actualización de índice** : indica la hora y la fecha en que se activó por última vez el trabajo de indización avanzada.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-132">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="5a4b8-133">Esta propiedad también indicará cuándo está actualmente en curso el proceso de indización avanzada.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-133">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="5a4b8-134">Edición de un custodio</span><span class="sxs-lookup"><span data-stu-id="5a4b8-134">Edit a custodian</span></span>

<span data-ttu-id="5a4b8-135">A medida que avanza el caso, es posible que descubra que puede haber orígenes de datos adicionales relacionados con un custodio específico & su caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="5a4b8-136">En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y considerados como no relevantes.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="5a4b8-137">Para actualizar los orígenes de datos asociados a un custodio:</span><span class="sxs-lookup"><span data-stu-id="5a4b8-137">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="5a4b8-138">Vaya a **eDiscovery _GT_ Advanced eDiscovery** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-138">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="5a4b8-139">Haga clic \*\*\*\* en la ficha custodios.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-139">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="5a4b8-140">Seleccione un custodio de la lista y haga clic en **Editar** en la página de control flotante.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-140">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Edición de orígenes de datos](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="5a4b8-142">Haga clic en la pestaña **Elegir orígenes de datos** para cambiar la configuración de la cuenta de OneDrive y el buzón de Exchange del custodio, haga clic en **Elegir orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-142">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="5a4b8-143">Haga clic en la pestaña **seleccionar orígenes de datos adicionales** para agregar o quitar los buzones de correo de Microsoft Teams, SharePoint o Exchange asociados con el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-143">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="5a4b8-144">Para obtener más información acerca de los orígenes de datos asociados a un custodio, consulte "paso 3: asociar orígenes de datos adicionales a un custodio" en [Agregar custodios a un caso](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span><span class="sxs-lookup"><span data-stu-id="5a4b8-144">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="5a4b8-145">Haga clic en **realizar suspensiones de custodia** para habilitar o deshabilitar la retención para el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-145">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="resolve-custodian-processing-errors"></a><span data-ttu-id="5a4b8-146">Resolver errores de procesamiento de custodios</span><span class="sxs-lookup"><span data-stu-id="5a4b8-146">Resolve custodian processing errors</span></span>

<span data-ttu-id="5a4b8-147">En la mayoría de los flujos de trabajo de eDiscovery para investigaciones legales, se busca un subconjunto de los datos de un custodio una vez que se agrega el custodio a un caso legal.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-147">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="5a4b8-148">Debido a los tamaños de archivo muy grandes o a posibles daños en los datos, algunos elementos de los orígenes de datos asociados con un custodio pueden indizarse parcialmente.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-148">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="5a4b8-149">Mediante el uso de la funcionalidad de [indización avanzada](indexing-custodian-data.md) en la exhibición avanzada de documentos electrónicos, la mayoría de los elementos indizados parcialmente pueden corregirse automáticamente mediante la reindización de estos elementos a petición.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-149">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="5a4b8-150">Cuando se agrega un custodio a un caso, los datos ubicados en los orígenes de datos asociados con el custodio se vuelven a indexar automáticamente (mediante el proceso de indización avanzado).</span><span class="sxs-lookup"><span data-stu-id="5a4b8-150">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="5a4b8-151">Esto significa que puede dejar los datos en el lugar en lugar de tener que descargarlos y corregirlos y, a continuación, buscar en ellos sin conexión).</span><span class="sxs-lookup"><span data-stu-id="5a4b8-151">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="5a4b8-152">Sin embargo, durante el ciclo de vida de un caso legal, se pueden asociar nuevos orígenes de datos a un custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-152">However, during the lifecycle of a legal case new data sources might be associated to a custodian.</span></span> <span data-ttu-id="5a4b8-153">En este caso, debe volver a indizar los datos del custodio al volver a ejecutar el proceso de indización avanzado para corregir los elementos parcialmente indizados y actualizar el índice de los datos del custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-153">In this case, you re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="5a4b8-154">Para desencadenar el proceso de reindización para tratar los elementos parcialmente indizados:</span><span class="sxs-lookup"><span data-stu-id="5a4b8-154">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="5a4b8-155">Vaya a **eDiscovery _GT_ Advanced eDiscovery** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-155">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="5a4b8-156">Haga clic en la **ficha custodios**y, a continuación, seleccione una custodia cuyos datos se deban reindizar.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-156">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="5a4b8-157">En la página flotante, haga clic en **Actualizar índice**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-157">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="5a4b8-158">Se muestra un cuadro de diálogo que indica que se ha creado el trabajo de índice.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-158">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="5a4b8-159">La nueva indexación de los datos del custodio es un proceso de ejecución prolongada; el trabajo correspondiente que se crea se denomina **volver a indizar los datos del custodio**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-159">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="5a4b8-160">Puede realizar un seguimiento del progreso en la ficha **trabajos** o en la ficha custodios mediante la supervisión del estado en la columna Estado de la **tarea de indización** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5a4b8-160">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="5a4b8-161">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="5a4b8-161">For more information, see:</span></span>

- [<span data-ttu-id="5a4b8-162">Trabajar con errores de proceso</span><span class="sxs-lookup"><span data-stu-id="5a4b8-162">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="5a4b8-163">Administrar trabajos</span><span class="sxs-lookup"><span data-stu-id="5a4b8-163">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="5a4b8-164">Liberar un custodio de un caso</span><span class="sxs-lookup"><span data-stu-id="5a4b8-164">Release a custodian from a case</span></span>

<span data-ttu-id="5a4b8-165">Un custodio se publica en situaciones en las que se cierra un caso, el custodio ya no está obligado a preservar el contenido de un caso, o cuando se considera que el custodio ya no es relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-165">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="5a4b8-166">Si libera un custodio después de que se publique un aviso de retención, se enviará una notificación de publicación al custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-166">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="5a4b8-167">Además, se quitan las suspensiones colocadas en los orígenes de datos asociados con el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-167">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="5a4b8-168">Si el custodio se puso en una *retención silenciosa*, donde no se emitieron notificaciones legales, no se enviará una notificación de la versión, pero se quitarán todas las suspensiones que se hayan colocado en orígenes de datos asociados con el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-168">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="5a4b8-169">Para liberar un custodio:</span><span class="sxs-lookup"><span data-stu-id="5a4b8-169">To release a custodian:</span></span> 

1. <span data-ttu-id="5a4b8-170">Vaya a **eDiscovery _GT_ Advanced eDiscovery** y abra el caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-170">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="5a4b8-171">Vaya a la \*\*\*\* pestaña custodios.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-171">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="5a4b8-172">Haga clic en la **ficha custodios**y, a continuación, seleccione el custodio que se está publicando desde el caso.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-172">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="5a4b8-173">En la página flotante, haga clic en **liberar custodio**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-173">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="5a4b8-174">Se muestra una página de advertencia que explica que si se coloca una retención en un origen de datos asociado al custodio, se quitará la retención y se seguirá aplicando cualquier otra retención asociada a un caso de exhibición avanzada de documentos electrónicos diferente.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-174">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="5a4b8-175">Esto incluye otros tipos de características de conservación y retención en Office 365 (como una directiva de retención de Office 365).</span><span class="sxs-lookup"><span data-stu-id="5a4b8-175">That includes other types of preservation and retention features in Office 365 (such as an Office 365 retention policy).</span></span>

5. <span data-ttu-id="5a4b8-176">Haga clic en **sí** para confirmar que desea liberar el custodio.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-176">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="5a4b8-177">Tenga en cuenta que el estado de este \*\*\*\* usuario en la pestaña de custodios está establecido en **lanzado** y el **Estado de conservación** en la página de control flotante se cambia a **false**.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-177">Note that status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="5a4b8-178">Un custodio puede estar involucrado de forma simultánea en varios casos legales.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-178">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="5a4b8-179">Cuando se publica un custodio desde un caso, las suspensiones y notificaciones en otros asuntos no se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-179">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="5a4b8-180">Custodios de edición en masa</span><span class="sxs-lookup"><span data-stu-id="5a4b8-180">Bulk-edit custodians</span></span>

<span data-ttu-id="5a4b8-181">Puede usar el editor masivo para editar varios custodios a la vez.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-181">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="5a4b8-182">Para ello, seleccione dos o más custodios en la ficha **custodios** para mostrar el editor masivo y, a continuación, haga clic en una de las tareas.</span><span class="sxs-lookup"><span data-stu-id="5a4b8-182">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Página de control flotante para editar la configuración de varios custodios](../media/AeDBulkEditCustodians.png)
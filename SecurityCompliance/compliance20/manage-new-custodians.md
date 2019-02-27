---
title: Administrar los custodios en un caso de eDiscovery avanzado (vista previa)
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
ms.openlocfilehash: 95a1bcbbc279ad4e476fc479e701b0f8a921c83b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295683"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="406fc-102">Administrar los custodios en un caso de eDiscovery avanzado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="406fc-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="406fc-p101">La ficha custodios contiene una lista de todos los custodios que se puede ordenar en el caso. Después de agregar custodios a un caso, los detalles de cada custodio se recopilarán de forma automática desde Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="406fc-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="406fc-105">Visualización de detalles de custodios</span><span class="sxs-lookup"><span data-stu-id="406fc-105">Viewing custodian details</span></span>

<span data-ttu-id="406fc-p102">La página de control flotante que contiene los detalles de custodios aparece después de agregar un custodio a un caso y seleccionarlos \*\*\*\* en la lista de la ficha custodios. Desde aquí, puede ver todos los detalles relacionados con el custodio. La página de control flotante contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="406fc-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="406fc-108">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="406fc-108">Contact information</span></span>

  - <span data-ttu-id="406fc-p103">**Nombre para mostrar**: nombre que se muestra en la libreta de direcciones del custodio. Suele ser la combinación del nombre del custodio, la inicial del segundo nombre y el apellido.</span><span class="sxs-lookup"><span data-stu-id="406fc-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="406fc-111">**Correo/SMTP**: la dirección SMTP de la custodio, por ejemplo, Jeff@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="406fc-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="406fc-112">**Title**: el puesto del custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="406fc-113">**Departamento**: nombre del Departamento en el que trabaja el custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="406fc-p104">**Administrador**: el administrador del custodio. El administrador designado recibirá todas las comunicaciones de escalado para este custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="406fc-116">Información de ubicación</span><span class="sxs-lookup"><span data-stu-id="406fc-116">Location information</span></span>

  - <span data-ttu-id="406fc-117">**City**: la ciudad en la que se encuentra el custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="406fc-118">**State**: el estado o provincia de la dirección del custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="406fc-119">**País o región**: el país o región en el que se encuentra el custodio; por ejemplo, "US" o "UK".</span><span class="sxs-lookup"><span data-stu-id="406fc-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="406fc-120">**Oficina**: la ubicación de la oficina en el lugar de trabajo del custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="406fc-121">Información del caso</span><span class="sxs-lookup"><span data-stu-id="406fc-121">Case information</span></span>

  - <span data-ttu-id="406fc-122">**Estado de suspensión**: indica si el custodio se ha puesto en retención.</span><span class="sxs-lookup"><span data-stu-id="406fc-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="406fc-p105">**Estado de comunicación**: indica si el custodio ha emitido un aviso de retenciones. Si se ha emitido un aviso al custodio, este se marcará como *publicado*. Si no se ha emitido un aviso al custodio, este estado no se *publicará*.</span><span class="sxs-lookup"><span data-stu-id="406fc-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="406fc-p106">**Status**: el estado del custodio en el caso. Estará *activo* si el custodio todavía está en espera para el caso. Si se quita un custodio de un caso, su estado cambiará a *lanzado*.</span><span class="sxs-lookup"><span data-stu-id="406fc-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="406fc-129">Estado de procesamiento</span><span class="sxs-lookup"><span data-stu-id="406fc-129">Processing status</span></span>

  - <span data-ttu-id="406fc-130">**Estado**de indización: indica el estado del trabajo de indización profunda.</span><span class="sxs-lookup"><span data-stu-id="406fc-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="406fc-131">**Fecha y hora de la última actualización**de la indización: indica el fecha de Cuándo se desencadenó por última vez el trabajo de indización en profundidad.</span><span class="sxs-lookup"><span data-stu-id="406fc-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="406fc-132">**Orígenes de datos**: muestra el número de buzones de correo, sitios y equipos que se han seleccionado para el custodio.</span><span class="sxs-lookup"><span data-stu-id="406fc-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="406fc-133">Actualización de un custodio</span><span class="sxs-lookup"><span data-stu-id="406fc-133">Updating a custodian</span></span>

<span data-ttu-id="406fc-p107">A medida que avanza el caso, es posible que descubra que puede haber orígenes de datos adicionales relacionados con un custodio específico & su caso. En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y considerados como no relevantes.</span><span class="sxs-lookup"><span data-stu-id="406fc-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="406fc-136">Para actualizar un custodio y los orígenes de datos seleccionados:</span><span class="sxs-lookup"><span data-stu-id="406fc-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="406fc-137">Seleccione un caso existente de la exhibición de documentos electrónicos **_GT_ Advanced eDiscovery (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="406fc-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="406fc-138">En el caso, haga clic \*\*\*\* en la ficha custodios.</span><span class="sxs-lookup"><span data-stu-id="406fc-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="406fc-139">Seleccione los custodios de la lista y haga clic en **editar fuentes**.</span><span class="sxs-lookup"><span data-stu-id="406fc-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="406fc-140">Para actualizar las selecciones para las ubicaciones de Exchange y OneDrive, haga clic en **Elegir orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="406fc-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="406fc-p108">Agregar o quitar buzones de correo de Microsoft Teams, SharePoint o Exchange asigne el usuario haciendo clic para **seleccionar orígenes de datos adicionales**. Para obtener más información sobre cómo asignar orígenes de datos a un custodio, consulte [Add custodios to a case](add-custodians-to-case.md).</span><span class="sxs-lookup"><span data-stu-id="406fc-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="406fc-143">Para actualizar el estado de conservación de custodios, haga clic en **realizar suspensiones de custodia**y habilite o deshabilite la retención para los custodios.</span><span class="sxs-lookup"><span data-stu-id="406fc-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="406fc-144">Puede seleccionar varios custodios para realizar acciones en masa, como volver a indexar, liberar o editar un conjunto de custodios.</span><span class="sxs-lookup"><span data-stu-id="406fc-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="406fc-145">Resolver errores de procesamiento de custodios</span><span class="sxs-lookup"><span data-stu-id="406fc-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="406fc-p109">En la mayoría de los flujos de trabajo legales, después de agregar custodios para una investigación específica, se buscará un subconjunto de los datos de los usuarios. Debido a los tamaños de archivo grandes o posibles daños, algunos elementos de los orígenes de datos de los custodios pueden indizarse parcialmente. Mediante el uso de la función de indización profunda de eDiscovery avanzado (versión preliminar), estos elementos parcialmente indizados se pueden corregir automáticamente volviendo a rastrear y indizar estos elementos a petición.</span><span class="sxs-lookup"><span data-stu-id="406fc-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="406fc-p110">Cuando se agrega un custodio a un caso, sus datos se "indizarán automáticamente" de forma automática, lo que permite a los usuarios dejar estos elementos parcialmente indizados en lugar de tener que descargar, corregir y volver a ejecutar búsquedas fuera de Office 365. Durante el ciclo de vida de un caso, un usuario puede corregir elementos o agregar nuevos orígenes de datos para un custodio determinado. Esto puede requerir que se actualice el índice de custodios.</span><span class="sxs-lookup"><span data-stu-id="406fc-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="406fc-152">Para desencadenar un proceso de reindización para tratar los elementos parcialmente indizados:</span><span class="sxs-lookup"><span data-stu-id="406fc-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="406fc-153">Vaya a **eDiscovery _GT_ Advanced eDiscovery (Preview)** y seleccione un caso existente.</span><span class="sxs-lookup"><span data-stu-id="406fc-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="406fc-154">En el caso, haga clic en para la **ficha custodios**.</span><span class="sxs-lookup"><span data-stu-id="406fc-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="406fc-155">Seleccione los custodios que se deben reindizar y, a continuación, haga clic en **Actualizar índice** en la página de control flotante.</span><span class="sxs-lookup"><span data-stu-id="406fc-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="406fc-156">Compruebe el estado del índice de custodios haciendo clic en el vínculo de la columna **Estado de trabajo** de \*\*\*\* indización en la ficha custodios.</span><span class="sxs-lookup"><span data-stu-id="406fc-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="406fc-157">También se puede realizar un seguimiento del estado del proceso de reindización en la pestaña **trabajos** .</span><span class="sxs-lookup"><span data-stu-id="406fc-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="406fc-158">Para obtener más información acerca de cómo volver a indizar y corregir los elementos parcialmente indizados, vea [corregir errores de procesamiento](processing-data-for-case.md).</span><span class="sxs-lookup"><span data-stu-id="406fc-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="406fc-159">Liberar un custodio de un caso</span><span class="sxs-lookup"><span data-stu-id="406fc-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="406fc-160">Un custodio se publica en situaciones en las que se cierra un caso, ya que un custodio ya no está obligado a preservar el contenido de un caso, o cuando se considera que un custodio ya no es relevante para un caso en particular.</span><span class="sxs-lookup"><span data-stu-id="406fc-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="406fc-p111">Si libera un custodio después de que se publique un aviso de retención, se enviará una notificación de publicación al custodio. Además, también se eliminarán todos los retenciones de privación que se hayan atribuido a los custodios emitidos.</span><span class="sxs-lookup"><span data-stu-id="406fc-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="406fc-163">Si el custodio se puso en una retención silenciosa, donde no se emitieron notificaciones legales de retención, se eliminarán todos los retenciones de privación que se hayan atribuido a los custodios emitidos.</span><span class="sxs-lookup"><span data-stu-id="406fc-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="406fc-164">Para liberar un custodio:</span><span class="sxs-lookup"><span data-stu-id="406fc-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="406fc-165">Vaya a la \*\*\*\* pestaña custodios.</span><span class="sxs-lookup"><span data-stu-id="406fc-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="406fc-166">Seleccione el custodio de la lista y haga clic en **liberar custodios** en la página de flotante.</span><span class="sxs-lookup"><span data-stu-id="406fc-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="406fc-167">El estado del custodio en la ficha **custodios** está establecido en **lanzado** y el estado de la **retención** en la página de control flotante cambia a inactivo. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="406fc-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="406fc-p112">Un custodio puede estar involucrado de manera simultánea en varias cuestiones legales de retención. Cuando se publica un custodio desde un caso, las suspensiones y notificaciones en otros asuntos no se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="406fc-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="406fc-170">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="406fc-170">Related information</span></span>

 - [<span data-ttu-id="406fc-171">Corrección de errores al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="406fc-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="406fc-172">Trabajar con las comunicaciones</span><span class="sxs-lookup"><span data-stu-id="406fc-172">Work with communications</span></span>](managing-custodian-communications.md)

---
title: Información general sobre el administrador del plan de archivos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 'El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.'
ms.openlocfilehash: 4feacf20444591f6da2d55a928a81e86b56c5d9a
ms.sourcegitcommit: 9f34ace6bbe3d5e07e24ebaae96613750869cddf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25019281"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="e80ad-103">Información general sobre el administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="e80ad-103">Overview of file plan manager</span></span>

<span data-ttu-id="e80ad-104">El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.</span><span class="sxs-lookup"><span data-stu-id="e80ad-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Página del plan de archivos](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a><span data-ttu-id="e80ad-106">Importante: Esta característica está disponible solo como parte del programa Office 365 Preview</span><span class="sxs-lookup"><span data-stu-id="e80ad-106">Important: This feature is currently available only as part of the Office 365 Preview program</span></span>

<span data-ttu-id="e80ad-107">Solo verá esta característica en su inquilino si su organización se ha inscrito en el programa de Office 365 Preview.</span><span class="sxs-lookup"><span data-stu-id="e80ad-107">You will see this feature in your tenant only if your organization has enrolled in the Office 365 Preview program.</span></span>

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="e80ad-108">Acceder al administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="e80ad-108">Accessing file plan manager</span></span>

<span data-ttu-id="e80ad-109">Hay dos requisitos para obtener acceso al administrador del plan de archivos, son:</span><span class="sxs-lookup"><span data-stu-id="e80ad-109">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="e80ad-110">Una suscripción de Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="e80ad-110">An Office 365 Enterprise E5 subscription with user licenses.</span></span>
- <span data-ttu-id="e80ad-111">El usuario tiene asignado uno de los siguientes roles del Centro de seguridad y cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="e80ad-111">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="e80ad-112">Administrador de retención</span><span class="sxs-lookup"><span data-stu-id="e80ad-112">Retention Manager</span></span>
    - <span data-ttu-id="e80ad-113">Administrador de retención con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="e80ad-113">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="e80ad-114">Navegar por el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="e80ad-114">Navigating your file plan</span></span>

<span data-ttu-id="e80ad-115">El administrador del plan de archivos facilita ver y revisar la configuración de todas las directivas y etiquetas de retención en una vista.</span><span class="sxs-lookup"><span data-stu-id="e80ad-115">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="e80ad-116">Tenga en cuenta que las etiquetas de retención creadas fuera del plan de archivos estarán disponibles en el plan de archivos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="e80ad-116">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="e80ad-117">En la pestaña **Etiquetas del plan de archivos**, están disponibles la siguiente información adicional y funciones:</span><span class="sxs-lookup"><span data-stu-id="e80ad-117">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="e80ad-118">Columnas de configuración de etiqueta</span><span class="sxs-lookup"><span data-stu-id="e80ad-118">Label settings columns</span></span>
 
- <span data-ttu-id="e80ad-p101">**En base a** identifica el tipo de desencadenador que iniciará el período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="e80ad-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="e80ad-121">Evento</span><span class="sxs-lookup"><span data-stu-id="e80ad-121">Event</span></span>
    - <span data-ttu-id="e80ad-122">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="e80ad-122">When created</span></span>
    - <span data-ttu-id="e80ad-123">Fecha de última modificación</span><span class="sxs-lookup"><span data-stu-id="e80ad-123">When last modified</span></span>
    - <span data-ttu-id="e80ad-124">Fecha de etiquetado</span><span class="sxs-lookup"><span data-stu-id="e80ad-124">When labeled</span></span>
- <span data-ttu-id="e80ad-p102">**Registro** identifica si el elemento se convertirá en un registro declarado cuando se aplique la etiqueta. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="e80ad-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="e80ad-127">No</span><span class="sxs-lookup"><span data-stu-id="e80ad-127">No</span></span>
    - <span data-ttu-id="e80ad-128">Sí</span><span class="sxs-lookup"><span data-stu-id="e80ad-128">Yes</span></span>
    - <span data-ttu-id="e80ad-129">Sí (Normativa)</span><span class="sxs-lookup"><span data-stu-id="e80ad-129">Yes(Regulatory)</span></span>
- <span data-ttu-id="e80ad-p103">**Retención** identifica el tipo de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="e80ad-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="e80ad-132">Conservar</span><span class="sxs-lookup"><span data-stu-id="e80ad-132">Keep</span></span>
    - <span data-ttu-id="e80ad-133">Conservar y eliminar</span><span class="sxs-lookup"><span data-stu-id="e80ad-133">Keep and delete</span></span>
    - <span data-ttu-id="e80ad-134">Eliminar</span><span class="sxs-lookup"><span data-stu-id="e80ad-134">Delete</span></span>
- <span data-ttu-id="e80ad-p104">**Disposición** identifica qué ocurrirá con el contenido al final del período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="e80ad-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="e80ad-137">null</span><span class="sxs-lookup"><span data-stu-id="e80ad-137">Null</span></span>
    - <span data-ttu-id="e80ad-138">Ninguna acción</span><span class="sxs-lookup"><span data-stu-id="e80ad-138">No action necessary.</span></span>
    - <span data-ttu-id="e80ad-139">Eliminación automática</span><span class="sxs-lookup"><span data-stu-id="e80ad-139">Auto-delete</span></span>
    - <span data-ttu-id="e80ad-140">Revisión necesaria (también conocido como revisión de disposición)</span><span class="sxs-lookup"><span data-stu-id="e80ad-140">Review required (aka Disposition review)</span></span>

![Configuración de etiqueta en el plan de archivos](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="e80ad-142">Columnas de descriptores del plan de archivos de las etiquetas</span><span class="sxs-lookup"><span data-stu-id="e80ad-142">Label file plan descriptors columns</span></span>

<span data-ttu-id="e80ad-p105">Ahora puede incluir más información en la configuración de las etiquetas de retención. Insertar descriptores del plan de archivos en las etiquetas mejorará la administración y la organización de su plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="e80ad-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="e80ad-p106">Para comenzar, el administrador del plan de archivos proporciona algunos valores de fábrica para: función o departamento, categoría, tipo de autoridad y aprovisionamiento o cita. Puede agregar nuevos archivos valores descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="e80ad-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="e80ad-147">Esta es una vista del paso de descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="e80ad-147">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descriptores del plan de archivos](media/file-plan-descriptors.png)

<span data-ttu-id="e80ad-149">Esta es una vista de las columnas de descriptores del plan de archivos en la pestaña de etiquetas del administrador del plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="e80ad-149">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="e80ad-151">Exportar etiquetas del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="e80ad-151">Export labels out of your file plan</span></span>

<span data-ttu-id="e80ad-152">Desde el administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv para facilitar el revisiones de cumplimiento periódicas con partes interesadas del gobierno de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="e80ad-152">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="e80ad-153">Para exportar todas las etiquetas de retención, vaya al **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Exportar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-153">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opción para exportar el plan de archivos](media/file-plan-export-labels-option.png)

<span data-ttu-id="e80ad-155">Se abrirá un archivo \*.csv que contiene todas las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="e80ad-155">A \*.csv file containing all existing retention labels will open.</span></span>

![Archivo CSV que muestra todas las etiquetas de retención](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="e80ad-157">Importar etiquetas en el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="e80ad-157">Import labels into your file plan</span></span>

<span data-ttu-id="e80ad-158">Desde el administrador del plan de archivos, puede importar en masa nuevas etiquetas así como modificar las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="e80ad-158">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="e80ad-159">Para importar nuevas etiquetas de retención y realizar actualizaciones en etiquetas de retención existentes, vaya a **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Importar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-159">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opción para importar el plan de archivos](media/file-plan-import-labels-option.png)

![Opción para descargar una plantilla de plan de archivos en blanco](media/file-plan-blank-template-option.png)

<span data-ttu-id="e80ad-162">Descargue una plantilla en blanco (o empiece desde una exportación de su plan actual del archivo).</span><span class="sxs-lookup"><span data-stu-id="e80ad-162">Download a blank template (or start from an export of your current file plan).</span></span>

![Plantilla en blanco del plan de archivos abierta en Excel](media/file-plan-blank-template.png)

<span data-ttu-id="e80ad-164">Rellene la plantilla (próximamente publicaremos la información de referencia acerca de los valores válidos para las entradas).</span><span class="sxs-lookup"><span data-stu-id="e80ad-164">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![Plantilla del plan de archivos con información rellenada](media/file-plan-filled-out-template.png)

<span data-ttu-id="e80ad-166">Cargue la plantilla rellenada y el administrador del plan de archivos validará las entradas y mostrará las estadísticas de importación.</span><span class="sxs-lookup"><span data-stu-id="e80ad-166">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Estadísticas de importación del plan de archivos](media/file-plan-import-statistics.png)

<span data-ttu-id="e80ad-168">Una vez completada la importación, vuelva al administrador del plan de archivos para asignar nuevas etiquetas a las directivas nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="e80ad-168">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opción para publicar etiquetas](media/file-plan-publish-labels-option.png)


---
title: Información general sobre el administrador del plan de archivos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 'El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.'
ms.openlocfilehash: 328b8f1aeed3e25fb0ab5eb651fb3846b123747c
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410525"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="b9411-103">Información general sobre el administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="b9411-103">Overview of file plan manager</span></span>

<span data-ttu-id="b9411-104">El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.</span><span class="sxs-lookup"><span data-stu-id="b9411-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Página del plan de archivos](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="b9411-106">Acceder al administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="b9411-106">Accessing file plan manager</span></span>

<span data-ttu-id="b9411-107">Hay dos requisitos para obtener acceso al administrador del plan de archivos, son:</span><span class="sxs-lookup"><span data-stu-id="b9411-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="b9411-108">Una suscripción de Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="b9411-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="b9411-109">El usuario tiene asignado uno de los siguientes roles del Centro de seguridad y cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="b9411-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="b9411-110">Administrador de retención</span><span class="sxs-lookup"><span data-stu-id="b9411-110">Retention Manager</span></span>
    - <span data-ttu-id="b9411-111">Administrador de retención con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="b9411-111">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="b9411-112">Navegar por el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="b9411-112">Navigating your file plan</span></span>

<span data-ttu-id="b9411-113">El administrador del plan de archivos facilita ver y revisar la configuración de todas las directivas y etiquetas de retención en una vista.</span><span class="sxs-lookup"><span data-stu-id="b9411-113">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="b9411-114">Tenga en cuenta que las etiquetas de retención creadas fuera del plan de archivos estarán disponibles en el plan de archivos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="b9411-114">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="b9411-115">En la pestaña **Etiquetas del plan de archivos**, están disponibles la siguiente información adicional y funciones:</span><span class="sxs-lookup"><span data-stu-id="b9411-115">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="b9411-116">Columnas de configuración de etiqueta</span><span class="sxs-lookup"><span data-stu-id="b9411-116">Label settings columns</span></span>
 
- <span data-ttu-id="b9411-p101">**En base a** identifica el tipo de desencadenador que iniciará el período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="b9411-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="b9411-119">Evento</span><span class="sxs-lookup"><span data-stu-id="b9411-119">Event</span></span>
    - <span data-ttu-id="b9411-120">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="b9411-120">When created</span></span>
    - <span data-ttu-id="b9411-121">Fecha de última modificación</span><span class="sxs-lookup"><span data-stu-id="b9411-121">When last modified</span></span>
    - <span data-ttu-id="b9411-122">Fecha de etiquetado</span><span class="sxs-lookup"><span data-stu-id="b9411-122">When labeled</span></span>
- <span data-ttu-id="b9411-p102">**Registro** identifica si el elemento se convertirá en un registro declarado cuando se aplique la etiqueta. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="b9411-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="b9411-125">No</span><span class="sxs-lookup"><span data-stu-id="b9411-125">No</span></span>
    - <span data-ttu-id="b9411-126">Sí</span><span class="sxs-lookup"><span data-stu-id="b9411-126">Yes</span></span>
    - <span data-ttu-id="b9411-127">Sí (Normativa)</span><span class="sxs-lookup"><span data-stu-id="b9411-127">Yes(Regulatory)</span></span>
- <span data-ttu-id="b9411-p103">**Retención** identifica el tipo de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="b9411-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="b9411-130">Conservar</span><span class="sxs-lookup"><span data-stu-id="b9411-130">Keep</span></span>
    - <span data-ttu-id="b9411-131">Conservar y eliminar</span><span class="sxs-lookup"><span data-stu-id="b9411-131">Keep and delete</span></span>
    - <span data-ttu-id="b9411-132">Eliminar</span><span class="sxs-lookup"><span data-stu-id="b9411-132">Delete</span></span>
- <span data-ttu-id="b9411-p104">**Disposición** identifica qué ocurrirá con el contenido al final del período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="b9411-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="b9411-135">null</span><span class="sxs-lookup"><span data-stu-id="b9411-135">null</span></span>
    - <span data-ttu-id="b9411-136">Ninguna acción</span><span class="sxs-lookup"><span data-stu-id="b9411-136">No action</span></span>
    - <span data-ttu-id="b9411-137">Eliminación automática</span><span class="sxs-lookup"><span data-stu-id="b9411-137">Auto-delete</span></span>
    - <span data-ttu-id="b9411-138">Revisión necesaria (también conocido como revisión de disposición)</span><span class="sxs-lookup"><span data-stu-id="b9411-138">Review required (aka Disposition review)</span></span>

![Configuración de etiqueta en el plan de archivos](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="b9411-140">Columnas de descriptores del plan de archivos de las etiquetas</span><span class="sxs-lookup"><span data-stu-id="b9411-140">Label file plan descriptors columns</span></span>

<span data-ttu-id="b9411-p105">Ahora puede incluir más información en la configuración de las etiquetas de retención. Insertar descriptores del plan de archivos en las etiquetas mejorará la administración y la organización de su plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="b9411-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="b9411-p106">Para comenzar, el administrador del plan de archivos proporciona algunos valores de fábrica para: función o departamento, categoría, tipo de autoridad y aprovisionamiento o cita. Puede agregar nuevos archivos valores descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="b9411-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="b9411-145">Esta es una vista del paso de descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="b9411-145">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descriptores del plan de archivos](media/file-plan-descriptors.png)

<span data-ttu-id="b9411-147">Esta es una vista de las columnas de descriptores del plan de archivos en la pestaña de etiquetas del administrador del plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="b9411-147">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="b9411-149">Exportar etiquetas del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="b9411-149">Export labels out of your file plan</span></span>

<span data-ttu-id="b9411-150">Desde el administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv para facilitar el revisiones de cumplimiento periódicas con partes interesadas del gobierno de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="b9411-150">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="b9411-151">Para exportar todas las etiquetas de retención, vaya al **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Exportar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="b9411-151">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opción para exportar el plan de archivos](media/file-plan-export-labels-option.png)

<span data-ttu-id="b9411-153">Se abrirá un archivo \*.csv que contiene todas las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="b9411-153">A \*.csv file containing all existing retention labels will open.</span></span>

![Archivo CSV que muestra todas las etiquetas de retención](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="b9411-155">Importar etiquetas en el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="b9411-155">Import labels into your file plan</span></span>

<span data-ttu-id="b9411-156">Desde el administrador del plan de archivos, puede importar en masa nuevas etiquetas así como modificar las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="b9411-156">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="b9411-157">Para importar nuevas etiquetas de retención y realizar actualizaciones en etiquetas de retención existentes, vaya a **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Importar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="b9411-157">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opción para importar el plan de archivos](media/file-plan-import-labels-option.png)

![Opción para descargar una plantilla de plan de archivos en blanco](media/file-plan-blank-template-option.png)

<span data-ttu-id="b9411-160">Descargue una plantilla en blanco (o empiece desde una exportación de su plan actual del archivo).</span><span class="sxs-lookup"><span data-stu-id="b9411-160">Download a blank template (or start from an export of your current file plan).</span></span>

![Plantilla en blanco del plan de archivos abierta en Excel](media/file-plan-blank-template.png)

<span data-ttu-id="b9411-162">Rellene la plantilla (próximamente publicaremos la información de referencia acerca de los valores válidos para las entradas).</span><span class="sxs-lookup"><span data-stu-id="b9411-162">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![Plantilla del plan de archivos con información rellenada](media/file-plan-filled-out-template.png)

<span data-ttu-id="b9411-164">Cargue la plantilla rellenada y el administrador del plan de archivos validará las entradas y mostrará las estadísticas de importación.</span><span class="sxs-lookup"><span data-stu-id="b9411-164">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Estadísticas de importación del plan de archivos](media/file-plan-import-statistics.png)

<span data-ttu-id="b9411-166">Una vez completada la importación, vuelva al administrador del plan de archivos para asignar nuevas etiquetas a las directivas nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="b9411-166">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opción para publicar etiquetas](media/file-plan-publish-labels-option.png)


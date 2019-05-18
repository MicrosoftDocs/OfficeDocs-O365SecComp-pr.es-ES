---
title: Información general sobre el administrador del plan de archivos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 'El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.'
ms.openlocfilehash: 377589ab0a8fd2f4c5e73a21eac3988091fa3ed3
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152902"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="5a712-103">Información general sobre el administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="5a712-103">Overview of file plan manager</span></span>

<span data-ttu-id="5a712-104">El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.</span><span class="sxs-lookup"><span data-stu-id="5a712-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Página del plan de archivos](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="5a712-106">Acceder al administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="5a712-106">Accessing file plan manager</span></span>

<span data-ttu-id="5a712-107">Hay dos requisitos para obtener acceso al administrador del plan de archivos, son:</span><span class="sxs-lookup"><span data-stu-id="5a712-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="5a712-108">Una suscripción de Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="5a712-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="5a712-109">El usuario tiene asignado uno de los siguientes roles del Centro de seguridad y cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="5a712-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="5a712-110">Administrador de retención</span><span class="sxs-lookup"><span data-stu-id="5a712-110">Retention Manager</span></span>
    - <span data-ttu-id="5a712-111">Administrador de retención con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="5a712-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="5a712-112">Etiquetas de retención predeterminadas y directiva de etiquetas</span><span class="sxs-lookup"><span data-stu-id="5a712-112">Default retention labels and label policy</span></span>

<span data-ttu-id="5a712-113">Si no hay etiquetas de retención en el Centro de seguridad y cumplimiento, la primera vez que elija **Plan de archivos** en la parte izquierda, se creará una directiva de etiquetas denominada **Directiva de publicación predeterminada de gobierno de datos**.</span><span class="sxs-lookup"><span data-stu-id="5a712-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="5a712-114">Esta directiva de etiqueta contiene tres etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="5a712-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="5a712-115">**Procedimientos operativos**</span><span class="sxs-lookup"><span data-stu-id="5a712-115">**Operational procedure**</span></span>
- <span data-ttu-id="5a712-116">**General comercial**</span><span class="sxs-lookup"><span data-stu-id="5a712-116">**Business general**</span></span>
- <span data-ttu-id="5a712-117">**Acuerdo de contrato**</span><span class="sxs-lookup"><span data-stu-id="5a712-117">**Contract agreement**</span></span>

<span data-ttu-id="5a712-118">Estas etiquetas de retención se configuran solo para retener el contenido, no eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="5a712-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="5a712-119">Esta directiva de etiquetas se publicará en toda la organización y puede deshabilitarse o quitarse.</span><span class="sxs-lookup"><span data-stu-id="5a712-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="5a712-120">Puede determinar quién ha abierto el administrador del plan de archivos y desencadenado la experiencia de primera ejecución. Para ello, revise el registro de auditoría de las actividades **Directiva de retención creada** y **Configuración de retención para una directiva de retención creada**.</span><span class="sxs-lookup"><span data-stu-id="5a712-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="5a712-121">Debido a los comentarios de los clientes, hemos eliminado la característica que crea las etiquetas de retención predeterminadas y la directiva de etiquetas mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5a712-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="5a712-122">Solo verá esta directiva y estas etiquetas si usó el administrador del plan de archivos antes del 11 de abril de 2019.</span><span class="sxs-lookup"><span data-stu-id="5a712-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="5a712-123">Navegar por el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="5a712-123">Navigating your file plan</span></span>

<span data-ttu-id="5a712-124">El administrador del plan de archivos facilita ver y revisar la configuración de todas las directivas y etiquetas de retención en una vista.</span><span class="sxs-lookup"><span data-stu-id="5a712-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="5a712-125">Tenga en cuenta que las etiquetas de retención creadas fuera del plan de archivos estarán disponibles en el plan de archivos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="5a712-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="5a712-126">En la pestaña **Etiquetas del plan de archivos**, están disponibles la siguiente información adicional y funciones:</span><span class="sxs-lookup"><span data-stu-id="5a712-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="5a712-127">Columnas de configuración de etiqueta</span><span class="sxs-lookup"><span data-stu-id="5a712-127">Label settings columns</span></span>

- <span data-ttu-id="5a712-p103">**En base a** identifica el tipo de desencadenador que iniciará el período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="5a712-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="5a712-130">Evento</span><span class="sxs-lookup"><span data-stu-id="5a712-130">Event</span></span>
    - <span data-ttu-id="5a712-131">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="5a712-131">When created</span></span>
    - <span data-ttu-id="5a712-132">Fecha de última modificación</span><span class="sxs-lookup"><span data-stu-id="5a712-132">When last modified</span></span>
    - <span data-ttu-id="5a712-133">Fecha de etiquetado</span><span class="sxs-lookup"><span data-stu-id="5a712-133">When labeled</span></span>
- <span data-ttu-id="5a712-p104">**Registro** identifica si el elemento se convertirá en un registro declarado cuando se aplique la etiqueta. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="5a712-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="5a712-136">No</span><span class="sxs-lookup"><span data-stu-id="5a712-136">No</span></span>
    - <span data-ttu-id="5a712-137">Sí</span><span class="sxs-lookup"><span data-stu-id="5a712-137">Yes</span></span>
    - <span data-ttu-id="5a712-138">Sí (Normativa)</span><span class="sxs-lookup"><span data-stu-id="5a712-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="5a712-p105">**Retención** identifica el tipo de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="5a712-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="5a712-141">Conservar</span><span class="sxs-lookup"><span data-stu-id="5a712-141">Keep</span></span>
    - <span data-ttu-id="5a712-142">Conservar y eliminar</span><span class="sxs-lookup"><span data-stu-id="5a712-142">Keep and delete</span></span>
    - <span data-ttu-id="5a712-143">Eliminar</span><span class="sxs-lookup"><span data-stu-id="5a712-143">Delete</span></span>
- <span data-ttu-id="5a712-p106">**Disposición** identifica qué ocurrirá con el contenido al final del período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="5a712-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="5a712-146">null</span><span class="sxs-lookup"><span data-stu-id="5a712-146">null</span></span>
    - <span data-ttu-id="5a712-147">Ninguna acción</span><span class="sxs-lookup"><span data-stu-id="5a712-147">No action</span></span>
    - <span data-ttu-id="5a712-148">Eliminación automática</span><span class="sxs-lookup"><span data-stu-id="5a712-148">Auto-delete</span></span>
    - <span data-ttu-id="5a712-149">Revisión necesaria (también conocido como revisión de disposición)</span><span class="sxs-lookup"><span data-stu-id="5a712-149">Review required (aka Disposition review)</span></span>

![Configuración de etiqueta en el plan de archivos](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="5a712-151">Columnas de descriptores del plan de archivos de las etiquetas</span><span class="sxs-lookup"><span data-stu-id="5a712-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="5a712-p107">Ahora puede incluir más información en la configuración de las etiquetas de retención. Insertar descriptores del plan de archivos en las etiquetas mejorará la administración y la organización de su plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="5a712-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="5a712-p108">Para comenzar, el administrador del plan de archivos proporciona algunos valores de fábrica para: función o departamento, categoría, tipo de autoridad y aprovisionamiento o cita. Puede agregar nuevos archivos valores descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="5a712-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="5a712-156">Esta es una vista del paso de descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="5a712-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descriptores del plan de archivos](media/file-plan-descriptors.png)

<span data-ttu-id="5a712-158">Esta es una vista de las columnas de descriptores del plan de archivos en la pestaña de etiquetas del administrador del plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="5a712-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="5a712-160">Exportar etiquetas del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="5a712-160">Export labels out of your file plan</span></span>

<span data-ttu-id="5a712-161">Desde el administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv para facilitar el revisiones de cumplimiento periódicas con partes interesadas del gobierno de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="5a712-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="5a712-162">Para exportar todas las etiquetas de retención, vaya al **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Exportar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5a712-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opción para exportar el plan de archivos](media/file-plan-export-labels-option.png)

<span data-ttu-id="5a712-164">Se abrirá un archivo \*.csv que contiene todas las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="5a712-164">A \*.csv file containing all existing retention labels will open.</span></span>

![Archivo CSV que muestra todas las etiquetas de retención](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="5a712-166">Importar etiquetas en el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="5a712-166">Import labels into your file plan</span></span>

<span data-ttu-id="5a712-167">Desde el administrador del plan de archivos, puede importar en masa nuevas etiquetas así como modificar las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="5a712-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="5a712-168">Para importar nuevas etiquetas de retención y realizar actualizaciones en etiquetas de retención existentes, vaya a **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Importar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5a712-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opción para importar el plan de archivos](media/file-plan-import-labels-option.png)

![Opción para descargar una plantilla de plan de archivos en blanco](media/file-plan-blank-template-option.png)

<span data-ttu-id="5a712-171">Descargue una plantilla en blanco (o empiece desde una exportación de su plan actual del archivo).</span><span class="sxs-lookup"><span data-stu-id="5a712-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Plantilla en blanco del plan de archivos abierta en Excel](media/file-plan-blank-template.png)

<span data-ttu-id="5a712-173">Rellene la plantilla (próximamente publicaremos la información de referencia acerca de los valores válidos para las entradas).</span><span class="sxs-lookup"><span data-stu-id="5a712-173">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![Plantilla del plan de archivos con información rellenada](media/file-plan-filled-out-template.png)

<span data-ttu-id="5a712-175">Cargue la plantilla rellenada y el administrador del plan de archivos validará las entradas y mostrará las estadísticas de importación.</span><span class="sxs-lookup"><span data-stu-id="5a712-175">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Estadísticas de importación del plan de archivos](media/file-plan-import-statistics.png)

<span data-ttu-id="5a712-177">Una vez completada la importación, vuelva al administrador del plan de archivos para asignar nuevas etiquetas a las directivas nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="5a712-177">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opción para publicar etiquetas](media/file-plan-publish-labels-option.png)


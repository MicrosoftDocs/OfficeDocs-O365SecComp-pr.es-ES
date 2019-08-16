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
description: 'El administrador del plan de archivos proporciona funciones avanzadas de administración para las etiquetas de retención, directivas de etiquetas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y, por último, eliminación.'
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: f443de08971da2fe200a159b8efbed40effba125
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "36430017"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="c4ebf-103">Información general sobre el administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="c4ebf-103">Overview of file plan manager</span></span>

<span data-ttu-id="c4ebf-104">El administrador del plan de archivos proporciona funciones avanzadas de administración para las etiquetas de retención, directivas de etiquetas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y, por último, eliminación.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Página del plan de archivos](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="c4ebf-106">Acceder al administrador del plan de archivos</span><span class="sxs-lookup"><span data-stu-id="c4ebf-106">Accessing file plan manager</span></span>

<span data-ttu-id="c4ebf-107">Hay dos requisitos para obtener acceso al administrador del plan de archivos, son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="c4ebf-108">Una suscripción de Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="c4ebf-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="c4ebf-109">El usuario tiene asignado uno de los siguientes roles del Centro de seguridad y cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="c4ebf-110">Administrador de retención</span><span class="sxs-lookup"><span data-stu-id="c4ebf-110">Retention Manager</span></span>
    - <span data-ttu-id="c4ebf-111">Administrador de retención con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="c4ebf-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="c4ebf-112">Etiquetas de retención predeterminadas y directiva de etiquetas</span><span class="sxs-lookup"><span data-stu-id="c4ebf-112">Default retention labels and label policy</span></span>

<span data-ttu-id="c4ebf-113">Si no hay etiquetas de retención en el Centro de seguridad y cumplimiento, la primera vez que elija **Plan de archivos** en la parte izquierda, se creará una directiva de etiquetas denominada **Directiva de publicación predeterminada de gobierno de datos**.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="c4ebf-114">Esta directiva de etiqueta contiene tres etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="c4ebf-115">**Procedimientos operativos**</span><span class="sxs-lookup"><span data-stu-id="c4ebf-115">**Operational procedure**</span></span>
- <span data-ttu-id="c4ebf-116">**General comercial**</span><span class="sxs-lookup"><span data-stu-id="c4ebf-116">**Business general**</span></span>
- <span data-ttu-id="c4ebf-117">**Acuerdo de contrato**</span><span class="sxs-lookup"><span data-stu-id="c4ebf-117">**Contract agreement**</span></span>

<span data-ttu-id="c4ebf-118">Estas etiquetas de retención se configuran solo para retener el contenido, no eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="c4ebf-119">Esta directiva de etiquetas se publicará en toda la organización y puede deshabilitarse o quitarse.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="c4ebf-120">Puede determinar quién ha abierto el administrador del plan de archivos y desencadenado la experiencia de primera ejecución. Para ello, revise el registro de auditoría de las actividades **Directiva de retención creada** y **Configuración de retención para una directiva de retención creada**.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="c4ebf-121">Debido a los comentarios de los clientes, hemos eliminado la característica que crea las etiquetas de retención predeterminadas y la directiva de etiquetas de retención mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="c4ebf-122">Solo verá las etiquetas de retención y la directiva de etiqueta de retención si abrió el administrador del plan de archivos antes del 11 de abril de 2019.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="c4ebf-123">Navegar por el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="c4ebf-123">Navigating your file plan</span></span>

<span data-ttu-id="c4ebf-124">El administrador del plan de archivos facilita ver y revisar la configuración de todas las directivas y etiquetas de retención en una vista.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="c4ebf-125">Tenga en cuenta que las etiquetas de retención creadas fuera del plan de archivos estarán disponibles en el plan de archivos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="c4ebf-126">En la pestaña **Etiquetas del plan de archivos**, están disponibles la siguiente información adicional y funciones:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="c4ebf-127">Columnas de configuración de etiqueta</span><span class="sxs-lookup"><span data-stu-id="c4ebf-127">Label settings columns</span></span>

- <span data-ttu-id="c4ebf-p103">**En base a** identifica el tipo de desencadenador que iniciará el período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="c4ebf-130">Evento</span><span class="sxs-lookup"><span data-stu-id="c4ebf-130">Event</span></span>
    - <span data-ttu-id="c4ebf-131">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="c4ebf-131">When created</span></span>
    - <span data-ttu-id="c4ebf-132">Fecha de última modificación</span><span class="sxs-lookup"><span data-stu-id="c4ebf-132">When last modified</span></span>
    - <span data-ttu-id="c4ebf-133">Fecha de etiquetado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-133">When labeled</span></span>
- <span data-ttu-id="c4ebf-p104">**Registro** identifica si el elemento se convertirá en un registro declarado cuando se aplique la etiqueta. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="c4ebf-136">No</span><span class="sxs-lookup"><span data-stu-id="c4ebf-136">No</span></span>
    - <span data-ttu-id="c4ebf-137">Sí</span><span class="sxs-lookup"><span data-stu-id="c4ebf-137">Yes</span></span>
    - <span data-ttu-id="c4ebf-138">Sí (Normativa)</span><span class="sxs-lookup"><span data-stu-id="c4ebf-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="c4ebf-p105">**Retención** identifica el tipo de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="c4ebf-141">Conservar</span><span class="sxs-lookup"><span data-stu-id="c4ebf-141">Keep</span></span>
    - <span data-ttu-id="c4ebf-142">Conservar y eliminar</span><span class="sxs-lookup"><span data-stu-id="c4ebf-142">Keep and delete</span></span>
    - <span data-ttu-id="c4ebf-143">Eliminar</span><span class="sxs-lookup"><span data-stu-id="c4ebf-143">Delete</span></span>
- <span data-ttu-id="c4ebf-p106">**Disposición** identifica qué ocurrirá con el contenido al final del período de retención. Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="c4ebf-146">null</span><span class="sxs-lookup"><span data-stu-id="c4ebf-146">null</span></span>
    - <span data-ttu-id="c4ebf-147">Ninguna acción</span><span class="sxs-lookup"><span data-stu-id="c4ebf-147">No action</span></span>
    - <span data-ttu-id="c4ebf-148">Eliminación automática</span><span class="sxs-lookup"><span data-stu-id="c4ebf-148">Auto-delete</span></span>
    - <span data-ttu-id="c4ebf-149">Revisión necesaria (también conocido como revisión de disposición)</span><span class="sxs-lookup"><span data-stu-id="c4ebf-149">Review required (aka Disposition review)</span></span>

![Configuración de etiqueta en el plan de archivos](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="c4ebf-151">Columnas de descriptores del plan de archivos de las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="c4ebf-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="c4ebf-p107">Ahora puede incluir más información en la configuración de las etiquetas de retención. Insertar descriptores del plan de archivos en las etiquetas de retención mejorará la administración y la organización de su plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="c4ebf-p108">Para comenzar, el administrador del plan de archivos proporciona algunos valores de fábrica para: función o departamento, categoría, tipo de autoridad y aprovisionamiento o cita. Puede agregar nuevos archivos valores descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="c4ebf-156">Esta es una vista del paso de descriptores del plan de archivos al crear o editar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descriptores del plan de archivos](media/file-plan-descriptors.png)

<span data-ttu-id="c4ebf-158">Esta es una vista de las columnas de descriptores del plan de archivos en la pestaña de etiquetas del administrador del plan de archivos.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="c4ebf-160">Exportar todas las etiquetas de retención existentes para analizar y/o realizar revisiones sin conexión</span><span class="sxs-lookup"><span data-stu-id="c4ebf-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="c4ebf-161">Desde el administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv para facilitar el revisiones de cumplimiento periódicas con partes interesadas del gobierno de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="c4ebf-162">Para exportar todas las etiquetas de retención, vaya al **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Exportar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opción para exportar el plan de archivos](media/file-plan-export-labels-option.png)

<span data-ttu-id="c4ebf-164">Se abrirá un archivo \*.csv que contiene todas las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-164">A \*.csv file containing all existing retention labels will open.</span></span>

![Archivo CSV que muestra todas las etiquetas de retención](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="c4ebf-166">Importar las etiquetas de retención en el plan de archivos</span><span class="sxs-lookup"><span data-stu-id="c4ebf-166">Import labels into your file plan</span></span>

<span data-ttu-id="c4ebf-167">Desde el administrador del plan de archivos, puede importar en masa nuevas etiquetas de retención así como modificar las etiquetas de retención existentes.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="c4ebf-168">Para importar nuevas etiquetas de retención y actualizar las etiquetas de retención existentes, vaya a **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Importar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opción para importar el plan de archivos](media/file-plan-import-labels-option.png)

![Opción para descargar una plantilla de plan de archivos en blanco](media/file-plan-blank-template-option.png)

<span data-ttu-id="c4ebf-171">Descargue una plantilla en blanco (o empiece desde una exportación de su plan actual del archivo).</span><span class="sxs-lookup"><span data-stu-id="c4ebf-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Plantilla en blanco del plan de archivos abierta en Excel](media/file-plan-blank-template.png)

<span data-ttu-id="c4ebf-173">Complete la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-173">Fill-out the template.</span></span> <span data-ttu-id="c4ebf-174">En esta tabla se muestran los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-174">This table provides valid values.</span></span>

|<span data-ttu-id="c4ebf-175">**Property**</span><span class="sxs-lookup"><span data-stu-id="c4ebf-175">**Property**</span></span>|<span data-ttu-id="c4ebf-176">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c4ebf-176">**Type**</span></span>|<span data-ttu-id="c4ebf-177">**Valores válidos**</span><span class="sxs-lookup"><span data-stu-id="c4ebf-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4ebf-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="c4ebf-178">LabelName</span></span>|<span data-ttu-id="c4ebf-179">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-179">String</span></span>|<span data-ttu-id="c4ebf-180">Si el valor contiene espacios, escríbalo entre comillas (").</span><span class="sxs-lookup"><span data-stu-id="c4ebf-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="c4ebf-181">Comment</span><span class="sxs-lookup"><span data-stu-id="c4ebf-181">Comment</span></span>|<span data-ttu-id="c4ebf-182">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-182">String</span></span>|<span data-ttu-id="c4ebf-183">Si el valor contiene espacios, escríbalo entre comillas (").</span><span class="sxs-lookup"><span data-stu-id="c4ebf-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="c4ebf-184">Notes</span><span class="sxs-lookup"><span data-stu-id="c4ebf-184">Notes</span></span>|<span data-ttu-id="c4ebf-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-185">String</span></span>|<span data-ttu-id="c4ebf-186">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-186">Custom</span></span>|
|<span data-ttu-id="c4ebf-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="c4ebf-187">IsRecordLabel</span></span>|<span data-ttu-id="c4ebf-188">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-188">String</span></span>|<span data-ttu-id="c4ebf-189">$True: La etiqueta es una etiqueta de registro.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-189">The 
                IsRecordLabel
              parameter specifies whether the label is a record label.</span></span></br><span data-ttu-id="c4ebf-190">$False: La etiqueta no es una etiqueta de registro.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-190">$false: The label isn't a record label.</span></span> <span data-ttu-id="c4ebf-191">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-191">This is the default value.</span></span>|
|<span data-ttu-id="c4ebf-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="c4ebf-192">RetentionAction</span></span>|<span data-ttu-id="c4ebf-193">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-193">String</span></span>|<span data-ttu-id="c4ebf-194">Delete</span><span class="sxs-lookup"><span data-stu-id="c4ebf-194">Delete</span></span></br><span data-ttu-id="c4ebf-195">Keep</span><span class="sxs-lookup"><span data-stu-id="c4ebf-195">Keep</span></span></br><span data-ttu-id="c4ebf-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="c4ebf-196">KeepAndDelete</span></span> |
|<span data-ttu-id="c4ebf-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="c4ebf-197">RetentionDuration</span></span>|<span data-ttu-id="c4ebf-198">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-198">String</span></span>|<span data-ttu-id="c4ebf-199">Esta propiedad especifica la cantidad de días que se va a conservar el contenido.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="c4ebf-200">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-200">Valid values are:</span></span></br><span data-ttu-id="c4ebf-201">Un número entero positivo.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-201">A positive integer.</span></span></br><span data-ttu-id="c4ebf-202">El valor es ilimitado.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="c4ebf-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="c4ebf-203">RetentionType</span></span>|<span data-ttu-id="c4ebf-204">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-204">String</span></span>|<span data-ttu-id="c4ebf-205">Esta propiedad especifica si se calcula la duración de retención desde la fecha de creación de contenidos, desde la fecha etiquetado o desde la fecha de la última modificación.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="c4ebf-206">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-206">Valid values are:</span></span></br><span data-ttu-id="c4ebf-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="c4ebf-207">CreationAgeInDays</span></span></br><span data-ttu-id="c4ebf-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="c4ebf-208">EventAgeInDays</span></span></br><span data-ttu-id="c4ebf-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="c4ebf-209">ModificationAgeInDays</span></span></br><span data-ttu-id="c4ebf-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="c4ebf-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="c4ebf-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="c4ebf-211">ReviewerEmail</span></span>|<span data-ttu-id="c4ebf-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="c4ebf-212">SmtpAddress</span></span>|<span data-ttu-id="c4ebf-213">Esta propiedad especifica la dirección de correo electrónico del revisor para las acciones de retención Delete y KeepAndDelete.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="c4ebf-214">Puede especificar varias direcciones de correo electrónico separadas por comas.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="c4ebf-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="c4ebf-215">ReferenceId</span></span>|<span data-ttu-id="c4ebf-216">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-216">String</span></span>|<span data-ttu-id="c4ebf-217">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-217">Custom</span></span>|
|<span data-ttu-id="c4ebf-218">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="c4ebf-218">Departmentname</span></span>|<span data-ttu-id="c4ebf-219">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-219">String</span></span>|<span data-ttu-id="c4ebf-220">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-220">Custom</span></span>|
|<span data-ttu-id="c4ebf-221">Categoría</span><span class="sxs-lookup"><span data-stu-id="c4ebf-221">Category</span></span>|<span data-ttu-id="c4ebf-222">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-222">String</span></span>|<span data-ttu-id="c4ebf-223">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-223">Custom</span></span>|
|<span data-ttu-id="c4ebf-224">SubCategory</span><span class="sxs-lookup"><span data-stu-id="c4ebf-224">SubCategory</span></span>|<span data-ttu-id="c4ebf-225">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-225">String</span></span>|<span data-ttu-id="c4ebf-226">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-226">Custom</span></span>|
|<span data-ttu-id="c4ebf-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="c4ebf-227">AuthorityType</span></span>|<span data-ttu-id="c4ebf-228">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-228">String</span></span>|<span data-ttu-id="c4ebf-229">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-229">Custom</span></span>|
|<span data-ttu-id="c4ebf-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="c4ebf-230">CitationName</span></span>|<span data-ttu-id="c4ebf-231">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-231">String</span></span>|<span data-ttu-id="c4ebf-232">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-232">Custom</span></span>|
|<span data-ttu-id="c4ebf-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="c4ebf-233">CitationUrl</span></span>|<span data-ttu-id="c4ebf-234">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-234">String</span></span>|<span data-ttu-id="c4ebf-235">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-235">Custom</span></span>|
|<span data-ttu-id="c4ebf-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="c4ebf-236">CitationJurisdiction</span></span>|<span data-ttu-id="c4ebf-237">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-237">String</span></span>|<span data-ttu-id="c4ebf-238">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-238">Custom</span></span>|
|<span data-ttu-id="c4ebf-239">Regulatory</span><span class="sxs-lookup"><span data-stu-id="c4ebf-239">Regulatory</span></span>|<span data-ttu-id="c4ebf-240">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-240">String</span></span>|<span data-ttu-id="c4ebf-241">Personalizado</span><span class="sxs-lookup"><span data-stu-id="c4ebf-241">Custom</span></span>|
|<span data-ttu-id="c4ebf-242">EventType</span><span class="sxs-lookup"><span data-stu-id="c4ebf-242">EventType</span></span>|<span data-ttu-id="c4ebf-243">Cadena</span><span class="sxs-lookup"><span data-stu-id="c4ebf-243">String</span></span>|<span data-ttu-id="c4ebf-244">Esta propiedad especifica la regla de retención que está asociada a la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-244">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="c4ebf-245">Puede usar cualquier valor que identifique de forma exclusiva la regla.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="c4ebf-246">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c4ebf-246">For example:</span></span></br><span data-ttu-id="c4ebf-247">Nombre</span><span class="sxs-lookup"><span data-stu-id="c4ebf-247">Name</span></span></br><span data-ttu-id="c4ebf-248">Nombre completo (DN)</span><span class="sxs-lookup"><span data-stu-id="c4ebf-248">Distinguished name (DN)</span></span></br><span data-ttu-id="c4ebf-249">GUID</span><span class="sxs-lookup"><span data-stu-id="c4ebf-249">GUID</span></span> </br><span data-ttu-id="c4ebf-250">Puede usar el cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/es-ES/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) para ver las reglas de retención disponibles.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-250">You can use the [Get-DataEncryptionPolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available policies.</span></span>|

![Plantilla del plan de archivos con información rellenada](media/file-plan-filled-out-template.png)

<span data-ttu-id="c4ebf-252">Cargue la plantilla rellenada y el administrador del plan de archivos validará las entradas y mostrará las estadísticas de importación.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Estadísticas de importación del plan de archivos](media/file-plan-import-statistics.png)

<span data-ttu-id="c4ebf-254">En caso de que se produzca un error de validación, la importación del plan de archivo seguirá validando todas las entradas del archivo de importación y mostrará todos los errores que hacen referencia a los números de línea/fila en el archivo de importación. Copie los resultados de error mostrados para que pueda volver fácilmente al archivo de importación y corregir los errores.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="c4ebf-255">Una vez completada la importación, vuelva al administrador del plan de archivos para asociar las nuevas etiquetas de retención a las directivas de etiquetas de retención nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="c4ebf-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opción para publicar etiquetas](media/file-plan-publish-labels-option.png)


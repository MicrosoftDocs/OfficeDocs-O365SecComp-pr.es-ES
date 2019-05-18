---
title: Notas de la versión de Microsoft Compliance Manager
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: f01e70b7852e6421c7c77dbe5ed4b6ca2aa395b2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152072"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="469ae-104">Notas de la versión del administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="469ae-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="469ae-105">La versión preliminar pública del administrador de cumplimiento le proporciona acceso anticipado a las actualizaciones y funciones futuras.</span><span class="sxs-lookup"><span data-stu-id="469ae-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="469ae-106">Puede usar la herramienta actualizada del [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) en el portal de confianza de [servicios](https://servicetrust.microsoft.com) para realizar un seguimiento, asignar y comprobar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="469ae-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="469ae-107">Novedades del administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="469ae-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="469ae-108">**Integración con la puntuación segura de Microsoft:** El administrador de cumplimiento admite la integración con la [puntuación segura de Microsoft](microsoft-secure-score.md) mediante la asignación de acciones administradas por el cliente a más de 50 acciones de calificación seguras.</span><span class="sxs-lookup"><span data-stu-id="469ae-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="469ae-109">Al completar una acción asignada en calificación segura, la acción correspondiente del administrador de cumplimiento se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="469ae-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="469ae-110">**Importar evaluaciones personalizadas:** Además de las evaluaciones integradas, el administrador de cumplimiento ahora admite la importación de plantillas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="469ae-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="469ae-111">Puede crear evaluaciones personalizadas para cualquier producto o servicio y cualquier normativa o estándar.</span><span class="sxs-lookup"><span data-stu-id="469ae-111">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="469ae-112">**Elementos de acciones:** Los elementos de acción son ahora elementos individuales y muchos incluyen la colección de telemetría de la API de Microsoft Secure score Graph.</span><span class="sxs-lookup"><span data-stu-id="469ae-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="469ae-113">Siempre que sea posible, las recomendaciones de acciones técnicas ahora tienen vínculos a la página de configuración correspondiente en el servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="469ae-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="469ae-114">**Administración de inquilinos:** Nueva interfaz para la administración de elementos de datos nuevos en el administrador de cumplimiento (versión preliminar):</span><span class="sxs-lookup"><span data-stu-id="469ae-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="469ae-115">**Dimensiones:** Permite ver, agregar y personalizar metadatos para plantillas, evaluaciones y elementos de acción que permiten crear tablas dinámicas personalizadas para los filtros.</span><span class="sxs-lookup"><span data-stu-id="469ae-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="469ae-116">**Propietarios:** Especifique un propietario para cada elemento de acción.</span><span class="sxs-lookup"><span data-stu-id="469ae-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="469ae-117">**Acciones del cliente:** Administrar la lista completa de elementos de acciones incluidos en el administrador de cumplimiento (versión preliminar) y habilitar o deshabilitar la supervisión de la puntuación segura para los elementos de acción integrados con calificación segura.</span><span class="sxs-lookup"><span data-stu-id="469ae-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="469ae-118">**Puntuación de cumplimiento actualizada**: la metodología ha cambiado para admitir la sincronización con calificación segura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="469ae-118">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="469ae-119">El sistema de puntuación quita los créditos de los controles administrados por Microsoft y se centra únicamente en la finalización de los controles administrados por el cliente.</span><span class="sxs-lookup"><span data-stu-id="469ae-119">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="469ae-120">Problemas conocidos en el administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="469ae-120">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="469ae-121">En las siguientes secciones se abordan los problemas conocidos que deben resolverse en próximas versiones del administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="469ae-121">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="469ae-122">Puntuación de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="469ae-122">Compliance Score</span></span>

- <span data-ttu-id="469ae-123">Para los elementos de acción marcados como **no en el ámbito**, la puntuación asignada al elemento de acción no se excluye del cálculo de puntuación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="469ae-123">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="469ae-124">Los elementos de acción marcados **sin ámbito** no aumentan la puntuación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="469ae-124">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="469ae-125">Puntuación segura</span><span class="sxs-lookup"><span data-stu-id="469ae-125">Secure Score</span></span>

- <span data-ttu-id="469ae-126">Los resultados de la puntuación segura no están disponibles para algunos elementos de acciones en determinadas suscripciones de Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="469ae-126">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="469ae-127">El resultado de la puntuación segura es "no se pudo detectar" en estos casos.</span><span class="sxs-lookup"><span data-stu-id="469ae-127">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="469ae-128">A veces, se devuelven resultados de puntuación seguros para las directivas y los elementos de acción correspondientes no completados.</span><span class="sxs-lookup"><span data-stu-id="469ae-128">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="469ae-129">Controles administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="469ae-129">Microsoft-managed Controls</span></span>

- <span data-ttu-id="469ae-130">La fecha de prueba de los controles administrados por Microsoft no aparece en la interfaz de usuario, incluso cuando se incluye en la evaluación.</span><span class="sxs-lookup"><span data-stu-id="469ae-130">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="469ae-131">Para ver la información de fecha de prueba, debe exportar la evaluación.</span><span class="sxs-lookup"><span data-stu-id="469ae-131">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="469ae-132">Personalización</span><span class="sxs-lookup"><span data-stu-id="469ae-132">Customization</span></span>

- <span data-ttu-id="469ae-133">Agregar controles personalizados permite agregar un control nuevo a una familia de controles existente, pero no permite agregar una nueva familia de controles.</span><span class="sxs-lookup"><span data-stu-id="469ae-133">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="469ae-134">Esta versión no admite la vinculación de elementos de acción ni la adición de elementos o controles de acciones a una evaluación.</span><span class="sxs-lookup"><span data-stu-id="469ae-134">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="469ae-135">Si crea una acción personalizada, no podrá editarla ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="469ae-135">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="469ae-136">Familias de control que no se muestran en las evaluaciones</span><span class="sxs-lookup"><span data-stu-id="469ae-136">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="469ae-137">Al importar una plantilla, todas las evaluaciones basadas en dicha plantilla reflejan todas las familias de controles que forman parte de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="469ae-137">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="469ae-138">Pero si agrega nuevas familias de controles a la plantilla, las evaluaciones existentes no reflejarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="469ae-138">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="469ae-139">Solo las nuevas evaluaciones creadas a partir de la plantilla actualizada reflejan los cambios.</span><span class="sxs-lookup"><span data-stu-id="469ae-139">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="469ae-140">Filtros</span><span class="sxs-lookup"><span data-stu-id="469ae-140">Filters</span></span>

- <span data-ttu-id="469ae-141">El filtrado de los elementos de acción o los controles no produce de forma coherente resultados correctos.</span><span class="sxs-lookup"><span data-stu-id="469ae-141">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="469ae-142">Plantillas</span><span class="sxs-lookup"><span data-stu-id="469ae-142">Templates</span></span>

- <span data-ttu-id="469ae-143">Las plantillas archivadas son editables y no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="469ae-143">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="469ae-144">Las plantillas bloqueadas permiten la creación de evaluaciones cuando no deberían.</span><span class="sxs-lookup"><span data-stu-id="469ae-144">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="469ae-145">Bloquear una plantilla tiene como objetivo evitar que se use para crear evaluaciones.</span><span class="sxs-lookup"><span data-stu-id="469ae-145">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="469ae-146">Exportar</span><span class="sxs-lookup"><span data-stu-id="469ae-146">Export</span></span>

- <span data-ttu-id="469ae-147">Se produce un error en la exportación de plantillas a JSON cuando \*\*\*\* el estado de la plantilla está establecido en importado o **pendiente de aprobación**.</span><span class="sxs-lookup"><span data-stu-id="469ae-147">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="469ae-148">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="469ae-148">Supported browsers</span></span>

- <span data-ttu-id="469ae-149">Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.</span><span class="sxs-lookup"><span data-stu-id="469ae-149">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="469ae-150">Puede haber casos en los que los datos actualizados no aparezcan hasta que se actualice el explorador.</span><span class="sxs-lookup"><span data-stu-id="469ae-150">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="469ae-151">La versión preliminar de Microsoft Edge no es compatible, pero no tiene problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="469ae-151">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="469ae-152">Internet Explorer no es compatible.</span><span class="sxs-lookup"><span data-stu-id="469ae-152">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="469ae-153">Tiempo de espera de sesión</span><span class="sxs-lookup"><span data-stu-id="469ae-153">Session timeout</span></span>

- <span data-ttu-id="469ae-154">Cuando se agota el tiempo de espera de una sesión, puede aparecer un error "se ha producido un problema".</span><span class="sxs-lookup"><span data-stu-id="469ae-154">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="469ae-155">Para solucionarlo, vaya al [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) e inicie sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="469ae-155">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="469ae-156">Compatibilidad con idiomas</span><span class="sxs-lookup"><span data-stu-id="469ae-156">Language support</span></span>

- <span data-ttu-id="469ae-157">No todos los idiomas son compatibles con todas las páginas Web.</span><span class="sxs-lookup"><span data-stu-id="469ae-157">All languages are not supported for all webpages.</span></span> <span data-ttu-id="469ae-158">Si el idioma local no es compatible, consulte en inglés (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="469ae-158">If your local language is unsupported, view in US English.</span></span>
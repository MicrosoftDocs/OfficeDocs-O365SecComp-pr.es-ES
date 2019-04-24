---
title: Notas de la versión para eDiscovery avanzado (versión preliminar)
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
description: Este artículo contiene las notas de la versión para eDiscovery avanzado (versión preliminar).
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240945"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a><span data-ttu-id="7fdd9-103">Notas de la versión para eDiscovery avanzado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="7fdd9-103">Release notes for Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="7fdd9-104">El programa de vista previa pública para eDiscovery avanzado es la forma de obtener acceso anticipado a la próxima funcionalidad y actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="7fdd9-105">Para obtener acceso anticipado a las características más recientes, simplemente cree y use un caso de exhibición avanzada de documentos electrónicos (versión preliminar) en el centro de seguridad & cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-105">To get early access to the newest features, just create and use an Advanced eDiscovery (Preview) case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="7fdd9-106">Consulte [Create a New Case](create-new-ediscovery-case.md).</span><span class="sxs-lookup"><span data-stu-id="7fdd9-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="7fdd9-107">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="7fdd9-107">Known issues</span></span>

<span data-ttu-id="7fdd9-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="7fdd9-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="7fdd9-109">Los datos correspondientes a un formulario creado antes del 31 de enero de 2019 no se podrán buscar al usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos (versión preliminar) para buscar buzones de custodios.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="7fdd9-110">Los formularios creados después de esta fecha estarán disponibles para su búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="7fdd9-111">Un formulario creado por un usuario puede seguir recibiendo respuestas incluso después de que se elimine el usuario que creó el formulario.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="7fdd9-112">Sin embargo, los datos correspondientes para las respuestas (que se produjeron después de que se eliminó el buzón de custodio) no se podrán buscar cuando se use la herramienta de búsqueda en eDiscovery avanzado (versión preliminar) para buscar buzones de correo de custodios.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span>
 
<span data-ttu-id="7fdd9-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="7fdd9-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="7fdd9-114">Si un usuario edita un Sway justo antes de eliminar la cuenta de usuario para el propietario de ese Sway, es posible que los cambios no se puedan buscar al usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos (versión preliminar) para buscar buzones de correo de custodios.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="7fdd9-115">Sway bloquea los cambios en un Sway tan pronto como recibe una señal de que la cuenta se eliminó.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="7fdd9-116">Sin embargo, hay una pequeña posibilidad de que se pueda editar un Sway antes de que se reciba esta señal.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="7fdd9-117">Problemas corregidos en esta versión</span><span class="sxs-lookup"><span data-stu-id="7fdd9-117">Issues fixed in this release</span></span>

- <span data-ttu-id="7fdd9-118">DCR: control de excepciones para elementos sin indexar y elementos huérfanos</span><span class="sxs-lookup"><span data-stu-id="7fdd9-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="7fdd9-119">DCR: mantener notificaciones</span><span class="sxs-lookup"><span data-stu-id="7fdd9-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="7fdd9-120">DCR: custodios en eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7fdd9-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="7fdd9-121">Novedades</span><span class="sxs-lookup"><span data-stu-id="7fdd9-121">What’s new</span></span>

- <span data-ttu-id="7fdd9-122">**La navegación rediseñada en el centro de seguridad _AMP_ cumplimiento del** -Advanced EDiscovery (versión preliminar) tiene un aspecto nuevo.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery (Preview) has a new look and feel.</span></span> <span data-ttu-id="7fdd9-123">Use la exhibición avanzada de documentos electrónicos (versión preliminar) para administrar más el flujo de trabajo de casos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-123">Use Advanced eDiscovery (Preview) to manage more of your case workflow.</span></span>

- <span data-ttu-id="7fdd9-124">**Administración de casos** : hay compatibilidad adicional para nuevos tipos de casos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="7fdd9-125">También puede seleccionar y guardar sus casos de reciente y favoritos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="7fdd9-126">Seguimiento y supervisión de la actividad en y a través de los casos con nuevos paneles.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="7fdd9-127">**Administración** de custodios – agregue y elimine usuarios como custodios de datos en un caso.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="7fdd9-128">**Integración de Exchange, onedrive y Teams** : agregue automáticamente el buzón actual de un usuario, la cuenta de onedrive para la empresa y los sitios de Microsoft Teams a un caso.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="7fdd9-129">**Comunicaciones** de custodios: Envíe y administre notificaciones de retención legal en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="7fdd9-130">**Portal de custodia** : nuevo portal para los custodios para acceder a sus avisos de espera activos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="7fdd9-131">**IndizaCión profunda** : vuelva a rastrear los elementos indexados parcialmente a petición.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="7fdd9-132">**Corrección** de errores: corregir o descargar errores de procesamiento; Esto incluye compatibilidad con la corrección para tipos de archivo grandes, archivos protegidos con contraseña y mucho más.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="7fdd9-133">**Mejoras en la búsqueda** : cree una búsqueda identificando los custodios o las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="7fdd9-134">**Conjuntos de trabajo** : administre, realice un seguimiento y audite conjuntos de documentos estáticos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-134">**Working sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="7fdd9-135">**Revisión** : Use una vista nativa, de texto y casi nativa para revisar los documentos agregados al conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-135">**Review** – Use a native, text, and near-native view to review documents added to your working set.</span></span>

- <span data-ttu-id="7fdd9-136">**Censurar, etiquetar y anotar** : censurar texto, aplicar etiquetas y crear anotaciones mientras revisa documentos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="7fdd9-137">**Revisión con tecnología de análisis**: aproveche el análisis de eDiscovery para buscar, buscar y deshacer resultados en un conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-137">**Analytics-powered review**– Leverage eDiscovery analytics to find, search, and cull results within a working set.</span></span>

- <span data-ttu-id="7fdd9-138">**Trabajos** : seguimiento del estado de los procesos de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="7fdd9-139">**Nuevas actividades de auditoría** : realizar un seguimiento y ver una nueva actividad de auditoría para la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="7fdd9-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>

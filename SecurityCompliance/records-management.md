---
title: Administración de registros en Microsoft 365
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
description: Con la administración de registros de Microsoft 365, puede aplicar las programaciones de retención específicas de su organización en un plan de archivos para administrar la retención, la declaración de registros y la eliminación para dar soporte al ciclo de vida completo del contenido.
ms.openlocfilehash: 7e7167cdc37c37cf785eb2a248c8610661ba7f5c
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547895"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="e0256-103">Administración de registros en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0256-103">Records management in Microsoft 365</span></span>

<span data-ttu-id="e0256-104">Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="e0256-104">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="e0256-105">La administración de registros de Microsoft 365 ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no es necesario retener, que no son de gran valor o que ya no son necesarios para fines empresariales.</span><span class="sxs-lookup"><span data-stu-id="e0256-105">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="e0256-106">La solución de administración de registros es compatible con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e0256-106">The records-management solution supports the following elements:</span></span>

-   <span data-ttu-id="e0256-107">**Migrar y administrar su plan de retención con el plan de archivos** y usar el [administrador del plan de archivos](file-plan-manager.md) para incorporar su plan de retención existente, o crear uno nuevo con los descriptores de archivo y las jerarquías de expansión.</span><span class="sxs-lookup"><span data-stu-id="e0256-107">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

-   <span data-ttu-id="e0256-108">**Establecer directivas de retención y eliminación en la etiqueta de registro**.</span><span class="sxs-lookup"><span data-stu-id="e0256-108">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="e0256-109">Defina períodos de [retención](retention-policies.md#retaining-content-for-a-specific-period-of-time) y [eliminación](retention-policies.md#deleting-content-thats-older-than-a-specific-age) en función de una serie de factores, como la fecha de la última modificación o creación.</span><span class="sxs-lookup"><span data-stu-id="e0256-109">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on a variety of factors including the date last modified or created.</span></span>

-   <span data-ttu-id="e0256-110">**Activar retención basada en eventos** con [retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="e0256-110">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

-   <span data-ttu-id="e0256-111">**Etiquetar como un registro**.</span><span class="sxs-lookup"><span data-stu-id="e0256-111">**Label as a record**.</span></span> <span data-ttu-id="e0256-112">Publique [etiquetas de registro](labels.md#using-retention-labels-for-records-management) para ser aplicadas por los usuarios finales o [aplique automáticamente etiquetas de registro](labels.md#applying-a-retention-label-automatically-based-on-conditions) a elementos que contengan información confidencial, palabras clave o tipos de contenido específicos.</span><span class="sxs-lookup"><span data-stu-id="e0256-112">Publish [record labels](labels.md#using-retention-labels-for-records-management) to be applied by end users, or [auto-apply record labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to items containing specific sensitive information, keywords or content types.</span></span>

-   <span data-ttu-id="e0256-113">**Revisar y validar la eliminación** con [la revisión de eliminación](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="e0256-113">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

-   <span data-ttu-id="e0256-114">**Revisar elementos eliminados con la revisión de eliminaciones** y [exportar un informe de eliminación](disposition-reviews.md#export-the-disposition-items) para mayor validación y creación de informes.</span><span class="sxs-lookup"><span data-stu-id="e0256-114">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

-   <span data-ttu-id="e0256-115">**Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e0256-115">**Set specific permissions** for records manager functions in your organization to [have the right access](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="e0256-116">Con la solución de administración de registros de Microsoft 365, puede incorporar las programaciones de retención de su organización en el plan de archivos para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.</span><span class="sxs-lookup"><span data-stu-id="e0256-116">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span> 

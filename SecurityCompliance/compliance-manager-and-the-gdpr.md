---
title: Administrador de cumplimiento de Microsoft y el RGPD
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: af0efa2711215946930c091fc7c38cc1b9f575fd
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786655"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="53822-104">Administrador de cumplimiento de Microsoft y el RGPD</span><span class="sxs-lookup"><span data-stu-id="53822-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="53822-105">El Reglamento General de protección de datos (RGPD) aprobado por la Unión Europea puede afectar a su estrategia de cumplimiento y exigir acciones específicas para administrar la información de usuarios y clientes que se usa en el administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="53822-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="53822-106">Configuración de privacidad del usuario</span><span class="sxs-lookup"><span data-stu-id="53822-106">User Privacy settings</span></span>

<span data-ttu-id="53822-107">Algunas reglamentaciones requieren que una organización tenga que eliminar datos del historial del usuario.</span><span class="sxs-lookup"><span data-stu-id="53822-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="53822-108">El administrador de cumplimiento proporciona funciones de **configuración de privacidad del usuario** que permiten a los administradores:</span><span class="sxs-lookup"><span data-stu-id="53822-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="53822-109">Buscar un usuario</span><span class="sxs-lookup"><span data-stu-id="53822-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="53822-110">Exportar un informe de historial de datos de cuenta</span><span class="sxs-lookup"><span data-stu-id="53822-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="53822-111">Eliminar el historial de datos de usuarios</span><span class="sxs-lookup"><span data-stu-id="53822-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="53822-112">Buscar un usuario</span><span class="sxs-lookup"><span data-stu-id="53822-112">Search for a user</span></span>

<span data-ttu-id="53822-113">Para buscar una cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="53822-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="53822-114">Escriba el alias de correo electrónico del usuario (la información a la izquierda del símbolo @) y elija el nombre del dominio en la lista de sufijos de dominio de la derecha.</span><span class="sxs-lookup"><span data-stu-id="53822-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="53822-115">En el caso de organizaciones con varios dominios registrados, compruebe el sufijo de nombre de dominio para asegurarse de que es correcto.</span><span class="sxs-lookup"><span data-stu-id="53822-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="53822-116">Cuando se haya escrito correctamente el nombre de usuario, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="53822-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="53822-117">Para las cuentas de usuario que no se devuelven, se muestra "usuario no encontrado" en la página.</span><span class="sxs-lookup"><span data-stu-id="53822-117">For user accounts not returned, 'User not found' is displayed on the page.</span></span> <span data-ttu-id="53822-118">Compruebe la información de la dirección de correo del usuario y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="53822-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="53822-119">Para volver a intentarlo, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="53822-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="53822-120">Para las cuentas de usuario devueltas, el texto del botón cambia de **búsqueda** a **borrado**.</span><span class="sxs-lookup"><span data-stu-id="53822-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="53822-121">Esto indica que la cuenta de usuario devuelta es el contexto operativo de las funciones adicionales y que estas funciones se aplican a esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="53822-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="53822-122">Para borrar los resultados de la búsqueda y buscar a otro usuario, seleccione **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="53822-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="53822-123">Exportar un informe de historial de datos de cuenta</span><span class="sxs-lookup"><span data-stu-id="53822-123">Export a report of account data history</span></span>

<span data-ttu-id="53822-124">Para cada cuenta de usuario identificada, puede generar un informe de dependencias vinculadas a esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="53822-124">For each user account identified, you can generate a report of dependencies linked to this account.</span></span> <span data-ttu-id="53822-125">Esta información le permite reasignar elementos de acción abiertos o garantizar el acceso a pruebas cargadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="53822-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="53822-126">Para generar y exportar un informe:</span><span class="sxs-lookup"><span data-stu-id="53822-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="53822-127">Seleccione **exportar** para generar y descargar un informe de los elementos de acción de control del administrador de cumplimiento asignados actualmente a la cuenta de usuario devuelta y la lista de documentos cargados por dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="53822-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="53822-128">Si no hay ninguna acción asignada o documentos cargados, un mensaje de error indica "no hay datos para este usuario".</span><span class="sxs-lookup"><span data-stu-id="53822-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="53822-129">El informe se descarga en segundo plano en la ventana del explorador activa si no ve un elemento emergente de descarga que desea comprobar el historial de descargas del explorador.</span><span class="sxs-lookup"><span data-stu-id="53822-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="53822-130">Abra el documento para revisar los datos del informe.</span><span class="sxs-lookup"><span data-stu-id="53822-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53822-131">Los datos del informe no son una lista histórica que conserva y muestra los cambios de estado en el historial de asignación de elementos de acción.</span><span class="sxs-lookup"><span data-stu-id="53822-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="53822-132">El informe generado es una instantánea de los elementos de acción de control asignados en el momento en que se ejecuta el informe (fecha y marca de tiempo escrita en el informe).</span><span class="sxs-lookup"><span data-stu-id="53822-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="53822-133">Por ejemplo, cualquier reasignación posterior de los elementos de acción producirá diferentes datos del informe de instantáneas si el informe se genera de nuevo para el mismo usuario.</span><span class="sxs-lookup"><span data-stu-id="53822-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="53822-134">Eliminar el historial de datos de usuarios</span><span class="sxs-lookup"><span data-stu-id="53822-134">Delete user data history</span></span>

<span data-ttu-id="53822-135">Establece todos los elementos de acción de control asignados al usuario devuelto en "sin asignar".</span><span class="sxs-lookup"><span data-stu-id="53822-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="53822-136">Establece el valor **cargado por** en todos los documentos cargados por el usuario devuelto en ' usuario quitado '.</span><span class="sxs-lookup"><span data-stu-id="53822-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="53822-137">Para eliminar el elemento de acción de la cuenta de usuario y el historial de carga de documentos:</span><span class="sxs-lookup"><span data-stu-id="53822-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="53822-138">Seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="53822-138">Select **Delete**.</span></span>

    <span data-ttu-id="53822-139">Se muestra un cuadro de diálogo de confirmación, "*esto quita todas las asignaciones de elementos de acción de control y el historial de carga de documentos para el usuario seleccionado. Esta acción es permanente. ¿Está seguro de que desea continuar?*"</span><span class="sxs-lookup"><span data-stu-id="53822-139">A confirmation dialog is displayed, "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="53822-140">Para continuar, seleccione **Aceptar**; en caso contrario, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="53822-140">To continue select **OK**, otherwise select **Cancel**.</span></span>

---
title: 'Ejecutar un informe de grupo de roles de administrador en EOP '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Los administradores pueden aprender a ejecutar un informe de grupo de roles de administrador en Exchange Online Protection (EOP). Este informe registra cuando un administrador agrega o quita miembros de grupos de roles de administrador, Microsoft Exchange Online Protection (EOP) registra cada ocurrencia.
ms.openlocfilehash: 6973574ca1eeabee85dd57bd087ba5d0675da084
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676523"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="2f2c2-104">Ejecutar un informe de grupo de roles de administrador en EOP</span><span class="sxs-lookup"><span data-stu-id="2f2c2-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="2f2c2-105">Cuando un administrador agrega o quita miembros de grupos de roles de administrador, Exchange Online Protection (EOP) registra cada ocurrencia.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="2f2c2-106">Al ejecutar un informe de grupo de roles de administrador en el centro de administración de Exchange (EAC), las entradas se muestran como resultados de búsqueda e incluyen los grupos de funciones afectados, quién cambió la pertenencia al grupo de roles y cuándo se realizaron las actualizaciones de pertenencia.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="2f2c2-107">Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f2c2-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="2f2c2-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f2c2-109">Tiempo estimado para finalizar: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="2f2c2-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="2f2c2-110">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2f2c2-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2f2c2-p103">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Sección "Informes" del tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="2f2c2-113">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="2f2c2-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="2f2c2-114">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="2f2c2-114">Having problems?</span></span> <span data-ttu-id="2f2c2-115">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="2f2c2-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="2f2c2-116">Usar el EAC para ejecutar un informe de grupo de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="2f2c2-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="2f2c2-117">Ejecute el informe de grupo de roles de administrador para buscar los cambios en los grupos de roles de administración de la organización dentro de un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>
  
1. <span data-ttu-id="2f2c2-118">En el EAC, vaya a **Administración de cumplimiento** \> **Auditoría** y haga clic en **Ejecutar un informe de grupo de roles de administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="2f2c2-p105">Elija la **Fecha de inicio** y la **Fecha de finalización**. De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p105">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="2f2c2-p106">Para ver los cambios de un determinado grupo de roles, haga clic en **Seleccionar grupos de roles**. Seleccione el grupo o los grupos de roles en el siguiente cuadro de diálogo y haga clic en **Aceptar**. También puede dejar el campo en blanco para buscar todos los grupos de roles cambiados.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p106">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="2f2c2-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-124">Click **Search**.</span></span>

<span data-ttu-id="2f2c2-p107">Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2f2c2-127">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="2f2c2-127">How do you know this worked?</span></span>

<span data-ttu-id="2f2c2-p108">Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="2f2c2-131">Supervisión de cambios en la pertenencia a grupos de funciones</span><span class="sxs-lookup"><span data-stu-id="2f2c2-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="2f2c2-p109">Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="2f2c2-p110">Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**:</span><span class="sxs-lookup"><span data-stu-id="2f2c2-p110">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>
  
> <span data-ttu-id="2f2c2-136">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="2f2c2-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="2f2c2-137">Administrador</span><span class="sxs-lookup"><span data-stu-id="2f2c2-137">Administrator</span></span> <br> <span data-ttu-id="2f2c2-138">Miembros actualizados: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="2f2c2-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="2f2c2-139">2/06/2018 10:09 A.M.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="2f2c2-140">Administrador</span><span class="sxs-lookup"><span data-stu-id="2f2c2-140">Administrator</span></span> <br> <span data-ttu-id="2f2c2-141">Miembros actualizados: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="2f2c2-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="2f2c2-142">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="2f2c2-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="2f2c2-143">Administrador</span><span class="sxs-lookup"><span data-stu-id="2f2c2-143">Administrator</span></span> <br> <span data-ttu-id="2f2c2-144">Miembros actualizados: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="2f2c2-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="2f2c2-145">En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="2f2c2-145">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="2f2c2-146">El 2/06/2018 agrega el usuario tonip.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="2f2c2-147">El 2/19/2018, eliminó el usuario pilarp.</span><span class="sxs-lookup"><span data-stu-id="2f2c2-147">On 2/19/2018, they removed the user pilarp.</span></span>

---
title: Editar o quitar directivas de barrera de información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Obtenga información sobre cómo editar o quitar directivas para las barreras de información.
ms.openlocfilehash: e6bed4df2329d426f86bd4cde07bdc7d1a2792cd
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35215653"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a><span data-ttu-id="b5a89-103">Editar o quitar directivas de barrera de información (vista previa)</span><span class="sxs-lookup"><span data-stu-id="b5a89-103">Edit or remove information barrier policies (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="b5a89-104">Información general</span><span class="sxs-lookup"><span data-stu-id="b5a89-104">Overview</span></span>

<span data-ttu-id="b5a89-105">Una vez que haya [definido las directivas de barrera de información](information-barriers-policies.md), es posible que deba realizar cambios en dichas directivas o en sus segmentos de usuario, como parte de la solución de [problemas](information-barriers-troubleshooting.md) o del mantenimiento regular.</span><span class="sxs-lookup"><span data-stu-id="b5a89-105">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="b5a89-106">Use este artículo como guía.</span><span class="sxs-lookup"><span data-stu-id="b5a89-106">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5a89-107">Para llevar a cabo las tareas descritas en este artículo, debe tener asignada una función adecuada, como una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5a89-107">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="b5a89-108">-Administrador global de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b5a89-108">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="b5a89-109">-Office 365 administrador global</span><span class="sxs-lookup"><span data-stu-id="b5a89-109">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="b5a89-110">-Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5a89-110">- Compliance Administrator</span></span><br/><span data-ttu-id="b5a89-111">-IB Compliance Management (este es un nuevo rol).</span><span class="sxs-lookup"><span data-stu-id="b5a89-111">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="b5a89-112">Para obtener más información sobre los requisitos previos para las barreras de información, vea [requisitos previos (para las directivas de barrera de información)](information-barriers-policies.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="b5a89-112">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="b5a89-113">Asegúrese de [conectarse a PowerShell del centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="b5a89-113">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="b5a89-114">Editar atributos de cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="b5a89-114">Edit user account attributes</span></span>

<span data-ttu-id="b5a89-115">Use este procedimiento para editar los atributos que se usan para segmentar usuarios.</span><span class="sxs-lookup"><span data-stu-id="b5a89-115">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="b5a89-116">Por ejemplo, si está usando un atributo de departamento y una o más cuentas de usuario no tienen actualmente ningún valor en la lista de departamento, debe editar esas cuentas de usuario para incluir la información del Departamento.</span><span class="sxs-lookup"><span data-stu-id="b5a89-116">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="b5a89-117">Los atributos de cuenta de usuario se usan para definir segmentos para que se puedan asignar directivas de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="b5a89-117">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="b5a89-118">Para ver los detalles de una cuenta de usuario específica, como los valores de atributo y los segmentos asignados, use el cmdlet **Get-InformationBarrierRecipientStatus** con parámetros Identity.</span><span class="sxs-lookup"><span data-stu-id="b5a89-118">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

   <span data-ttu-id="b5a89-119">Consta`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="b5a89-119">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 
    
   <span data-ttu-id="b5a89-120">Puede usar cualquier valor que identifique de forma exclusiva a cada usuario, como el nombre, el alias, el nombre distintivo, el nombre de dominio canónico, la dirección de correo electrónico o el GUID.</span><span class="sxs-lookup"><span data-stu-id="b5a89-120">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 
    
   <span data-ttu-id="b5a89-121">Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="b5a89-121">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 
    
   <span data-ttu-id="b5a89-122">En este ejemplo, se hace referencia a dos cuentas de usuario en Office 365: *meganb* para *Nuria*y *alexw* para *Alex*.</span><span class="sxs-lookup"><span data-stu-id="b5a89-122">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 
    
   <span data-ttu-id="b5a89-123">(También puede usar este cmdlet para un solo usuario: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="b5a89-123">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> 
    
2. <span data-ttu-id="b5a89-124">Determine qué atributo desea editar para los perfiles de cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="b5a89-124">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="b5a89-125">Consulte [atributos para las directivas de barrera de información (vista previa)](information-barriers-attributes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b5a89-125">Refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="b5a89-126">Edite una o más cuentas de usuario para incluir valores para el atributo que seleccionó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b5a89-126">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="b5a89-127">Para ello, use uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5a89-127">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="b5a89-128">Para editar una sola cuenta, vea [Agregar o actualizar la información de Perfil de un usuario con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="b5a89-128">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="b5a89-129">Para editar varias cuentas (o usar PowerShell para editar una sola cuenta), vea [Configure User Account Properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5a89-129">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="b5a89-130">Edición de un segmento</span><span class="sxs-lookup"><span data-stu-id="b5a89-130">Edit a segment</span></span>

<span data-ttu-id="b5a89-131">Use este procedimiento para editar la definición de un segmento de usuario.</span><span class="sxs-lookup"><span data-stu-id="b5a89-131">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="b5a89-132">Por ejemplo, puede cambiar el nombre de un segmento o el filtro que se usa para determinar quién está incluido en el segmento.</span><span class="sxs-lookup"><span data-stu-id="b5a89-132">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="b5a89-133">Para ver todos los segmentos existentes, use el cmdlet **Get-OrganizationSegment** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-133">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="b5a89-134">Consta`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="b5a89-134">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="b5a89-135">Verá una lista de segmentos y detalles para cada uno, como tipo de segmento, su valor UserGroupFilter, que lo creó o modificó por última vez, GUID, etc.</span><span class="sxs-lookup"><span data-stu-id="b5a89-135">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="b5a89-136">Imprime o guarda la lista de segmentos para hacer referencia a ellos más adelante.</span><span class="sxs-lookup"><span data-stu-id="b5a89-136">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="b5a89-137">Por ejemplo, si desea editar un segmento, necesitará conocer su nombre o identificar el valor (que se usa con el parámetro Identity).</span><span class="sxs-lookup"><span data-stu-id="b5a89-137">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="b5a89-138">Para editar un segmento, use el cmdlet **set-OrganizationSegment** con el parámetro **Identity** y los detalles pertinentes.</span><span class="sxs-lookup"><span data-stu-id="b5a89-138">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="b5a89-139">Consta`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="b5a89-139">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="b5a89-140">Ejemplo: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="b5a89-140">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="b5a89-141">En este ejemplo, para el segmento que tiene el GUID *c96e0837-c232-4a8a-841E-ef45787d8fcd*, se actualizó el nombre del Departamento a "HRDept".</span><span class="sxs-lookup"><span data-stu-id="b5a89-141">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="b5a89-142">Una vez finalizada la edición de segmentos de la organización, puede [definir](information-barriers-policies.md#part-2-define-information-barrier-policies) o [Editar](#edit-a-policy) las directivas de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="b5a89-142">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="b5a89-143">Editar una directiva</span><span class="sxs-lookup"><span data-stu-id="b5a89-143">Edit a policy</span></span>

1. <span data-ttu-id="b5a89-144">Para ver una lista de las directivas de barrera de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-144">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="b5a89-145">Consta`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="b5a89-145">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="b5a89-146">En la lista de resultados, identifique la Directiva que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="b5a89-146">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="b5a89-147">Anote el GUID y el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b5a89-147">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="b5a89-148">Use el cmdlet **set-InformationBarrierPolicy** con un parámetro **Identity** y especifique los cambios que desea realizar.</span><span class="sxs-lookup"><span data-stu-id="b5a89-148">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="b5a89-149">Ejemplo: Supongamos que se ha definido una directiva para bloquear el segmento de *investigación* para que no pueda comunicarse con los segmentos de *ventas* y *marketing* .</span><span class="sxs-lookup"><span data-stu-id="b5a89-149">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="b5a89-150">La Directiva se definió mediante este cmdlet:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="b5a89-150">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="b5a89-151">Supongamos que queremos cambiarla para que las personas del segmento de *investigación* solo puedan comunicarse con los usuarios del segmento de *recursos humanos* .</span><span class="sxs-lookup"><span data-stu-id="b5a89-151">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="b5a89-152">Para realizar este cambio, usamos este cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="b5a89-152">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="b5a89-153">En este ejemplo, hemos cambiado "SegmentsBlocked" por "SegmentsAllowed" y hemos especificado el segmento de *recursos humanos* .</span><span class="sxs-lookup"><span data-stu-id="b5a89-153">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="b5a89-154">Cuando termine de editar una directiva, asegúrese de aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b5a89-154">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="b5a89-155">(Consulte [aplicar directivas de barrera de información](information-barriers-policies.md#part-3-apply-information-barrier-policies)).</span><span class="sxs-lookup"><span data-stu-id="b5a89-155">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="b5a89-156">Definir un estado inactivo de una directiva</span><span class="sxs-lookup"><span data-stu-id="b5a89-156">Set a policy to inactive status</span></span>

1. <span data-ttu-id="b5a89-157">Para ver una lista de las directivas de barrera de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-157">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="b5a89-158">Consta`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="b5a89-158">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="b5a89-159">En la lista de resultados, identifique la Directiva que desea cambiar (o quitar).</span><span class="sxs-lookup"><span data-stu-id="b5a89-159">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="b5a89-160">Anote el GUID y el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b5a89-160">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="b5a89-161">Para establecer el estado de la Directiva como inactivo, use el cmdlet **set-InformationBarrierPolicy** con un parámetro Identity y el parámetro State establecido en INACTIVE.</span><span class="sxs-lookup"><span data-stu-id="b5a89-161">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="b5a89-162">Consta`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="b5a89-162">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="b5a89-163">En este ejemplo, se establece una directiva de barrera de información que tiene un GUID *43c37853-ea10-4b90-a23d-ab8c9377247* en un estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="b5a89-163">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="b5a89-164">Para aplicar los cambios, use el cmdlet **Start-InformationBarrierPoliciesApplication** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-164">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="b5a89-165">Consta`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="b5a89-165">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="b5a89-166">Se aplican los cambios, usuario por usuario, para la organización.</span><span class="sxs-lookup"><span data-stu-id="b5a89-166">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="b5a89-167">Si su organización es grande, puede tardar 24 horas (o más) en completarse este proceso.</span><span class="sxs-lookup"><span data-stu-id="b5a89-167">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="b5a89-168">(Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000).</span><span class="sxs-lookup"><span data-stu-id="b5a89-168">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="b5a89-169">En este punto, se establecen una o varias directivas de barrera de información en estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="b5a89-169">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="b5a89-170">Desde aquí, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b5a89-170">From here, you can do any of the following:</span></span>
- <span data-ttu-id="b5a89-171">Mantenlo tal cual (el estado de una directiva establecida en inactivo no tiene efecto sobre los usuarios)</span><span class="sxs-lookup"><span data-stu-id="b5a89-171">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="b5a89-172">Editar una directiva</span><span class="sxs-lookup"><span data-stu-id="b5a89-172">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="b5a89-173">Quitar una directiva</span><span class="sxs-lookup"><span data-stu-id="b5a89-173">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="b5a89-174">Quitar una directiva</span><span class="sxs-lookup"><span data-stu-id="b5a89-174">Remove a policy</span></span>

1. <span data-ttu-id="b5a89-175">Para ver una lista de las directivas de barrera de información actuales, use el cmdlet **Get-InformationBarrierPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-175">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="b5a89-176">Consta`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="b5a89-176">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="b5a89-177">En la lista de resultados, identifique la Directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="b5a89-177">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="b5a89-178">Anote el GUID y el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="b5a89-178">Note the policy's GUID and name.</span></span> <span data-ttu-id="b5a89-179">Asegúrese de que la Directiva está establecida en estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="b5a89-179">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="b5a89-180">Use el cmdlet **Remove-InformationBarrierPolicy** con un parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="b5a89-180">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="b5a89-181">Consta`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="b5a89-181">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="b5a89-182">Ejemplo: Supongamos que queremos quitar una directiva que tenga GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span><span class="sxs-lookup"><span data-stu-id="b5a89-182">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="b5a89-183">Para ello, usamos este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5a89-183">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="b5a89-184">Cuando se le pida, confirme el cambio.</span><span class="sxs-lookup"><span data-stu-id="b5a89-184">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="b5a89-185">Repita los pasos 1-2 para cada directiva que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="b5a89-185">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="b5a89-186">Cuando haya terminado de quitar directivas, aplique los cambios.</span><span class="sxs-lookup"><span data-stu-id="b5a89-186">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="b5a89-187">Para ello, use el cmdlet **Start-InformationBarrierPoliciesApplication** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-187">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="b5a89-188">Consta`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="b5a89-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="b5a89-189">Se aplican los cambios, usuario por usuario, para la organización.</span><span class="sxs-lookup"><span data-stu-id="b5a89-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="b5a89-190">Si su organización es grande, puede tardar 24 horas (o más) en completarse este proceso.</span><span class="sxs-lookup"><span data-stu-id="b5a89-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="b5a89-191">Detención de una aplicación de Directiva</span><span class="sxs-lookup"><span data-stu-id="b5a89-191">Stop a policy application</span></span>

<span data-ttu-id="b5a89-192">Si, después de empezar a aplicar directivas de barrera de información, desea detener la aplicación de estas directivas, use el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b5a89-192">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="b5a89-193">Tenga en cuenta que el proceso tardará aproximadamente 30-35 minutos en comenzar.</span><span class="sxs-lookup"><span data-stu-id="b5a89-193">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="b5a89-194">Para ver el estado de la aplicación de directiva de barrera de información más reciente, use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="b5a89-194">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="b5a89-195">Consta`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="b5a89-195">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="b5a89-196">Anote el GUID de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b5a89-196">Note the application's GUID.</span></span>

2. <span data-ttu-id="b5a89-197">Use el cmdlet **Stop-InformationBarrierPoliciesApplication** con un parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="b5a89-197">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="b5a89-198">Consta`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="b5a89-198">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="b5a89-199">Ejemplo: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="b5a89-199">Example: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

    <span data-ttu-id="b5a89-200">En este ejemplo, estamos deteniendo que se apliquen las directivas de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="b5a89-200">In this example, we are stopping information barrier policies from being applied.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b5a89-201">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="b5a89-201">Related articles</span></span>

[<span data-ttu-id="b5a89-202">Obtener información general sobre las barreras de la información</span><span class="sxs-lookup"><span data-stu-id="b5a89-202">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="b5a89-203">Definir directivas para las barreras de información (vista previa)</span><span class="sxs-lookup"><span data-stu-id="b5a89-203">Define policies for information barriers (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="b5a89-204">Obtenga más información sobre las barreras de la información en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5a89-204">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="b5a89-205">Atributos de las directivas de barrera de información (vista previa)</span><span class="sxs-lookup"><span data-stu-id="b5a89-205">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="b5a89-206">Solución de problemas de las barreras de la información (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b5a89-206">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

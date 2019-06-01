---
title: Solución de problemas de obstáculos para la información
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use este artículo como guía para solucionar problemas con las barreras de la información.
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668341"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="8eb23-103">Solución de problemas de las barreras de la información (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="8eb23-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="8eb23-104">Las barreras de información pueden ayudar a su organización a permanecer conforme con los requisitos legales y las regulaciones del sector.</span><span class="sxs-lookup"><span data-stu-id="8eb23-104">Information barriers can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="8eb23-105">Por ejemplo, con barreras de información, puede restringir la comunicación entre grupos de usuarios específicos para evitar un conflicto de intereses u otros problemas.</span><span class="sxs-lookup"><span data-stu-id="8eb23-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="8eb23-106">Para obtener más información, consulte barreras de la [información (vista previa)](information-barriers.md).</span><span class="sxs-lookup"><span data-stu-id="8eb23-106">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span>

<span data-ttu-id="8eb23-107">En este artículo se proporcionan instrucciones que puede usar para obtener respuestas a preguntas o resolver problemas que pueden surgir debido a las barreras de la información.</span><span class="sxs-lookup"><span data-stu-id="8eb23-107">This article provides guidance you can use to get answers to questions or resolve issues that may arise with information barriers.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="8eb23-108">Antes de comenzar...</span><span class="sxs-lookup"><span data-stu-id="8eb23-108">Before you begin...</span></span>

<span data-ttu-id="8eb23-109">Para llevar a cabo las tareas descritas en este artículo, debe tener asignada una función adecuada, como una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8eb23-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="8eb23-110">Administrador global de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8eb23-110">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="8eb23-111">Administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="8eb23-111">Office 365 Global Administrator</span></span>
- <span data-ttu-id="8eb23-112">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="8eb23-112">Compliance Administrator</span></span>
- <span data-ttu-id="8eb23-113">IB Compliance Management (este es un nuevo rol)</span><span class="sxs-lookup"><span data-stu-id="8eb23-113">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="8eb23-114">Para obtener más información acerca de los roles y los permisos, consulte Permissions [in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8eb23-114">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="8eb23-115">Para obtener más información sobre los requisitos previos para las barreras de información, vea [requisitos previos (para las directivas de barrera de información)](information-barriers-policies.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="8eb23-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="8eb23-116">Además, asegúrese de [conectarse a PowerShell del centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="8eb23-116">Also, make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="8eb23-117">Problema: se impide que los usuarios se comuniquen de forma inesperada en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8eb23-117">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="8eb23-118">En este caso, los usuarios están notificando problemas inesperados que se comunican en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8eb23-118">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="8eb23-119">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="8eb23-119">Examples:</span></span>
- <span data-ttu-id="8eb23-120">Un usuario no puede encontrar o comunicarse con otro usuario en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8eb23-120">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="8eb23-121">Un usuario no puede ver ni seleccionar A otro usuario en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8eb23-121">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="8eb23-122">Un usuario puede ver, pero no puede enviar mensajes a otro usuario en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8eb23-122">A user can see, but cannot send messages to, another user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8eb23-123">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="8eb23-123">What to do</span></span>

1. <span data-ttu-id="8eb23-124">Determinar si los usuarios están afectados por una directiva de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="8eb23-124">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="8eb23-125">Para ello, use el cmdlet **Get-InformationBarrierRecipientStatus** con el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="8eb23-125">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="8eb23-126">La sintaxis es`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="8eb23-126">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="8eb23-127">Puede usar cualquier valor de identidad que identifique de forma exclusiva a cada destinatario, como el nombre, el alias, el nombre distintivo (DN), el DN canónico, la dirección de correo electrónico o el GUID.</span><span class="sxs-lookup"><span data-stu-id="8eb23-127">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="8eb23-128">Ejemplo: `Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="8eb23-128">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="8eb23-129">En este ejemplo, se usa un alias (*meganb*) para el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="8eb23-129">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="8eb23-130">Este cmdlet devolverá información que indica si el usuario está afectado por una directiva de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="8eb23-130">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="8eb23-131">(Busque \* ExoPolicyId: \<guid>).</span><span class="sxs-lookup"><span data-stu-id="8eb23-131">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="8eb23-132">Si los usuarios no se incluyen en las directivas de barrera de información, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8eb23-132">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="8eb23-133">En caso contrario, continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="8eb23-133">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="8eb23-134">Averigüe qué segmentos se incluyen en una directiva de barrera de información.</span><span class="sxs-lookup"><span data-stu-id="8eb23-134">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="8eb23-135">Para ello, use el `Get-InformationBarrierPolicy` cmdlet con el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="8eb23-135">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="8eb23-136">Use los detalles, como el GUID de directiva (ExoPolicyId) que ha recibido durante el paso anterior, como un valor de identidad.</span><span class="sxs-lookup"><span data-stu-id="8eb23-136">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="8eb23-137">Ejemplo: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="8eb23-137">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="8eb23-138">En este ejemplo, se obtiene información detallada sobre la Directiva de barrera de información que tiene ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span><span class="sxs-lookup"><span data-stu-id="8eb23-138">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="8eb23-139">Después de ejecutar el cmdlet, en los resultados, busque los valores de **AssignedSegment**, **SegmentsAllowed**y **SegmentsBlocked** .</span><span class="sxs-lookup"><span data-stu-id="8eb23-139">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="8eb23-140">Ejemplo: después de ejecutar `Get-InformationBarrierPolicy` el cmdlet, vimos lo siguiente en nuestra lista de resultados:</span><span class="sxs-lookup"><span data-stu-id="8eb23-140">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="8eb23-141">En este caso, podemos ver que una directiva de barrera de información afecta a las personas que están en los segmentos de ventas y de investigación.</span><span class="sxs-lookup"><span data-stu-id="8eb23-141">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="8eb23-142">En este caso, se impide que las personas de ventas se comuniquen con personas en investigación.</span><span class="sxs-lookup"><span data-stu-id="8eb23-142">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="8eb23-143">Si esto parece correcto, las barreras de la información funcionan como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="8eb23-143">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="8eb23-144">Si no es así, continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="8eb23-144">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="8eb23-145">Asegúrese de que los segmentos se han definido correctamente.</span><span class="sxs-lookup"><span data-stu-id="8eb23-145">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="8eb23-146">Para ello, use el `Get-OrganizationSegment` cmdlet y revise la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="8eb23-146">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="8eb23-147">Para ver los detalles de un segmento específico, use `Get-OrganizationSegment` el cmdlet con un parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="8eb23-147">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="8eb23-148">Ejemplo: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="8eb23-148">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="8eb23-149">En este ejemplo, se obtiene información acerca del segmento que tiene el GUID *c96e0837-c232-4a8a-841E-ef45787d8fcd*.</span><span class="sxs-lookup"><span data-stu-id="8eb23-149">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="8eb23-150">Revise los detalles del segmento.</span><span class="sxs-lookup"><span data-stu-id="8eb23-150">Review the details for the segment.</span></span> <span data-ttu-id="8eb23-151">Si es necesario, [edite un segmento](information-barriers-policies.md#edit-a-segment)y, a continuación, `Start-InformationBarrierPoliciesApplication` vuelva a usar el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8eb23-151">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="8eb23-152">Si sigue teniendo problemas con la Directiva de barrera de información, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8eb23-152">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="8eb23-153">Problema: el proceso de aplicación de la barrera de información está tardando mucho</span><span class="sxs-lookup"><span data-stu-id="8eb23-153">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="8eb23-154">Después de ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** , el proceso toma un tiempo muy largo para finalizar.</span><span class="sxs-lookup"><span data-stu-id="8eb23-154">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="8eb23-155">Qué hacer</span><span class="sxs-lookup"><span data-stu-id="8eb23-155">What to do</span></span>

1. <span data-ttu-id="8eb23-156">Tenga en cuenta que, al ejecutar el cmdlet de aplicación de Directiva, se aplican (o quitan) directivas de barrera de información, usuario por usuario, para todas las cuentas de la organización.</span><span class="sxs-lookup"><span data-stu-id="8eb23-156">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="8eb23-157">Si tiene muchos usuarios, tardará un rato en procesarse.</span><span class="sxs-lookup"><span data-stu-id="8eb23-157">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="8eb23-158">(Como regla general, tarda aproximadamente una hora en procesar las cuentas de usuario de 5.000).</span><span class="sxs-lookup"><span data-stu-id="8eb23-158">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span> 

2. <span data-ttu-id="8eb23-159">Use el cmdlet **Get-InformationBarrierPoliciesApplicationStatus** para comprobar el estado.</span><span class="sxs-lookup"><span data-stu-id="8eb23-159">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status.</span></span>

    <span data-ttu-id="8eb23-160">Consta`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="8eb23-160">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="8eb23-161">Para mostrar el estado de todas las aplicaciones de directiva de barrera de información, use`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="8eb23-161">To display status for all information barrier policy applications, use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span>

    <span data-ttu-id="8eb23-162">Esto mostrará información sobre si la aplicación de la Directiva se completó, produjo un error o está en curso.</span><span class="sxs-lookup"><span data-stu-id="8eb23-162">This will display information about whether policy application completed, failed, or is in progress..</span></span>

3. <span data-ttu-id="8eb23-163">Según los resultados del paso 2, realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8eb23-163">Depending on the results of step 2, take one of the following steps:</span></span>

    - <span data-ttu-id="8eb23-164">Si la aplicación no se ha iniciado y ha transcurrido más de 45 minutos desde que se ejecutó el cmdlet **Start-InformationBarrierPoliciesApplication** , revise el registro de auditoría para ver si hay errores en las definiciones de directiva o algún otro motivo por el que el la aplicación no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="8eb23-164">If the application has not started, and it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span>

    - <span data-ttu-id="8eb23-165">Si se ha producido un error en la aplicación, revise los segmentos y las directivas.</span><span class="sxs-lookup"><span data-stu-id="8eb23-165">If the application has failed, review your segments and policies.</span></span> <span data-ttu-id="8eb23-166">Si es necesario, [modifique los segmentos](information-barriers-policies.md#edit-a-segment) o [edite las directivas](information-barriers-policies.md#edit-a-policy)y, a continuación, vuelva a ejecutar el cmdlet **Start-InformationBarrierPoliciesApplication** .</span><span class="sxs-lookup"><span data-stu-id="8eb23-166">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>

    - <span data-ttu-id="8eb23-167">Si la aplicación sigue en curso, permita más tiempo para completarse.</span><span class="sxs-lookup"><span data-stu-id="8eb23-167">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="8eb23-168">Si ha sido varios días, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8eb23-168">If it has been several days, contact support.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8eb23-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8eb23-169">Related topics</span></span>

[<span data-ttu-id="8eb23-170">Definir directivas para las barreras de información en Microsoft Teams (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="8eb23-170">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="8eb23-171">Barreras de la información (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="8eb23-171">Information barriers (Preview)</span></span>](information-barriers.md)




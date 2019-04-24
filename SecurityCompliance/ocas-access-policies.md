---
title: Directivas de acceso en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Las directivas de acceso de Office 365 Cloud App Security permiten la supervisión y el control en tiempo real del acceso a las aplicaciones en la nube en función del usuario, la ubicación, el dispositivo y la aplicación. Puede crear directivas de acceso para cualquier dispositivo, incluidos los dispositivos que no están Unidos a un dominio y que Windows Intune no administra mediante la implementación de certificados de cliente en dispositivos administrados o mediante el uso de certificados existentes, como certificados MDM de terceros. Por ejemplo, puede implementar certificados de cliente en dispositivos administrados y, a continuación, bloquear el acceso desde dispositivos sin un certificado.
ms.openlocfilehash: 5e8b8fa293420bc9ff3616daf288b8e02a2eb768
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263012"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="946c4-105">Directivas de acceso en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="946c4-105">Access policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="946c4-106">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="946c4-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="946c4-107">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="946c4-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="946c4-108">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="946c4-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="946c4-109">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="946c4-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="946c4-110">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="946c4-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="946c4-111">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="946c4-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="946c4-112">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="946c4-112">You are here!</span></span>  <br/> [<span data-ttu-id="946c4-113">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="946c4-113">Next step</span></span>](group-your-ip-addresses-in-ocas.md) <br/> |[<span data-ttu-id="946c4-114">Empezar a usar</span><span class="sxs-lookup"><span data-stu-id="946c4-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="946c4-115">Las directivas de acceso de Office 365 Cloud App Security permiten la supervisión y el control en tiempo real del acceso a las aplicaciones en la nube en función del usuario, la ubicación, el dispositivo y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="946c4-115">Office 365 Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app.</span></span> <span data-ttu-id="946c4-116">Puede crear directivas de acceso para cualquier dispositivo, incluidos los dispositivos que no están Unidos a un dominio y que Windows Intune no administra mediante la implementación de certificados de cliente en dispositivos administrados o mediante el uso de certificados existentes, como certificados MDM de terceros.</span><span class="sxs-lookup"><span data-stu-id="946c4-116">You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates.</span></span> <span data-ttu-id="946c4-117">Por ejemplo, puede implementar certificados de cliente en dispositivos administrados y, a continuación, bloquear el acceso desde dispositivos sin un certificado.</span><span class="sxs-lookup"><span data-stu-id="946c4-117">For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.</span></span>

<span data-ttu-id="946c4-118">En lugar de permitir o bloquear completamente el acceso, con [directivas](ocas-session-policies.md) de sesión puede permitir el acceso a la vez que supervisa la sesión o limita actividades de sesión específicas.</span><span class="sxs-lookup"><span data-stu-id="946c4-118">Instead of allowing or blocking access completely, with [session policies](ocas-session-policies.md) you can allow access while monitoring the session and/or limit specific session activities.</span></span>

## <a name="prerequisites-to-using-access-policies"></a><span data-ttu-id="946c4-119">Requisitos previos para usar directivas de acceso</span><span class="sxs-lookup"><span data-stu-id="946c4-119">Prerequisites to using access policies</span></span>

- <span data-ttu-id="946c4-120">Licencia de Azure AD Premium P1</span><span class="sxs-lookup"><span data-stu-id="946c4-120">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="946c4-121">Las aplicaciones relevantes deben [implementarse con el control de aplicación de acceso condicional](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span><span class="sxs-lookup"><span data-stu-id="946c4-121">The relevant apps should be [deployed with Conditional Access App Control](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span></span>

- <span data-ttu-id="946c4-122">debe haber una  [directiva de acceso condicional de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)que redirija a los usuarios a Office 365 Cloud App Security, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="946c4-122">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security, as described below.</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="946c4-123">Crear una directiva de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="946c4-123">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="946c4-124">Directivas de acceso condicional de Azure Active Directory y directivas de sesión de Cloud App Security trabajan conjuntamente para examinar cada sesión de usuario y tomar decisiones de directiva para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="946c4-124">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app.</span></span> <span data-ttu-id="946c4-125">Para configurar una directiva de acceso condicional en Azure AD, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="946c4-125">To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="946c4-126">Configure una  [Directiva de acceso condicional de Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)con asignaciones para el usuario o grupo de usuarios y la aplicación que quiera controlar con el control de aplicación de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="946c4-126">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control.</span></span><br><span data-ttu-id="946c4-127">Nota: esta directiva solo afectará a las aplicaciones que se implementaron con el  [control de aplicación de acceso condicional](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).</span><span class="sxs-lookup"><span data-stu-id="946c4-127">NOTE: Only apps that were [deployed with Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) will be affected by this policy.</span></span>

2. <span data-ttu-id="946c4-128">enrutar a los usuarios a Office 365 Cloud App Security seleccionando la opción **usar Control de aplicación de acceso condicional en restricciones** forzadas en la **sesión**.</span><span class="sxs-lookup"><span data-stu-id="946c4-128">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.</span></span>

## <a name="create-a-cloud-app-security-access-policy"></a><span data-ttu-id="946c4-129">Crear una directiva de acceso de Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="946c4-129">Create a Cloud App Security access policy</span></span>

<span data-ttu-id="946c4-130">Para crear una nueva Directiva de acceso, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="946c4-130">To create a new access policy, follow this procedure:</span></span>

1. <span data-ttu-id="946c4-131">En el portal, seleccione **control** seguido de **directivas**.</span><span class="sxs-lookup"><span data-stu-id="946c4-131">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="946c4-132">En la página **directivas** , haga clic en **crear Directiva** y seleccione **Directiva de acceso**.</span><span class="sxs-lookup"><span data-stu-id="946c4-132">In the **Policies** page, click **Create policy** and select **Access policy**.</span></span>

3. <span data-ttu-id="946c4-133">En la ventana **Directiva** de acceso, asigne un nombre a la Directiva, como *bloquear el acceso desde dispositivos no administrados*.</span><span class="sxs-lookup"><span data-stu-id="946c4-133">In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.</span></span>

4. <span data-ttu-id="946c4-134">En la sección **actividades que coinciden con todas las de la siguiente** sección, en origen de la **actividad**, seleccione filtros de actividad adicionales para aplicarlos a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="946c4-134">In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy.</span></span> <span data-ttu-id="946c4-135">Los filtros incluyen las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="946c4-135">Filters include the following options:</span></span>
    
    - <span data-ttu-id="946c4-136">**Etiquetas de dispositivo**: Use este filtro para identificar los dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="946c4-136">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="946c4-137">**Ubicación**: Use este filtro para identificar ubicaciones desconocidas (y, por lo tanto, arriesgadas).</span><span class="sxs-lookup"><span data-stu-id="946c4-137">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="946c4-138">**Dirección IP**: Use este filtro para filtrar por direcciones IP o use etiquetas de direcciones IP asignadas previamente.</span><span class="sxs-lookup"><span data-stu-id="946c4-138">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="946c4-139">**Etiqueta de agente de usuario**: Use este filtro para habilitar la heurística de identificación de aplicaciones móviles y de escritorio.</span><span class="sxs-lookup"><span data-stu-id="946c4-139">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps.</span></span> <span data-ttu-id="946c4-140">Este filtro se puede establecer en igual a o no es igual a.</span><span class="sxs-lookup"><span data-stu-id="946c4-140">This filter can be set to equals or does not equal.</span></span> <span data-ttu-id="946c4-141">Los valores deben probarse con sus aplicaciones móviles y de escritorio para cada aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="946c4-141">The values should be tested against your mobile and desktop apps for each cloud app.</span></span>

5. <span data-ttu-id="946c4-142">En **acciones**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="946c4-142">Under **Actions**, select one of the following options:</span></span>
    
    - <span data-ttu-id="946c4-143">**Permitir**: establezca esta acción para permitir explícitamente el acceso según los filtros de directiva que establezca.</span><span class="sxs-lookup"><span data-stu-id="946c4-143">**Allow**: Set this action to explicitly allow access according to the policy filters you set.</span></span>
    
    - <span data-ttu-id="946c4-144">**Bloquear**: establezca esta acción para bloquear explícitamente el acceso de acuerdo con los filtros de directiva que establezca.</span><span class="sxs-lookup"><span data-stu-id="946c4-144">**Block**: Set this action to explicitly block access according to the policy filters you set.</span></span>

6. <span data-ttu-id="946c4-145">Puede  **crear una alerta para cada evento que coincida con la gravedad de la Directiva**y establecer un límite de alerta y seleccionar si desea la alerta como un correo electrónico, un mensaje de texto o ambos.</span><span class="sxs-lookup"><span data-stu-id="946c4-145">You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.</span></span>

## <a name="next-steps"></a><span data-ttu-id="946c4-146">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="946c4-146">Next steps</span></span>

- [<span data-ttu-id="946c4-147">Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="946c4-147">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)
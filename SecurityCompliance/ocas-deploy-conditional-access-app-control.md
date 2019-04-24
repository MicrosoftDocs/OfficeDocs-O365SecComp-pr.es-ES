---
title: Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Siga estos pasos para configurar las aplicaciones de Azure AD Office 365 para que se controlen con el control de aplicación de acceso condicional de seguridad de aplicación de nube de Office 365.
ms.openlocfilehash: 72be95b3213b90cfe60d851d0852d465cdbe6ef9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263122"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a><span data-ttu-id="75a9c-103">Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365</span><span class="sxs-lookup"><span data-stu-id="75a9c-103">Deploy Conditional Access App Control for Office 365 apps</span></span>

|<span data-ttu-id="75a9c-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="75a9c-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="75a9c-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="75a9c-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="75a9c-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="75a9c-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="75a9c-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="75a9c-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="75a9c-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="75a9c-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="75a9c-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="75a9c-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="75a9c-110">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="75a9c-110">You are here!</span></span>  <br/> [<span data-ttu-id="75a9c-111">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="75a9c-111">Next step</span></span>](ocas-session-policies.md) <br/> |[<span data-ttu-id="75a9c-112">Empezar a usar</span><span class="sxs-lookup"><span data-stu-id="75a9c-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="75a9c-113">Siga estos pasos para configurar las aplicaciones de Azure AD Office 365 para que se controlen con el control de aplicación de acceso condicional de seguridad de aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="75a9c-113">Follow these steps to configure Azure AD Office 365 apps to be controlled by Office 365 Cloud App Security Conditional Access App Control.</span></span>

<span data-ttu-id="75a9c-114">**Paso 1: [crear una directiva de prueba de acceso condicional de Azure ad](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span><span class="sxs-lookup"><span data-stu-id="75a9c-114">**Step 1: [Create an Azure AD conditional access test policy](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span></span>

<span data-ttu-id="75a9c-115">**Paso 2: [iniciar sesión con un usuario en el ámbito de la Directiva en las aplicaciones](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span><span class="sxs-lookup"><span data-stu-id="75a9c-115">**Step 2: [Sign in with a user scoped to the policy in the apps](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span></span>

<span data-ttu-id="75a9c-116">**Paso 3: Si no seleccionó una directiva de seguridad de aplicaciones en la nube integrada en Azure AD o si quiere aplicar la Directiva a una aplicación no destacada, configure los [controles avanzados en Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal) .**</span><span class="sxs-lookup"><span data-stu-id="75a9c-116">**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [Configure advanced controls in the Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span></span>

<span data-ttu-id="75a9c-117">**Paso 4: [probar la implementación](#step-4-test-the-deployment)**</span><span class="sxs-lookup"><span data-stu-id="75a9c-117">**Step 4: [Test the deployment](#step-4-test-the-deployment)**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75a9c-118">para implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365, necesitará una [licencia válida para Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) , así como una licencia de seguridad de la aplicación de nube de office 365.</span><span class="sxs-lookup"><span data-stu-id="75a9c-118">To deploy Conditional Access App Control for Office 365 apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Office 365 Cloud App Security license.</span></span>

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a><span data-ttu-id="75a9c-119">Paso 1: crear una directiva de prueba de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="75a9c-119">Step 1: Create an Azure AD conditional access test policy</span></span> 

1. <span data-ttu-id="75a9c-120">En Azure Active Directory, en **seguridad**, haga clic en **acceso condicional**.</span><span class="sxs-lookup"><span data-stu-id="75a9c-120">In Azure Active Directory, under **Security**, click on **Conditional access**.</span></span>

2. <span data-ttu-id="75a9c-121">Haga clic en **nueva Directiva** y cree una nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="75a9c-121">Click **New policy** and create a new policy.</span></span>

3. <span data-ttu-id="75a9c-122">En la Directiva de pruebas, en **usuarios**, asigne un usuario o usuario de prueba que se pueda usar para el inicio de sesión inicial y la comprobación.</span><span class="sxs-lookup"><span data-stu-id="75a9c-122">In the TEST policy, under **Users**, assign a test user or user that can be used for an initial sign-on and verification.</span></span>

4. <span data-ttu-id="75a9c-123">En la Directiva de pruebas, en aplicación de la **nube**, asigne las aplicaciones que quiera controlar con el control de aplicación de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="75a9c-123">In the TEST policy, under **Cloud app**, assign the apps you want to control with Conditional Access App Control.</span></span>

5. <span data-ttu-id="75a9c-124">En **sesión**, establezca la Directiva para que use cualquiera de las directivas integradas, **supervise solo** o **bloquee las descargas**.</span><span class="sxs-lookup"><span data-stu-id="75a9c-124">Under **Session**, set the policy to use either of the built-in policies, **Monitor only** or **Block downloads**.</span></span> <span data-ttu-id="75a9c-125">O seleccione **usar Directiva** personalizada para establecer una directiva avanzada en Cloud App Security portal.</span><span class="sxs-lookup"><span data-stu-id="75a9c-125">Or select **Use custom policy** to set an advanced policy in the Cloud App Security portal.</span></span>

6. <span data-ttu-id="75a9c-126">Agregue las **asignaciones** de condición aplicables o conceda **los controles** (opcional).</span><span class="sxs-lookup"><span data-stu-id="75a9c-126">Add any applicable **Condition assignments** or **Grant controls** (optional).</span></span>

> ![Acceso condicional de Azure AD](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a><span data-ttu-id="75a9c-128">Paso 2: iniciar sesión con un usuario en el ámbito de la Directiva en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="75a9c-128">Step 2: Sign in with a user scoped to the policy in the apps</span></span> 

<span data-ttu-id="75a9c-129">Una vez que haya creado la Directiva, inicie sesión en cada una de las aplicaciones configuradas en dicha Directiva.</span><span class="sxs-lookup"><span data-stu-id="75a9c-129">After you've created the policy, sign in to each app configured in that policy.</span></span> <span data-ttu-id="75a9c-130">Asegúrese de iniciar sesión con un usuario configurado en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="75a9c-130">Make sure you sign in using a user configured in the policy.</span></span> <span data-ttu-id="75a9c-131">Asegúrese de cerrar primero la sesión de las sesiones existentes.</span><span class="sxs-lookup"><span data-stu-id="75a9c-131">Make sure to first sign out of existing sessions.</span></span>

<span data-ttu-id="75a9c-132">Cloud App Security sincronizará los detalles de la Directiva con sus servidores para cada nueva aplicación en la que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="75a9c-132">Cloud App Security will sync your policy details to its servers for each new app you log in to.</span></span> <span data-ttu-id="75a9c-133">Esto puede tardar hasta un minuto.</span><span class="sxs-lookup"><span data-stu-id="75a9c-133">This may take up to one minute.</span></span>

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a><span data-ttu-id="75a9c-134">Paso 3: configurar controles avanzados en Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="75a9c-134">Step 3: Configure advanced controls in the Cloud App Security portal</span></span> 

<span data-ttu-id="75a9c-135">Las instrucciones anteriores le ayudaron a crear una directiva de seguridad de aplicación en la nube integrada para las aplicaciones destacadas directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="75a9c-135">The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.</span></span>

<span data-ttu-id="75a9c-136">para configurar una directiva avanzada, cree una directiva de [acceso](ocas-access-policies.md) o una [directiva](ocas-session-policies.md) de sesión en el portal de seguridad de aplicaciones de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="75a9c-136">To configure an advanced policy, create an [access policy](ocas-access-policies.md) or a [session policy](ocas-session-policies.md) in the Office 365 Cloud App Security portal.</span></span>

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a><span data-ttu-id="75a9c-137">Para identificar los dispositivos que usan certificados de cliente (esto es opcional):</span><span class="sxs-lookup"><span data-stu-id="75a9c-137">To identify devices using client certificates (this is optional):</span></span>

1. <span data-ttu-id="75a9c-138">Vaya a la configuración COG y elija **identificación del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="75a9c-138">Go to the settings cog and choose **Device identification**.</span></span>

2. <span data-ttu-id="75a9c-139">Cargar uno o más certificados raíz o intermedios.</span><span class="sxs-lookup"><span data-stu-id="75a9c-139">Upload one or more root or intermediate certificates.</span></span>

3. <span data-ttu-id="75a9c-140">Una vez cargado el certificado, puede crear directivas de acceso y directivas de sesión basadas en la **etiqueta de dispositivo** y el **certificado de cliente válido**.</span><span class="sxs-lookup"><span data-stu-id="75a9c-140">After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.</span></span>

![IDENTIFICADOR de dispositivo de control de aplicación de acceso condicional](media/image2.png)

> [!NOTE]
> <span data-ttu-id="75a9c-142">Solo se solicita un certificado a un usuario si la sesión coincide con una directiva que usa el filtro de certificado de cliente válido.</span><span class="sxs-lookup"><span data-stu-id="75a9c-142">A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.</span></span>
> 
## <a name="step-4-test-the-deployment"></a><span data-ttu-id="75a9c-143">Paso 4: probar la implementación</span><span class="sxs-lookup"><span data-stu-id="75a9c-143">Step 4: Test the deployment</span></span> 

1. <span data-ttu-id="75a9c-144">Primero cierre la sesión de las sesiones existentes.</span><span class="sxs-lookup"><span data-stu-id="75a9c-144">First sign out of any existing sessions.</span></span> <span data-ttu-id="75a9c-145">A continuación, intente iniciar sesión en cada aplicación que se implementó correctamente.</span><span class="sxs-lookup"><span data-stu-id="75a9c-145">Then, try to sign in to each app that was successfully deployed.</span></span> <span data-ttu-id="75a9c-146">Inicie sesión con un usuario que coincida con la Directiva configurada en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="75a9c-146">Sign in using a user that matches the policy configured in Azure AD.</span></span>

2. <span data-ttu-id="75a9c-147">En Cloud App Security portal, en **investigar**, seleccione **registro de actividades**y asegúrese de que se capturan las actividades de inicio de sesión de cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="75a9c-147">In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.</span></span>

3. <span data-ttu-id="75a9c-148">Puede filtrar haciendo clic en **avanzadas**y, a continuación, filtrando mediante el **control de acceso de origen es igual**a.</span><span class="sxs-lookup"><span data-stu-id="75a9c-148">You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.</span></span>

4. <span data-ttu-id="75a9c-149">Se recomienda iniciar sesión en aplicaciones móviles y de escritorio desde dispositivos administrados y no administrados.</span><span class="sxs-lookup"><span data-stu-id="75a9c-149">It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices.</span></span> <span data-ttu-id="75a9c-150">Esto es para asegurarse de que las actividades se capturan correctamente en el registro de actividades.</span><span class="sxs-lookup"><span data-stu-id="75a9c-150">This is to make sure that the activities are properly captured in the activity log.</span></span> <span data-ttu-id="75a9c-151">Para comprobar que la actividad se ha capturado correctamente, haga clic en un inicio de sesión de inicio de sesión único en el que se abre el cajón de actividades.</span><span class="sxs-lookup"><span data-stu-id="75a9c-151">To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer.</span></span> <span data-ttu-id="75a9c-152">Asegúrese de que la **etiqueta** de agente de usuario refleja correctamente si el dispositivo es un cliente nativo (es decir, una aplicación móvil o de escritorio) o si es un dispositivo administrado (compatible, unido a un dominio o un certificado de cliente válido).</span><span class="sxs-lookup"><span data-stu-id="75a9c-152">Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).</span></span>

> [!NOTE]
> <span data-ttu-id="75a9c-153">Una vez implementada, no se puede quitar una aplicación de la página de control de la aplicación de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="75a9c-153">After it is deployed, you can't remove an app from the Conditional Access App Control page.</span></span> <span data-ttu-id="75a9c-154">Siempre que no se establezca una directiva de acceso o sesión en la aplicación, el control de aplicación de acceso condicional no cambiará ningún comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75a9c-154">As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="75a9c-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="75a9c-155">Next steps</span></span>

- [<span data-ttu-id="75a9c-156">Obtener información sobre las directivas de sesión en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75a9c-156">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="75a9c-157">Obtenga información sobre las directivas de acceso en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75a9c-157">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 

- [<span data-ttu-id="75a9c-158">Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75a9c-158">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)
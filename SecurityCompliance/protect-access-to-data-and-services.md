---
title: Proteger el acceso a datos y servicios de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Página de aterrizaje para proteger el acceso a los datos y servicios de O365
ms.openlocfilehash: 95933c5a7bc95f9fd70e8f3470055b57193971d4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213540"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="ed6e7-103">Proteger el acceso a datos y servicios de Office 365</span><span class="sxs-lookup"><span data-stu-id="ed6e7-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="ed6e7-p101">Proteger el acceso a los datos y servicios de Office 365 es crucial para defenderse contra ataques cibernéticos y protegerse contra la pérdida de datos. Se pueden aplicar las mismas protecciones a otras aplicaciones SaaS en su entorno e incluso a aplicaciones locales publicadas con el proxy de aplicación de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="ed6e7-106">Paso 1: revisar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="ed6e7-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="ed6e7-107">Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="ed6e7-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="ed6e7-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="ed6e7-109">Paso 2: configurar la MFA</span><span class="sxs-lookup"><span data-stu-id="ed6e7-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="ed6e7-110">Use estos recursos para orientarse a la MFA, decida qué versión es la más adecuada para usted y, después, planee e implemente la MFA para su entorno.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="ed6e7-111">¿Qué es Azure multi-factor Authentication?</span><span class="sxs-lookup"><span data-stu-id="ed6e7-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="ed6e7-112">Elija la solución Azure multi-factor Authentication para usted</span><span class="sxs-lookup"><span data-stu-id="ed6e7-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="ed6e7-113">Cómo obtener Azure multi-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="ed6e7-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="ed6e7-114">Planeación de multi-factor Authentication para implementaciones de Office 365</span><span class="sxs-lookup"><span data-stu-id="ed6e7-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="ed6e7-115">Configurar autenticación multifactor para usuarios de Office 365</span><span class="sxs-lookup"><span data-stu-id="ed6e7-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="ed6e7-116">Planeación de la implementación de MFA, nube o local</span><span class="sxs-lookup"><span data-stu-id="ed6e7-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="ed6e7-117">Configuración de Azure multi-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="ed6e7-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="ed6e7-118">Paso 3: exigir la MFA con las reglas de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="ed6e7-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="ed6e7-119">Si usa Azure AD MFA, cree una regla de acceso condicional que requiera MFA para obtener acceso a Office 365 y otras aplicaciones SaaS en su entorno.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="ed6e7-120">Acceso condicional en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed6e7-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a><span data-ttu-id="ed6e7-121">Paso 4: configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ed6e7-121">Step 4: Configure privileged access management</span></span>

<span data-ttu-id="ed6e7-p102">La administración de acceso privilegiado permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365.  Puede ayudar a proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a las opciones de configuración fundamentales.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-p102">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="ed6e7-124">Información general sobre la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ed6e7-124">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="ed6e7-125">Configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="ed6e7-125">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a><span data-ttu-id="ed6e7-126">Paso 5: configurar las directivas de acceso a dispositivos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ed6e7-126">Step 5: Configure SharePoint device access policies</span></span>

<span data-ttu-id="ed6e7-p103">Se recomiendan las directivas de acceso de dispositivo para SharePoint Online y OneDrive para la empresa para proteger datos confidenciales, clasificados y regulados. La capacidad para aplicar directivas de acceso a dispositivos en sitios de grupo individuales estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-p103">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="ed6e7-129">Control de acceso desde dispositivos no administrados</span><span class="sxs-lookup"><span data-stu-id="ed6e7-129">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="ed6e7-130">Paso 6: configurar la protección de datos y aplicaciones para dispositivos</span><span class="sxs-lookup"><span data-stu-id="ed6e7-130">Step 6: Configure app and data protection for devices</span></span>

<span data-ttu-id="ed6e7-p104">Puede administrar aplicaciones en dispositivos móviles independientemente de si los dispositivos están inscritos para la administración de dispositivos móviles. Esto protege contra la fuga accidental de datos en Office 365, incluidos el correo y los archivos.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-p104">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="ed6e7-133">Para iOS y Android: [proteger datos de aplicaciones mediante directivas de protección de aplicaciones con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="ed6e7-133">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="ed6e7-134">Para Windows 10, configure Windows Information Protection (WIP) para evitar pérdidas de datos accidentales.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-134">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="ed6e7-135">Para dispositivos administrados: [crear una directiva de Windows Information Protection (WIP) con la Directiva de inscripción mediante el portal de Azure para Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="ed6e7-135">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="ed6e7-136">Para dispositivos no administrados: [crear e implementar la Directiva de protección de aplicaciones de Windows Information Protection (WIP) con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="ed6e7-136">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-7-manage-devices-with-intune"></a><span data-ttu-id="ed6e7-137">Paso 7: administrar dispositivos con Intune</span><span class="sxs-lookup"><span data-stu-id="ed6e7-137">Step 7: Manage devices with Intune</span></span>

<span data-ttu-id="ed6e7-p105">La administración de dispositivos le permite garantizar que son correctos y compatibles antes de permitirles el acceso a los recursos de su entorno. Las reglas de acceso condicional basadas en dispositivos ayudan a garantizar que los atacantes no puedan obtener acceso a sus recursos desde dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-p105">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="ed6e7-140">Inscribir dispositivos para la administración en Intune</span><span class="sxs-lookup"><span data-stu-id="ed6e7-140">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="ed6e7-141">Paso 8: configurar directivas de Intune adicionales y reglas de acceso condicional para el entorno</span><span class="sxs-lookup"><span data-stu-id="ed6e7-141">Step 8: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="ed6e7-142">Use estas configuraciones recomendadas como punto de partida para escenarios de escala empresarial o seguridad de acceso sofisticada.</span><span class="sxs-lookup"><span data-stu-id="ed6e7-142">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="ed6e7-143">Directivas y configuraciones de correo electrónico seguro</span><span class="sxs-lookup"><span data-stu-id="ed6e7-143">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    


---
title: Proteger el acceso a datos y servicios de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: página de inicio para la protección de acceso a datos de Office 365 y servicios
ms.openlocfilehash: 652a14c5f1f29187aeac51355e7a924c9378806f
ms.sourcegitcommit: 15dfa0c83aa88816c18e30a44a49e36e733d952c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "24011282"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="3cb36-103">Proteger el acceso a datos y servicios de Office 365</span><span class="sxs-lookup"><span data-stu-id="3cb36-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="3cb36-p101">Proteger el acceso a sus datos de Office 365 y servicios es crucial para la defensa contra ataques cibernéticos y protección contra la pérdida de datos. Las protecciones de mismas se pueden aplicar a otras aplicaciones de SaaS en su entorno y publicado incluso a las aplicaciones local con el Proxy de aplicación de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3cb36-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="3cb36-106">Paso 1: Recomendaciones de revisión</span><span class="sxs-lookup"><span data-stu-id="3cb36-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="3cb36-107">Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cb36-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="3cb36-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="3cb36-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="3cb36-109">Paso 2: Configurar MFA</span><span class="sxs-lookup"><span data-stu-id="3cb36-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="3cb36-110">Use estos recursos para orientarse a MFA, decidir qué versión es adecuada para usted y, a continuación, planear e implementar MFA para su entorno.</span><span class="sxs-lookup"><span data-stu-id="3cb36-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="3cb36-111">¿Qué es la autenticación multifactor Azure?</span><span class="sxs-lookup"><span data-stu-id="3cb36-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="3cb36-112">Elegir la solución de autenticación multifactor Azure para usted</span><span class="sxs-lookup"><span data-stu-id="3cb36-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="3cb36-113">Cómo obtener la autenticación multifactor Azure</span><span class="sxs-lookup"><span data-stu-id="3cb36-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="3cb36-114">Planeación de la autenticación multifactor para las implementaciones de Office 365</span><span class="sxs-lookup"><span data-stu-id="3cb36-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="3cb36-115">Configurar la autenticación multifactor para usuarios de Office 365</span><span class="sxs-lookup"><span data-stu-id="3cb36-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="3cb36-116">Planeación de dónde implementar MFA, en la nube o local</span><span class="sxs-lookup"><span data-stu-id="3cb36-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="3cb36-117">Establecer la configuración de la autenticación multifactor Azure</span><span class="sxs-lookup"><span data-stu-id="3cb36-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="3cb36-118">Paso 3: Aplicar MFA con las reglas de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="3cb36-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="3cb36-119">Si está utilizando Azure AD MFA, crear una regla de acceso condicional para requerir MFA para tener acceso a Office 365 y otras aplicaciones de SaaS en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3cb36-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="3cb36-120">Acceso condicional en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3cb36-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a><span data-ttu-id="3cb36-121">Paso 4: Configurar la administración con privilegios de acceso</span><span class="sxs-lookup"><span data-stu-id="3cb36-121">Step 4: Configure privileged access management</span></span>

<span data-ttu-id="3cb36-p102">Con privilegios de acceso permite la administración de control de acceso granular a través de las tareas de administración con privilegios en Office 365.  Puede ayudar a proteger la organización de las infracciones que pueden usar cuentas con privilegios de administración existentes con acceso permanente a los datos confidenciales o acceso a la configuración de configuración crítica.</span><span class="sxs-lookup"><span data-stu-id="3cb36-p102">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="3cb36-124">Información general de con privilegios de administración de acceso</span><span class="sxs-lookup"><span data-stu-id="3cb36-124">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="3cb36-125">Configurar la administración con privilegios de acceso</span><span class="sxs-lookup"><span data-stu-id="3cb36-125">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a><span data-ttu-id="3cb36-126">Paso 5: Configurar las directivas de acceso de dispositivo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3cb36-126">Step 5: Configure SharePoint device access policies</span></span>

<span data-ttu-id="3cb36-p103">Las directivas de acceso de dispositivo para SharePoint Online y OneDrive para la empresa se recomiendan para proteger los datos confidenciales, clasificados y regulados. Próximamente es la capacidad para aplicar las directivas de acceso de dispositivo a los sitios de grupo individuales.</span><span class="sxs-lookup"><span data-stu-id="3cb36-p103">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="3cb36-129">Control de acceso desde dispositivos no administrados</span><span class="sxs-lookup"><span data-stu-id="3cb36-129">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="3cb36-130">Paso 6: Configurar la aplicación y protección de datos para dispositivos</span><span class="sxs-lookup"><span data-stu-id="3cb36-130">Step 6: Configure app and data protection for devices</span></span>

<span data-ttu-id="3cb36-p104">Puede administrar las aplicaciones en dispositivos móviles, independientemente de si los dispositivos se inscriben para administración de dispositivos móviles. Esto protege contra la fuga accidental de datos de Office 365, incluidos correo y los archivos.</span><span class="sxs-lookup"><span data-stu-id="3cb36-p104">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="3cb36-133">Para iOS y Android: [proteger los datos de aplicación mediante directivas de protección de aplicaciones con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="3cb36-133">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="3cb36-134">10 de Windows, configure Windows información protección (trabajo en curso) para evitar pérdidas de datos accidentales.</span><span class="sxs-lookup"><span data-stu-id="3cb36-134">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="3cb36-135">Para los dispositivos administrados: [crear un Windows información protección (trabajo en curso) con la directiva de inscripción mediante el portal de Azure para Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="3cb36-135">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="3cb36-136">Para dispositivos no gestionados: [crear e implementar la directiva de protección de aplicación de protección de información de Windows (curso) con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="3cb36-136">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-7-manage-devices-with-intune"></a><span data-ttu-id="3cb36-137">Paso 7: Administración de dispositivos con Intune</span><span class="sxs-lookup"><span data-stu-id="3cb36-137">Step 7: Manage devices with Intune</span></span>

<span data-ttu-id="3cb36-p105">Administración de dispositivos permite asegurarse de que son compatibles con y en buen estado antes de permitir el acceso a los recursos en el entorno. Dispositivo en función de acceso condicional reglas ayudan a garantizar que los atacantes no se pueden obtener acceso a los recursos desde dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="3cb36-p105">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="3cb36-140">Inscribirse dispositivos para la administración en Intune</span><span class="sxs-lookup"><span data-stu-id="3cb36-140">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="3cb36-141">Paso 8: Configurar directivas Intune adicionales y las reglas de acceso condicional para su entorno</span><span class="sxs-lookup"><span data-stu-id="3cb36-141">Step 8: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="3cb36-142">Use estas configuraciones recomendadas como punto de partida para escenarios de seguridad de acceso sofisticados o de escala empresarial.</span><span class="sxs-lookup"><span data-stu-id="3cb36-142">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="3cb36-143">Configuraciones y directivas de correo electrónico seguro</span><span class="sxs-lookup"><span data-stu-id="3cb36-143">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    


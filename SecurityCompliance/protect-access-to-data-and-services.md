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
# <a name="protect-access-to-data-and-services-in-office-365"></a>Proteger el acceso a datos y servicios de Office 365

Proteger el acceso a los datos y servicios de Office 365 es crucial para defenderse contra ataques cibernéticos y protegerse contra la pérdida de datos. Se pueden aplicar las mismas protecciones a otras aplicaciones SaaS en su entorno e incluso a aplicaciones locales publicadas con el proxy de aplicación de Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Paso 1: revisar recomendaciones

Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>Paso 2: configurar la MFA

Use estos recursos para orientarse a la MFA, decida qué versión es la más adecuada para usted y, después, planee e implemente la MFA para su entorno.
  
- [¿Qué es Azure multi-factor Authentication?](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [Elija la solución Azure multi-factor Authentication para usted](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Cómo obtener Azure multi-factor Authentication](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [Planeación de multi-factor Authentication para implementaciones de Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Configurar autenticación multifactor para usuarios de Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [Planeación de la implementación de MFA, nube o local](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Configuración de Azure multi-factor Authentication](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>Paso 3: exigir la MFA con las reglas de acceso condicional de Azure AD

Si usa Azure AD MFA, cree una regla de acceso condicional que requiera MFA para obtener acceso a Office 365 y otras aplicaciones SaaS en su entorno.
  
- [Acceso condicional en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>Paso 4: configurar la administración del acceso con privilegios

La administración de acceso privilegiado permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365.  Puede ayudar a proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a las opciones de configuración fundamentales.

- [Información general sobre la administración del acceso con privilegios](privileged-access-management-overview.md)
- [Configurar la administración del acceso con privilegios](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>Paso 5: configurar las directivas de acceso a dispositivos de SharePoint

Se recomiendan las directivas de acceso de dispositivo para SharePoint Online y OneDrive para la empresa para proteger datos confidenciales, clasificados y regulados. La capacidad para aplicar directivas de acceso a dispositivos en sitios de grupo individuales estará disponible próximamente.
  
- [Control de acceso desde dispositivos no administrados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>Paso 6: configurar la protección de datos y aplicaciones para dispositivos

Puede administrar aplicaciones en dispositivos móviles independientemente de si los dispositivos están inscritos para la administración de dispositivos móviles. Esto protege contra la fuga accidental de datos en Office 365, incluidos el correo y los archivos.
  
- Para iOS y Android: [proteger datos de aplicaciones mediante directivas de protección de aplicaciones con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
Para Windows 10, configure Windows Information Protection (WIP) para evitar pérdidas de datos accidentales.
  
- Para dispositivos administrados: [crear una directiva de Windows Information Protection (WIP) con la Directiva de inscripción mediante el portal de Azure para Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- Para dispositivos no administrados: [crear e implementar la Directiva de protección de aplicaciones de Windows Information Protection (WIP) con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>Paso 7: administrar dispositivos con Intune

La administración de dispositivos le permite garantizar que son correctos y compatibles antes de permitirles el acceso a los recursos de su entorno. Las reglas de acceso condicional basadas en dispositivos ayudan a garantizar que los atacantes no puedan obtener acceso a sus recursos desde dispositivos no administrados.
  
- [Inscribir dispositivos para la administración en Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>Paso 8: configurar directivas de Intune adicionales y reglas de acceso condicional para el entorno

Use estas configuraciones recomendadas como punto de partida para escenarios de escala empresarial o seguridad de acceso sofisticada.
  
- [Directivas y configuraciones de correo electrónico seguro](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    


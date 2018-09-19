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
# <a name="protect-access-to-data-and-services-in-office-365"></a>Proteger el acceso a datos y servicios de Office 365

Proteger el acceso a sus datos de Office 365 y servicios es crucial para la defensa contra ataques cibernéticos y protección contra la pérdida de datos. Las protecciones de mismas se pueden aplicar a otras aplicaciones de SaaS en su entorno y publicado incluso a las aplicaciones local con el Proxy de aplicación de Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Paso 1: Recomendaciones de revisión

Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>Paso 2: Configurar MFA

Use estos recursos para orientarse a MFA, decidir qué versión es adecuada para usted y, a continuación, planear e implementar MFA para su entorno.
  
- [¿Qué es la autenticación multifactor Azure?](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [Elegir la solución de autenticación multifactor Azure para usted](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Cómo obtener la autenticación multifactor Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [Planeación de la autenticación multifactor para las implementaciones de Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Configurar la autenticación multifactor para usuarios de Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [Planeación de dónde implementar MFA, en la nube o local](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Establecer la configuración de la autenticación multifactor Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>Paso 3: Aplicar MFA con las reglas de acceso condicional de Azure AD

Si está utilizando Azure AD MFA, crear una regla de acceso condicional para requerir MFA para tener acceso a Office 365 y otras aplicaciones de SaaS en su entorno.
  
- [Acceso condicional en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>Paso 4: Configurar la administración con privilegios de acceso

Con privilegios de acceso permite la administración de control de acceso granular a través de las tareas de administración con privilegios en Office 365.  Puede ayudar a proteger la organización de las infracciones que pueden usar cuentas con privilegios de administración existentes con acceso permanente a los datos confidenciales o acceso a la configuración de configuración crítica.

- [Información general de con privilegios de administración de acceso](privileged-access-management-overview.md)
- [Configurar la administración con privilegios de acceso](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>Paso 5: Configurar las directivas de acceso de dispositivo de SharePoint

Las directivas de acceso de dispositivo para SharePoint Online y OneDrive para la empresa se recomiendan para proteger los datos confidenciales, clasificados y regulados. Próximamente es la capacidad para aplicar las directivas de acceso de dispositivo a los sitios de grupo individuales.
  
- [Control de acceso desde dispositivos no administrados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>Paso 6: Configurar la aplicación y protección de datos para dispositivos

Puede administrar las aplicaciones en dispositivos móviles, independientemente de si los dispositivos se inscriben para administración de dispositivos móviles. Esto protege contra la fuga accidental de datos de Office 365, incluidos correo y los archivos.
  
- Para iOS y Android: [proteger los datos de aplicación mediante directivas de protección de aplicaciones con Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
10 de Windows, configure Windows información protección (trabajo en curso) para evitar pérdidas de datos accidentales.
  
- Para los dispositivos administrados: [crear un Windows información protección (trabajo en curso) con la directiva de inscripción mediante el portal de Azure para Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- Para dispositivos no gestionados: [crear e implementar la directiva de protección de aplicación de protección de información de Windows (curso) con Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-7-manage-devices-with-intune"></a>Paso 7: Administración de dispositivos con Intune

Administración de dispositivos permite asegurarse de que son compatibles con y en buen estado antes de permitir el acceso a los recursos en el entorno. Dispositivo en función de acceso condicional reglas ayudan a garantizar que los atacantes no se pueden obtener acceso a los recursos desde dispositivos no administrados.
  
- [Inscribirse dispositivos para la administración en Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>Paso 8: Configurar directivas Intune adicionales y las reglas de acceso condicional para su entorno

Use estas configuraciones recomendadas como punto de partida para escenarios de seguridad de acceso sofisticados o de escala empresarial.
  
- [Configuraciones y directivas de correo electrónico seguro](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    


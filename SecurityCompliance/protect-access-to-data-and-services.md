---
title: Proteger el acceso de usuario y de dispositivo
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Página de aterrizaje para proteger el acceso a los datos y servicios de O365
ms.openlocfilehash: 0b693d9b259a671f0e2a3e45747f81e1020d7487
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156872"
---
# <a name="protect-user-and-device-access"></a>Proteger el acceso de usuario y de dispositivo

Proteger el acceso a los datos y servicios de Office 365 es crucial para defenderse contra ataques cibernéticos y protegerse contra la pérdida de datos. Se pueden aplicar las mismas protecciones a otras aplicaciones SaaS en su entorno e incluso a aplicaciones locales publicadas con el proxy de aplicación de Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Paso 1: revisar recomendaciones

Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Paso 2: proteger las cuentas de administrador y el acceso
Las cuentas administrativas que se usan para administrar el entorno de Office 365 incluyen privilegios elevados. Estos son objetivos muy valiosos para los hackers y los delincuentes cibernéticos. 

Empiece por usar las cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para uso normal, no administrativo y solo usar su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo.

Proteger las cuentas de administrador con autenticación multifactor y acceso condicional. Para obtener más información, consulte [Protecting Administrator accounts](https://docs.microsoft.com/en-us/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts). 

A continuación, configure la administración del acceso con privilegios en Office 365. La administración de acceso privilegiado permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a las opciones de configuración fundamentales.

- [Información general sobre la administración del acceso con privilegios](privileged-access-management-overview.md)
- [Configurar la administración del acceso con privilegios](privileged-access-management-configuration.md)

Otra recomendación es usar estaciones de trabajo configuradas específicamente para el trabajo administrativo. Se trata de dispositivos dedicados que solo se usan para tareas administrativas. Consulte [proteger el acceso privilegiado](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access).

Por último, puede mitigar el impacto de la falta de acceso administrativo involuntaria mediante la creación de dos o más cuentas de acceso de emergencia en el espacio empresarial. Consulte [administrar cuentas de acceso de emergencia en Azure ad](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Paso 3: configurar directivas de acceso a dispositivos e identidades recomendadas
Las directivas de autenticación multifactor (MFA) y de acceso condicional son herramientas eficaces para mitigar las cuentas en peligro y el acceso no autorizado. Le recomendamos que implemente un conjunto de directivas que se han probado en conjunto. Para obtener más información, incluidos los pasos de implementación, vea [configuración de identidad y acceso a dispositivos](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations).

 Estas directivas implementan las siguientes capacidades:
- Autenticación de factor múltiple
- Acceso condicional
- Protección de aplicaciones de Intune (protección de aplicaciones y datos para dispositivos)
- Compatibilidad con dispositivos de Intune
- Azure AD Identity Protection

Implemetning el cumplimiento del dispositivo de Intune requiere la inscripción del dispositivo. La administración de dispositivos le permite garantizar que son correctos y compatibles antes de permitirles el acceso a los recursos de su entorno. Consulte [inscribir dispositivos para la administración en Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Paso 4: configurar las directivas de acceso a dispositivos de SharePoint

Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido sensible y altamente regulado con controles de acceso a dispositivos. Para obtener más información, vea [recomendaciones de directivas para proteger los archivos y los sitios de SharePoint](https://docs.microsoft.com/en-us/microsoft-365/enterprise/sharepoint-file-access-policies).



    


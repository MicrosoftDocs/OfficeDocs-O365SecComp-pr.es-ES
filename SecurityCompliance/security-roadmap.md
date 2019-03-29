---
title: 'Guía básica de seguridad de Office 365: principales prioridades de los primeros 30 días, 90 días y versiones posteriores'
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Las principales recomendaciones del equipo de Cybersecurity de Microsoft para implementar las funciones de seguridad para proteger el entorno de Office 365. '
ms.openlocfilehash: ba74827c34a869ee11553f02d9085b6f015b2d9d
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955173"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Guía básica de seguridad de Office 365: principales prioridades de los primeros 30 días, 90 días y versiones posteriores

En este artículo se incluyen las principales recomendaciones del equipo de Cybersecurity de Microsoft para implementar las funciones de seguridad para proteger el entorno de Office 365. Este artículo se ha adaptado desde una sesión de Encendemiento de Microsoft: [proteger Office 365 como un Cybersecurity Pro: principales prioridades para los primeros 30 días, 90 días más allá](https://www.youtube.com/watch?v=luignzNyR-o). Esta sesión fue desarrollada y presentada por Mark Simos y Matt Kemelhar, Enterprise Cybersecurity Architects.
  
En este artículo:
  
- [Resultados del plan de desarrollo](security-roadmap.md#Roadmap)
    
- [30 días: ganada rapidez eficaz](security-roadmap.md#Thirdaydays)
    
- [90 días: protecciones mejoradas](security-roadmap.md#Ninetydays)
    
- [Más allá](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>Resultados del plan de desarrollo
<a name="Roadmap"> </a>

Estas recomendaciones de plan de desarrollo se almacenan en tres fases en un orden lógico con los siguientes objetivos.

|||
|:-----|:-----|
| |Resultados
|30 días|Configuración rápida:  <br/> • Protecciones de administración básicas  <br/> • Registro y análisis  <br/> • Protecciones de identidad básicas  <br/> Configuración de inquilino  <br/>  Preparar las partes interesadas  <br/> |
|90 días|Protecciones avanzadas:  <br/> • Cuentas de administrador  <br/>  • Cuentas &amp; de usuario de datos  <br/>  Visibilidad del cumplimiento, la amenaza y las necesidades de los usuarios  <br/>  Adaptación e implementación de directivas y protecciones predeterminadas  <br/> |
|Más allá|Ajustar y refinar directivas y controles clave  <br/> Ampliar las protecciones a las dependencias locales  <br/> Integración con procesos de seguridad y negocios (legal, amenaza interna, etc.)  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 días: ganada rapidez eficaz
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.
  
|||
|:-----|:-----|
|Área  <br/> |Tareas  <br/> |
|Administración de seguridad  <br/> |• Compruebe la puntuación segura y tome nota del resultado actual ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Active el registro de auditoría para Office 365. Consulte [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).  <br/> • [Configure el inquilino de Office 365 para mejorar la seguridad](tenant-wide-setup-for-increased-security.md) .  <br/>  • Revise de forma regular los paneles e informes en el centro de seguridad y la seguridad de aplicaciones en la nube de Microsoft 365.  <br/> |
|Protección contra amenazas  <br/> |[Conecte Office 365 a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar la supervisión con las directivas de detección de amenazas predeterminadas para comportamientos anómalos. Se necesitan siete días para crear una línea base para la detección de anomalías.  <br><br/>  Implemente la protección de las cuentas de administrador:  <br/> • Use cuentas de administrador dedicadas para la actividad de administración.  <br/>  • Exigir la autenticación multifactor (MFA) para las cuentas de administrador.  <br/>  • Use un [dispositivo de Windows 10 altamente seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) para la actividad de administración.  <br/> |
|Administración de identidad y acceso  <br/> |• [Habilite Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> • Para entornos de identidades federados, exija la seguridad de las cuentas (longitud de la contraseña, antigüedad, complejidad, etc.).  <br/> |
|Protección de la información  <br/> | Revise los ejemplos de recomendaciones de protección de la información. La protección de la información requiere coordinación en toda la organización. Empiece con estos recursos:  <br/> • [Office 365 Information Protection para RGPD](http://aka.ms/o365gdpr) <br/> • [Proteja los archivos y sitios de SharePoint Online](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (incluye uso compartido, clasificación, prevención de pérdida de datos y Azure Information Protection)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 días: protecciones mejoradas
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad. 
  
|||
|:-----|:-----|
|Área  <br/> |Tarea  <br/> |
|Administración de seguridad  <br/> | • Compruebe la puntuación segura para las acciones recomendadas para [https://securescore.office.com](https://securescore.office.com)su entorno ().  <br/>  • Continúe revisando regularmente los paneles e informes en el centro de seguridad 365 de Microsoft, la seguridad de aplicaciones en la nube y las herramientas SIEM.  <br/>  • Busque e implemente actualizaciones de software.  <br/>  • Realice simulaciones de ataque para ataques de contraseñas de "Spear-phishing", aerosoles y de fuerza bruta mediante simulador de [ataques](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b) (incluido en la [inteligencia sobre amenazas de Office 365](office-365-ti.md)).  <br/>  • Busque el riesgo de uso compartido revisando los informes integrados en Cloud App Security (en la pestaña investigar).  <br/>  • Compruebe el [Administrador de cumplimiento](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md) para revisar el estado de las regulaciones que se aplican a su organización (como RGPD, NIST 800-171).  <br/> |
|Protección contra amenazas  <br/> | Implementar protecciones mejoradas para cuentas de administrador:  <br/>  • Configure las [estaciones de trabajo de acceso privilegiado](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (huellas) para la actividad de administración.  <br/>  • Configurar [Azure ad privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).  <br/>  • Configurar una herramienta de administración de eventos e información de seguridad (SIEM) para recopilar datos de registro de Office 365, Cloud App Security y otros servicios, incluido AD FS. El registro de auditoría de Office 365 solo almacena datos de 90 días. La captura de estos datos en la herramienta SIEM le permite almacenar datos durante un período más largo.  <br/> |
|Administración de identidad y acceso  <br/> | • Habilite y aplique MFA para todos los usuarios.  <br/>  • Implemente un conjunto de [acceso condicional y directivas relacionadas](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Protección de la información  <br/> | Adaptar e implementar directivas de protección de la información. Estos recursos incluyen ejemplos:  <br/> • [Office 365 Information Protection para RGPD](http://aka.ms/o365gdpr) <br/> • [Proteja los archivos y sitios de SharePoint Online](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Use las directivas de prevención de pérdida de datos y las herramientas de supervisión en Office 365 para los datos almacenados en Office 365 (en lugar de Cloud App Security). <br><br>Use Cloud App Security con Office 365 para obtener características de alerta avanzadas (distintas de la prevención de pérdida de datos).  <br/> |
   
## <a name="beyond"></a>Más allá
<a name="Beyond"> </a>

Se trata de medidas de seguridad importantes que se basan en el trabajo anterior. 
  
|||
|:-----|:-----|
|Área  <br/> |Tarea  <br/> |
|Administración de seguridad  <br/> |• Seguir planificando las acciones siguientes mediante la calificación [https://securescore.office.com](https://securescore.office.com)segura ().  <br/>  • Continúe revisando regularmente los paneles e informes en el centro de seguridad 365 de Microsoft, la seguridad de aplicaciones en la nube y las herramientas SIEM.  <br/>  • Seguir buscando e implementando actualizaciones de software.  <br/>  • Integre la exhibición de documentos electrónicos en sus procesos de respuesta legal y amenaza.  <br/> |
|Protección contra amenazas  <br/> | • Implemente el [acceso con privilegios seguros](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) para los componentes de identidad de local (AD, AD FS).  <br/>  • Use Cloud App Security para supervisar las amenazas internas.  <br/>  • Descubra la información sobre el uso de SaaS de TI mediante Cloud App Security.  <br/> |
|Administración de identidad y acceso  <br/> | • Refinar las directivas de protección de la información:  <br/>  • Azure Information Protection y la prevención de pérdida de datos (DLP) de Office 365.  <br/>  • Directivas y alertas de Cloud App Security.  <br/> |
|Protección de la información  <br/> | • Perfeccione las directivas y los procesos operativos.  <br/>  • Use Azure AD Identity Protection para identificar amenazas de Insider.  <br/> |
   
Consulte también: [Cómo mitigar la cyberattacks rápida como Petya y WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/). 
  


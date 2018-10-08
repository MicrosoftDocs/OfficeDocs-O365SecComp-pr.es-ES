---
title: Guía de seguridad de Office 365 - principales prioridades para los primeros 30 días, 90 días y más allá
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Recomendaciones superiores de la ciberseguridad del equipo de Microsoft para la implementación de las funciones de seguridad para proteger el entorno de Office 365. '
ms.openlocfilehash: 58767ea9a2b825d1583d9135f9d8edcb0d20d7c2
ms.sourcegitcommit: 4a7d7717f0da05cf5a3c506df2989a9d02f33dfa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450085"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Guía de seguridad de Office 365 - principales prioridades para los primeros 30 días, 90 días y más allá

En este artículo incluye recomendaciones superiores de la ciberseguridad del equipo de Microsoft para la implementación de las funciones de seguridad para proteger el entorno de Office 365. En este artículo se ha adaptado de una sesión de Microsoft Ignite: [seguro, al igual que una ciberseguridad pro Office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](https://www.youtube.com/watch?v=luignzNyR-o). En esta sesión se ha desarrollado y presentado por Mark Simos y Matt Kemelhar, los arquitectos de la ciberseguridad Enterprise.
  
En este artículo:
  
- [Resultados de la guía básica](security-roadmap.md#Roadmap)
    
- [30 días: eficaces wins rápidos](security-roadmap.md#Thirdaydays)
    
- [90 días: mejorado protecciones](security-roadmap.md#Ninetydays)
    
- [Más allá de](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>Resultados de la guía básica
<a name="Roadmap"> </a>

Estas recomendaciones de la guía básica se almacenan provisionalmente a través de tres fases en un orden lógico con los siguientes objetivos.

|||
|:-----|:-----|
| |Resultados
|30 días|Configuración rápida:  <br/> • Administración básica protecciones  <br/> Análisis y el registro de •  <br/> • Protecciones de identidad básica  <br/> Configuración de inquilino  <br/>  Preparación de las partes interesadas  <br/> |
|90 días|Protecciones de avanzada:  <br/> Cuentas de administración •  <br/>  • Datos &amp; las cuentas de usuario  <br/>  Visibilidad de las necesidades de cumplimiento de normas, amenaza y usuario  <br/>  Adaptar e implementar protecciones y directivas predeterminadas  <br/> |
|Más allá de|Ajustar y refinar los controles y directivas de clave  <br/> Extender protecciones de dependencias de local  <br/> Integrar con los procesos empresariales y de seguridad (con fines legales, amenaza de ataque, etcetera).  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 días: eficaces wins rápidos
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.
  
|||
|:-----|:-----|
|Área  <br/> |Tareas  <br/> |
|Administración de seguridad  <br/> |• Compruebe la puntuación de seguro y tome nota de la puntuación actual ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Activar el registro de auditoría para Office 365. Vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).<br/> • [Configure el inquilino de Office 365 para aumentar la seguridad](tenant-wide-setup-for-increased-security.md) .  <br/>  • Revise con regularidad paneles e informes en el centro de cumplimiento y seguridad de Office 365 y seguridad de la aplicación en la nube.  <br/> |
|Protección contra amenazas  <br/> |[Conectarse a Office 365 para seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar la supervisión de uso de las directivas de detección de amenaza predeterminadas para comportamientos anómalos. Se tarda siete días para crear una línea de base para la detección de anomalías.<br><br/>  Implementar la protección de cuentas de administrador:  <br/> • Uso dedicado administración de cuentas para la actividad de administración de.  <br/>  • Aplicar la autenticación multifactor (MFA) para las cuentas de administrador.  <br/>  • Utilice un [dispositivo de Windows 10 de alta seguridad](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) para la actividad de administración de.  <br/> |
|Administración de identidad y acceso  <br/> |• [Activar la protección de identidad de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> • Para entornos de identidades federadas, reforzar la seguridad de cuenta (longitud de la contraseña, vigencia, complejidad, etcetera).  <br/> |
|Protección de la información  <br/> | Revise las recomendaciones de protección de información de ejemplo. Protección de la información requiere coordinación en toda la organización. Empezar a trabajar con estos recursos:<br/> • [Protección de office 365 información para GDPR](http://aka.ms/o365gdpr) <br/> • [Archivos y sitios de SharePoint Online seguro](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (que incluye el uso compartido, clasificación, prevención de pérdida de datos y protección de la información de Azure)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 días: mejorado protecciones
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad. 
  
|||
|:-----|:-----|
|Área  <br/> |Tarea  <br/> |
|Administración de seguridad  <br/> | • Comprobación de puntuación de seguro para acciones recomendadas para su entorno ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Continuar revisar con regularidad paneles e informes de la seguridad de Office 365 y centro de cumplimiento, seguridad de la aplicación en la nube y herramientas SIEM.  <br/>  • Busque e implementar actualizaciones de software.  <br/>  • Llevar a cabo simulaciones de ataque para lanza la suplantación de identidad, Aerosol de contraseña y los ataques de contraseña por fuerza bruta con [Simulador de ataque](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b) (incluido con [Información sobre amenazas de Office 365](office-365-ti.md)).  <br/>  • El aspecto para compartir el riesgo mediante la revisión de los informes integrados en la seguridad de la aplicación en la nube (en la ficha investigar).  <br/>  • Compruebe el [Administrador de cumplimiento](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md) para revisar el estado de las normativas que se aplican a su organización (por ejemplo, GDPR, NIST 800-171).  <br/> |
|Protección contra amenazas  <br/> | Implementar protecciones mejoradas para las cuentas de administración:  <br/>  • Configurar [Estaciones de trabajo con privilegios de acceso](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (huellas) para la actividad de administración de.  <br/>  • Configuración de [administración de identidades de Azure con privilegios de AD](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).  <br/>  • Configurar una herramienta de administración (SIEM) de eventos e información de seguridad para recopilar datos de registro de Office 365, seguridad de la aplicación en la nube y otros servicios, incluyendo AD FS. El registro de auditoría de Office 365 almacena datos para sólo 90 días. Capturar estos datos en la herramienta de SIEM le permite almacenar datos durante un período más largo.<br/> |
|Administración de identidad y acceso  <br/> | • Habilitar y exigir la aplicación de MFA para todos los usuarios.  <br/>  • Implementar un conjunto de [acceso condicional y las directivas relacionadas](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Protección de la información  <br/> | Adaptar e implementar directivas de protección de información. Estos recursos incluyen ejemplos de:<br/> • [Protección de office 365 información para GDPR](http://aka.ms/o365gdpr) <br/> • [Archivos y sitios de SharePoint Online seguro](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Usar directivas de prevención de pérdida de datos y herramientas de supervisión en Office 365 para los datos almacenados en Office 365 (en lugar de seguridad de la aplicación en la nube). <br><br>Usar seguridad de la aplicación en la nube con Office 365 para avanzada alertas características (distinto de prevención de pérdida de datos).  <br/> |
   
## <a name="beyond"></a>Más allá de
<a name="Beyond"> </a>

Estas son las medidas de seguridad importantes que se basan en el trabajo anterior. 
  
|||
|:-----|:-----|
|Área  <br/> |Tarea  <br/> |
|Administración de seguridad  <br/> |• Proseguir con la planeación acciones siguiente mediante el uso de puntuación de seguro ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Continuar revisar con regularidad paneles e informes de la seguridad de Office 365 y centro de cumplimiento, seguridad de la aplicación en la nube y herramientas SIEM.  <br/>  • Continuar buscar e implementar las actualizaciones de software.  <br/>  • Integrar la exhibición de documentos electrónicos en su departamento jurídico y los procesos de respuesta de amenaza.  <br/> |
|Protección contra amenazas  <br/> | • Implementar el [Acceso con privilegios seguro](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) para los componentes de identidad local (AD, AD FS).  <br/>  • Seguridad de la aplicación de uso en la nube para supervisar amenazas internas.  <br/>  • Detectar el uso de TI SaaS sombra mediante el uso de seguridad de la aplicación en la nube.  <br/> |
|Administración de identidad y acceso  <br/> | • Refinar políticas de protección de información:  <br/>  • Protección de la información de azure y Office 365 prevención de pérdida de datos (DLP).  <br/>  • Políticas de seguridad de la aplicación en la nube y alertas.  <br/> |
|Protección de la información  <br/> | • Refinar directivas y procesos operativos.  <br/>  • Protección de identidad usar Azure AD para identificar amenazas internas.  <br/> |
   
Vea también: [cómo mitigar rápida cyberattacks como Petya y WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/). 
  


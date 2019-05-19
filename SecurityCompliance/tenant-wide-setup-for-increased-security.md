---
title: Configurar su inquilino de Office 365 para aumentar la seguridad
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: Le guía por la configuración recomendada para la configuración de todos los inquilinos que afectan a la seguridad de su entorno de Office 365. Las necesidades de seguridad pueden requerir más o menos seguridad. Use estas recomendaciones como punto de partida.
ms.openlocfilehash: d5e84bfe5994d1f17ddc75bcb1141fb4f4beace3
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158262"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>Configurar su inquilino de Office 365 para aumentar la seguridad

Este tema le guiará a través de la configuración recomendada para la configuración de todos los inquilinos que afecten a la seguridad de su entorno de Office 365. Las necesidades de seguridad pueden requerir más o menos seguridad. Use estas recomendaciones como punto de partida.
  
## <a name="check-office-365-secure-score"></a>Comprobar la puntuación segura de Office 365

La puntuación segura de Office 365 analiza la seguridad de su organización de Office 365 en función de las actividades habituales y la configuración de seguridad y asigna una puntuación. Empiece por tomar nota del resultado actual. Si se ajusta la configuración de todo el inquilino, se incrementará su puntuación. El objetivo no es conseguir la puntuación máxima, sino que debe tener en cuenta las oportunidades para proteger su entorno que no afectan negativamente a la productividad de los usuarios. Consulte [calificación segura de Microsoft](microsoft-secure-score.md).
  
## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ajustar las directivas de administración de amenazas en el centro de seguridad 365 de Microsoft

El centro de seguridad 365 de Microsoft incluye capacidades que protegen el entorno. También incluye informes y paneles que puede usar para supervisar y realizar acciones. Algunas áreas vienen con configuraciones de directiva predeterminadas. Algunas áreas no incluyen directivas o reglas predeterminadas. Visite estas directivas en Threat Management para ajustar la configuración de administración de amenazas para un entorno más seguro. 
  
|Área * * * *|Incluye una directiva predeterminada * * * *|Recomendación * * * *|
|:-----|:-----|:-----|
|**Contra la suplantación de identidad** <br/> |Sí  <br/> | Si tiene un dominio personalizado, cree una directiva contra la suplantación de identidad (phishing) para proteger las cuentas de correo electrónico de los usuarios más valiosos, como su CEO, y para proteger su dominio. Revisión [Configure una directiva antiphishing](set-up-anti-phishing-policies.md) y cree una directiva siguiendo el ejemplo como guía: "ejemplo: Directiva contra la suplantación de identidad (phishing) para proteger un usuario y un dominio".|
|**Motor antimalware** <br/> |Sí  <br/> | Edite la directiva predeterminada:  <br/> &ensp;&ensp;• Filtro de tipos de datos adjuntos comunes: seleccione activado  <br/><br>  También puede crear directivas de filtro de malware personalizadas y aplicarlas a usuarios, grupos o dominios específicos de la organización.  <br/> <br> Más información:  <br/> &ensp;&ensp;• [Protección contra malware](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> &ensp;&ensp;• [Configurar directivas antimalware](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**Datos adjuntos seguros ATP** <br/> |No  <br/> | En la Página principal de datos adjuntos seguros, proteja los archivos en SharePoint, OneDrive y Microsoft Teams; para ello, Active esta casilla:  <br/>  &ensp;&ensp;• Activar ATP para SharePoint, OneDrive y Microsoft Teams  <br/> <br> Agregue una nueva Directiva de datos adjuntos seguros con esta configuración:  <br/>  &ensp;&ensp;• Bloquear: bloquear los correos electrónicos y archivos adjuntos actuales y futuros con malware detectado (elija esta opción).  <br/>  &ensp;&ensp;• Habilitar el redireccionamiento: (Active esta casilla y escriba una dirección de correo electrónico, como una cuenta de administrador o de cuarentena)  <br/>  &ensp;&ensp;• Aplique la selección anterior si el análisis de malware para archivos adjuntos se agota el tiempo de espera o se produce un error (Active esta casilla)  <br/>  &ensp;&ensp;• Se aplica a — el dominio del destinatario es (Seleccione su dominio)  <br/>  <br>Más información: [Configure las directivas de datos adjuntos seguros de Office 365 ATP](set-up-atp-safe-attachments-policies.md) <br/> |
|**Vínculos seguros de ATP** <br/> |Sí  <br/> | Agregue esta configuración a la directiva predeterminada para toda la organización:  <br/> &ensp;&ensp;• Use vínculos seguros en: Office 365 ProPlus, Office para iOS y Android (Seleccione esta opción).  <br/> <br>Directiva recomendada para destinatarios específicos:  <br/>  &ensp;&ensp;• Las direcciones URL se rescribirán y comprobarán con una lista de vínculos malintencionados conocidos cuando el usuario haga clic en el vínculo (Seleccione esta opción).  <br/>  &ensp;&ensp;• Use datos adjuntos seguros para analizar contenido descargable (Active esta casilla).  <br/>  &ensp;&ensp;• Se aplica a — el dominio del destinatario es (Seleccione su dominio).  <br/> <br> Más información: [vínculos seguros de ATP de Office 365](atp-safe-links.md).  <br/> |
|**Protección contra correo electrónico no deseado (filtrado de correo)** <br/> |Sí  <br/> | Qué se debe vigilar:  <br/>  &ensp;&ensp;• Demasiado correo no deseado: seleccione la configuración personalizada y edite la Directiva de filtro de correo no deseado predeterminada.  <br/>  &ensp;&ensp;• Inteligencia de suplantación de identidad: Revise a los remitentes que están suplantando su dominio. Bloquear o permitir estos remitentes.  <br/>  <br>Más información: [Office 365 protección contra correo no deseado en el correo electrónico](anti-spam-protection.md).  <br/> |
|***Autenticación de correo electrónico*** <br/> |Sí  <br/> |La autenticación de correo electrónico usa un sistema de nombres de dominio (DNS) para agregar información verificable a los mensajes de correo electrónico sobre el remitente de un correo electrónico. Office 365 configura la autenticación de correo electrónico para su dominio predeterminado (onmicrosoft.com), pero Office 365 administradores también pueden usar la autenticación de correo electrónico para los dominios personalizados. Se usan tres métodos de autenticación: <br/> <br> &ensp;&ensp;• Marco de directivas de remitente (o SPF).<br/>&ensp;&ensp;&ensp;&ensp;-Para la instalación, consulte [configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). <br/> &ensp;&ensp;• DomainKeys Identified Mail (DKIM). <br/> &ensp;&ensp;&ensp;&ensp;-Vea [usar DKIM para el correo electrónico en su dominio personalizado en Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email). <br>&ensp;&ensp;&ensp;&ensp;-Una vez que haya configurado DKIM, habilítelo en el centro de seguridad.<br/> &ensp;&ensp;• Autenticación de mensajes basada en el dominio, informes y cumplimiento (DMARC). <br/> &ensp;&ensp;&ensp;&ensp;-Para la instalación de DMARC, [use DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md).<br/>  <br/>
|

> [!NOTE]
> Para implementaciones no estándar de SPF, implementaciones híbridas y solución de problemas: [Cómo Office 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Ver paneles e informes en el centro de seguridad y cumplimiento

Visite estos informes y paneles para obtener más información sobre el estado de su entorno. Los datos de estos informes se harán más completos a medida que la organización use los servicios de Office 365. Por ahora, esté familiarizado con lo que puede supervisar y realizar acciones. Para obtener más información, consulte: [informes en los centros de seguridad y cumplimiento de Microsoft 365](reports-in-security-and-compliance.md).
  
|Panel * * * *|****Descripción****|
|:-----|:-----|
|Panel de administración de amenazas  <br/> |En la sección Administración de amenazas del centro de seguridad, use este panel para ver las amenazas que ya se han tratado y como una herramienta útil para informar a los responsables de la toma de decisiones empresariales sobre las capacidades de investigación y respuesta de las amenazas que ya se han realizado para proteger su empresa.  <br/> |
|Explorador de amenazas  <br/> |También se encuentra en la sección Administración de amenazas del centro de seguridad. Si está investigando o experimentando un ataque contra su inquilino de Office 365, use el explorador de amenazas para analizar las amenazas. Threat Explorer muestra el volumen de ataques a lo largo del tiempo y puede analizar estos datos por familias de amenazas, la infraestructura de los intrusos y mucho más. También puede marcar cualquier correo electrónico sospechoso para la lista de incidentes.  <br/> |
|Informes: panel  <br/> |En la sección informes del centro de seguridad, vea informes de auditoría para sus organizaciones de SharePoint Online y Exchange Online. También puede obtener acceso a los informes de inicio de sesión de usuario de Azure Active Directory (Azure AD), informes de actividad de usuario y el registro de auditoría de Azure AD desde la página ver informes.  <br/> |
   
![Panel del centro de seguridad](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurar opciones adicionales para todos los inquilinos de Exchange Online

Muchos de los controles de seguridad y protección en el centro de administración de Exchange también se incluyen en el centro de seguridad. No es necesario configurarlos en ambos lugares. Estas son algunas de las opciones de configuración adicionales que se recomiendan. 
  
|Área * * * *|Incluye una directiva predeterminada * * * *|Recomendación * * * *|
|:-----|:-----|:-----|
|**Flujo de correo** (reglas de flujo de correo, también conocidas como reglas de transporte)|No|Agregue una regla de flujo de correo para ayudar a proteger contra ransomware. Consulte "Cómo usar las reglas de transporte de Exchange para realizar un seguimiento o bloquear los correos electrónicos con extensiones de archivo usadas por ransomware" en este blog: [How To Deal with ransomware](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/). <br><br/> Vea estos temas: <br/>•[Protéjase contra ransomware](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide#ransomware)<br/>•[Malware y protección contra ransomware en Office 365](office-365-malware-and-ransomware-protection.md)<br/><br/>  Cree una regla de flujo de correo para impedir el reenvío automático de correo electrónico a dominios externos. Para obtener más información, consulte [Mitigating Client external Forwarding Rules with Secure score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/). <br/><br/> Más información: [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx)|
|**Habilitar la autenticación moderna**|No|La autenticación moderna en Office 365 es un requisito previo para usar multi-factor Authentication (MFA). Se recomienda MFA para proteger el acceso a los recursos en la nube, incluido el correo electrónico. <br/><br/> Vea estos temas:  <br/>• [Habilitar o deshabilitar la autenticación moderna en Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/>• [Skype empresarial online: habilitar el inquilino para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> La autenticación moderna está habilitada de forma predeterminada para los clientes de Office 2016, SharePoint Online y OneDrive para la empresa. <br/><br/> Más información: [using office 365 Modern Authentication With Office clients](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)|
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar directivas de uso compartido en todo el espacio empresarial en el centro de administración de SharePoint

Recomendaciones de Microsoft para configurar sitios de grupo de SharePoint en niveles de protección crecientes, comenzando con la protección de línea base. Para obtener más información, vea [proteger sitios y archivos de SharePoint Online](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files) .
  
Los sitios de grupo de SharePoint configurados en el nivel de línea base permiten compartir archivos con usuarios externos mediante vínculos de acceso anónimo. Se recomienda este método en lugar de enviar archivos por correo electrónico. 
  
Para admitir los objetivos de la protección de línea de base, configure las directivas de uso compartido para todos los inquilinos como se recomienda aquí. La configuración de uso compartido de sitios individuales puede ser más restrictiva que la Directiva de todo el espacio empresarial, pero no más permisiva. 
  
|Área * * * *|Incluye una directiva predeterminada * * * *|Recomendación * * * *|
|:-----|:-----|:-----|
|**Uso compartido** (SharePoint Online y OneDrive para la empresa)|Sí|El uso compartido externo está habilitado de forma predeterminada. Se recomiendan estas opciones de configuración: <br/>• Permitir el uso compartido con usuarios externos autenticados y con vínculos de acceso anónimos (configuración predeterminada). <br/>  • Los vínculos de acceso anónimo expiran en este número de días. Escriba un número, si lo desea, como 30 días. <br/>• Tipo de vínculo predeterminado: seleccione interno (solo personas de la organización). Los usuarios que quieran compartir mediante vínculos anónimos deben elegir esta opción en el menú de uso compartido. <br/><br/> Más información: [información general sobre el uso compartido externo](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85)|
   
El centro de administración de SharePoint y el centro de administración de OneDrive para la empresa incluyen la misma configuración. La configuración en cualquier centro de administración se aplica a ambos.
  
## <a name="configure-settings-in-azure-active-directory"></a>Configurar las opciones de Azure Active Directory

Asegúrese de visitar estas dos áreas de Azure Active Directory para completar la configuración para todos los inquilinos para entornos más seguros.
  
### <a name="configure-named-locations-under-conditional-access"></a>Configuración de ubicaciones con nombre (bajo el acceso condicional)

Si su organización incluye oficinas con acceso seguro a la red, agregue los intervalos de direcciones IP de confianza a Azure Active Directory como ubicaciones con nombre. Esta característica ayuda a reducir el número de falsos positivos notificados para eventos de riesgo de inicio de sesión. 
  
Consulte: [ubicaciones con nombre en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicaciones que no admiten la autenticación moderna

La autenticación multifactor requiere aplicaciones compatibles con la autenticación moderna. Las aplicaciones que no admiten la autenticación moderna no se pueden bloquear mediante reglas de acceso condicional.
  
Para entornos seguros, asegúrese de deshabilitar la autenticación para las aplicaciones que no admiten la autenticación moderna. Puede hacer esto en Azure Active Directory con un control que estará disponible próximamente.
  
Mientras tanto, use uno de los siguientes métodos para lograrlo en SharePoint Online y OneDrive para la empresa:
  
- Usar PowerShell, vea [bloquear aplicaciones que no usan la autenticación moderna](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication).
    
- Configure esto en el centro de administración de SharePoint en la página "acceso de dispositivo": "controlar el acceso desde las aplicaciones que no usan la autenticación moderna". Elija bloquear. 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Introducción a Cloud App Security o Office 365 Cloud App Security

Use Office 365 Cloud App Security para evaluar el riesgo, para avisar sobre actividades sospechosas y para emprender acciones automáticamente. Requiere el plan de Office 365 E5.
  
O bien, use Microsoft Cloud App Security para obtener una visibilidad más profunda incluso después de que se conceda acceso, controles completos y protección mejorada para todas las aplicaciones de la nube, incluido Office 365. 
  
Como esta solución recomienda el plan EMS E5, le recomendamos que empiece con Cloud App Security para que pueda usarla con otras aplicaciones SaaS en su entorno. Comience con la configuración y las directivas predeterminadas.
  
Más información:
  
- [Implementar Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Más información sobre Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
    
- [¿Qué es Cloud App Security?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
    
![Panel de Cloud App Security](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>Otros recursos

En estos artículos y guías se proporciona información preceptiva adicional para proteger el entorno de Office 365:
  
- [Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance) (puede usar estas recomendaciones en cualquier entorno, especialmente en entornos solo de nube) 
    
- [Directivas y configuraciones de seguridad recomendadas para las identidades y dispositivos](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (estas recomendaciones incluyen ayuda para entornos de AD FS) 
    


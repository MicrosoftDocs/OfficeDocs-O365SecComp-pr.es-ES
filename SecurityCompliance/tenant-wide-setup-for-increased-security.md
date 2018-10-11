---
title: Configurar su inquilino de Office 365 para aumentar la seguridad
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: Le guiará a través de la configuración recomendada para la configuración de todo el inquilino que afectan a la seguridad de su entorno de Office 365. Las necesidades de seguridad podrían requerir más o menos seguridad. Use estas recomendaciones como punto de partida.
ms.openlocfilehash: de3a1d19e09144105f9576b3a4eb8ed76eb08585
ms.sourcegitcommit: ba2175e394d0cb9f8ede9206aabb44b5b677fa0a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496874"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>Configurar su inquilino de Office 365 para aumentar la seguridad

En este tema le guiará a través de la configuración recomendada para la configuración de todo el inquilino que afectan a la seguridad de su entorno de Office 365. Las necesidades de seguridad podrían requerir más o menos seguridad. Use estas recomendaciones como punto de partida.
  
## <a name="check-office-365-secure-score"></a>Compruebe la puntuación segura de Office 365

Office 365 seguro puntuación analiza la seguridad de su organización de Office 365 basándose en sus actividades normales y la configuración de seguridad y asigna una puntuación. Empezar por tomar nota de su calificación actual. Ajustar algunas opciones de configuración de todo el inquilino aumentará su puntuación. El objetivo es no para lograr la puntuación máxima, pero tener en cuenta las oportunidades para proteger el entorno que no afectar negativamente a la productividad de los usuarios. Vea [Introducción a la puntuación de seguro de Office 365](office-365-secure-score.md).
  
## <a name="tune-threat-management-policies-in-the-office-365-security-amp-compliance-center"></a>Optimización de las directivas de administración de amenaza de la seguridad de Office 365 &amp; centro de cumplimiento

La seguridad de Office 365 &amp; centro de cumplimiento incluye capacidades que protección el entorno. También incluye informes y paneles que puede usar para supervisar y tomar medidas. Se incluyen algunas áreas con las configuraciones de directiva predeterminada. Algunas áreas no incluye directivas predeterminadas o reglas. Visite estas directivas en administración de amenaza para ajustar la configuración de administración de amenaza para un entorno más seguro. 
  
|Área ***|Incluye una directiva predeterminada ***|Recomendación ***|
|:-----|:-----|:-----|
|**Contra suplantación de identidad** <br/> |Sí  <br/> | Si tiene un dominio personalizado, cree una directiva contra suplantación de identidad para proteger las cuentas de correo electrónico de los usuarios más valiosos, como su director general y para proteger su dominio. Revise la [configuración de una directiva contra suplantación de identidad](set-up-anti-phishing-policies.md) y crear una directiva con el ejemplo como guía: "ejemplo: directiva contra suplantación de identidad para proteger un usuario y un dominio."|
|**Motor de Anti-Malware** <br/> |Sí  <br/> | Editar la directiva predeterminada:  <br/> • Comunes de datos adjuntos de tipos de filtro: seleccione en  <br/><br>  También puede crear directivas de filtro de malware personalizada y aplicarla a determinados usuarios, grupos o dominios en su organización.  <br/> <br> Más información:  <br/> • [Protección contra malware](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> • [Configure anti-malware policies](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**Datos adjuntos seguros ATP** <br/> |No  <br/> | En la página principal para los datos adjuntos seguros, proteger los archivos en SharePoint, OneDrive y Microsoft Teams al activar esta casilla de verificación:  <br/>  • Activar ATP para SharePoint, OneDrive y equipos de Microsoft  <br/> <br> Agregar una nueva directiva de datos adjuntos seguros con estas opciones:  <br/>  • Bloque: bloquear los correos electrónicos actuales y futuros y los datos adjuntos con malware detectado (elija esta opción)  <br/>  • Habilitar redireccionamiento: (Active esta casilla de verificación y escriba una dirección de correo electrónico, como una cuenta de administrador o cuarentena)  <br/>  • Se aplican a la selección anterior si se agota el tiempo de espera de análisis para datos adjuntos de malware o se produce error (esta casilla de verificación)  <br/>  • Aplicadas a: el dominio de destinatario es (seleccione su dominio)  <br/>  <br>Obtener más información: [configurar las directivas de los datos adjuntos seguros ATP de Office 365](set-up-atp-safe-attachments-policies.md) <br/> |
|**Vínculos de ATP seguras** <br/> |Sí  <br/> | Agregue esta configuración para la directiva predeterminada para toda la organización:  <br/> • Utilizar vínculos seguros en: Office 365 ProPlus, Office para iOS y Android (Seleccione esta opción).  <br/> <br>Directiva recomendada para destinatarios concretos:  <br/>  • Las direcciones URL se comprobarán con una lista de vínculos malintencionados conocidos cuando el usuario hace clic en el vínculo y se modificó (Seleccione esta opción).  <br/>  • Utilizar datos adjuntos seguros para examinar el contenido descargable (esta casilla de verificación).  <br/>  • Aplicadas a: el dominio de destinatario es (seleccione su dominio).  <br/> <br> Obtener más información: [vínculos seguros ATP de Office 365](atp-safe-links.md).  <br/> |
|**Contra correo no deseado (filtrado de correo)** <br/> |Sí  <br/> | ¿Qué inspeccionar:  <br/>  • Demasiado correo no deseado, elija la configuración personalizada y editar la directiva de filtro de spam de forma predeterminada.  <br/>  • Inteligencia de suplantación, revise los remitentes que son suplantación de su dominio. Bloquear o permitir a estos remitentes.<br/>  <br>Obtener más información: [Protección contra correo no deseado de Office 365 correo](anti-spam-protection.md).  <br/> |
|**DKIM (correo identifican por claves de dominio)** <br/> |Sí  <br/> |DKIM es un proceso de autenticación que puede ayudar a proteger los remitentes y destinatarios de falsificado (falso) y el correo electrónico de suplantación de identidad. El inquilino incluye una firma predeterminada para su dominio. Crear una firma DKIM adicional si agregar dominios personalizados a su inquilino.<br/> <br>Obtener más información: [Uso de DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx) <br/> |
   
## <a name="view-dashboards-and-reports-in-the-security-amp-compliance-center"></a>Ver informes y paneles en la seguridad &amp; centro de cumplimiento

Visite estos informes y paneles para obtener más información sobre el estado de su entorno. Los datos de estos informes se convierten en más rico como la organización usa servicios de Office 365. Por ahora, estar familiarizado con lo que puede supervisar y tomar medidas. Para obtener más información, vea: [informes en la seguridad de Office 365 &amp; centro de cumplimiento](reports-in-security-and-compliance.md).
  
|Panel ***|****Descripción****|
|:-----|:-----|
|Panel de administración de amenaza  <br/> |En la sección Administración de amenazas de seguridad &amp; cumplimiento del centro, use este panel para consulte amenazas que ya se han controlado y como una herramienta útil para informar sobre en responsables de decisiones empresariales en lo que ya ha hecho inteligencia de amenaza para proteger su empresarial.  <br/> |
|Explorador de amenaza  <br/> |Esto es también en la sección Administración de amenazas de seguridad &amp; centro de cumplimiento. Si va a investigar o víctima de un ataque contra el inquilino de Office 365, utilice el Explorador de amenaza para analizar las amenazas. El Explorador de amenaza muestra el volumen de los ataques a través del tiempo, y puede analizar estos datos por familias de amenazas, infraestructura atacante y mucho más. También puede marcar cualquier correo electrónico sospechoso para la lista de incidentes.  <br/> |
|Informes, panel  <br/> |En la sección informes de seguridad &amp; centro de cumplimiento, informes de auditoría de vista para las organizaciones de Exchange Online y SharePoint Online. También se pueden acceder Azure Active Directory (AD) inicio de sesión de informes de usuario, informes de actividad del usuario, y la auditoría de Azure AD inicie sesión desde la página de informes de la vista.  <br/> |
   
![Seguridad &amp; panel del centro de cumplimiento](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurar opciones adicionales de todo el inquilino Exchange Online

Muchos de los controles de seguridad y protección en el centro de administración de Exchange también se incluyen en el centro de cumplimiento y seguridad. No es necesario configurarlos en ambos lugares. A continuación presentamos un par de opciones adicionales que se recomiendan. 
  
|Área ***|Incluye una directiva predeterminada ***|Recomendación ***|
|:-----|:-----|:-----|
|**Flujo de correo** (Las reglas de transporte)  <br/> |No  <br/> | Agregar una regla de flujo de correo para ayudar a proteger contra ransomware. Consulte "Cómo usar las reglas de transporte de Exchange para realizar un seguimiento o bloquear mensajes de correo electrónico con extensiones de archivo utilizadas por ransomware" en este artículo de blog: [cómo abordar los problemas con ransomware](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/).<br><br/> Crear una regla de transporte para evitar el reenvío automático de correo electrónico a dominios externos. Para obtener más información, vea [Mitigación de cliente externo las reglas de desvío con puntuación seguro](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).<br/> <br>Obtener más información: [el flujo de correo rules (reglas de transporte) en Exchange Online](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx) <br/> |
|**Habilitar la autenticación moderna** <br/> |No  <br/> | Autenticación moderna en Office 365 es un requisito previo para usar la autenticación multifactor (MFA). Se recomienda MFA para proteger el acceso a los recursos de la nube, incluido el correo electrónico.<br/>  <br>Consulte los temas siguientes:  <br/> • [Habilitar o deshabilitar la autenticación moderna en Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/> • [Skype para profesionales Online: habilitar el inquilino de para la autenticación moderno](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/>  <br>Autenticación moderna está habilitada de forma predeterminada para Office 2016 clientes, SharePoint Online y OneDrive para la empresa.  <br/>  <br>Obtener más información: [uso de Office 365 autenticación moderna con los clientes de Office](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a) <br/> |
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar directivas de uso compartidas de todo el inquilino en el centro de administración de SharePoint

Recomendaciones de Microsoft para configurar sitios de grupo de SharePoint a aumentar los niveles de protección, empezando por la protección de línea de base. Para obtener más información, vea [archivos y sitios de SharePoint Online seguro](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)
  
Sitios de grupo de SharePoint configurados en el nivel de línea de base permiten el uso compartido de archivos con usuarios externos mediante el uso de vínculos de acceso anónimo. Se recomienda este enfoque en lugar de enviar archivos por correo electrónico. 
  
Para admitir los objetivos de protección de línea de base, configure las directivas de uso compartidas de todo el inquilino recomendadas aquí. Uso compartido de configuración para sitios individuales puede ser más restrictivo que esta directiva de todo el inquilino, pero no más permisivo. 
  
|Área ***|Incluye una directiva predeterminada ***|Recomendación ***|
|:-----|:-----|:-----|
|**Uso compartido** (SharePoint Online y OneDrive para la empresa)  <br/> |Sí  <br/> | Uso compartido externo está habilitado de forma predeterminada. Se recomienda esta configuración:<br/>  • Permitir el uso compartido para los usuarios externos autenticados y utilizar los vínculos de acceso anónimo (valor predeterminado).  <br/>  • Acceso anónimo vínculos expiran en este número de días. Escriba un número, si así lo desea, por ejemplo, 30 días.<br/>  • Tipo de vínculo predeterminado: seleccione interna (las personas de la organización sólo). Los usuarios que desean compartir con vínculos anónimo deben elegir esta opción en el menú de uso compartido.<br/>  <br>Obtener más información: [información general de uso compartido externo](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85) <br/> |
   
Centro de administración de SharePoint y OneDrive para el centro de administración de negocio incluyen la misma configuración. La configuración en el centro de administración de ambos se aplica a ambos.
  
## <a name="configure-settings-in-azure-active-directory"></a>Establecer la configuración en Azure Active Directory

No olvide visitar estas dos áreas en Azure Active Directory para completar la instalación de todo el inquilino para entornos más seguros.
  
### <a name="configure-named-locations-under-conditional-access"></a>Configurar las ubicaciones con nombre (bajo acceso condicional)

Si su organización incluye oficinas con acceso a la red segura, agregar los intervalos de direcciones IP confianza a Azure Active Directory como ubicaciones con nombre. Esta característica ayuda a reducir el número de reportados falsos positivos para eventos de inicio de sesión de riesgo. 
  
Véase: [ubicaciones con nombre en Active Directory de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicaciones que no admiten la autenticación moderna

Autenticación multifactor requiere aplicaciones que admiten la autenticación moderna. No se pueden bloquear las aplicaciones que no admiten la autenticación moderna mediante el uso de las reglas de acceso condicional.
  
Para entornos seguros, asegúrese de deshabilitar la autenticación para aplicaciones que no admiten la autenticación moderna. Puede hacerlo en Azure Active Directory con un control que estará disponible próximamente.
  
Mientras tanto, use uno de los métodos siguientes para hacerlo para SharePoint Online y OneDrive para la empresa:
  
- Usar PowerShell, vea [bloquear aplicaciones que no usan autenticación moderna](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication).
    
- Configurar en el centro de administración de SharePoint en la "página de acceso de dispositivos:"Controlar el acceso desde aplicaciones que no usan autenticación moderna". Elija bloquear. 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Empezar a trabajar con la seguridad de la aplicación en la nube o seguridad de la aplicación de nube de Office 365

Usar la seguridad de la aplicación de Office 365 en la nube para evaluar el riesgo, en la alerta de actividad sospechosa y llevar a cabo acciones. Requiere planeación de Office 365 E5.
  
O bien, usar seguridad de la aplicación de Microsoft en la nube para obtener visibilidad más profunda incluso después de que se concede el acceso, controles completa y una mejor protección para todas las aplicaciones en la nube, como Office 365. 
  
Debido a que esta solución recomienda el plan de EMS E5, se recomienda que iniciar con seguridad de la aplicación en la nube, por lo que puede usar con otras aplicaciones de SaaS en su entorno. Iniciar con la configuración y directivas predeterminadas.
  
Más información:
  
- [Implementar Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Más información sobre Microsoft Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Introducción a Office 365 Cloud App Security](office-365-cas-overview.md)
    
![Panel de Cloud App Security](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>Otros recursos

Estos artículos y guías proporcionan información descriptiva adicional para proteger el entorno de Office 365:
  
- [Orientación de seguridad de Microsoft para campañas políticas, las ONG y otras organizaciones ágiles](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance) (puede usar estos recomendación en cualquier entorno, especialmente en entornos de nube) 
    
- [Las directivas de seguridad recomendado y las configuraciones para las identidades y dispositivos](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (estas recomendaciones incluyen Ayuda para entornos de AD FS) 
    


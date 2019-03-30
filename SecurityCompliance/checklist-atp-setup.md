---
title: 'Inicio rápido: configurar la protección contra amenazas avanzada de Office 365'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Esta es una guía de inicio rápido que puede usar para asegurarse de que la protección contra amenazas avanzada de Office 365 (ATP) está configurada y configurada para su organización.
ms.openlocfilehash: a071c626327aa7d0055df522e8fec5ebe41d6a83
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999403"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a>Guía de inicio rápido: Configurar la Protección contra amenazas avanzada de Office 365

Esta es una guía de inicio rápido que puede usar como una lista de comprobación para asegurarse de que la protección contra amenazas avanzada (ATP) de Office 365 está configurada para su organización. Si no está familiarizado con la protección contra amenazas en Office 365 o no está seguro de dónde empezar, use las siguientes instrucciones como punto de partida. 

> [!IMPORTANT]
> **Se incluye la configuración recomendada inicial para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas de su organización**. Espere unos 30 minutos para que las directivas o los cambios funcionen a través del centro de proceso de trabajo.

## <a name="prerequisites"></a>Requisitos previos

- La organización debe tener una suscripción que incluya la [protección contra amenazas avanzada de Office 365](office-365-atp.md) (ATP).

- Debe tener asignado un rol adecuado para acceder a las características de ATP. En la tabla siguiente se incluyen algunos ejemplos: 

    |Rol o grupo de roles  |Dónde obtener más información  |
    |---------|---------|
    |Administrador global de Office 365 |[Acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |Administrador de seguridad |[Permisos de rol de administrador en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |Administración de la organización de Exchange Online |[Permisos en Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>y<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    (Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md)).

## <a name="part-1---anti-malware"></a>Parte 1: anti-malware

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija**anti-malware**de**Directiva** > de **Administración** > de amenazas.
2. Haga doble clic en la directiva **predeterminada** y, a continuación, elija **configuración**.
3. Especifique las siguientes opciones de configuración:
    - En la sección **respuesta de detección de malware** , mantenga el valor predeterminado de **no**.
    - En la sección **filtro de tipos de datos adjuntos comunes** , elija **activado**.
4. Haga clic en **Guardar **.

Para obtener más información acerca de las opciones de directiva antimalware, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---zero-day-protection"></a>Parte 2: protección de día cero

La protección de día cero se configura mediante directivas, como las directivas de vínculos seguros de ATP y de datos adJuntos seguros.

### <a name="atp-safe-attachments-policies"></a>Directivas de datos adJuntos seguros de ATP

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione la**Directiva** > de **Administración** > de amenazas datos adjuntos**seguros de ATP**.
2. Seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.
3. En la sección **proteger archivos adjuntos de correo electrónico** , haga**+** clic en el signo más ().
4. Especifique las siguientes opciones de configuración:
    - En el cuadro **nombre** , escriba `Block malware`.
    - En la sección respuesta, elija **bloquear**.
    - En la sección **redirigir datos** adjuntos, seleccione la opción **Habilitar**redireccionamiento y, a continuación, especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización que va a revisar los archivos detectados.
    - En la sección **aplicado a** , elija **el dominio del destinatario es**. A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.
5. Haga clic en **Guardar **.
6. (Paso adicional recomendado) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true* para su entorno de Office 365. (Esto impide que los usuarios abran, muevan, copien o compartan archivos que se detectan como malintencionados.)  

Para obtener más información, consulte [configurar las directivas de datos adjuntos seguros de office 365 ATP](set-up-atp-safe-attachments-policies.md) y [activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Directivas de vínculos seguros de ATP

Para configurar los vínculos seguros ATP, revise su directiva predeterminada y agregue una directiva.

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**vínculos seguros ATP**de la**Directiva** > de **Administración** > de amenazas.
2. Haga doble clic en la directiva **predeterminada** .
3. En la sección **usar vínculos seguros en** , seleccione la opción **Office 365 ProPlus, Office para iOS y Android**y, a continuación, haga clic en **Guardar**.
4. En la sección **directivas que se aplican a destinatarios específicos** , haga clic en**+** el signo más ().
5. Especifique las siguientes opciones de configuración:
    - En el cuadro **nombre** , escriba un nombre, como `Safe Links`.
    - En la sección **seleccionar la acción** , elija **activado**.
    - Seleccione estas opciones:
        - **Usar datos adjuntos seguros para analizar contenido descargable** 
        - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
        - **No permitir que los usuarios hagan clic en los vínculos seguros a la dirección URL original**
    - En la sección **aplicado a** , elija **el dominio del destinatario es**. A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.
6. Haga clic en **Guardar **.

Para obtener más información, consulte [configurar las directivas de vínculos seguros de Office 365 ATP](set-up-atp-safe-links-policies.md). 

## <a name="part-3---anti-phishing"></a>Parte 3: contra la suplantación de identidad 

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija la**Directiva** > de **Administración** > de amenazas**ATP anti-phishing**.
2. Haga clic en **directiva predeterminada**.
3. En la **** sección suplantación, haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:
    -  En la pestaña **Agregar usuarios a proteger** , desactive la protección. A continuación, agregue usuarios, como los miembros del Consejo de su organización, su CEO, director financiero y otros líderes senior. (Puede escribir una dirección de correo electrónico individual o hacer clic en para mostrar una lista).
    - En la pestaña **Agregar dominios para proteger** , Active **incluir automáticamente los dominios que posea**. Si tiene dominios personalizados, agréguelos también.
    - En la ficha **acciones** , seleccione **mover mensaje a las carpetas de correo no deseado de los destinatarios para el** usuario suplantado y para el dominio suplantado, y active las sugerencias de seguridad.
    - En la pestaña inteligencia de buzones de **correo** , asegúrese de que la inteligencia de buzones está activada.
    - En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**.
4. En la **** sección suplantación, haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:
    - En la pestaña **configuración de filtro** de suplantaCión de identidad, asegúrese de que está activada la protección contra la suplantación de identidad.
    - En la ficha **acciones** , elija Mover mensaje a las carpetas de correo no deseado de los destinatarios.
    - En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**. (Si no realizó ningún cambio, haga clic en **Cancelar**).
5. Cierre la página Configuración de directiva predeterminada.

Para obtener más información acerca de las opciones de la Directiva antiphishing, consulte Configurar las directivas de protección contra suplantación de identidad [y antiphishing de Office 365 ATP](set-up-anti-phishing-policies.md).

## <a name="part-4---anti-spam"></a>Parte 4: contra el correo no deseado

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**anti-spam**de la**Directiva** > de **Administración** > de amenazas.
2. En la ficha **personalizado** , active la **Configuración personalizada** .
3. ExPanda **directiva predeterminada de filtro de correo no deseado**, haga clic en **Editar Directiva**y especifique la siguiente configuración:
    - En la sección **correo electrónico no deseado y acciones en masa** , establezca el umbral en un valor de 5 o 6.
    - En la sección **listas** de permitidos, revise (y, si es necesario, Edit) los remitentes y dominios permitidos.
4. Haga clic en **Guardar **.

Para obtener más información sobre las opciones de la Directiva contra correo no deseado, consulte [configurar las directivas contra correo no deseado](configure-the-anti-spam-policies.md).

## <a name="part-5---service-wide-settings"></a>Parte 5: configuración de todo el servicio

### <a name="zero-hour-auto-purge"></a>Purga automática de cero horas

La depuración automática de cero horas (ZAP) está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones:
- Las acciones de correo no deseado se establecen para **mover el mensaje a la carpeta correo no deseado** en las directivas contra correo no deseado.
- Los usuarios han mantenido su configuración predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado.

Para obtener más información, consulte depuración [automática de cero horas-protección contra correo no deseado y malware](zero-hour-auto-purge.md).

### <a name="audit-logging"></a>Registro de auditoría

Para poder ver los datos de los informes de protección contra amenazas, como el [Panel de seguridad](security-dashboard.md) y el [Explorador](use-explorer-in-security-and-compliance.md), el registro de auditoría debe estar activado para su organización.

Consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Tareas posteriores a la instalación

### <a name="watch-for-new-features-and-service-updates"></a>Vea las nuevas características y actualizaciones de servicio

- [Visite el plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [Vea la descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a>Ver cómo está trabajando ATP para su organización

- [Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)

- [Usar el explorador en el &amp; centro de seguridad y cumplimiento](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a>Revisar y revisar periódicamente las directivas de ATP

- [Mantener a los usuarios de Office 365 seguros con Office 365 de investigación y respuesta de amenazas](keep-users-safe-with-office-365-ti.md) 

- [Uso de la información y los informes inteligentes del centro de seguridad &amp; y cumplimiento de Office 365](reports-and-insights-in-security-and-compliance.md) 
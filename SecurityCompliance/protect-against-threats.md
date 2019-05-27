---
title: Protección contra amenazas en Office 365
ms.author: tracyp
author: msfttracyp
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Use este artículo como guía para configurar las características de protección contra amenazas ahora.
ms.openlocfilehash: a9a2baccb4709b3e8d77f620281458d51ed0583a
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408395"
---
# <a name="protect-against-threats-in-office-365"></a>Protección contra amenazas en Office 365

Office 365 incluye una variedad de características de protección contra amenazas. Esta es una guía de inicio rápido que puede usar como una lista de comprobación para asegurarse de que las características de protección contra amenazas se configuran para su organización. Si no está familiarizado con las características de protección contra amenazas de Office 365 o no está seguro de dónde empezar, use las siguientes instrucciones como punto de partida. 

> [!IMPORTANT]
> **Se incluye la configuración recomendada inicial para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas de su organización**. Espere unos 30 minutos para que las directivas o los cambios funcionen a través del centro de proceso de trabajo.

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Suscripciones

Las características de protección contra amenazas se incluyen en todas las suscripciones de Office 365; sin embargo, algunas suscripciones incluyen características más avanzadas. En la siguiente tabla se enumeran las características de protección que se incluyen en este artículo junto con los requisitos mínimos de suscripción.<br/>

|Tipo de protección  |Requisito de suscripción  |
|---------|---------|
|Protección contra malware    | [Protección en línea de Exchange](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) EOP        |
|Protección frente a direcciones URL y archivos malintencionados en correo electrónico y documentos de Office    | [Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) ATP       |
|Protección contra suplantación de identidad    | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|Protección contra suplantación de identidad avanzada    | [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|Protección contra correo no deseado     | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|Purgado automático de cero horas (para correo electrónico)    | [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) EOP        |
|Registro de auditoría (se usa con fines de informes)    | [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a>Roles y permisos

Debe tener asignado un rol apropiado para configurar directivas en el [centro de seguridad _AMP_ cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). En la tabla siguiente se incluyen algunos ejemplos: 

|Rol o grupo de roles  |Dónde obtener más información  |
|---------|---------|
|Administrador global de Office 365 |[Acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Administrador de seguridad |[Permisos de rol de administrador en Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización de Exchange Online |[Permisos en Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>y<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Para obtener más información, consulte Permissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1: protección contra malware

La [protección contra malware](anti-malware-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). 

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija**anti-malware**de**Directiva** > de **Administración** > de amenazas.

2. Haga doble clic en la directiva **predeterminada** y, a continuación, elija **configuración**.

3. Especifique las siguientes opciones de configuración:

    - En la sección **respuesta de detección de malware** , mantenga el valor predeterminado de **no**.

    - En la sección **filtro de tipos de datos adjuntos comunes** , elija **activado**.

4. Haga clic en **Guardar **.

Para obtener más información acerca de las opciones de directiva antimalware, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Parte 2: protección frente a direcciones URL y archivos malintencionados

La protección del tiempo de clic de los archivos y las direcciones URL malintencionadas está disponible en las suscripciones que incluyen [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) y se configuran mediante las directivas de [datos adjuntos seguros de ATP](atp-safe-attachments.md) y [vínculos seguros ATP](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Directivas de datos adjuntos seguros de ATP

Para configurar los [datos adjuntos seguros de ATP](atp-safe-attachments.md), debe definir al menos una directiva de datos adjuntos seguros ATP. 

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione la**Directiva** > de **Administración** > de amenazas datos adjuntos**seguros de ATP**.

2. Seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.

3. En la sección **proteger archivos adjuntos de correo electrónico** , haga**+** clic en el signo más ().

4. Especifique las siguientes opciones de configuración:

    - En el cuadro **nombre** , escriba `Block malware`.

    - En la sección respuesta, elija **bloquear**.

    - En la sección **redirigir datos** adjuntos, seleccione la opción **Habilitar**redireccionamiento y, a continuación, especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización que va a revisar los archivos detectados.

    - En la sección **aplicado a** , elija **el dominio del destinatario es**. A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.

5. Haga clic en **Guardar **.

6. (**Paso adicional recomendado**) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true* para su entorno de Office 365. (Esto impide que los usuarios abran, muevan, copien o compartan archivos que se detectan como malintencionados.)  

Para obtener más información, consulte [configurar las directivas de datos adjuntos seguros de office 365 ATP](set-up-atp-safe-attachments-policies.md) y [activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Directivas de vínculos seguros de ATP

Para configurar [vínculos seguros ATP](atp-safe-links.md), revise y edite su directiva predeterminada y agregue una directiva para usuarios específicos.

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

## <a name="part-3---anti-phishing-protection"></a>Parte 3: protección contra la suplantación de identidad

[La protección contra suplantación de identidad (phishing)](anti-phishing-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). La protección contra suplantación de identidad avanzada está disponible en [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). El siguiente procedimiento describe cómo configurar una directiva contra la suplantación de identidad ATP. Los pasos son similares a la configuración de una directiva contra la suplantación de identidad (sin ATP).

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija la**Directiva** > de **Administración** > de amenazas**ATP anti-phishing**.

2. Haga clic en **directiva predeterminada**.

3. En la **** sección suplantación, haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:

    - En la pestaña **Agregar usuarios a proteger** , desactive la protección. A continuación, agregue usuarios, como los miembros del Consejo de su organización, su CEO, director financiero y otros líderes senior. (Puede escribir una dirección de correo electrónico individual o hacer clic en para mostrar una lista).

    - En la pestaña **Agregar dominios para proteger** , Active **incluir automáticamente los dominios que posea**. Si tiene dominios personalizados, agréguelos también.

    - En la ficha **acciones** , seleccione **mover mensaje a las carpetas de correo no deseado de los destinatarios para el** usuario suplantado y para el dominio suplantado, y active las sugerencias de seguridad.

    - En la pestaña inteligencia de buzones de **correo** , asegúrese de que la inteligencia de buzones está activada.

    - En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**.

4. En la **** sección suplantación, haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:

    - En la pestaña **configuración de filtro** de suplantación de identidad, asegúrese de que está activada la protección contra la suplantación de identidad.

    - En la ficha **acciones** , elija Mover mensaje a las carpetas de correo no deseado de los destinatarios.

    - En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**. (Si no realizó ningún cambio, haga clic en **Cancelar**).

5. Cierre la página Configuración de directiva predeterminada.

Para obtener más información sobre las opciones de la Directiva antiphishing, consulte [set up anti-phishing Policies](set-up-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Parte 4: protección contra correo no deseado

[La protección contra correo no deseado](anti-spam-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**anti-spam**de la**Directiva** > de **Administración** > de amenazas.

2. En la ficha **personalizado** , active la **Configuración personalizada** .

3. Expanda **directiva predeterminada de filtro de correo no deseado**, haga clic en **Editar Directiva**y especifique la siguiente configuración:

    - En la sección **correo electrónico no deseado y acciones en masa** , establezca el umbral en un valor de 5 o 6.

    - En la sección **listas** de permitidos, revise (y, si es necesario, Edit) los remitentes y dominios permitidos.

4. Haga clic en **Guardar **.

Para obtener más información sobre las opciones de la Directiva contra correo no deseado, consulte [configurar las directivas contra correo no deseado](configure-the-anti-spam-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Parte 5: configuración adicional para configurar

Además de configurar la protección contra malware, archivos y direcciones URL malintencionadas, suplantación de identidad (phishing) y correo no deseado, le recomendamos que configure las opciones de configuración de registro de auditoría y de purga automática de cero horas.

### <a name="zero-hour-auto-purge-for-email"></a>Purgado automático de cero horas para correo electrónico

[Purga automática de cero horas](zero-hour-auto-purge.md) (ZAP) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). Esta protección está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones para que la protección esté en vigor:

- Las acciones de correo no deseado se establecen para **mover el mensaje a la carpeta correo no deseado** en [las directivas contra correo no deseado](anti-spam-protection.md).

- Los usuarios han mantenido su [configuración](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado.

Para obtener más información, consulte depuración [automática de cero horas-protección contra correo no deseado y malware](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Registro de auditoría para informes e investigación

El registro de auditoría está disponible en las suscripciones que incluyen [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description). Para poder ver los datos de los informes de protección contra amenazas, como el [Panel de seguridad](security-dashboard.md), los informes de [seguridad de correo electrónico](view-email-security-reports.md)y el [Explorador](use-explorer-in-security-and-compliance.md), el registro de auditoría debe estar activado para su organización. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Tareas posteriores a la instalación

Una vez que haya configurado las características de protección contra amenazas, asegúrese de supervisar cómo funcionan estas características, revise y revise las directivas según sea necesario, y vea las nuevas características y actualizaciones de servicio.

|Qué hacer  |Recursos para obtener más información  |
|---------|---------|
|Ver cómo funcionan las características de protección contra amenazas en su organización al ver los informes    |[Panel de seguridad](security-dashboard.md)<br/>[Informes de seguridad de correo electrónico](view-email-security-reports.md)<br/>[Informes para Office 365 ATP](view-reports-for-atp.md)<br/>[Explorador de amenazas](use-explorer-in-security-and-compliance.md)    |
|Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario    |[Puntuación segura](microsoft-secure-score.md)<br/>[Informes inteligentes y perspectivas](reports-and-insights-in-security-and-compliance.md)<br/>[Características de respuesta y investigación de amenazas de Office 365](keep-users-safe-with-office-365-ti.md)          |
|Vea las nuevas características y actualizaciones de servicio     |[Opciones de versión estándar y de destino](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[Centro de mensajes](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descripciones de servicio](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |

---
title: Capacidades de administración de dispositivos móviles integrada para Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.DevicePolicySupportedDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: a1da44e5-7475-4992-be91-9ccec25905b0
description: Administración de dispositivos móviles para Office 365 puede ayudar a proteger y administrar dispositivos móviles como iPhone, iPad, Androids y teléfonos de Windows que se usan en la organización. Crear directivas de administración de dispositivos móviles con opciones de configuración que pueden ayudar a controlar el acceso a correo electrónico de Office 365 y los documentos para dispositivos móviles y aplicaciones de su organización y le permiten borrar un dispositivo de forma remota si lo ha sido robado.
ms.openlocfilehash: b7200eee3b50c2fc6d3e0ea0920236d71837a88b
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272605"
---
# <a name="capabilities-of-built-in-mobile-device-management-for-office-365"></a>Capacidades de administración de dispositivos móviles integrada para Office 365

Administración de dispositivos móviles para Office 365 puede ayudar a proteger y administrar dispositivos móviles como iPhone, iPad, Androids y teléfonos de Windows utilizado por los usuarios con licencia de Office 365 en su organización. Puede crear directivas de administración de dispositivos móviles con la configuración que puede ayudar a controlar el acceso a correo electrónico de Office 365 de su organización y documentos para aplicaciones y dispositivos móviles compatibles. Si un dispositivo está perdido o robado, puede borrado el dispositivo para quitar información confidencial de la organización.
    
¿Necesita más funcionalidad que se incluye en MDM para Office 365? Vea si Microsoft Intune tiene lo que necesita: [Elija entre MDM para Office 365 y Microsoft Intune](choose-between-mdm-and-intune.md).
  
## <a name="supported-devices"></a>Dispositivos admitidos

Puede usar MDM para Office 365 para proteger y administrar los siguientes tipos de dispositivos.
  
- Windows Phone 8.1 +
    
- iOS 7.1 o versiones posteriores
    
- Android 4 o versiones posteriores
    
- Windows 8.1\*
    
- Windows 8.1 RT\*
    
- 10 de Windows\*\*
    
- Windows 10 Mobile\*\*
    
\*Control de acceso para los dispositivos de Windows 8.1 y Windows 8.1 RT está limitada a Exchange ActiveSync.
  
\*\*Requiere el dispositivo para unirse a Azure Active Directory y se inscriben en el servicio de administración de dispositivos móviles de la organización.
  
Si las personas de su organización usar dispositivos móviles que no son compatibles con la administración de dispositivos móviles para Office 365, es posible que desee bloquear el acceso de la aplicación de Exchange ActiveSync para correo electrónico de Office 365 para esos dispositivos, para ayudar a proteger los datos de la organización. Los pasos para bloquear Exchange ActiveSync: vea [Administrar la configuración de acceso de dispositivo](manage-device-access-settings.md).
  
## <a name="access-control-for-office-365-email-and-documents"></a>Control de acceso para los documentos y el correo electrónico de Office 365

Las aplicaciones compatibles para los diferentes tipos de dispositivos móviles en la tabla siguiente le pedirá a los usuarios inscribirse en MDM para Office 365 donde hay una nueva directiva de administración de dispositivo móvil que se aplica a un dispositivo del usuario y el usuario no ha inscrito previamente el dispositivo. Si el dispositivo del usuario no cumple con una directiva, dependiendo de cómo establecer la directiva de, se podría bloquear un usuario pueda tener acceso a recursos de Office 365 en estas aplicaciones, o es posible que tienen acceso pero Office 365 informará una infracción de la directiva.
  
||**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|**Exchange** <br/> Exchange ActiveSync incluye integrado de correo y las aplicaciones de terceros, como informativos, que utilizan Exchange ActiveSync versión 14,1 o posterior.  <br/> |![Icono de Exchange ActiveSync](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Icono de correo de Exchange móvil](media/5b5312b4-3bfb-4fc7-84ff-d7ab21227c10.png)Correo de Exchange  <br/> |![Icono de Exchange ActiveSync](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Icono de iPhone Mail Mobile](media/888bdc7a-8354-4013-a0b2-0d4432a9a92e.png)Correo  <br/> |![Icono de Exchange ActiveSync](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Icono de correo electrónico de Android](media/20b48492-4adc-40ce-99cf-1b47bd2b389d.png)Correo electrónico  <br/> |
|**Office** y **OneDrive para la Empresa** <br/> |Aplicaciones no admitidas  <br/> |![Icono de iPhone Outlook Mobile](media/6c63112d-c10c-4040-85cc-feeccc3dd424.png)Outlook  <br/> ![Icono de iPhone OneDrive Mobile](media/560ec187-82d9-4793-b72f-7ba595972bdc.png)OneDrive  <br/> ![Icono de iPhone Word Mobile](media/63a3a749-1f98-402f-b211-e46b9224b655.png)Word  <br/> ![Icono de iPhone Excel Mobile](media/5b8f62c0-96aa-4602-9ed8-f837bbf5fa9e.png)Excel  <br/> ![Icono de iPhone PowerPoint Mobile](media/17c02dca-f60a-4d13-a610-00d576a40943.png)PowerPoint  <br/> |**En teléfonos y tablets:** <br/> ![Android icono de teléfono y tablet Outlook mobile](media/ed2a813d-f481-46e0-acc9-6422f0d16072.png)Outlook  <br/> ![Icono de teléfono Android OneDrive móvil](media/64855d02-1684-4795-b4c5-863860f18722.png)OneDrive  <br/> ![Icono móvil de Word Android](media/f618fe83-b163-4680-b924-fcedc06ab4ba.png)Word  <br/> ![Icono móvil Excel Android](media/659c7a5f-5797-4b47-a776-4a0c8f784c89.png)Excel  <br/> ![Icono móvil de PowerPoint Android](media/35b98bce-d7cb-40ce-87e3-07b9764207b1.png)PowerPoint  <br/> **Solamente en teléfonos:** <br/> ![Icono de Office móvil móvil](media/1aa9e978-6eb2-40aa-82da-62fb79cee313.png)Office Mobile  <br/> |
   
> [!NOTE]
>  Compatibilidad con iOS 7.1 y versiones posteriores incluye dispositivos iPhone y iPad. > Administración de dispositivos BlackBerry no es compatible con administración de dispositivos móviles para Office 365. Usar BlackBerry Business Cloud Services (BBCS) de BlackBerry para administrar los dispositivos BlackBerry. > No se pedirá a los usuarios inscribirse y que no se bloquee o notificando infracción de la directiva si usan el explorador móvil para tener acceso a sitios de SharePoint de Office 365, documentos en Office Online, o el correo electrónico en Outlook Web App. 
  
El siguiente diagrama muestra lo que sucede cuando un usuario con un nuevo dispositivo inicia sesión en una aplicación que es compatible con control de acceso con MDM para Office 365. El usuario está bloqueado el acceso a recursos de Office 365 en la aplicación hasta que inscribirse en su dispositivo.
  
![Muestra el proceso de inscripción para el nuevo dispositivo.](media/O365-MDM-Capabilities-EnrollmentExample.png)
  
> [!NOTE]
> Directivas y reglas de acceso creadas en MDM para Office 365 invalidará las directivas de buzón de correo de dispositivos móviles de Exchange ActiveSync y las reglas de acceso de dispositivo creado en el centro de administración de Exchange. Después de que un dispositivo está inscrito en MDM para Office 365, cualquier directiva de buzón de Exchange ActiveSync dispositivo móvil o se omitirá la regla de acceso de dispositivo aplicado para el dispositivo. Para obtener más información acerca de Exchange ActiveSync, consulte [Exchange ActiveSync en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380). 
  
## <a name="policy-settings-for-mobile-devices"></a>Configuración de directivas para dispositivos móviles

Si crea una directiva para bloquear el acceso con determinadas opciones de activado, se bloqueará a los usuarios tengan acceso a recursos de Office 365 cuando se usa una aplicación compatible que aparece en el [control de acceso para los documentos y correo electrónico de Office 365](#access-control-for-office-365-email-and-documents). La configuración que puede impedir que los usuarios obtener acceso a recursos de Office 365 se encuentran en estas secciones:
  
- Seguridad
    
- Cifrado
    
- Liberación
    
- Perfil de correo electrónico administrado
    
Por ejemplo, el siguiente diagrama muestra lo que sucede cuando un usuario con un dispositivo inscrito no es compatible con una configuración de seguridad de una directiva de administración de dispositivo móvil que se aplica a su dispositivo. El usuario inicia sesión una aplicación que es compatible con control de acceso con MDM para Office 365. Se impide obtener acceso a recursos de Office 365 en la aplicación hasta que su dispositivo cumple con la configuración de seguridad.
  
![Muestra que el usuario se bloquea cuando el dispositivo no es compatible.](media/O365-MDM-Capabilities-ComplianceExample.png)
  
Las secciones siguientes muestran la configuración de directiva que puede usar para ayudar a proteger y administrar los dispositivos móviles que se conectan a recursos de Office 365 de su organización. 
  
### <a name="security-settings"></a>Configuración de seguridad

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Requerir contraseña  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Evitar contraseña sencilla  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Exigir una contraseña alfanumérica  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Longitud mínima de la contraseña  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Número de errores de inicio de sesión antes de que se eliminen datos del dispositivo  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Minutos de inactividad antes de que se bloquee el dispositivo  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Expiración de contraseña (días)  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Recordar el historial de contraseñas y evitar la reutilización  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="encryption-settings"></a>Configuración de cifrado

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Requerir cifrado de datos en los dispositivos  <br/> |Windows Phone 8.1 ya está cifrado y no se puede descifrar  <br/> |✖  <br/> |✔  <br/> |✔\*  <br/> |
   
\*Con Samsung Knox, también puede requerir cifrado en tarjetas de almacenamiento.
  
### <a name="jail-broken-setting"></a>Configuración de liberación

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|El dispositivo no puede liberarse ni tener acceso raíz  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="managed-email-profile-option"></a>Opción de perfil de correo electrónico administrado

La siguiente opción puede impedir que los usuarios obtener acceso a su correo electrónico de Office 365, si está usando un perfil de correo electrónico creada manualmente. Los usuarios de dispositivos iOS deben eliminar su perfil de correo electrónico creada manualmente antes de tener acceso a su correo electrónico. Después de eliminar el perfil, se creará automáticamente un nuevo perfil en el dispositivo.
  
|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|El perfil de correo electrónico es administrado  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="cloud-settings"></a>Configuración de nube

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Bloquear copia de seguridad de la nube  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Bloquear sincronización de documentos  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Bloquear sincronización de fotos  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Permitir la copia de seguridad de Google  <br/> |N/D  <br/> |N/D  <br/> |✖  <br/> |✔  <br/> |
|Permitir la sincronización automática de cuenta de Google  <br/> |N/D  <br/> |N/D  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="system-settings"></a>Configuración del sistema

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Bloquear captura de pantalla  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|Bloquear el envío de datos de diagnóstico de dispositivos  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="application-settings"></a>Configuración de aplicaciones

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Bloquear las videoconferencias en el dispositivo  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Bloquear el acceso a la tienda de aplicaciones  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|Requerir contraseña al acceder a la tienda de aplicaciones  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="device-capabilities-settings"></a>Configuración de las funcionalidades del dispositivo

|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4+**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|:-----|
|Bloquear conexión con almacenamiento extraíble  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|Bloquear conexión Bluetooth  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="additional-settings"></a>Opciones adicionales

Puede establecer la siguiente configuración de directiva adicionales mediante el uso de los cmdlets de PowerShell. Para obtener más información, vea [Office 365 seguridad &amp; centro de cumplimiento cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=827804).
  
|**Nombre de la opción**|**Windows Phone 8.1 +**|**iOS 7.1 +**|**Android 4 + (incluido a Samsung Knox)**|
|:-----|:-----|:-----|:-----|
|CameraEnabled  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|RegionRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MoviesRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|TVShowsRating  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AppsRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceDialing  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceAssistant  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowAssistantWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowPassbookWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MaxPasswordGracePeriod  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|PasswordQuality  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|SystemSecurityTLS  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|WLANEnabled  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="settings-supported-by-windows"></a>Configuración compatibles con Windows

Puede administrar los dispositivos de Windows 8.1 y 10 de Windows al inscribirse a ellos como dispositivos móviles. Una vez se haya implementado una directiva aplicable, los usuarios con los dispositivos de Windows 8.1 RT y Windows 10 RT se necesitará para inscribirse en MDM para Office 365 la primera vez que usen la aplicación de correo electrónico integrada para tener acceso a su correo electrónico de Office 365. 
  
Se admiten las siguientes opciones para dispositivos Windows 8.1 y 10 de Windows que están inscritos como dispositivos móviles. Estos valores de configuración no impida que los usuarios tengan acceso a recursos de Office 365.
  
 **Configuración de seguridad**
  
- Exigir una contraseña alfanumérica
    
- Longitud mínima de la contraseña
    
- Número de errores de inicio de sesión antes de que se eliminen datos del dispositivo
    
- Minutos de inactividad antes de que se bloquee el dispositivo
    
- Expiración de contraseña (días)
    
- Recordar el historial de contraseñas y evitar la reutilización
    
 **Configuración del sistema**
  
Bloquear el envío de datos de diagnóstico de dispositivos
  
 **Configuración adicional**
  
Puede establecer las siguientes opciones de directiva adicionales usando cmdlets de PowerShell:
  
- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus
    
- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    
## <a name="remotely-wipe-a-mobile-device"></a>Borrar de forma remota un dispositivo móvil

 Si un dispositivo está perdido o robado, puede quitar datos confidenciales de la organización y ayudar a impedir el acceso a recursos de Office 365 de su organización siguiendo un borrado de seguridad ** &amp; centro de cumplimiento\>prevención de pérdida de datos\>dispositivo administración de**. Se puede realizar un borrado selectivo para quitar sólo datos de la organización o un borrado completo para eliminar toda la información desde un dispositivo y restaurar a su configuración de fábrica.
  
Para obtener más información, consulte [Borrar un dispositivo móvil en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518157).
  
## <a name="see-also"></a>Vea también

[Introducción a la administración de dispositivos móviles para Office 365](overview-of-mdm.md)
  
[Crear e implementar directivas de seguridad de dispositivos](create-device-security-policies.md)


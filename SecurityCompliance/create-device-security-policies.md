---
title: Crear e implementar directivas de seguridad de dispositivos
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/9/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewDevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: d310f556-8bfb-497b-9bd7-fe3c36ea2fd6
description: 'Pasos para crear e implementar directivas de seguridad para la administración de dispositivos móviles en Office 365 que pueden ayudar a protegen la información de su organización en Office 365 obtenga acceso no autorizado. '
ms.openlocfilehash: ab1fc1960a3e55eb3080dde7df0ec742c58b2cc7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272075"
---
# <a name="create-and-deploy-device-security-policies"></a>Crear e implementar directivas de seguridad de dispositivos

Puede usar Administración de dispositivos móviles para Office 365 para crear directivas de seguridad que ayudan a proteger la información de su organización en Office 365 obtenga acceso no autorizado. Puede aplicar directivas a cualquier dispositivo móvil en la organización, donde el usuario del dispositivo tiene una licencia de Office 365 aplicables y el dispositivo en MDM haya inscrito para Office 365.
  
## <a name="before-you-begin"></a>Antes de empezar

- Obtenga información sobre los dispositivos, aplicaciones de dispositivo móvil y configuración de seguridad que admite MDM para Office 365. Consulte [las capacidades de administración de dispositivos móviles para Office 365](capabilities-of-mobile-device-management.md).
    
- Crear grupos de seguridad que se incluyen los usuarios de Office 365 que se desean implementar directivas para y para los usuarios que desea impedir que bloqueó el acceso a Office 365. Se recomienda que, antes de implementar una nueva directiva para la organización, se prueba la directiva mediante la implementación para un pequeño número de usuarios. Puede crear y utilizar un grupo de seguridad que incluye sólo usted o un pequeño número Office 365 a los usuarios que pueden comprobar la directiva. Para obtener más información acerca de los grupos de seguridad, vea [crear, editar o eliminar un grupo de seguridad](https://go.microsoft.com/fwlink/p/?LinkId=518555).
    
- **Importante:** Antes de poder crear una directiva de dispositivo móvil, debe activar y configurar MDM para Office 365. Vea [información general de administración de dispositivos móviles para Office 365](overview-of-mdm.md).
    
- Para crear e implementar directivas de administración de dispositivos móviles en Office 365, debe ser un administrador global de Office 365. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).
    
- Antes de implementar las directivas, que la organización sepan los impactos potenciales de inscripción de un dispositivo en MDM para Office 365. Dependiendo de cómo configurar las directivas, se pueden bloquear dispositivos no conformes tengan acceso a Office 365 y datos, incluidas las aplicaciones instaladas, fotos e información personal en un dispositivo inscrito, se pueden eliminar.
    
> [!NOTE]
> Directivas y reglas de acceso creadas en MDM para Office 365 invalidará las directivas de buzón de correo de dispositivos móviles de Exchange ActiveSync y las reglas de acceso de dispositivo creado en el centro de administración de Exchange. Después de que un dispositivo está inscrito en MDM para Office 365, cualquier directiva de buzón de Exchange ActiveSync dispositivo móvil o se omitirá la regla de acceso de dispositivo aplicado para el dispositivo. Para obtener más información acerca de Exchange ActiveSync, consulte [Exchange ActiveSync en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380). 
  
## <a name="step-1-create-a-security-policy-and-deploy-to-a-test-group"></a>Paso 1: Crear una directiva de seguridad e implementar en un grupo de pruebas

Antes de empezar, asegúrese de que ha activado y configurado MDM para Office 365. Para obtener instrucciones, vea [Información general de administración de dispositivos móviles para Office 365](overview-of-mdm.md) . 
  
1. En Office 365, en la seguridad &amp; centro de cumplimiento, vaya a la **prevención de pérdida de datos** \> **las directivas de seguridad de dispositivo**.
    
    > [!NOTE]
    > Las **directivas de seguridad de dispositivo** aparecerá en el menú sólo después de que ha activado la administración de dispositivos móviles. 
  
2. Elija **+ crear una directiva**.
    
    ![Creación de una directiva de dispositivo MDN bajo las directivas de seguridad de dispositivo](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
3. Especifique un **nombre** y una **Descripción** para la nueva directiva y, a continuación, elija **siguiente**.
    
    ![Establecer un nombre para la directiva de seguridad de dispositivo](media/d382e845-4a7f-4f72-8a09-813ea4cbd0c4.png)
  
4. En la **¿Qué requisitos desea tener en dispositivos?** de página, especificar los requisitos que desea aplicar a los dispositivos móviles en su organización y, a continuación, elija **siguiente**.
    
    ![La página de configuración en la directiva de seguridad de dispositivo](media/186b3bd5-5e3d-4059-978f-94113111a8ca.png)
  
5. En la **¿Qué desea configurar?** de página, especifique cualquier requisito adicional que desea aplicar a los dispositivos móviles en su organización y, a continuación, elija **siguiente**.
    
6. En el **¿desea aplicar ahora esta directiva?** de página, elija **Sí**y, a continuación, elija **+ Agregar**. 
    
    ![Agregar la directiva](media/89ab7cab-1b7a-4c78-9aa6-3db7d7667f8e.png)
  
7. Seleccione los grupos que va a probar la directiva antes de implementarlo en su organización y, a continuación, elija **Agregar**.
    
8. Elija **Siguiente**.
    
9. Revise y confirme los detalles de la nueva directiva de dispositivo y, a continuación, elija **crear esta directiva**.
    
    ![Elija crear esta directiva para crear una directiva de dispositivo de finsih](media/e410bcf3-8a36-44ed-9fea-00e742db06fb.png)
  
10. Haga clic en **Cerrar**.
    
Cada usuario que se aplica la directiva tendrá la directiva que se envían a sus dispositivos la próxima vez que inicie sesión en Office 365 con su dispositivo móvil. Si los usuarios no han tenido una directiva aplicada a su dispositivo móvil antes, a continuación, después de implementar la directiva, recibirá una notificación en su dispositivo que incluye los [pasos para inscribirse y activar MDM para Office 365](https://go.microsoft.com/fwlink/?LinkId=615272). Hasta que se complete inscripción, se restringen el acceso a correo electrónico, OneDrive y otros servicios. Después de completar la inscripción mediante la aplicación de Portal de empresa Intune, podrá usar los servicios y la directiva se aplicará a su dispositivo.
  
## <a name="step-2-verify-your-policy-works"></a>Paso 2: Comprobar el funcionamiento de la directiva

Después de haber creado una directiva de seguridad, debe comprobar que la directiva funciona según lo previsto antes de implementarlo en su organización.
  
1. En Office 365, vaya a **seguridad &amp; centro de cumplimiento** \> **prevención de pérdida de datos** \> **administración de dispositivos**.
    
2. En la página **Administración de dispositivos móviles para Office 365** , compruebe el estado de los dispositivos de usuario que tienen aplicada la directiva. Puede filtrar u ordenar por **todos los** para ver todos los dispositivos o **bloqueado** para ver los dispositivos bloqueados. 
    
    ![Ver los dispositivos que son administrados por MDM](media/5c9fd069-b716-40d8-9b36-f9cfeae2139f.png)
  
3. También puede hacer una limpieza completa o selectiva en el dispositivo. Para obtener instrucciones, consulte [Borrar un dispositivo móvil en Office 365](wipe-a-mobile-device.md).
    
## <a name="step-3-deploy-a-policy-to-your-organization"></a>Paso 3: Implementar una directiva para su organización

Una vez que haya creado una directiva de dispositivo móvil y verificado que funciona según lo previsto, implementarlo en su organización.
  
1. En Office 365, vaya a **seguridad &amp; centro de cumplimiento** \> **prevención de pérdida de datos** \> **las directivas de seguridad de dispositivo**.
    
2. Seleccione la directiva que desea implementar y seleccione **Editar directiva** en el \< _nombre de la directiva_ \> panel.  
    
3. Seleccione la pestaña **Implementación**. 
    
4. En la ficha **implementación** , elija **Sí** por encima de **seleccionar uno o más grupos de seguridad que contienen las personas a las que desea aplicar esta directiva a** y, a continuación, **Agregar**.
    
  - En el panel **Seleccionar un grupo** , puede buscar un grupo agregar, puede filtrar por alias o por nombre para mostrar. También puede agregar un grupo existente de la lista de **grupos** . 
    
    Puede agregar varios grupos para aplicar la directiva.
    
    Seleccione **Agregar** en la parte inferior del panel. 
    
5. En la ficha **implementación** , elija **Guardar** . 
    
    ![Implemente directivas MDM en la organización.](media/dc3e7fe5-201a-4e45-abe3-fc93e0b59028.png)
  
Cada usuario que se aplica la directiva tendrá la directiva que se envían a sus dispositivos la próxima vez que inician sesión en Office 365 desde su dispositivo móvil. Si los usuarios no han tenido una directiva aplicada a su dispositivo móvil, podrá [obtener una notificación en su dispositivo](https://go.microsoft.com/fwlink/?LinkId=615272) con pasos para inscribirse y activarlo para MDM para Office 365. Una vez que han terminado la inscripción, la directiva se aplicará a su dispositivo. 
  
## <a name="step-4-block-email-access-for-unsupported-devices"></a>Paso 4: Bloquear correo electrónico el acceso a dispositivos no compatibles

Para ayudar a proteger la información de su organización, debe bloquear el acceso de aplicación para correo electrónico de Office 365 para dispositivos móviles que no son compatibles con MDM para Office 365. Vea [las capacidades de administración de dispositivos móviles integrada para Office 365](capabilities-of-mobile-device-management.md) para obtener una lista de los dispositivos que son compatibles. Para hacer esto: 
  
1. Vaya a seguridad &amp; centro de cumplimiento\> **prevención de pérdida de datos** \> **las directivas de seguridad de dispositivo**.
    
2. Seleccione **Administrar la configuración de acceso de dispositivo de toda la organización**.
    
    ![Ir al centro de cumplimiento de normas \> dispositivos y haga clic en vincula la configuración de acceso del dispositivo de administrar.](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. Para bloquear los dispositivos no compatibles, elija **Bloquear** en **Si un dispositivo no es compatible con MDM para Office 365, ¿desea permitir o bloquear desde con una cuenta de Exchange para obtener acceso a correo electrónico de la organización** \> **Guardar**.
  
## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Paso 5: Elija los grupos de seguridad que desea excluir de las comprobaciones de acceso condicional

Si desea excluir algunas personas de las comprobaciones de acceso condicional en sus dispositivos móviles y ha creado uno o más grupos de seguridad para estas personas, agregue los grupos de seguridad aquí. Los usuarios de estos grupos no tendrán ninguna directiva exigida para sus dispositivos móviles admitidos.
  
1. Vaya a seguridad &amp; centro de cumplimiento\> **prevención de pérdida de datos** \> **las directivas de seguridad de dispositivo**.
    
2. Seleccione **Administrar la configuración de acceso de dispositivo de toda la organización**.
    
    ![Ir al centro de cumplimiento de normas \> dispositivos y haga clic en vincula la configuración de acceso del dispositivo de administrar.](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. Seleccione **Agregar** para agregar el grupo de seguridad que tiene usuarios que le gustaría usar para impedir que se ha bloqueado el acceso a Office 365. Cuando un usuario se ha agregado a esta lista, podrá tener acceso a correo electrónico de Office 365 cuando se usa un dispositivo no compatible. 
    
4. Seleccione el grupo de seguridad que desea usar en el panel **Seleccione grupo** . 
    
5. Seleccione el nombre y, a continuación, en **Agregar** \> **Guardar**.
    
6. En el panel **configuración de acceso de dispositivo de toda la organización** , elija **Guardar**.
  
## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>¿Cuál es el impacto de las directivas de seguridad en distintos tipos de dispositivos?

Al aplicar una directiva a los dispositivos de usuario, el impacto en cada dispositivo varía ligeramente entre los distintos tipos de dispositivos. Consulte la siguiente tabla para obtener ejemplos del impacto de las directivas en diferentes dispositivos.
  


|**Directiva de seguridad**|**Windows Phone 8.1 +**|**Android 4+**|**Samsung Knox**|**IOS 6 +**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |Se requiere copia de seguridad cifrada de iOS.  <br/> |
|Bloquear copia de seguridad de la nube  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |Bloquear copia de seguridad de Google en Android (atenuado), copia de seguridad de la nube en iOS.  <br/> |
|Bloquear sincronización de documentos  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS: Bloquear documentos en la nube.  <br/> |
|Bloquear sincronización de fotos  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS (nativo): Bloquear Photo Stream.  <br/> |
|Bloquear captura de pantalla  <br/> |✔  <br/> |X  <br/> |✔  <br/> |✔  <br/> |Se bloquea cuando se intenta.  <br/> |
|Bloquear videoconferencia  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |Se bloquea FaceTime en iOS, no Skype u otros.  <br/> |
|Bloquear el envío de datos de diagnóstico  <br/> |✖  <br/> |X  <br/> |✔  <br/> |✔  <br/> |Bloquear el envío de informes de bloqueo de Google en Android.  <br/> |
|Bloquear el acceso a la tienda de aplicaciones  <br/> |✔  <br/> |X  <br/> |✔  <br/> |✔  <br/> |Falta el icono de la tienda de aplicaciones en la página principal de Android, está deshabilitado en Windows, falta en iOS.  <br/> |
|Requerir contraseña para la tienda de aplicaciones  <br/> |✖  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |iOS: Contraseña necesaria para las compras de iTunes.  <br/> |
|Bloquear conexión a almacenamiento extraíble  <br/> |✔  <br/> |X  <br/> |✔  <br/> |N/D  <br/> |Android: La tarjeta SD aparecerá atenuada en la configuración, Windows notifica al usuario, las aplicaciones instaladas no están disponibles  <br/> |
|Bloquear conexión Bluetooth  <br/> |✔  <br/> |\*\*\*  <br/> |\*\*\*  <br/> |✖  <br/> |\*\*\*No podemos deshabilitamos BlueTooth como una opción de configuración en Android. En su lugar, se deshabilitación todas las transacciones que requieren BlueTooth: distribución avanzada de Audio, Control remoto de Audio y vídeo, los dispositivos de manos libres, auriculares con micrófono, acceso de la libreta de direcciones y puerto serie. Cuando se usa alguno de estos, aparece un mensaje de notificación emergente pequeña en la parte inferior de la página.  <br/> |
   
## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>¿Qué ocurre al eliminar una directiva o quitar un usuario de la directiva?

Al eliminar una directiva o quitar un usuario de un grupo al que la directiva se implementó en, la configuración de directiva, perfiles de correo electrónico de Office 365 y mensajes de correo electrónico almacenados en caché pueden quitarse el dispositivo del usuario. Vea la siguiente tabla para ver los elementos que se quitaron para los distintos tipos de dispositivos:
  
|**Lo que se quita**|**Windows Phone 8.1 +**|**iOS 6 +**|**Android 4 + (incluido a Samsung Knox)**|
|:-----|:-----|:-----|:-----|
|Perfiles de correo electrónico administradas\*  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|Configuración de directivas  <br/> |✔  <br/>           Excepto en el caso de **Bloquear el envío de datos de diagnóstico de dispositivos**. <br/> |✔  <br/> |✖  <br/> |
   
> [!NOTE]
> \*Si la directiva se implementó con la opción de **perfil de correo electrónico se administra** seleccionado, a continuación, el perfil de correo electrónico administradas y almacena en caché los correos electrónicos en que se eliminará el perfil desde el dispositivo del usuario. 
  
Cada usuario que aplica la directiva se ha quitado tendrá la directiva que se ha quitado desde su dispositivo la próxima vez que se comprueba su dispositivo móvil con MDM para Office 365. Si implementa una nueva directiva que se aplica a dispositivos los usuarios en estos, se pedirá a volver a inscribirse en MDM para Office 365.
  
También puede [Borrar un dispositivo](wipe-a-mobile-device.md), ya sea completamente o selectivamente Barrido hacia la información de la organización desde el dispositivo.
  
## <a name="related-topics"></a>Temas relacionados

[Introducción a la administración de dispositivos móviles para Office 365](overview-of-mdm.md)
  
[Funcionalidades de administración de dispositivos móviles para Office 365](capabilities-of-mobile-device-management.md)
  


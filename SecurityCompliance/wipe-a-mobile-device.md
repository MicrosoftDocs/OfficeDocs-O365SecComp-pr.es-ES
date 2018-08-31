---
title: Barrido hacia un dispositivo móvil en Office 365
ms.author: dianef
author: dianef77
manager: scotv
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_WipeDevice
- O365E_WipeDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9d727c7d-8b47-4499-bf24-d046b449214c
description: Puede usar Administración de dispositivos móviles integrada para Office 365 para realizar un borrado selectivo para quitar sólo información de la organización o un borrado completo para eliminar toda la información desde un dispositivo móvil y restaurar a su configuración de fábrica.
ms.openlocfilehash: d3eb28575924ca3bb4a647ae9af2f96b55116a53
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272505"
---
# <a name="wipe-a-mobile-device-in-office-365"></a>Barrido hacia un dispositivo móvil en Office 365
  
Puede usar Administración de dispositivos móviles integrada para Office 365 para realizar un borrado selectivo para quitar sólo información de la organización o un borrado completo para eliminar toda la información desde un dispositivo móvil y restaurar a su configuración de fábrica.
  
## <a name="what-to-know-before-you-begin"></a>Lo que debe saber antes de empezar

- Dispositivos móviles pueden almacenar información confidencial de la organización y proporcionar acceso a los recursos de Office 365 de su organización. Para ayudar a proteger la información de su organización, puede hacer una limpieza completa o un borrado selectivo:
    
  - **Borrado completo**: elimina todos los datos en el dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, fotos e información personal. Una vez finalizada la eliminación, el dispositivo se restaura a su configuración de fábrica. 
    
  - **Barrido hacia la selectiva**: quita sólo datos de la organización y aplicaciones abandona instalado, fotos e información personal en el dispositivo móvil de un usuario. 
    
- Cuando se suprime un dispositivo (borrado completa o selectiva borrado), el dispositivo se quita de la lista de los dispositivos administrados.
    
- Puede configurar una directiva de administración de dispositivos móviles que elimina automáticamente (borrado completo) un dispositivo después de que el usuario intenta escribir la contraseña del dispositivo sin éxito un número específico de veces. Siga los pasos descritos en [crear e implementar directivas de seguridad de dispositivo](create-device-security-policies.md).
    
- Si desea conocer lo que un usuario no experimentará cuando borrar su dispositivo, consulte [Cuál es el impacto de usuario y del dispositivo?](wipe-a-mobile-device.md#BKMK_Impact).
    
## <a name="wipe-a-mobile-device"></a>Barrido hacia un dispositivo móvil

1. Vaya a la [ ![haga clic aquí para ir al centro de administración de Office 365.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

2. Vaya a [vaya a la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) \> **prevención de pérdida de datos** \> **administración de dispositivos**.
    
3. Seleccione el dispositivo que desea borrar.
    
4. Seleccione el tipo de borrado remoto que desea realizar.
    
  - Para realizar un borrado selectivo y eliminar sólo Office 365 información de la organización, en el panel derecho, seleccione **Borrar selectiva**.
    
  - Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, en el panel derecho, seleccione **borrado completo**.
    
![Seleccione un dispositivo y, a continuación, elija el tipo de barrido para hacer.](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. Seleccione **Sí** para confirmar. 
    
Hasta que finalice el borrado, el **estado del dispositivo** se mostrarán como **RetirePending** o **RetireIssued**.
  
### <a name="how-do-i-know-it-worked"></a>¿Cómo se puede saber que ha funcionado?

Ya no se verá el dispositivo móvil en la lista de los dispositivos administrados.
  
## <a name="why-would-you-want-to-wipe-a-device"></a>¿Por qué que desea borrar un dispositivo?

Existen varias razones para barrido de dispositivos:
  
- Dispositivos móviles como smartphones y tabletas se están convirtiendo en más completo todo el tiempo. Esto significa que es más fácil para los usuarios almacenar información corporativa confidencial (por ejemplo, de identificación personal o comunicaciones confidenciales) y obtener acceso a él en cualquier lugar. Si uno de estos dispositivos móviles está perdido o robado, barrido inmediatamente el dispositivo puede ayudar a evitar que la información de su organización desde la copia de seguridad que terminan en manos incorrectos.
    
- Cuando un usuario sale de la organización con un dispositivo personal que está inscrito en MDM para Office 365, puede ayudar a impedir que la información organizativa en marcha con el que el usuario realizando un borrado selectivo.
    
- Si su organización proporciona dispositivos móviles a los usuarios, es posible que necesite reasignar los dispositivos de vez en cuando. Realizar un borrado completo en un dispositivo antes de asignar a un usuario nuevo, le ayuda a se asegura de que cualquier información confidencial por parte del propietario anterior se ha eliminado.
    
## <a name="whats-the-user-and-device-impact"></a>¿Qué es el usuario y el impacto de dispositivo?

La eliminación se envía inmediatamente al dispositivo móvil. El dispositivo también está marcado como no compatible en AAD.
  
En la siguiente tabla se describe el contenido que se ha quitado para cada tipo de dispositivo cuando un dispositivo de forma selectiva se borra.
  
|**Impacto de contenido**|**Windows Phone 8.1**|**iOS 7.1 +**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|Aplicación de Portal de empresa\* se ha desinstalado.  <br/> |N/D  <br/> |✔  <br/> |N/D  <br/> |
|Datos de aplicación de Office 365 hospedados por aplicaciones donde el control de acceso es compatible con MDM para Office 365 están se ha quitado (Outlook actualmente y OneDrive para la empresa). No se quitan las aplicaciones.  <br/> Outlook para Android no elimina los mensajes de correo electrónico almacenados en caché.  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Configuración de la directiva que se han aplicado por MDM para Office 365 a los dispositivos ya no se aplica en el dispositivo y los usuarios pueden cambiar la configuración.  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|Se quitan los perfiles de correo electrónico creada por MDM para Office 365 y se elimina el correo electrónico almacenado en caché en el dispositivo.  <br/> |N/D  <br/> |✔  <br/> |N/D  <br/> |
   
> [!NOTE]
> \*Aplicación de Portal de empresa está disponible en la tienda de aplicaciones para iOS y el almacén de reproducir para dispositivos Android. 
  
## <a name="related-content"></a>Contenido relacionado

[Administrar dispositivos móviles en Office 365](set-up-mobile-device-management.md)
  


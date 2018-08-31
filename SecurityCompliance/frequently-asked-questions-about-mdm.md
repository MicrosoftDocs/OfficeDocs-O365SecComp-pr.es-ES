---
title: Preguntas más frecuentes acerca de la administración de dispositivos móviles para Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 3871f99c-c9db-4a23-86f9-902c1b02f58d
description: Este artículo contiene las preguntas más frecuentes acerca de Mobile Device Management (MDM) para Office 365, una característica que le ayuda a administrar y proteger los dispositivos móviles en Office 365.
ms.openlocfilehash: 6c4a5b3603d392b3d83769cd0f17450ce70565be
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272275"
---
# <a name="frequently-asked-questions-about-mobile-device-management-for-office-365"></a>Preguntas más frecuentes acerca de la administración de dispositivos móviles para Office 365

Este artículo contiene las preguntas más frecuentes acerca de Mobile Device Management (MDM) para Office 365, una característica que le ayuda a administrar y proteger los dispositivos móviles en Office 365.
  
## <a name="faqs"></a>Preguntas más frecuentes

- [¿Cómo puedo obtener MDM para Office 365? No se puede ver en el centro de administración de Office 365](#how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center)
    
- [¿Cómo comenzar con la administración de dispositivos de MDM](#how-can-i-get-started-with-device-management-in-mdm)
    
- [Estoy intentando configurar MDM pero parece estar colapsado. Ha sido que muestra el estado del servicio Office 365 "aprovisionamiento" durante un tiempo. ¿Qué puedo hacer?](#im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do)
    
- [¿Qué puedo hacer si se produce un error en la inscripción del dispositivo?](#what-can-i-do-if-device-enrollment-fails)
    
- [¿Cuál es la diferencia entre Intune y MDM para Office 365?](#whats-the-difference-between-intune-and-mdm-for-office-365)
    
- [¿Cómo funcionan las directivas para MDM? ¿Cómo configuro ellos? ¿Deshabilitarlas?](#how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them)
    
- [¿Cambiar de administración de dispositivos de Exchange ActiveSync a MDM para Office 365?](#can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365)
    
- [Configuro MDM pero ahora desea quitarlo. ¿Cuáles son los pasos?](#i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps)
    
- [Sigue necesitando ayuda](#still-need-help)
    
## <a name="how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center"></a>¿Cómo puedo obtener MDM para Office 365? No se puede ver en el centro de administración de Office 365

Hemos completado implantar esta característica para los clientes de Office 365. Busque la ficha de **Administración de dispositivos** en la [vaya a la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8). Si no lo ve, háganoslo saber. Vea [aún necesita ayuda?](#still-need-help), y le ayudaremos a empezar a trabajar. 
  
## <a name="how-can-i-get-started-with-device-management-in-mdm"></a>¿Cómo comenzar con la administración de dispositivos de MDM

Hay cuatro pasos para empezar a trabajar con MDM para Office 365 (obtener información detallada en [Set up Mobile Device Management (MDM) en Office 365](set-up-mobile-device-management.md)):
  
1. **Activar MDM.** Vaya a la [vaya a la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) y seleccione **administración de dispositivos**. Haga clic en **vamos a empezar** a iniciar el proceso de activación. 
    
2. **Completar la configuración para MDM**. Esto podría requerir la configuración de certificados APN y actualizaciones para los registros DNS para su dominio. 
    
3. **Crear directivas**. Crear directivas de administración de dispositivos y aplicarla a grupos de usuarios que están [configurados en grupos de seguridad](create-device-security-policies.md). Se recomienda que inicie mediante la implementación de las directivas a un grupo de prueba pequeño. En la seguridad &amp; centro de cumplimiento, seleccione **las directivas de seguridad de dispositivo**.
    
4. **Los usuarios inscribirse dispositivos.** Los usuarios que han tenido una directiva aplicada a ellos le pide que [inscribirse en sus dispositivos](enroll-your-mobile-device.md) cuando intenten tener acceso a datos de Office 365 (mediante su cliente de correo electrónico, por ejemplo). 
    
## <a name="im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estoy intentando configurar MDM pero parece estar colapsado. Ha sido que muestra el estado del servicio Office 365 "aprovisionamiento" durante un tiempo. ¿Qué puedo hacer?

Puede tardar algún tiempo en obtener listo para que el servicio. Cuando se complete el aprovisionamiento, verá la administración de dispositivos móviles para la página de Office 365. Si ha esperado a 24 horas y el estado sigue siendo **aprovisionamiento**, vea [aún necesita ayuda?](#still-need-help) y ayudaremos a saber cuál es el problema. 
  
## <a name="what-can-i-do-if-device-enrollment-fails"></a>¿Qué puedo hacer si se produce un error en la inscripción del dispositivo?

Si tiene algún problema a un dispositivo inscriben, intente primero comprobar lo siguiente:
  
- Asegúrese de que el dispositivo no está ya inscrito con otro proveedor de administración de dispositivos móviles, como Intune.
    
- Asegúrese de que el dispositivo está configurado para la fecha y hora correctas.
    
- Cambie a un diferente Wi-Fi o la red de telefonía móvil en el dispositivo.
    
- Para los dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación de Portal de empresa Intune en el dispositivo.
    
Si sigue inscripción no funciona, [intente estos pasos adicionales para solucionar problemas](troubleshoot-mdm.md).
  
## <a name="whats-the-difference-between-intune-and-mdm-for-office-365"></a>¿Cuál es la diferencia entre Intune y MDM para Office 365?

Ambos MDM para Office 365 y Intune proporcionan soluciones basadas en la nube para la administración de dispositivos de la organización. Use esta [comparación en paralelo](choose-between-mdm-and-intune.md) de los dos servicios que le ayudarán a decidir si usar Intune o MDM para Office 365 es perfecto para usted. 
  
## <a name="how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them"></a>¿Cómo funcionan las directivas para MDM? ¿Cómo configuro ellos? ¿Deshabilitarlas?

Después de completar el programa de instalación inicial de MDM para Office 365, [crear directivas y aplicarlos a grupos de usuarios](create-device-security-policies.md) en [vaya a la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8). Para los usuarios que se aplican las directivas a las directivas requieren que los usuarios inscribirse en sus dispositivos en MDM Office 365 antes de que el dispositivo se puede usar para tener acceso a datos de Office 365. Las directivas que ha configurado determinan la configuración de dispositivos móviles, por ejemplo, ¿con qué frecuencia se deben restablecer contraseñas o si se requiere cifrado de datos. 
  
Se proporcionan instrucciones paso a paso para [crear e implementar directivas de seguridad de dispositivo](create-device-security-policies.md). Crear las directivas en la seguridad &amp; centro de cumplimiento y se pueden deshabilitar una o varias directivas mediante la devolución a la seguridad &amp; centro de cumplimiento y la directiva de edición para quitar el grupo aplicado. O bien, puede elegir no quitar por completo la directiva.
  
Si desea excluir un grupo específico de usuarios de que se ven afectados por directivas, a continuación, puede agregar un grupo al grupo de exclusión. En la seguridad &amp; centro de cumplimiento, en la ficha **dispositivos** , seleccione **Administrar la configuración de acceso de dispositivo**y, a continuación, agregue el grupo de la **¿hay algún grupo de seguridad que desea excluir del control de acceso?** sección. 
  
## <a name="can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365"></a>¿Cambiar de administración de dispositivos de Exchange ActiveSync a MDM para Office 365?

Si ya utiliza [las directivas de Exchange ActiveSync](https://go.microsoft.com/fwlink/?LinkId=615145) para administrar dispositivos móviles, puede empezar a usar MDM para Office 365, siga los pasos para [establecer la seguridad de Mobile Device Management (MDM) en Office 365](set-up-mobile-device-management.md).
  
Al aplicar las directivas que se crean en MDM para Office 365 a los grupos de usuarios, estas directivas reemplazan las directivas de buzón de correo de dispositivos móviles de Exchange ActiveSync y las reglas de acceso de dispositivo que haya creado previamente en el centro de administración de Exchange para esos usuarios. 
  
Después de que un dispositivo está inscrito en MDM para Office 365, cualquier directiva de buzón de Exchange ActiveSync dispositivo móvil o se omitirá la regla de acceso de dispositivo aplicado para el dispositivo.
  
## <a name="i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps"></a>Configuro MDM pero ahora desea quitarlo. ¿Cuáles son los pasos?

Desafortunadamente, no se puede simplemente "deshace el aprovisionamiento de" MDM para Office 365 después de que ha configurado. Pero puede hacerlo para grupos de usuarios mediante la eliminación de grupos de seguridad de usuario de las directivas de dispositivo que se ha creado. O bien, deshabilitar para todos los usuarios mediante la eliminación de las directivas de dispositivo para que no están en su lugar y no se aplican. Vea [cómo desactivar la administración de dispositivos móviles en Office 365](turn-off-mdm.md).
  
## <a name="still-need-help"></a>¿Aún necesita ayuda?

[![Obtener ayuda en los foros de la comunidad de Office 365](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Administradores: Iniciar sesión y crear una solicitud de servicio](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Administradores: Llamar al soporte técnico](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

  


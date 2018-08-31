---
title: Información general de administración de dispositivos móviles (MDM) para Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365M_MDMConfigDomains
- O365E_MDMConfigDomains
- ms.o365.cc.DevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: faa7d8e5-645d-4d59-839c-c8d4c1869e4a
description: Puede administrar y proteger los dispositivos móviles cuando están conectados a la organización de Office 365 mediante el uso de administración de dispositivos móviles para Office 365. Dispositivos móviles como smartphones y tabletas que se usan para tener acceso a correo electrónico del trabajo, calendario, contactos y documentos reproducción una parte importante en asegurándose de que los empleados realizar su trabajo en cualquier momento y desde cualquier lugar. Por lo que es crítico se ayuda a proteger la información de su organización cuando las personas usan dispositivos. Puede usar MDM para Office 365 establece las reglas de acceso y directivas de seguridad del dispositivo y borrar dispositivos móviles si está perdidos o robados.
ms.openlocfilehash: f06cef11b68ee0673f13c54738f07f4556495fdd
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272495"
---
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a>Información general de administración de dispositivos móviles (MDM) para Office 365

Puede administrar y proteger los dispositivos móviles cuando están conectados a la organización de Office 365 mediante el uso de administración de dispositivos móviles para Office 365. Dispositivos móviles como smartphones y tabletas que se usan para tener acceso a correo electrónico del trabajo, calendario, contactos y documentos reproducción una parte importante en asegurándose de que los empleados realizar su trabajo en cualquier momento y desde cualquier lugar. Por lo que es crítico se ayuda a proteger la información de su organización cuando las personas usan dispositivos. Puede usar MDM para Office 365 establece las reglas de acceso y directivas de seguridad del dispositivo y borrar dispositivos móviles si está perdidos o robados.
  
![MDM en el teléfono Android](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a>¿Qué tipos de dispositivos se pueden administrar?

Puede usar MDM para Office 365 para administrar los diversos tipos de dispositivos móviles como iPad, iPhone, Android y Windows Phone. Para administrar los dispositivos móviles usados por las personas de su organización, cada persona debe tener una licencia de Office 365 aplicables y su dispositivo debe inscrito en MDM para Office 365. 
  
Para ver qué MDM para Office 365 admite para cada tipo de dispositivo, consulte [Las capacidades de administración de dispositivos móviles para Office 365](capabilities-of-mobile-device-management.md).
  
## <a name="setup-steps-for-mdm"></a>Pasos de configuración para MDM

Un administrador global de Office 365 debe completar los pasos siguientes para activar y configurar MDM para Office 365. Siga las instrucciones en el tema sobre la [configuración de MDM para Office 365](set-up-mobile-device-management.md) para ver los pasos detallados. Éste es un resumen rápido: 
  
> Paso 1: Activar MDM para Office 365 siguiendo los pasos en el [conjunto de copia de seguridad Mobile Device Management (MDM) en Office 365](set-up-mobile-device-management.md).
    
> Paso 2: Configurar MDM para Office 365 por, por ejemplo, crear un certificado APN para administrar dispositivos iOS y agregar un registro del sistema de nombres de dominio (DNS) para su dominio admitir teléfonos de Windows.
    
> Paso 3: Crear directivas de dispositivo y aplicarla a grupos de usuarios. En este caso, los usuarios recibirán un [mensaje de inscripción en su dispositivo](enroll-your-mobile-device.md). Y cuando se ha completado la inscripción, sus dispositivos se limitará por las directivas que ha configurado para ellos.
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Una vez tienes MDM para Office 365, configurar y los usuarios han inscrito sus dispositivos, puede administrar los dispositivos, bloquee el acceso o borrar un dispositivo, si es necesario. Obtenga más información sobre [algunas tareas comunes de administración de dispositivos](manage-devices-in-mdm.md), incluido where para llevar a cabo las tareas.
  
## <a name="other-ways-to-manage-devices-and-apps"></a>Otras maneras de administrar dispositivos y aplicaciones

Si necesita más funcionalidad que MDM para Office 365 incluye, desproteger esta [comparación de las características MDM y Intune de Microsoft](choose-between-mdm-and-intune.md) para ver si una suscripción Intune cumple las necesidades de su organización. 
  
Si sólo necesita administración de aplicaciones móviles (MAM), quizás para personas actualizar proyectos de trabajo en sus propios dispositivos, Intune proporciona otra opción además de inscripción y administración de dispositivos. Una suscripción Intune le permite configurar las directivas MAM mediante el portal de Azure, incluso si no se suscriben Intune dispositivos de las personas. Vea [proteger los datos de aplicación con las directivas de MAM](https://go.microsoft.com/fwlink/?LinkId=825439). 
  
## <a name="see-also"></a>Vea también

[Obtener detalles acerca de los dispositivos administrados por MDM](get-details-about-mdm-managed-devices.md)

[Configurar MDM para Office 365](set-up-mobile-device-management.md)
  
[Inscribirse en dispositivos móviles en MDM](enroll-your-mobile-device.md)
  
[Administrar dispositivos inscritos en MDM](manage-devices-in-mdm.md)


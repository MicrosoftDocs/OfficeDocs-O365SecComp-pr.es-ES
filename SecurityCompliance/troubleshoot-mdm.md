---
title: Solución de problemas de inscripción de dispositivos con MDM para Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2015
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c863b2bf-45f3-483a-ba05-29fc7f4d6434
description: Si está ejecutando en problemas al intentar inscribirse en un dispositivo en Mobile Device Management (MDM) Office 365, pruebe los pasos que se muestran aquí para realizar un seguimiento del problema. Si los pasos generales no soluciona el problema, vea las secciones posteriores con los pasos específicos para el tipo de dispositivo.
ms.openlocfilehash: 490259fc623b38ab5ad6cf8553c5074c77b77426
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272115"
---
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a>Solución de problemas de inscripción de dispositivos con MDM para Office 365

Si está ejecutando en problemas al intentar inscribirse en un dispositivo en Mobile Device Management (MDM) Office 365, pruebe los pasos que se muestran aquí para realizar un seguimiento del problema. Si los pasos generales no soluciona el problema, vea las secciones posteriores con los pasos específicos para el tipo de dispositivo.
  
## <a name="steps-to-try-first"></a>Pasos para intentar en primer lugar

Para iniciar, compruebe lo siguiente:
  
- Asegúrese de que el dispositivo no está ya inscrito con otro proveedor de administración de dispositivos móviles, como Intune.
    
- Asegúrese de que el dispositivo está configurado para la fecha y hora correctas.
    
- Cambie a un diferente Wi-Fi o la red de telefonía móvil en el dispositivo.
    
- Para los dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación de Portal de empresa Intune en el dispositivo.
    
## <a name="ios-phone-or-tablet"></a>iOS teléfono o tableta

- Asegúrese de que ha agregado el [conjunto de copia de seguridad un certificado APN](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).
    
- En la **configuración** de \> **General** \> **perfiles** (o **Administración de dispositivos**), asegúrese de que un **Perfil de administración** no está instalado. Si es así, quitarlo. 
    
- Si ve el mensaje de error "Dispositivo no pudo inscribirse," iniciar sesión en Office 365 y asegúrese de que se asignó una licencia que incluye Exchange Online para el usuario que ha iniciado sesión en el dispositivo.
    
- Si ve el mensaje de error, "Perfil no se pudo instalar," Pruebe una de las siguientes opciones:
    
  - Asegúrese de que Safari es el explorador predeterminado en el dispositivo, y que las cookies no están deshabilitadas.
    
  - Reiniciar el dispositivo, a continuación, vaya a portal.manage.microsoft.com, iniciar sesión con su identificador de usuario de Office 365 y la contraseña e intente instalar manualmente el perfil.
    
## <a name="windows-rt-tablet"></a>Tableta Windows RT

- Asegúrese de que su dominio está [configurada en Office 365 para que funcione con MDM](set-up-mobile-device-management.md).
    
- Asegúrese de que el usuario es elegir **Turn On** , en lugar de elegir **unirse a**.
    
## <a name="windows-phone"></a>Windows Phone

- Asegúrese de que su dominio está [configurada en Office 365 para que funcione con MDM](set-up-mobile-device-management.md).
    
- Asegúrese de que el dispositivo se está ejecutando Windows 8.1 o posterior.
    
## <a name="android-phone-or-tablet"></a>Teléfono Android o tableta

- Asegúrese de que el dispositivo se está ejecutando Android 4.0 o posterior.
    
- Si ve el mensaje de error "Se no podríamos inscribirse en este dispositivo," iniciar sesión en Office 365 y asegúrese de que se asignó una licencia que incluye Exchange Online para el usuario que ha iniciado sesión en el dispositivo.
    
- Comprobar el **Área de notificación** en el dispositivo para ver si todas las acciones de usuario final necesarios están pendientes y, si es así, realice las acciones. 
    


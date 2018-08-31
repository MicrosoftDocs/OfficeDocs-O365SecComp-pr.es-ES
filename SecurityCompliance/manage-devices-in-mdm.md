---
title: Administrar dispositivos inscritos en administración de dispositivos móviles en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 28dd276b-beeb-4c5b-8b22-7551186127fe
description: Siga estos pasos para establecer la seguridad de Mobile Device Management (MDM) en Office 365.
ms.openlocfilehash: 3a84b6904b866e07eb4efabe0f39041b282d0ba9
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272315"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-office-365"></a>Administrar dispositivos inscritos en administración de dispositivos móviles en Office 365

La administración de dispositivos móviles integrada para Office 365 le ayuda a proteger y administrar los dispositivos móviles como iPhone, iPad, Androids, los usuarios y teléfonos de Windows. El primer paso es iniciar sesión en Office 365 y [Configurar MDM para Office 365](set-up-mobile-device-management.md). 
  
Una vez haya configurado copia de seguridad, las personas de su organización debe [inscribirse sus dispositivos](enroll-your-mobile-device.md) en el servicio. A continuación, puede usar MDM para Office 365 para ayudar a administrar los dispositivos de su organización. Por ejemplo, puede usar las directivas de seguridad de dispositivo para ayudar a limitar el acceso al correo electrónico u otros servicios, ver informes de dispositivos y borrado remoto de un dispositivo. Normalmente, se le dirigirá a la [vaya a la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) para realizar estas tareas. 
  
## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Para obtener en el panel de administración del dispositivo, siga estos pasos. 
  
1. Vaya al Centro de administración de Office 365.
    
2. Escriba administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles** de la lista de resultados. 
    
    ![Tipo de Mobile Device Manager en el campo de búsqueda de Office 365](media/e2e2f1c0-e543-431a-959b-e26c2ba328a7.png)
  
Una vez que tenga MDM para Office 365, configurar, aquí es cómo puede administrar los dispositivos móviles en la organización. 
  
|**Para hacer esto...**|**Haga esto…**|
|:-----|:-----|
|Eliminar los datos de un dispositivo  <br/> |En el panel de administración de dispositivos, seleccione *el nombre de dispositivo* , a continuación, **borrado completo** para eliminar todos los información o **Borrar selectiva** para eliminar únicamente información de la organización en el dispositivo.  <br/> Consulte [Borrar un dispositivo en Office 365](wipe-a-mobile-device.md).  <br/> |
|Bloquear el acceso de dispositivos no compatibles al correo electrónico de Exchange con Exchange ActiveSync  <br/> |En el panel de administración de dispositivos, seleccione **Bloquear**.  <br/> |
|Configurar las directivas de dispositivo al igual que los requisitos de contraseña y configuración de seguridad  <br/> |En el panel de administración de dispositivos, haga clic en \> **las directivas de seguridad de dispositivo** \> **Agregar +**.  <br/> Vea [crear e implementar directivas de seguridad de dispositivo](create-device-security-policies.md).  <br/> |
|Ver la lista de dispositivos bloqueados  <br/> |En el panel de administración de dispositivos, en **Seleccione una vista** , seleccione **bloqueado**.  <br/> ||
|Desbloquear un dispositivo no compatible o no admitido para un usuario o grupo de usuarios  <br/> | Puede desbloquear varias maneras de dispositivos no compatibles dependiendo de su situación. Elija una de las siguientes:<br/>  Quitar el usuario o los usuarios del grupo de seguridad que se ha aplicado la directiva. Vaya al **Centro de administración de Office 365** \> **grupos**y, a continuación, seleccione * nombre del grupo *. Haga clic en **Editar los miembros y los administradores**.<br/>  Quitar el grupo de seguridad de que los usuarios son un miembro de la directiva de dispositivo. Vaya a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **las directivas de seguridad de dispositivo**. Seleccione * nombre de la directiva de dispositivo *, a continuación, haga clic en **Editar** ![icono Editar](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **implementación**.<br/>  Desbloquear todos los dispositivos no compatibles para una directiva de dispositivo. Vaya a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **las directivas de seguridad de dispositivo**. Seleccione el *nombre de la directiva de dispositivo* y, a continuación, haga clic en **Editar** ![icono Editar](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **los requisitos de acceso**. Seleccione **Permitir infracción de acceso y el informe**.<br/>  Para desbloquear un dispositivo no compatible o no compatible para un usuario o un grupo de usuarios, consulte Go to **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **Device management** \> configuración **Administrar acceso de dispositivo **. Agregar un grupo de seguridad con los miembros que desea impedir que se ha bloqueado el acceso a Office 365. Vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).<br/> |
|Obtener detalles acerca de los dispositivos de la organización  <br/> |Para obtener información detallada, como qué dispositivos están inscritos y compatible con las directivas de seguridad de dispositivo, siga los pasos descritos en [obtener detalles acerca de los dispositivos administrados por MDM](get-details-about-mdm-managed-devices.md).  <br/> |
|Quitar los usuarios, por lo que sus dispositivos ya no están administrados por MDM  <br/> |Editar el grupo de seguridad que tiene las directivas de administración de dispositivos de MDM quitar el usuario. Vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).<br/> Para quitar MDM de todos los usuarios de Office 365, vea [desactivar la administración de dispositivos móviles en Office 365](turn-off-mdm.md).  <br/> |
   


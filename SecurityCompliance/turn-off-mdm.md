---
title: Cómo desactivar la administración de dispositivos móviles en Office 365
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
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: Siga estos pasos para detener las directivas de MDM desde que se aplican para dispositivos móviles en su organización de Office 365.
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272225"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a>Cómo desactivar la administración de dispositivos móviles en Office 365

Para desactivar eficazmente MDM para Office 365, quitar grupos de personas (definidos por grupos de seguridad) de las directivas de administración de dispositivos o quitar las directivas de ellos mismos. 
  
- Quitar grupos de usuarios mediante la eliminación de grupos de seguridad de usuario de las directivas de dispositivo que se ha creado. 
    
- Deshabilitar MDM para todos los usuarios mediante la eliminación de todas las directivas de dispositivo MDM. 
    
Estas opciones eliminarán cumplimiento MDM para dispositivos en su organización. Desafortunadamente, no se puede simplemente "deshace el aprovisionamiento de" MDM para Office 365 después de que ha configurado.
  
> [!IMPORTANT]
> Tenga en cuenta el impacto en dispositivos de los usuarios al quitar grupos de seguridad de usuario de directivas o quitar las directivas de ellos mismos. Por ejemplo, los perfiles de correo electrónico y mensajes de correo electrónico almacenados en caché pueden ser eliminadas, dependiendo del dispositivo. Véase: [¿Cuál es el impacto de las directivas de seguridad en distintos tipos de dispositivos?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a>Quitar grupos de seguridad de usuario de las directivas de dispositivos MDM

1. Vaya a **seguridad &amp; centro de cumplimiento** \> **prevención de pérdida de datos** \> **las directivas de seguridad del dispositivo**.
    
2. Seleccione una directiva de dispositivo y haga clic en ![icono Editar](media/O365-MDM-CreatePolicy-EditIcon.gif) **Editar directiva**.
    
3. En la **implementación**, haga clic en **: quitar**.
    
    En **grupos**, seleccione un grupo de seguridad.
    
4.  Haga clic en **Quitar**.
    
5. Haga clic en **Guardar**.
    
## <a name="remove-mdm-device-policies"></a>Quitar directivas de dispositivo MDM

1. Vaya a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **las directivas de seguridad de dispositivo**.
    
2. Seleccione una directiva de dispositivo y, a continuación, haga clic en ![imagen de la Papelera puede icono. ](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Eliminar directiva**.
    
3. En el cuadro de diálogo de **Advertencia** , haga clic en **Sí**. 
    


---
title: Crear un certificado de APNs para dispositivos iOS
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Para administrar dispositivos iOS como iPad y iPhone en la administración de dispositivos móviles para Office 365, siga estos pasos para crear primero un certificado de APNs.
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220460"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear un certificado de APNs para dispositivos iOS

 Para administrar dispositivos iOS como iPad y iPhone en la administración de dispositivos móviles para Office 365 debe crear un certificado de APNs. 
  
Para ello, siga los pasos del vínculo **configurar** en la página del portal. (Vaya a **seguridad &amp; del centro** \> de seguridad y **directivas** \> de seguridad **Administración** \> de dispositivos administre la **configuración**).
  
![Configurar los pasos necesarios y recomendados para la administración de dispositivos móviles](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Junto a **configurar un certificado de APNs para dispositivos iOS**, seleccione **configurar**.
    
2. Seleccione **descargar el archivo CSR** y guardar la solicitud de firma de certificado en algún lugar del equipo que recuerde. 
    
    ![Cuadro de diálogo instalar certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. Seleccione **Siguiente**.
    
4. Crear un certificado de APN.
    
  - Seleccione **portal de APNS de Apple** para abrir el portal de certificados push de Apple. 
    
    ![Instalar el cuadro de diálogo de certificado de notificación de APN con el portal de APNS de Apple seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Inicie sesión con un identificador de Apple.
    
    > [!IMPORTANT]
    > Use un identificador Apple de empresa asociado con una cuenta de correo electrónico que vaya a permanecer con la organización incluso si el usuario que administra la cuenta la deja. Guarde este identificador, ya que tendrá que usar el mismo identificador cuando sea el momento de renovar el certificado. 
  
  - Seleccione **crear un certificado** y acepte los **términos de uso**.
    
  - **Vaya** a la solicitud de firma de certificado que descargó en el equipo desde Office 365 y seleccione **cargar**.
    
  - **Descargue** el certificado APN creado por el portal de certificados push de Apple en su equipo. 
    
    > [!TIP]
    > Si está teniendo problemas para descargar el certificado, actualice el explorador. 
  
5. Vuelva a Office 365 y seleccione **siguiente** para ir a la página **cargar certificado de APNS** . 
    
6. Vaya al certificado de APN que ha descargado desde el portal de certificados push de Apple.
    
    ![Haga clic en el botón Examinar para seleccionar el certificado de APNS que ha descargado de Apple.](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Seleccione **Finalizar**.
    
Volver a **seguridad del &amp; centro** \> de cumplimiento de seguridad **directivas** \> de **Administración** \> de dispositivos administre la **configuración** para completar la configuración. 
  


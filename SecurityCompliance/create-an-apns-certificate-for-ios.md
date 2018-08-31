---
title: Crear un certificado APN para dispositivos iOS
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Para administrar dispositivos iOS como iPad e iPhone en administración de dispositivos móviles para Office 365, siga estos pasos para crear primero un certificado APN.
ms.openlocfilehash: 28e8888d7dd57c3052cdcb5994725f11a5f0445f
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272055"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear un certificado APN para dispositivos iOS

 Debe crear un certificado APN para administrar dispositivos iOS como iPad e iPhone en administración de dispositivos móviles para Office 365. 
  
Para ello, siga los pasos desde el vínculo **Configurar** en la página del portal. (Vaya a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **Device management** \> **Administrar la configuración de**.)
  
![Configurar la administración de dispositivos móviles pasos necesarios y recomendados](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Junto a **configurar un certificado APN para dispositivos iOS**, seleccione **Configurar**.
    
2. Seleccione **descargar el archivo CSR** y guarde la solicitud de firma de certificado a en algún lugar en el equipo que sea fácil de recordar. 
    
    ![Instalar el cuadro de diálogo certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. Seleccione **siguiente**.
    
4. Cree un certificado APN.
    
  - Seleccione **Apple APN Portal** para abrir el Portal de certificados de inserción de Apple. 
    
    ![Instalar el cuadro de diálogo de notificación APN cert con Apple APN Portal seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Iniciar sesión con un identificador de Apple.
    
    > [!IMPORTANT]
    > Use una compañía que Apple identificador asociado con una cuenta de correo electrónico que permanecerá con la organización, incluso si sale el usuario que administra la cuenta. Guarde este identificador porque debe usar el mismo identificador cuando es el momento de renovar el certificado. 
  
  - Seleccione **crear un certificado** y acepte los **Términos de uso**.
    
  - **Vaya** a la solicitud de firma de certificado descargado en el equipo de Office 365 y seleccione **cargar**.
    
  - **Descargar** el certificado APN creado por el Portal del certificado de inserción de Apple en su equipo. 
    
    > [!TIP]
    > Si tiene problemas para descargar el certificado, actualice el explorador. 
  
5. Vuelva a Office 365 y seleccione **siguiente** para ir a la página **cargar APN certificado** . 
    
6. Busque el certificado APN que ha descargado desde el Portal de certificados de inserción de Apple.
    
    ![Haga clic en el botón Examinar para seleccionar cert APN que descargó de Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Seleccione **Finalizar**.
    
Vuelva a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **Device management** \> **Administrar la configuración** para completar la instalación. 
  


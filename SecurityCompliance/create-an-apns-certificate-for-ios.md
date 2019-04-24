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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258648"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear un certificado de APNs para dispositivos iOS

 Para administrar dispositivos iOS como iPad y iPhone en la administración de dispositivos móviles para Office 365 debe crear un certificado de APNs. 
  
Para ello, siga los pasos del vínculo **configurar** en la página del portal. (Vaya a **seguridad &amp; del centro** \> de seguridad y **directivas** \> de seguridad **Administración** \> de dispositivos administre la **configuración**).
  
![Configurar los pasos necesarios y recomendados para la administración de dispositivos móviles](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.
    
2. Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember. 
    
    ![Cuadro de diálogo instalar certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3.  Select **Next**. 
    
4.  Create an APN certificate.
    
  - Select **Apple APNS Portal** to open the Apple Push Certificates Portal.  
    
    ![Instalar el cuadro de diálogo de certificado de notificación de APN con el portal de APNS de Apple seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Sign in with an Apple ID.
    
    > [!IMPORTANT]
    > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate. 
  
  - Select **Create a Certificate** and accept the **Terms of Use**.
    
  - **Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.
    
  - **Download** the APN certificate created by the Apple Push Certificate Portal to your computer. 
    
    > [!TIP]
    > If you're having trouble downloading the certificate, refresh your browser. 
  
5. Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page. 
    
6.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
    ![Haga clic en el botón Examinar para seleccionar el certificado de APNS que ha descargado de Apple.](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Select **Finish**.
    
Volver a **seguridad del &amp; centro** \> de cumplimiento de seguridad **directivas** \> de **Administración** \> de dispositivos administre la **configuración** para completar la configuración. 
  


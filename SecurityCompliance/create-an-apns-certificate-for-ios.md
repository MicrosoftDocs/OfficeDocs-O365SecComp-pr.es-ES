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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="1becc-103">Crear un certificado APN para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="1becc-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="1becc-104">Debe crear un certificado APN para administrar dispositivos iOS como iPad e iPhone en administración de dispositivos móviles para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1becc-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="1becc-p101">Para ello, siga los pasos desde el vínculo **Configurar** en la página del portal. (Vaya a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **Device management** \> **Administrar la configuración de**.)</span><span class="sxs-lookup"><span data-stu-id="1becc-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![Configurar la administración de dispositivos móviles pasos necesarios y recomendados](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="1becc-108">Junto a **configurar un certificado APN para dispositivos iOS**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="1becc-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="1becc-109">Seleccione **descargar el archivo CSR** y guarde la solicitud de firma de certificado a en algún lugar en el equipo que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="1becc-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![Instalar el cuadro de diálogo certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="1becc-111">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1becc-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="1becc-112">Cree un certificado APN.</span><span class="sxs-lookup"><span data-stu-id="1becc-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="1becc-113">Seleccione **Apple APN Portal** para abrir el Portal de certificados de inserción de Apple.</span><span class="sxs-lookup"><span data-stu-id="1becc-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![Instalar el cuadro de diálogo de notificación APN cert con Apple APN Portal seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="1becc-115">Iniciar sesión con un identificador de Apple.</span><span class="sxs-lookup"><span data-stu-id="1becc-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1becc-p102">Use una compañía que Apple identificador asociado con una cuenta de correo electrónico que permanecerá con la organización, incluso si sale el usuario que administra la cuenta. Guarde este identificador porque debe usar el mismo identificador cuando es el momento de renovar el certificado.</span><span class="sxs-lookup"><span data-stu-id="1becc-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="1becc-118">Seleccione **crear un certificado** y acepte los **Términos de uso**.</span><span class="sxs-lookup"><span data-stu-id="1becc-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="1becc-119">**Vaya** a la solicitud de firma de certificado descargado en el equipo de Office 365 y seleccione **cargar**.</span><span class="sxs-lookup"><span data-stu-id="1becc-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="1becc-120">**Descargar** el certificado APN creado por el Portal del certificado de inserción de Apple en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1becc-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="1becc-121">Si tiene problemas para descargar el certificado, actualice el explorador.</span><span class="sxs-lookup"><span data-stu-id="1becc-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="1becc-122">Vuelva a Office 365 y seleccione **siguiente** para ir a la página **cargar APN certificado** .</span><span class="sxs-lookup"><span data-stu-id="1becc-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="1becc-123">Busque el certificado APN que ha descargado desde el Portal de certificados de inserción de Apple.</span><span class="sxs-lookup"><span data-stu-id="1becc-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![Haga clic en el botón Examinar para seleccionar cert APN que descargó de Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="1becc-125">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1becc-125">Select **Finish**.</span></span>
    
<span data-ttu-id="1becc-126">Vuelva a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **Device management** \> **Administrar la configuración** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="1becc-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  


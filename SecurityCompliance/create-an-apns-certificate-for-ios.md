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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="c9d86-103">Crear un certificado de APNs para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="c9d86-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="c9d86-104">Para administrar dispositivos iOS como iPad y iPhone en la administración de dispositivos móviles para Office 365 debe crear un certificado de APNs.</span><span class="sxs-lookup"><span data-stu-id="c9d86-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="c9d86-p101">Para ello, siga los pasos del vínculo **configurar** en la página del portal. (Vaya a **seguridad &amp; del centro** \> de seguridad y **directivas** \> de seguridad **Administración** \> de dispositivos administre la **configuración**).</span><span class="sxs-lookup"><span data-stu-id="c9d86-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![Configurar los pasos necesarios y recomendados para la administración de dispositivos móviles](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="c9d86-108">Junto a **configurar un certificado de APNs para dispositivos iOS**, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="c9d86-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="c9d86-109">Seleccione **descargar el archivo CSR** y guardar la solicitud de firma de certificado en algún lugar del equipo que recuerde.</span><span class="sxs-lookup"><span data-stu-id="c9d86-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![Cuadro de diálogo instalar certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="c9d86-111">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c9d86-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="c9d86-112">Crear un certificado de APN.</span><span class="sxs-lookup"><span data-stu-id="c9d86-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="c9d86-113">Seleccione **portal de APNS de Apple** para abrir el portal de certificados push de Apple.</span><span class="sxs-lookup"><span data-stu-id="c9d86-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![Instalar el cuadro de diálogo de certificado de notificación de APN con el portal de APNS de Apple seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="c9d86-115">Inicie sesión con un identificador de Apple.</span><span class="sxs-lookup"><span data-stu-id="c9d86-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c9d86-p102">Use un identificador Apple de empresa asociado con una cuenta de correo electrónico que vaya a permanecer con la organización incluso si el usuario que administra la cuenta la deja. Guarde este identificador, ya que tendrá que usar el mismo identificador cuando sea el momento de renovar el certificado.</span><span class="sxs-lookup"><span data-stu-id="c9d86-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="c9d86-118">Seleccione **crear un certificado** y acepte los **términos de uso**.</span><span class="sxs-lookup"><span data-stu-id="c9d86-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="c9d86-119">**Vaya** a la solicitud de firma de certificado que descargó en el equipo desde Office 365 y seleccione **cargar**.</span><span class="sxs-lookup"><span data-stu-id="c9d86-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="c9d86-120">**Descargue** el certificado APN creado por el portal de certificados push de Apple en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c9d86-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c9d86-121">Si está teniendo problemas para descargar el certificado, actualice el explorador.</span><span class="sxs-lookup"><span data-stu-id="c9d86-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="c9d86-122">Vuelva a Office 365 y seleccione **siguiente** para ir a la página **cargar certificado de APNS** .</span><span class="sxs-lookup"><span data-stu-id="c9d86-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="c9d86-123">Vaya al certificado de APN que ha descargado desde el portal de certificados push de Apple.</span><span class="sxs-lookup"><span data-stu-id="c9d86-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![Haga clic en el botón Examinar para seleccionar el certificado de APNS que ha descargado de Apple.](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="c9d86-125">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c9d86-125">Select **Finish**.</span></span>
    
<span data-ttu-id="c9d86-126">Volver a **seguridad del &amp; centro** \> de cumplimiento de seguridad **directivas** \> de **Administración** \> de dispositivos administre la **configuración** para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c9d86-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  


---
title: Inscribirse en su dispositivo móvil en Office 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: c8ac722d-dcaf-4135-8345-3e6327f5d3c5
description: Antes de poder usar servicios de Office 365 con su dispositivo, debe seguir estos pasos para inscribirse en administración de dispositivos móviles para Office 365 (MDM). Para ello, al agregar su trabajo o escuela cuenta de correo electrónico a su dispositivo por primera vez.
ms.openlocfilehash: 63e4052d42007d97928f158a704beb9721758a44
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272305"
---
# <a name="enroll-your-mobile-device-in-office-365"></a><span data-ttu-id="94fac-104">Inscribirse en su dispositivo móvil en Office 365</span><span class="sxs-lookup"><span data-stu-id="94fac-104">Enroll your mobile device in Office 365</span></span>

<span data-ttu-id="94fac-p102">El uso de su teléfono, Tablet PC y otros dispositivos móviles para el trabajo es una excelente manera de mantenerse informado y trabajar en proyectos de negocio mientras está fuera de la oficina. Antes de poder usar servicios de Office 365 con su dispositivo, debe primero inscribirse lo en administración de dispositivos móviles para Office 365 (MDM) utilizando Microsoft Intune compañía Portal.</span><span class="sxs-lookup"><span data-stu-id="94fac-p102">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you're away from the office. Before you can use Office 365 services with your device, you may need to first enroll it in Mobile Device Management for Office 365 (MDM) using Microsoft Intune Company Portal.</span></span>
  
<span data-ttu-id="94fac-p103">Las organizaciones eligen MDM para que los empleados puedan utilizar sus dispositivos móviles forma segura para obtener acceso a correo electrónico del trabajo, calendarios y documentos mientras protege los datos importantes de la empresa y cumpla sus requisitos de cumplimiento. [Obtenga información acerca de MDM en Office 365](https://go.microsoft.com/fwlink/?LinkId=615142).</span><span class="sxs-lookup"><span data-stu-id="94fac-p103">Organizations choose MDM so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements. [Learn about MDM in Office 365](https://go.microsoft.com/fwlink/?LinkId=615142).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="94fac-p104">Cuando inscribirse su dispositivo en MDM para Office 365, pueden requerirse para establecer una contraseña, junto con lo que permite la opción para la organización de trabajo borrar el dispositivo. Un borrado de dispositivo puede realizarse (desde el centro de administración de Office 365), por ejemplo, para quitar todos los datos del dispositivo si la contraseña se han escrito incorrectamente demasiadas veces o si se rompen los términos de uso.</span><span class="sxs-lookup"><span data-stu-id="94fac-p104">When you enroll your device in MDM for Office 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device. A device wipe can be performed (from the Office 365 admin center), for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span> 
  
 <span data-ttu-id="94fac-111">**Dispositivos admitidos**</span><span class="sxs-lookup"><span data-stu-id="94fac-111">**Supported devices**</span></span>
  
<span data-ttu-id="94fac-p105">MDM y InTune funciona con la mayoría, pero no todos los dispositivos móviles. Las siguientes son compatibles con MDM para Office 365.</span><span class="sxs-lookup"><span data-stu-id="94fac-p105">MDM and InTune works with most, but not all, mobile devices. The following are supported with MDM for Office 365.</span></span>
  
- <span data-ttu-id="94fac-114">iOS 7.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="94fac-114">iOS 7.1 or later</span></span>
    
- <span data-ttu-id="94fac-115">Android 4 o posterior</span><span class="sxs-lookup"><span data-stu-id="94fac-115">Android 4 or later</span></span>
    
- <span data-ttu-id="94fac-116">Windows 8.1 (teléfono y PC) y más adelante para incluir Windows 10</span><span class="sxs-lookup"><span data-stu-id="94fac-116">Windows 8.1 (Phone and PC) and later to include Windows 10</span></span>
    
- <span data-ttu-id="94fac-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="94fac-117">Windows 10</span></span>
    
<span data-ttu-id="94fac-118">Si su dispositivo no está enumerado arriba, y debe usar con MDM y Intune, póngase en contacto con el administrador del trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="94fac-118">If your device is not listed above, and you need to use it with MDM and Intune, contact your work or school administrator.</span></span>
  
> [!TIP]
> <span data-ttu-id="94fac-119">Si tiene problemas de inscripción de su dispositivo, consulte: [solución de problemas inscripción de dispositivos con MDM para Office 365](troubleshoot-mdm.md).</span><span class="sxs-lookup"><span data-stu-id="94fac-119">If you're having trouble enrolling your device, see: [Troubleshoot device enrollment with MDM for Office 365](troubleshoot-mdm.md).</span></span> 
  
## <a name="set-up-your-mobile-device-with-intune-and-mdm-for-office-365"></a><span data-ttu-id="94fac-120">Configurar su dispositivo móvil con Intune y MDM para Office 365</span><span class="sxs-lookup"><span data-stu-id="94fac-120">Set up your mobile device with Intune and MDM for Office 365</span></span>

<span data-ttu-id="94fac-121">El Portal de la compañía Intune permite a un dispositivo administrado por Office 365 y MDM.</span><span class="sxs-lookup"><span data-stu-id="94fac-121">The Intune Company Portal enables a device to be managed by Office 365 and MDM.</span></span>
  
### <a name="iphone-or-ipad"></a><span data-ttu-id="94fac-122">iPhone o iPad</span><span class="sxs-lookup"><span data-stu-id="94fac-122">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="94fac-123">No podrá enviar y recibir correo electrónico hasta que haya terminado este paso.</span><span class="sxs-lookup"><span data-stu-id="94fac-123">You won't be able to send and receive email until you complete this step.</span></span> 
  
> <span data-ttu-id="94fac-124">Vaya a la tienda de aplicaciones de Apple, descargue e instale el Portal de empresa Intune.</span><span class="sxs-lookup"><span data-stu-id="94fac-124">Go to the Apple App Store, download and install Intune Company Portal.</span></span>
    
> <span data-ttu-id="94fac-125">[Siga estos pasos para configurar y conectar](https://go.microsoft.com/fwlink/?linkid=875316) el teléfono iOS o tableta con el portal de la compañía a Office 365.</span><span class="sxs-lookup"><span data-stu-id="94fac-125">[Follow these steps to configure and connect](https://go.microsoft.com/fwlink/?linkid=875316) your iOS phone or tablet with the Company portal to Office 365.</span></span> 
    
### <a name="android-phone-or-tablet"></a><span data-ttu-id="94fac-126">Teléfono Android o tableta</span><span class="sxs-lookup"><span data-stu-id="94fac-126">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="94fac-127">No podrá enviar y recibir correo electrónico hasta que haya terminado este paso.</span><span class="sxs-lookup"><span data-stu-id="94fac-127">You won't be able to send and receive email until you complete this step.</span></span> 
  
> <span data-ttu-id="94fac-128">Vaya a la tienda de Google reproducir, descargue e instale Intune Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="94fac-128">Go to the Google Play store, download and install Intune Company Portal.</span></span>
    
> <span data-ttu-id="94fac-129">[Siga estos pasos para configurar y conectar](https://go.microsoft.com/fwlink/?linkid=875317) el teléfono Android o tableta con el portal de la compañía a Office 365.</span><span class="sxs-lookup"><span data-stu-id="94fac-129">[Follow these steps to configure and connect](https://go.microsoft.com/fwlink/?linkid=875317) your Android phone or tablet with the Company portal to Office 365.</span></span> 
    
## <a name="whats-next"></a><span data-ttu-id="94fac-130">¿Qué es lo siguiente</span><span class="sxs-lookup"><span data-stu-id="94fac-130">What's next</span></span>

<span data-ttu-id="94fac-131">Después de que su dispositivo está inscrito en MDM para Office 365, puede empezar a usar aplicaciones de Office en su dispositivo para trabajar con correo electrónico, calendario, contactos y documentos.</span><span class="sxs-lookup"><span data-stu-id="94fac-131">After your device is enrolled in MDM for Office 365, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
  


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
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a><span data-ttu-id="632e9-104">Solución de problemas de inscripción de dispositivos con MDM para Office 365</span><span class="sxs-lookup"><span data-stu-id="632e9-104">Troubleshoot device enrollment with MDM for Office 365</span></span>

<span data-ttu-id="632e9-p102">Si está ejecutando en problemas al intentar inscribirse en un dispositivo en Mobile Device Management (MDM) Office 365, pruebe los pasos que se muestran aquí para realizar un seguimiento del problema. Si los pasos generales no soluciona el problema, vea las secciones posteriores con los pasos específicos para el tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="632e9-p102">If you're running into issues when you try to enroll a device in Mobile Device Management (MDM) for Office 365, try the steps listed here to track down the problem. If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>
  
## <a name="steps-to-try-first"></a><span data-ttu-id="632e9-107">Pasos para intentar en primer lugar</span><span class="sxs-lookup"><span data-stu-id="632e9-107">Steps to try first</span></span>

<span data-ttu-id="632e9-108">Para iniciar, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="632e9-108">To start, check the following:</span></span>
  
- <span data-ttu-id="632e9-109">Asegúrese de que el dispositivo no está ya inscrito con otro proveedor de administración de dispositivos móviles, como Intune.</span><span class="sxs-lookup"><span data-stu-id="632e9-109">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="632e9-110">Asegúrese de que el dispositivo está configurado para la fecha y hora correctas.</span><span class="sxs-lookup"><span data-stu-id="632e9-110">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="632e9-111">Cambie a un diferente Wi-Fi o la red de telefonía móvil en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="632e9-111">Switch to a different Wi-Fi or cellular network on the device.</span></span>
    
- <span data-ttu-id="632e9-112">Para los dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación de Portal de empresa Intune en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="632e9-112">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span>
    
## <a name="ios-phone-or-tablet"></a><span data-ttu-id="632e9-113">iOS teléfono o tableta</span><span class="sxs-lookup"><span data-stu-id="632e9-113">iOS phone or tablet</span></span>

- <span data-ttu-id="632e9-114">Asegúrese de que ha agregado el [conjunto de copia de seguridad un certificado APN](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span><span class="sxs-lookup"><span data-stu-id="632e9-114">Make sure that you've [set up an APNs certificate](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span></span>
    
- <span data-ttu-id="632e9-p103">En la **configuración** de \> **General** \> **perfiles** (o **Administración de dispositivos**), asegúrese de que un **Perfil de administración** no está instalado. Si es así, quitarlo.</span><span class="sxs-lookup"><span data-stu-id="632e9-p103">In **Settings** \> **General** \> **Profile** (or **Device Management**), make sure that a **Management Profile** is not already installed. If it is, remove it.</span></span> 
    
- <span data-ttu-id="632e9-117">Si ve el mensaje de error "Dispositivo no pudo inscribirse," iniciar sesión en Office 365 y asegúrese de que se asignó una licencia que incluye Exchange Online para el usuario que ha iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="632e9-117">If you see the error message, "Device failed to enroll," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="632e9-118">Si ve el mensaje de error, "Perfil no se pudo instalar," Pruebe una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="632e9-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
  - <span data-ttu-id="632e9-119">Asegúrese de que Safari es el explorador predeterminado en el dispositivo, y que las cookies no están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="632e9-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
  - <span data-ttu-id="632e9-120">Reiniciar el dispositivo, a continuación, vaya a portal.manage.microsoft.com, iniciar sesión con su identificador de usuario de Office 365 y la contraseña e intente instalar manualmente el perfil.</span><span class="sxs-lookup"><span data-stu-id="632e9-120">Reboot the device, then navigate to portal.manage.microsoft.com, sign in with your Office 365 user ID and password, and attempt to install the profile manually.</span></span>
    
## <a name="windows-rt-tablet"></a><span data-ttu-id="632e9-121">Tableta Windows RT</span><span class="sxs-lookup"><span data-stu-id="632e9-121">Windows RT tablet</span></span>

- <span data-ttu-id="632e9-122">Asegúrese de que su dominio está [configurada en Office 365 para que funcione con MDM](set-up-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="632e9-122">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="632e9-123">Asegúrese de que el usuario es elegir **Turn On** , en lugar de elegir **unirse a**.</span><span class="sxs-lookup"><span data-stu-id="632e9-123">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>
    
## <a name="windows-phone"></a><span data-ttu-id="632e9-124">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="632e9-124">Windows Phone</span></span>

- <span data-ttu-id="632e9-125">Asegúrese de que su dominio está [configurada en Office 365 para que funcione con MDM](set-up-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="632e9-125">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="632e9-126">Asegúrese de que el dispositivo se está ejecutando Windows 8.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="632e9-126">Make sure the device is running Windows 8.1 or later.</span></span>
    
## <a name="android-phone-or-tablet"></a><span data-ttu-id="632e9-127">Teléfono Android o tableta</span><span class="sxs-lookup"><span data-stu-id="632e9-127">Android phone or tablet</span></span>

- <span data-ttu-id="632e9-128">Asegúrese de que el dispositivo se está ejecutando Android 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="632e9-128">Make sure the device is running Android 4.0 or later.</span></span>
    
- <span data-ttu-id="632e9-129">Si ve el mensaje de error "Se no podríamos inscribirse en este dispositivo," iniciar sesión en Office 365 y asegúrese de que se asignó una licencia que incluye Exchange Online para el usuario que ha iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="632e9-129">If you see the error message, "We couldn't enroll this device," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="632e9-130">Comprobar el **Área de notificación** en el dispositivo para ver si todas las acciones de usuario final necesarios están pendientes y, si es así, realice las acciones.</span><span class="sxs-lookup"><span data-stu-id="632e9-130">Check the **Notification Area** on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span> 
    


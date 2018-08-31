---
title: Barrido hacia un dispositivo móvil en Office 365
ms.author: dianef
author: dianef77
manager: scotv
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_WipeDevice
- O365E_WipeDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9d727c7d-8b47-4499-bf24-d046b449214c
description: Puede usar Administración de dispositivos móviles integrada para Office 365 para realizar un borrado selectivo para quitar sólo información de la organización o un borrado completo para eliminar toda la información desde un dispositivo móvil y restaurar a su configuración de fábrica.
ms.openlocfilehash: d3eb28575924ca3bb4a647ae9af2f96b55116a53
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272505"
---
# <a name="wipe-a-mobile-device-in-office-365"></a><span data-ttu-id="5baa0-103">Barrido hacia un dispositivo móvil en Office 365</span><span class="sxs-lookup"><span data-stu-id="5baa0-103">Wipe a mobile device in Office 365</span></span>
  
<span data-ttu-id="5baa0-104">Puede usar Administración de dispositivos móviles integrada para Office 365 para realizar un borrado selectivo para quitar sólo información de la organización o un borrado completo para eliminar toda la información desde un dispositivo móvil y restaurar a su configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="5baa0-104">You can use built-in mobile device management for Office 365 to do a selective wipe to remove only organizational information, or a full wipe to delete all information from a mobile device and restore it to its factory settings.</span></span>
  
## <a name="what-to-know-before-you-begin"></a><span data-ttu-id="5baa0-105">Lo que debe saber antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5baa0-105">What to know before you begin</span></span>

- <span data-ttu-id="5baa0-p101">Dispositivos móviles pueden almacenar información confidencial de la organización y proporcionar acceso a los recursos de Office 365 de su organización. Para ayudar a proteger la información de su organización, puede hacer una limpieza completa o un borrado selectivo:</span><span class="sxs-lookup"><span data-stu-id="5baa0-p101">Mobile devices can store sensitive organizational information and provide access to your organization's Office 365 resources. To help protect your organization's information, you can do a full wipe or a selective wipe:</span></span>
    
  - <span data-ttu-id="5baa0-p102">**Borrado completo**: elimina todos los datos en el dispositivo móvil de un usuario, incluidas las aplicaciones instaladas, fotos e información personal. Una vez finalizada la eliminación, el dispositivo se restaura a su configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="5baa0-p102">**Full wipe**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information. When the wipe is complete, the device is restored to its factory settings.</span></span> 
    
  - <span data-ttu-id="5baa0-110">**Barrido hacia la selectiva**: quita sólo datos de la organización y aplicaciones abandona instalado, fotos e información personal en el dispositivo móvil de un usuario.</span><span class="sxs-lookup"><span data-stu-id="5baa0-110">**Selective wipe**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span> 
    
- <span data-ttu-id="5baa0-111">Cuando se suprime un dispositivo (borrado completa o selectiva borrado), el dispositivo se quita de la lista de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="5baa0-111">When a device is wiped (full wipe or selective wipe), the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="5baa0-p103">Puede configurar una directiva de administración de dispositivos móviles que elimina automáticamente (borrado completo) un dispositivo después de que el usuario intenta escribir la contraseña del dispositivo sin éxito un número específico de veces. Siga los pasos descritos en [crear e implementar directivas de seguridad de dispositivo](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5baa0-p103">You can set up a mobile device management policy that automatically wipes (full wipe) a device after the user unsuccessfully tries to enter the device's password a specific number of times. Follow the steps in [Create and deploy device security policies](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="5baa0-114">Si desea conocer lo que un usuario no experimentará cuando borrar su dispositivo, consulte [Cuál es el impacto de usuario y del dispositivo?](wipe-a-mobile-device.md#BKMK_Impact).</span><span class="sxs-lookup"><span data-stu-id="5baa0-114">If you want to know what a user will experience when you wipe their device, see [What's the user and device impact?](wipe-a-mobile-device.md#BKMK_Impact).</span></span>
    
## <a name="wipe-a-mobile-device"></a><span data-ttu-id="5baa0-115">Barrido hacia un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="5baa0-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="5baa0-116">Vaya a la [ ![haga clic aquí para ir al centro de administración de Office 365.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="5baa0-116">Go to the [![Click here to go to the Office 365 admin center.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="5baa0-117">Vaya a [vaya a la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) \> **prevención de pérdida de datos** \> **administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5baa0-117">Go to [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **Data loss prevention** \> **Device management**.</span></span>
    
3. <span data-ttu-id="5baa0-118">Seleccione el dispositivo que desea borrar.</span><span class="sxs-lookup"><span data-stu-id="5baa0-118">Select the device you want to wipe.</span></span>
    
4. <span data-ttu-id="5baa0-119">Seleccione el tipo de borrado remoto que desea realizar.</span><span class="sxs-lookup"><span data-stu-id="5baa0-119">Select the type of remote wipe you want to do.</span></span>
    
  - <span data-ttu-id="5baa0-120">Para realizar un borrado selectivo y eliminar sólo Office 365 información de la organización, en el panel derecho, seleccione **Borrar selectiva**.</span><span class="sxs-lookup"><span data-stu-id="5baa0-120">To do a selective wipe and delete only Office 365 organization information, in the right pane, select **Selective wipe**.</span></span>
    
  - <span data-ttu-id="5baa0-121">Para realizar un borrado completo y restaurar el dispositivo a su configuración de fábrica, en el panel derecho, seleccione **borrado completo**.</span><span class="sxs-lookup"><span data-stu-id="5baa0-121">To do a full wipe and restore the device to its factory settings, in the right pane, select **Full wipe**.</span></span>
    
![Seleccione un dispositivo y, a continuación, elija el tipo de barrido para hacer.](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. <span data-ttu-id="5baa0-123">Seleccione **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="5baa0-123">Select **Yes** to confirm.</span></span> 
    
<span data-ttu-id="5baa0-124">Hasta que finalice el borrado, el **estado del dispositivo** se mostrarán como **RetirePending** o **RetireIssued**.</span><span class="sxs-lookup"><span data-stu-id="5baa0-124">Until the wipe finishes, the **Device status** will show as **RetirePending** or **RetireIssued**.</span></span>
  
### <a name="how-do-i-know-it-worked"></a><span data-ttu-id="5baa0-125">¿Cómo se puede saber que ha funcionado?</span><span class="sxs-lookup"><span data-stu-id="5baa0-125">How do I know it worked?</span></span>

<span data-ttu-id="5baa0-126">Ya no se verá el dispositivo móvil en la lista de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="5baa0-126">You'll no longer see the mobile device in the list of managed devices.</span></span>
  
## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="5baa0-127">¿Por qué que desea borrar un dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5baa0-127">Why would you want to wipe a device?</span></span>

<span data-ttu-id="5baa0-128">Existen varias razones para barrido de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="5baa0-128">There are several reasons for wiping devices:</span></span>
  
- <span data-ttu-id="5baa0-p104">Dispositivos móviles como smartphones y tabletas se están convirtiendo en más completo todo el tiempo. Esto significa que es más fácil para los usuarios almacenar información corporativa confidencial (por ejemplo, de identificación personal o comunicaciones confidenciales) y obtener acceso a él en cualquier lugar. Si uno de estos dispositivos móviles está perdido o robado, barrido inmediatamente el dispositivo puede ayudar a evitar que la información de su organización desde la copia de seguridad que terminan en manos incorrectos.</span><span class="sxs-lookup"><span data-stu-id="5baa0-p104">Mobile devices like smartphones and tablets are becoming more full-featured all the time. This means it's easier for your users to store sensitive corporate information (such as personal identification or confidential communications) and access it on the go. If one of these mobile devices is lost or stolen, wiping the device immediately can help prevent your organization's information from ending up in the wrong hands.</span></span>
    
- <span data-ttu-id="5baa0-132">Cuando un usuario sale de la organización con un dispositivo personal que está inscrito en MDM para Office 365, puede ayudar a impedir que la información organizativa en marcha con el que el usuario realizando un borrado selectivo.</span><span class="sxs-lookup"><span data-stu-id="5baa0-132">When a user leaves the organization with a personal device that is enrolled in MDM for Office 365, you can help prevent organizational information from going with that user by doing a selective wipe.</span></span>
    
- <span data-ttu-id="5baa0-p105">Si su organización proporciona dispositivos móviles a los usuarios, es posible que necesite reasignar los dispositivos de vez en cuando. Realizar un borrado completo en un dispositivo antes de asignar a un usuario nuevo, le ayuda a se asegura de que cualquier información confidencial por parte del propietario anterior se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="5baa0-p105">If your organization provides mobile devices to users, you might need to reassign devices from time to time. Doing a full wipe on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>
    
## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="5baa0-135">¿Qué es el usuario y el impacto de dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5baa0-135">What's the user and device impact?</span></span>

<span data-ttu-id="5baa0-p106">La eliminación se envía inmediatamente al dispositivo móvil. El dispositivo también está marcado como no compatible en AAD.</span><span class="sxs-lookup"><span data-stu-id="5baa0-p106">The wipe is sent immediately to the mobile device. The device is also marked as not compliant in AAD.</span></span>
  
<span data-ttu-id="5baa0-138">En la siguiente tabla se describe el contenido que se ha quitado para cada tipo de dispositivo cuando un dispositivo de forma selectiva se borra.</span><span class="sxs-lookup"><span data-stu-id="5baa0-138">The following table describes what content is removed for each device type when a device is selectively wiped.</span></span>
  
|<span data-ttu-id="5baa0-139">**Impacto de contenido**</span><span class="sxs-lookup"><span data-stu-id="5baa0-139">**Content impact**</span></span>|<span data-ttu-id="5baa0-140">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="5baa0-140">**Windows Phone 8.1**</span></span>|<span data-ttu-id="5baa0-141">**iOS 7.1 +**</span><span class="sxs-lookup"><span data-stu-id="5baa0-141">**iOS 7.1+**</span></span>|<span data-ttu-id="5baa0-142">**Android 4+**</span><span class="sxs-lookup"><span data-stu-id="5baa0-142">**Android 4+**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5baa0-143">Aplicación de Portal de empresa\* se ha desinstalado.</span><span class="sxs-lookup"><span data-stu-id="5baa0-143">Company Portal app\* is uninstalled.</span></span>  <br/> |<span data-ttu-id="5baa0-144">N/D</span><span class="sxs-lookup"><span data-stu-id="5baa0-144">N/A</span></span>  <br/> |<span data-ttu-id="5baa0-145">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-145">✔</span></span>  <br/> |<span data-ttu-id="5baa0-146">N/D</span><span class="sxs-lookup"><span data-stu-id="5baa0-146">N/A</span></span>  <br/> |
|<span data-ttu-id="5baa0-p107">Datos de aplicación de Office 365 hospedados por aplicaciones donde el control de acceso es compatible con MDM para Office 365 están se ha quitado (Outlook actualmente y OneDrive para la empresa). No se quitan las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5baa0-p107">Office 365 app data hosted by apps where access control is supported by MDM for Office 365 is removed (currently Outlook and OneDrive for Business). The apps are not removed.</span></span>  <br/> <span data-ttu-id="5baa0-149">Outlook para Android no elimina los mensajes de correo electrónico almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="5baa0-149">Outlook for Android does not remove cached emails.</span></span>  <br/> |<span data-ttu-id="5baa0-150">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-150">✔</span></span>  <br/> |<span data-ttu-id="5baa0-151">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-151">✔</span></span>  <br/> |<span data-ttu-id="5baa0-152">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-152">✔</span></span>  <br/> |
|<span data-ttu-id="5baa0-153">Configuración de la directiva que se han aplicado por MDM para Office 365 a los dispositivos ya no se aplica en el dispositivo y los usuarios pueden cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="5baa0-153">Policy settings that were applied by MDM for Office 365 to devices are no longer enforced on the device and users can change the settings.</span></span>  <br/> |<span data-ttu-id="5baa0-154">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-154">✔</span></span>  <br/> |<span data-ttu-id="5baa0-155">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-155">✔</span></span>  <br/> |<span data-ttu-id="5baa0-156">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-156">✔</span></span>  <br/> |
|<span data-ttu-id="5baa0-157">Se quitan los perfiles de correo electrónico creada por MDM para Office 365 y se elimina el correo electrónico almacenado en caché en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5baa0-157">Email profiles created by MDM for Office 365 are removed and cached email on the device is deleted.</span></span>  <br/> |<span data-ttu-id="5baa0-158">N/D</span><span class="sxs-lookup"><span data-stu-id="5baa0-158">N/A</span></span>  <br/> |<span data-ttu-id="5baa0-159">✔</span><span class="sxs-lookup"><span data-stu-id="5baa0-159">✔</span></span>  <br/> |<span data-ttu-id="5baa0-160">N/D</span><span class="sxs-lookup"><span data-stu-id="5baa0-160">N/A</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="5baa0-161">\*Aplicación de Portal de empresa está disponible en la tienda de aplicaciones para iOS y el almacén de reproducir para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="5baa0-161">\* Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="5baa0-162">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="5baa0-162">Related content</span></span>

[<span data-ttu-id="5baa0-163">Administrar dispositivos móviles en Office 365</span><span class="sxs-lookup"><span data-stu-id="5baa0-163">Manage mobile devices in Office 365</span></span>](set-up-mobile-device-management.md)
  


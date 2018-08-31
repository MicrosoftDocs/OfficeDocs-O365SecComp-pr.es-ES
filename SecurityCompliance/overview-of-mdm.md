---
title: Información general de administración de dispositivos móviles (MDM) para Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365M_MDMConfigDomains
- O365E_MDMConfigDomains
- ms.o365.cc.DevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: faa7d8e5-645d-4d59-839c-c8d4c1869e4a
description: Puede administrar y proteger los dispositivos móviles cuando están conectados a la organización de Office 365 mediante el uso de administración de dispositivos móviles para Office 365. Dispositivos móviles como smartphones y tabletas que se usan para tener acceso a correo electrónico del trabajo, calendario, contactos y documentos reproducción una parte importante en asegurándose de que los empleados realizar su trabajo en cualquier momento y desde cualquier lugar. Por lo que es crítico se ayuda a proteger la información de su organización cuando las personas usan dispositivos. Puede usar MDM para Office 365 establece las reglas de acceso y directivas de seguridad del dispositivo y borrar dispositivos móviles si está perdidos o robados.
ms.openlocfilehash: f06cef11b68ee0673f13c54738f07f4556495fdd
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272495"
---
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="0f249-106">Información general de administración de dispositivos móviles (MDM) para Office 365</span><span class="sxs-lookup"><span data-stu-id="0f249-106">Overview of Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="0f249-p102">Puede administrar y proteger los dispositivos móviles cuando están conectados a la organización de Office 365 mediante el uso de administración de dispositivos móviles para Office 365. Dispositivos móviles como smartphones y tabletas que se usan para tener acceso a correo electrónico del trabajo, calendario, contactos y documentos reproducción una parte importante en asegurándose de que los empleados realizar su trabajo en cualquier momento y desde cualquier lugar. Por lo que es crítico se ayuda a proteger la información de su organización cuando las personas usan dispositivos. Puede usar MDM para Office 365 establece las reglas de acceso y directivas de seguridad del dispositivo y borrar dispositivos móviles si está perdidos o robados.</span><span class="sxs-lookup"><span data-stu-id="0f249-p102">You can manage and secure mobile devices when they're connected to your Office 365 organization by using Mobile Device Management for Office 365. Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere. So it's critical that you help protect your organization's information when people use devices. You can use MDM for Office 365 to set device security policies and access rules, and to wipe mobile devices if they're lost or stolen.</span></span>
  
![MDM en el teléfono Android](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="0f249-112">¿Qué tipos de dispositivos se pueden administrar?</span><span class="sxs-lookup"><span data-stu-id="0f249-112">What types of devices can you manage?</span></span>

<span data-ttu-id="0f249-p103">Puede usar MDM para Office 365 para administrar los diversos tipos de dispositivos móviles como iPad, iPhone, Android y Windows Phone. Para administrar los dispositivos móviles usados por las personas de su organización, cada persona debe tener una licencia de Office 365 aplicables y su dispositivo debe inscrito en MDM para Office 365.</span><span class="sxs-lookup"><span data-stu-id="0f249-p103">You can use MDM for Office 365 to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad. To manage mobile devices used by people in your organization, each person must have an applicable Office 365 license and their device must be enrolled in MDM for Office 365.</span></span> 
  
<span data-ttu-id="0f249-115">Para ver qué MDM para Office 365 admite para cada tipo de dispositivo, consulte [Las capacidades de administración de dispositivos móviles para Office 365](capabilities-of-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="0f249-115">To see what MDM for Office 365 supports for each type of device, see [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
  
## <a name="setup-steps-for-mdm"></a><span data-ttu-id="0f249-116">Pasos de configuración para MDM</span><span class="sxs-lookup"><span data-stu-id="0f249-116">Setup steps for MDM</span></span>

<span data-ttu-id="0f249-p104">Un administrador global de Office 365 debe completar los pasos siguientes para activar y configurar MDM para Office 365. Siga las instrucciones en el tema sobre la [configuración de MDM para Office 365](set-up-mobile-device-management.md) para ver los pasos detallados. Éste es un resumen rápido:</span><span class="sxs-lookup"><span data-stu-id="0f249-p104">An Office 365 global admin must complete the following steps to activate and set up MDM for Office 365. Follow the guidance in the topic on [setting up MDM for Office 365](set-up-mobile-device-management.md) to see detailed steps. Here's a quick summary:</span></span> 
  
> <span data-ttu-id="0f249-120">Paso 1: Activar MDM para Office 365 siguiendo los pasos en el [conjunto de copia de seguridad Mobile Device Management (MDM) en Office 365](set-up-mobile-device-management.md).</span><span class="sxs-lookup"><span data-stu-id="0f249-120">Step 1: Activate MDM for Office 365 by following steps in the [Set up Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).</span></span>
    
> <span data-ttu-id="0f249-121">Paso 2: Configurar MDM para Office 365 por, por ejemplo, crear un certificado APN para administrar dispositivos iOS y agregar un registro del sistema de nombres de dominio (DNS) para su dominio admitir teléfonos de Windows.</span><span class="sxs-lookup"><span data-stu-id="0f249-121">Step 2: Set up MDM for Office 365 by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>
    
> <span data-ttu-id="0f249-p105">Paso 3: Crear directivas de dispositivo y aplicarla a grupos de usuarios. En este caso, los usuarios recibirán un [mensaje de inscripción en su dispositivo](enroll-your-mobile-device.md). Y cuando se ha completado la inscripción, sus dispositivos se limitará por las directivas que ha configurado para ellos.</span><span class="sxs-lookup"><span data-stu-id="0f249-p105">Step 3: Create device policies and apply them to groups of users. When you do this, your users will get an [enrollment message on their device](enroll-your-mobile-device.md). And when they've completed enrollment, their devices will be restricted by the policies you've set up for them.</span></span>
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a><span data-ttu-id="0f249-125">Tareas de administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0f249-125">Device management tasks</span></span>

<span data-ttu-id="0f249-p106">Una vez tienes MDM para Office 365, configurar y los usuarios han inscrito sus dispositivos, puede administrar los dispositivos, bloquee el acceso o borrar un dispositivo, si es necesario. Obtenga más información sobre [algunas tareas comunes de administración de dispositivos](manage-devices-in-mdm.md), incluido where para llevar a cabo las tareas.</span><span class="sxs-lookup"><span data-stu-id="0f249-p106">After you've got MDM for Office 365 set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if needed. Learn more about [some common device management tasks](manage-devices-in-mdm.md), including where to complete the tasks.</span></span>
  
## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="0f249-128">Otras maneras de administrar dispositivos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0f249-128">Other ways to manage devices and apps</span></span>

<span data-ttu-id="0f249-129">Si necesita más funcionalidad que MDM para Office 365 incluye, desproteger esta [comparación de las características MDM y Intune de Microsoft](choose-between-mdm-and-intune.md) para ver si una suscripción Intune cumple las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="0f249-129">If you need more functionality than MDM for Office 365 includes, check out this [comparison of MDM and Microsoft Intune features](choose-between-mdm-and-intune.md) to see if an Intune subscription would meet your organization's needs.</span></span> 
  
<span data-ttu-id="0f249-p107">Si sólo necesita administración de aplicaciones móviles (MAM), quizás para personas actualizar proyectos de trabajo en sus propios dispositivos, Intune proporciona otra opción además de inscripción y administración de dispositivos. Una suscripción Intune le permite configurar las directivas MAM mediante el portal de Azure, incluso si no se suscriben Intune dispositivos de las personas. Vea [proteger los datos de aplicación con las directivas de MAM](https://go.microsoft.com/fwlink/?LinkId=825439).</span><span class="sxs-lookup"><span data-stu-id="0f249-p107">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices. An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune. See [Protect app data using MAM policies](https://go.microsoft.com/fwlink/?LinkId=825439).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0f249-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f249-133">See also</span></span>

[<span data-ttu-id="0f249-134">Obtener detalles acerca de los dispositivos administrados por MDM</span><span class="sxs-lookup"><span data-stu-id="0f249-134">Get details about devices managed by MDM</span></span>](get-details-about-mdm-managed-devices.md)

[<span data-ttu-id="0f249-135">Configurar MDM para Office 365</span><span class="sxs-lookup"><span data-stu-id="0f249-135">Set up MDM for Office 365</span></span>](set-up-mobile-device-management.md)
  
[<span data-ttu-id="0f249-136">Inscribirse en dispositivos móviles en MDM</span><span class="sxs-lookup"><span data-stu-id="0f249-136">Enroll mobile devices in MDM</span></span>](enroll-your-mobile-device.md)
  
[<span data-ttu-id="0f249-137">Administrar dispositivos inscritos en MDM</span><span class="sxs-lookup"><span data-stu-id="0f249-137">Manage devices enrolled in MDM</span></span>](manage-devices-in-mdm.md)


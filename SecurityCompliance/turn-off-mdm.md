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
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a><span data-ttu-id="84577-103">Cómo desactivar la administración de dispositivos móviles en Office 365</span><span class="sxs-lookup"><span data-stu-id="84577-103">How to turn off Mobile Device Management in Office 365</span></span>

<span data-ttu-id="84577-104">Para desactivar eficazmente MDM para Office 365, quitar grupos de personas (definidos por grupos de seguridad) de las directivas de administración de dispositivos o quitar las directivas de ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="84577-104">To effectively turn off MDM for Office 365, you remove groups of people (defined by security groups) from the device management policies, or remove the policies themselves.</span></span> 
  
- <span data-ttu-id="84577-105">Quitar grupos de usuarios mediante la eliminación de grupos de seguridad de usuario de las directivas de dispositivo que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="84577-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span> 
    
- <span data-ttu-id="84577-106">Deshabilitar MDM para todos los usuarios mediante la eliminación de todas las directivas de dispositivo MDM.</span><span class="sxs-lookup"><span data-stu-id="84577-106">Disable MDM for everyone by removing all MDM device policies.</span></span> 
    
<span data-ttu-id="84577-p101">Estas opciones eliminarán cumplimiento MDM para dispositivos en su organización. Desafortunadamente, no se puede simplemente "deshace el aprovisionamiento de" MDM para Office 365 después de que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="84577-p101">These options will remove MDM enforcement for devices in your organization. Unfortunately, you can't simply "unprovision" MDM for Office 365 after you've set it up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="84577-p102">Tenga en cuenta el impacto en dispositivos de los usuarios al quitar grupos de seguridad de usuario de directivas o quitar las directivas de ellos mismos. Por ejemplo, los perfiles de correo electrónico y mensajes de correo electrónico almacenados en caché pueden ser eliminadas, dependiendo del dispositivo. Véase: [¿Cuál es el impacto de las directivas de seguridad en distintos tipos de dispositivos?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span><span class="sxs-lookup"><span data-stu-id="84577-p102">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves. For example, email profiles and cached emails may be removed, depending on the device. See: [What is the impact of security policies on different device types?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span></span>
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a><span data-ttu-id="84577-112">Quitar grupos de seguridad de usuario de las directivas de dispositivos MDM</span><span class="sxs-lookup"><span data-stu-id="84577-112">Remove user security groups from MDM device policies</span></span>

1. <span data-ttu-id="84577-113">Vaya a **seguridad &amp; centro de cumplimiento** \> **prevención de pérdida de datos** \> **las directivas de seguridad del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="84577-113">Go to **Security &amp; Compliance Center**\> **Data loss prevention** \> **Device security polices**.</span></span>
    
2. <span data-ttu-id="84577-114">Seleccione una directiva de dispositivo y haga clic en ![icono Editar](media/O365-MDM-CreatePolicy-EditIcon.gif) **Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="84577-114">Select a device policy, and click ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif) **Edit policy**.</span></span>
    
3. <span data-ttu-id="84577-115">En la **implementación**, haga clic en **: quitar**.</span><span class="sxs-lookup"><span data-stu-id="84577-115">Under **Deployment**, click **- Remove**.</span></span>
    
    <span data-ttu-id="84577-116">En **grupos**, seleccione un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="84577-116">Under **Groups**, select a security group.</span></span>
    
4.  <span data-ttu-id="84577-117">Haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="84577-117">Click **Remove**.</span></span>
    
5. <span data-ttu-id="84577-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="84577-118">Click **Save**.</span></span>
    
## <a name="remove-mdm-device-policies"></a><span data-ttu-id="84577-119">Quitar directivas de dispositivo MDM</span><span class="sxs-lookup"><span data-stu-id="84577-119">Remove MDM device policies</span></span>

1. <span data-ttu-id="84577-120">Vaya a **seguridad &amp; centro de cumplimiento** \> **las directivas de seguridad** \> **las directivas de seguridad de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="84577-120">Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**.</span></span>
    
2. <span data-ttu-id="84577-p103">Seleccione una directiva de dispositivo y, a continuación, haga clic en ![imagen de la Papelera puede icono. ](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="84577-p103">Select a device policy, and then click ![Image of the trash can icon.](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Delete policy**.</span></span>
    
3. <span data-ttu-id="84577-123">En el cuadro de diálogo de **Advertencia** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="84577-123">In the **Warning** dialog, click **Yes**.</span></span> 
    


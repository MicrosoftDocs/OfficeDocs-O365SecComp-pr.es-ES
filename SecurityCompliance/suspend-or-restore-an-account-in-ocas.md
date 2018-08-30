---
title: Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 en la nube seguridad de la aplicación, puede realizar las acciones de gobierno son suspender o quitar la suspensión de una cuenta de usuario. '
ms.openlocfilehash: a5c75edefc6ddb87b5676c4253aafe04817f6a1d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535789"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="34151-103">Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34151-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="34151-104">Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.</span><span class="sxs-lookup"><span data-stu-id="34151-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="34151-105">Evaluación **\>**</span><span class="sxs-lookup"><span data-stu-id="34151-105">****Evaluation** \>**</span></span>|<span data-ttu-id="34151-106">Planeación de **\>**</span><span class="sxs-lookup"><span data-stu-id="34151-106">****Planning** \>**</span></span>|<span data-ttu-id="34151-107">Implementación **\>**</span><span class="sxs-lookup"><span data-stu-id="34151-107">****Deployment** \>**</span></span>|<span data-ttu-id="34151-108">Utilización de \*\*\*</span><span class="sxs-lookup"><span data-stu-id="34151-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="34151-109">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="34151-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="34151-110">Comenzar a planear</span><span class="sxs-lookup"><span data-stu-id="34151-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="34151-111">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="34151-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="34151-112">¡Están aquí!</span><span class="sxs-lookup"><span data-stu-id="34151-112">You are here!</span></span>  <br/> [<span data-ttu-id="34151-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="34151-113">Next steps</span></span>](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="34151-p101">Suponga que recibe una alerta que se ha comprometido una de las cuentas de usuario de la organización para Office 365. O bien, suponga que ha recibido una alerta que indica que algo es incorrecto con una cuenta de usuario. Con la seguridad de la aplicación de nube de Office 365, puede suspender una cuenta de usuario y restaurarla más adelante después de haber investigar las alertas que reciba.</span><span class="sxs-lookup"><span data-stu-id="34151-p101">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised. Or, suppose that you've received an alert that indicates something is wrong with a user account. With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34151-p102">Seguridad de la aplicación de Office 365 en la nube está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, seguridad de la aplicación de nube de Office 365 puede adquirirse como un complemento. (Como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información, vea [Descripción del servicio Office 365 plataforma: seguridad de Office 365 &amp; centro de cumplimiento](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento de Office 365 para profesionales](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="34151-p102">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="34151-120">Para suspender una cuenta de usuario en la seguridad de la aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="34151-120">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="34151-p103">Cuando se suspende una cuenta de usuario, se evita que el usuario de iniciar sesión de nuevo. Es la misma que la cuenta de usuario directamente en Office 365 para establecer el estado de inicio de sesión para el **Inicio de sesión bloqueado**de edición.</span><span class="sxs-lookup"><span data-stu-id="34151-p103">When you suspend a user account, you prevent the user from signing in again. It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34151-p104">Si bloquea un usuario de inicio de sesión en Office 365, ya sea por ellos suspender o mediante la edición de su estado de inicio de sesión, tenga en cuenta que puede tardar una hora o lo surta efecto en todos los dispositivos y clientes ([Editar o cambiar un usuario en Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) del usuario. Si el usuario ha iniciado sesión en Office 365, el bloque de surtirán efecto siempre que Office 365 requiere que inicien sesión nuevo.</span><span class="sxs-lookup"><span data-stu-id="34151-p104">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="34151-p105">Como [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela. (Esto le llevará a la seguridad &amp; centro de cumplimiento.)</span><span class="sxs-lookup"><span data-stu-id="34151-p105">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="34151-127">En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.</span><span class="sxs-lookup"><span data-stu-id="34151-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="34151-128">Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.</span><span class="sxs-lookup"><span data-stu-id="34151-128">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="34151-130">En la barra de navegación a través de la parte superior de la pantalla, elija **alertas**.</span><span class="sxs-lookup"><span data-stu-id="34151-130">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="34151-131">En la columna de la **alerta** , haga doble clic en una alerta que pertenece a una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="34151-131">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="34151-132">En **las cuentas**, en la columna **estado** , elija configuración ![icono configuración](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **usuario Suspend**.</span><span class="sxs-lookup"><span data-stu-id="34151-132">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="34151-133">Para restaurar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="34151-133">To restore a user account</span></span>

<span data-ttu-id="34151-134">Vea [restaurar un usuario en Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="34151-134">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="34151-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="34151-135">Next steps</span></span>

- [<span data-ttu-id="34151-136">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34151-136">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="34151-137">Administrar permisos de aplicación con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="34151-137">Manage app permissions using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="34151-138">Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="34151-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


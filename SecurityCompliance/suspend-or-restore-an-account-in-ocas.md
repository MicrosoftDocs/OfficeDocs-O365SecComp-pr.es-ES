---
title: Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 Cloud App Security, las acciones de gobierno que puede realizar son suspender o anular la suspensión de una cuenta de usuario. '
ms.openlocfilehash: 10da1385f850fadf077b4e3f9e3a00e9e4629fdd
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862452"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="88949-103">Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="88949-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="88949-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="88949-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="88949-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="88949-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="88949-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="88949-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="88949-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="88949-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="88949-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="88949-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="88949-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="88949-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="88949-110">Iniciar la implementación</span><span class="sxs-lookup"><span data-stu-id="88949-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="88949-111">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="88949-111">You are here!</span></span>  <br/> [<span data-ttu-id="88949-112">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="88949-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="88949-113">SuPongamos que recibe una alerta de que una de las cuentas de usuario de su organización para Office 365 ha estado en peligro.</span><span class="sxs-lookup"><span data-stu-id="88949-113">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised.</span></span> <span data-ttu-id="88949-114">O bien, supongamos que ha recibido una alerta que indica que hay algún error en una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="88949-114">Or, suppose that you've received an alert that indicates something is wrong with a user account.</span></span> <span data-ttu-id="88949-115">Con Office 365 Cloud App Security, puede suspender una cuenta de usuario y restaurarla más tarde una vez que haya investigado las alertas que recibe.</span><span class="sxs-lookup"><span data-stu-id="88949-115">With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88949-116">Office 365 Cloud App Security está disponible en Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="88949-116">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="88949-117">Si su organización usa otra suscripción de Office 365 Enterprise, Office 365 Cloud App Security puede adquirirse como un complemento.</span><span class="sxs-lookup"><span data-stu-id="88949-117">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="88949-118">(como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Add**subscriptions). Para obtener más información, consulte [office 365 Platform Service Description: office &amp; 365 Security Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento para Office 365 para empresas](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="88949-118">(As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="88949-119">Para suspender una cuenta de usuario en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="88949-119">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="88949-120">Al suspender una cuenta de usuario, se impide que el usuario inicie sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="88949-120">When you suspend a user account, you prevent the user from signing in again.</span></span> <span data-ttu-id="88949-121">Es lo mismo que editar la cuenta de usuario directamente en Office 365 para establecer el estado de inicio de sesión para **iniciar sesión bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="88949-121">It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88949-122">Si impide que un usuario inicie sesión en Office 365, ya sea suspendiendo los cambios o editando su estado de inicio de sesión, tenga en cuenta que puede tardar una hora o para que surtan efecto en todos los clientes y dispositivos del usuario ([Editar o cambiar un usuario en Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)).</span><span class="sxs-lookup"><span data-stu-id="88949-122">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)).</span></span> <span data-ttu-id="88949-123">Si el usuario ha iniciado sesión en Office 365, el bloque entrará en vigor siempre que Office 365 lo requiera volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="88949-123">If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="88949-124">Como [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="88949-124">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> <span data-ttu-id="88949-125">(Esto le llevará al centro de &amp; seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="88949-125">(This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="88949-126">En el centro &amp; de seguridad y cumplimiento, elija **alertas** \> **Administrar alertas avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="88949-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="88949-127">Elija **ir a Office 365 Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="88949-127">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="88949-128">![En el centro &amp; de seguridad y cumplimiento, elija Administrar alertas avanzadas para ir a Office 365 Cloud App Security.](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="88949-128">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="88949-129">En la barra de navegación en la parte superior de la pantalla, elija **alertas**.</span><span class="sxs-lookup"><span data-stu-id="88949-129">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="88949-130">En la columna **alerta** , haga doble clic en una alerta que pertenezca a una cuenta de usuario específica.</span><span class="sxs-lookup"><span data-stu-id="88949-130">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="88949-131">En **cuentas**, en la columna **Estado** , ![elija configuración configuración icono](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **suspender usuario**.</span><span class="sxs-lookup"><span data-stu-id="88949-131">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="88949-132">Para restaurar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="88949-132">To restore a user account</span></span>

<span data-ttu-id="88949-133">Vea [restaurar un usuario en Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="88949-133">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="88949-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="88949-134">Next steps</span></span>

- [<span data-ttu-id="88949-135">Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="88949-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="88949-136">Administrar aplicaciones de OAuth con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="88949-136">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="88949-137">Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="88949-137">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


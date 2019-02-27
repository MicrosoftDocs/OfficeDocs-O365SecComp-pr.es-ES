---
title: Activar o desactivar la búsqueda de registros de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: Puede activar la característica de búsqueda de registros de auditoría en el centro de &amp; seguridad y cumplimiento de Office 365. Si cambia de opinión, puede desactivar la opción en cualquier momento. Cuando la búsqueda de registros de auditoría está desactivada, los administradores no pueden buscar en el registro de auditoría de Office 365 la actividad de usuario y de administrador de su organización.
ms.openlocfilehash: 17b98cce26054d073006fa78c55fe418b5f327d8
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295463"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="419b8-105">Activar o desactivar la búsqueda de registros de auditoría de Office 365</span><span class="sxs-lookup"><span data-stu-id="419b8-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="419b8-p102">Usted (u otro administrador) deben activar el registro de auditoría para poder empezar a buscar en el registro de auditoría de Office 365. Cuando se activa la búsqueda de registros de auditoría &amp; en el centro de seguridad y cumplimiento de Office 365, la actividad de usuario y administrador de la organización se registra en el registro de auditoría y se conserva durante 90 días. Sin embargo, es posible que su organización no desee registrar y conservar los datos del registro de auditoría. O puede que esté usando una aplicación de administración de eventos e información de seguridad (SIEM) de terceros para obtener acceso a los datos de auditoría. En esos casos, un administrador global puede desactivar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="419b8-p102">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log. When audit log search in the Office 365 Security &amp; Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days. However, your organization might not want to record and retain audit log data. Or you might be using a third-party security information and event management (SIEM) application to access your auditing data. In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="419b8-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="419b8-111">Before you begin</span></span>

- <span data-ttu-id="419b8-p103">Debe tener asignado el rol registros de auditoría en Exchange Online para activar o desactivar la búsqueda de registros de auditoría en su organización de Office 365. De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento y administración de la organización en la página **permisos** del centro de administración de Exchange. Los administradores globales de Office 365 son miembros del grupo de funciones de administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="419b8-p103">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization. By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="419b8-p104">Los usuarios deben tener asignados permisos en Exchange Online para activar o desactivar la búsqueda de registros de auditoría. Si asigna a los usuarios el rol registros de auditoría en la página **permisos** del &amp; centro de seguridad y cumplimiento, no podrán activar o desactivar la búsqueda de registros de auditoría. Esto se debe a que el cmdlet subyacente es un cmdlet de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="419b8-p104">Users have to be assigned permissions in Exchange Online to turn audit log search on or off. If you assign users the Audit Logs role on the **Permissions** page in the Security &amp; Compliance Center, they won't be able to turn audit log search on or off. This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="419b8-p105">Si desactiva la búsqueda de registros de auditoría en Office 365, podrá seguir usando la API de actividad de administración de Office 365 para acceder a los datos de auditoría de su organización. Desactivar la búsqueda de registros de auditoría mediante los pasos descritos en este artículo indica que no se devolverá ningún resultado cuando busque en el &amp; registro de auditoría mediante el centro de seguridad y cumplimiento o cuando ejecute el cmdlet **Search-UnifiedAuditLog** en Exchange Online. PowerShell. Sin embargo, si ha autorizado que cualquier aplicación tenga acceso a los datos de auditoría de su organización a través de la API de actividad de administración de Office 365, dichas aplicaciones seguirán funcionando.</span><span class="sxs-lookup"><span data-stu-id="419b8-p105">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization. Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security &amp; Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell. However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="419b8-121">Para obtener instrucciones paso a paso sobre cómo buscar en el registro de auditoría de Office 365, consulte [Buscar el registro de auditoría en &amp; el centro de seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="419b8-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="419b8-122">Activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="419b8-122">Turn on audit log search</span></span>

<span data-ttu-id="419b8-p106">Puede usar el centro de &amp; seguridad y cumplimiento o PowerShell para activar la búsqueda de registros de auditoría en Office 365. Puede tardar varias horas después de activar la búsqueda de registros de auditoría para poder devolver los resultados cuando busque en el registro de auditoría. Debe tener asignado el rol registros de auditoría en Exchange Online para activar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="419b8-p106">You can use the Security &amp; Compliance Center or PowerShell to turn on audit log search in Office 365. It might take several hours after you turn on audit log search before you can return results when you search the audit log. You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="419b8-126">Usar el centro &amp; de seguridad y cumplimiento para activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="419b8-126">Use the Security &amp; Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="419b8-127">En el centro &amp; de seguridad y cumplimiento, vaya a búsqueda de registro de \> **Auditoría**de \*\*investigación de búsqueda &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="419b8-127">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="419b8-128">Haga clic en **iniciar grabación de actividades de usuario y de administrador**.</span><span class="sxs-lookup"><span data-stu-id="419b8-128">Click **Start recording user and admin activities**.</span></span>
    
    ![Haga clic en Empezar a registrar las actividades administrativas y de usuarios para activar la auditoría](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="419b8-130">Se muestra un cuadro de diálogo que indica que la actividad de usuario y de administrador de su organización se registrará en el registro de auditoría de Office 365 y estará disponible para verlo en un informe.</span><span class="sxs-lookup"><span data-stu-id="419b8-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="419b8-131">Haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="419b8-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="419b8-132">Se muestra un mensaje que indica que se está preparando el registro de auditoría y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación.</span><span class="sxs-lookup"><span data-stu-id="419b8-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="419b8-133">Usar PowerShell para activar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="419b8-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="419b8-134">Conectarse a Exchange Online mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="419b8-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="419b8-135">Ejecute el siguiente comando de PowerShell para activar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="419b8-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="419b8-136">Se muestra un mensaje que indica que puede tardar hasta 60 minutos para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="419b8-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="419b8-137">Desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="419b8-137">Turn off audit log search</span></span>

<span data-ttu-id="419b8-p107">Debe usar PowerShell remoto conectado a su organización de Exchange Online para desactivar la búsqueda de registros de auditoría. De forma similar a activar la búsqueda de registros de auditoría, debe tener asignado el rol registros de auditoría en Exchange Online para desactivar la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="419b8-p107">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search. Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="419b8-140">Conectarse a Exchange Online mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="419b8-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="419b8-141">Ejecute el siguiente comando de PowerShell para desactivar la búsqueda de registros de auditoría en Office 365.</span><span class="sxs-lookup"><span data-stu-id="419b8-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="419b8-p108">Después de un rato, compruebe que la búsqueda de registros de auditoría está desactivada (deshabilitada). Hay dos formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="419b8-p108">After a while, verify that audit log search is turned off (disabled). There are two ways to do this:</span></span>
    
    - <span data-ttu-id="419b8-144">En PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="419b8-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="419b8-145">El valor de `False` para la propiedad _UnifiedAuditLogIngestionEnabled_ indica que la búsqueda de registros de auditoría está desactivada.</span><span class="sxs-lookup"><span data-stu-id="419b8-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="419b8-146">En el centro &amp; de seguridad y cumplimiento, vaya a búsqueda de registro de \> **Auditoría**de \*\* &amp; investigación\*\* y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="419b8-146">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="419b8-147">Se muestra un mensaje que indica que la búsqueda de registros de auditoría no está activada.</span><span class="sxs-lookup"><span data-stu-id="419b8-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![Un mensaje es dispayed si la auditoría está desactivada](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)

---
title: Activar o desactivar la búsqueda de registros de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: Puede activar la característica de búsqueda de registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento. Si cambia de opinión, puede activar si desactivado en cualquier momento. Cuando la búsqueda de registro de auditoría está desactivada, los administradores no pueden buscar el registro de auditoría de Office 365 para la actividad de usuario y administración de en su organización.
ms.openlocfilehash: 4fa6ac095222addce578294813cbd22dfc50a2ab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536211"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Activar o desactivar la búsqueda de registros de auditoría de Office 365

Usted (u otro administrador) debe activar el registro de auditoría antes de empezar, puede buscar en el registro de auditoría de Office 365. Búsqueda de registro en la seguridad de Office 365 de auditoría cuando &amp; centro de cumplimiento está activado, la actividad de usuario y administración de la organización está registrada en el registro de auditoría y se conservan durante 90 días. Sin embargo, la organización es posible que no desee registrar y conservar los datos de registro de auditoría. O bien, puede que esté utilizando una aplicación de administración (SIEM) de eventos e información de seguridad de terceros para tener acceso a los datos de auditoría. En esos casos, un administrador global puede desactivar la búsqueda de registro de auditoría en Office 365.
  
## <a name="before-you-begin"></a>Antes de empezar

- Se debe asignar el rol registros de auditoría en Exchange Online para activar o desactivar la búsqueda de registro de auditoría de la organización de Office 365. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de cumplimiento y administración de la organización en la página de **permisos** en el centro de administración de Exchange. Los administradores globales en Office 365 son miembros del grupo de roles de administración de la organización en Exchange Online. 
    
    > [!IMPORTANT]
    > Los usuarios tienen que tener asignados permisos en Exchange Online para activar o desactivar la búsqueda de registro de auditoría. Si se asigna a los usuarios la función de los registros de auditoría en la página de **permisos** en la seguridad &amp; centro de cumplimiento, no podrán activar o desactivar la búsqueda de registro de auditoría. Esto es debido a que el cmdlet subyacente es un cmdlet de Exchange Online. 
  
- Si desactiva la búsqueda de registro de auditoría en Office 365, aún puede usar la API de actividad de administración de Office 365 para obtener acceso a datos de auditoría para la organización. Si desactiva la búsqueda de registro de auditoría siguiendo los pasos descritos en este artículo significa que no se devolverá ningún resultado cuando busca en el registro de auditoría con la seguridad &amp; centro de cumplimiento o al ejecutar el cmdlet **UnifiedAuditLog de búsqueda** en Exchange Online PowerShell. Sin embargo, si ha autorizado cualquier aplicación para tener acceso a datos de auditoría de su organización a través de la API de actividad de administración de Office 365, dichas aplicaciones seguirán funcionando. 
    
- Para obtener instrucciones detalladas acerca de la búsqueda de Office 365 el registro de auditoría, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).
    
## <a name="turn-on-audit-log-search"></a>Activar la búsqueda de registro de auditoría

Puede usar la seguridad &amp; centro de cumplimiento o PowerShell para activar la búsqueda de registro de auditoría en Office 365. Puede tardar varias horas después de activar búsqueda de registro de auditoría antes de que puede devolver los resultados al buscar en el registro de auditoría. Se debe asignar el rol registros de auditoría en Exchange Online para activar la búsqueda de registro de auditoría.
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a>Usar la seguridad &amp; centro de cumplimiento para activar la búsqueda de registro de auditoría

1. En la seguridad &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de registro de auditoría**.
    
2. Haga clic en **Iniciar grabación de usuario y las actividades de administración**.
    
    ![Haga clic en Empezar a registrar las actividades administrativas y de usuarios para activar la auditoría](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Se muestra un cuadro de diálogo que indica que usuario y la actividad de administración de la organización estará grabado en el registro de auditoría de Office 365 y están disponibles para ver en un informe. 
    
3. Haga clic en **Activar**.
    
    Se muestra un mensaje que indica que se está preparando el registro de auditoría y que se puede ejecutar una búsqueda en un par de horas una vez finalizada la preparación.
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>Uso de PowerShell para activar la búsqueda de registro de auditoría

1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Ejecute el siguiente comando de PowerShell para activar la búsqueda de registro de auditoría en Office 365.
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Se muestra un mensaje que indica que puede tardar hasta 60 minutos para que el cambio surta efecto.
  
## <a name="turn-off-audit-log-search"></a>Desactivar la búsqueda de registro de auditoría

Se debe usar PowerShell remoto conectado a la organización de Exchange Online para desactivar la búsqueda de registro de auditoría. Similar a la activación de la búsqueda de registro de auditoría, se debe asignar el rol registros de auditoría en Exchange Online para desactivar la búsqueda de registro de auditoría.
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Ejecute el siguiente comando de PowerShell para desactivar la búsqueda de registro de auditoría en Office 365.
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Después de unos momentos, compruebe que la búsqueda de registro auditoría está desactivada (deshabilitado). Hay dos formas de hacer esto:
    
    - En PowerShell, ejecute el siguiente comando:

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        El valor de `False` para el _UnifiedAuditLogIngestionEnabled_ (propiedad) indica que la búsqueda de registro auditoría está desactivada. 
    
    - En la seguridad &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> de **búsqueda de registro de auditoría**y, a continuación, haga clic en **Buscar**.
    
      Se muestra un mensaje que indica que la búsqueda de registro auditoría no está activada. 
    
      ![Un mensaje es dispayed si la auditoría está desactivada](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)

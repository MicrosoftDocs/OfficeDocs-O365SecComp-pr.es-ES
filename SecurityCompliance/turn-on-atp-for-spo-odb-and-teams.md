---
title: Activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo activar ATP para SharePoint, OneDrive y Teams, incluido cómo establecer alertas para los archivos detectados.
ms.openlocfilehash: c4146ce97f09723a8da543b84dc57bc522581001
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600286"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [protección contra amenazas avanzada de Office 365](office-365-atp.md). Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) protege a su organización de archivos malintencionados que se comparten de forma inadvertida. Cuando se detecta un archivo malintencionado, se bloquea el archivo para que nadie lo pueda abrir, copiar, mover ni compartir hasta que el equipo de seguridad de la organización haya realizado otras acciones. Lea este artículo para activar ATP para SharePoint, OneDrive y Microsoft Teams, configurar alertas para que se notifiquen sobre los archivos detectados y realizar los pasos siguientes. 
  
Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se describen algunos ejemplos:

|Role  |Dónde y cómo se asigna  |
|---------|---------|
|Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar ATP para SharePoint, OneDrive y Microsoft Teams.

**Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya esté activado para su entorno de Office 365**. Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com)e inicie sesión con su cuenta profesional o educativa.
    
2. En el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **Administración de amenazas**, seleccione **Directiva** \> de datos adjuntos **seguros**. <br/>![En el centro &amp; de seguridad y cumplimiento, elija \> Directiva de administración de amenazas](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. Seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.<br/>![Activar la protección contra amenazas avanzada para SharePoint Online, OneDrive para la empresa y Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. Haga clic en **Guardar **.
    
5. Revise (y, según corresponda, Edit) las directivas de [datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) de su organización y [las directivas de vínculos a prueba](set-up-atp-safe-links-policies.md)de errores.
    
6. Recomenda Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true*. <br/>
      - Si se establece el parámetro en *true* , se bloquearán todas las acciones (excepto eliminar) de los archivos detectados. Los usuarios no pueden abrir, mover, copiar o compartir los archivos detectados.
      - Si el parámetro se establece en *false* , se bloquearán todas las acciones excepto eliminar y descargar. Los usuarios pueden elegir entre aceptar el riesgo y descargar un archivo detectado.  
   
7. Espere hasta 30 minutos para que los cambios se extiendan a todos los centros de seguridad de Office 365.
    
8. Recomenda Proceda a configurar alertas para los archivos detectados.
    
Para obtener más información sobre el uso de PowerShell con Office 365, consulte [administrar office 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). 

Para obtener más información acerca de la experiencia del usuario cuando un archivo se ha detectado como malintencionado, consulte [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, en OneDrive o en Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2). 
  
## <a name="set-up-alerts-for-detected-files"></a>Configurar alertas para los archivos detectados

Para recibir una notificación cuando se identificó un archivo en SharePoint Online, OneDrive para la empresa o Microsoft Teams como malintencionado, puede configurar una alerta.
  
1. En el [centro de seguridad &amp; y cumplimiento de Office 365](https://protection.office.com), elija **alertas** \> **Administrar alertas**.
    
2. Elija **nueva Directiva de alerta**.
    
3. Especifique un nombre para la alerta. Por ejemplo, podría escribir archivos malintencionados en bibliotecas.
    
4. Escriba una descripción de la alerta. Por ejemplo, puede escribir notificar a los administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.
    
5. En la sección **enviar esta alerta cuando...** , haga lo siguiente: 
    
    a. En la lista **actividades** , seleccione **malware detectado en el archivo**.
    
    b. Deje el campo **usuarios** vacío. 
    
6. En la sección **enviar esta alerta a...** , seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecte un archivo malintencionado. 
    
7. Haga clic en **Guardar **.
    
Para obtener más información acerca de las alertas, consulte [crear alertas de actividad en &amp; el centro de seguridad y cumplimiento de Office 365](create-activity-alerts.md). 
  
## <a name="next-steps"></a>Pasos siguientes

1. [Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [Administrar archivos y mensajes en cuarentena como un administrador en Office 365](manage-quarantined-messages-and-files.md)
    

  


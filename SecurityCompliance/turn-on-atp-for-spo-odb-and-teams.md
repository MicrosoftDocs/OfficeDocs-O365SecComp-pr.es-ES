---
title: Activar Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: Obtenga información sobre cómo activar ATP para SharePoint, OneDrive y equipos, incluido cómo establecer alertas para los archivos detectados.
ms.openlocfilehash: 9745d45428035cc52346d19aa42e5e134123d016
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755301"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft

[Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) protege su organización de forma inadvertida uso compartido de archivos malintencionados. Cuando se detecta un archivo malintencionado, ese archivo se bloquea para que nadie puede abrir, copiar, mover o compártalo hasta que se toman más acciones por el equipo de seguridad de la organización. Lea este artículo para activar ATP para SharePoint, OneDrive y los equipos, configuración alertas para recibir una notificación acerca de los archivos detectados y lleve a cabo los pasos siguiente. 
  
Para definir las directivas de ATP (o editar), debe asignar uno de los roles que se describen en la siguiente tabla:

|Rol  |Dónde y cómo asignado  |
|---------|---------|
|Administrador Global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Administración de la organización en línea de Exchange |Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar ATP para SharePoint, OneDrive y Microsoft Teams.

**Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya está activado para el entorno de Office 365**. Normalmente, esto se realiza por una persona que tenga el rol de los registros de auditoría asignado en Exchange Online. Para obtener más información, vea [activar Office 365 de búsqueda de registros de auditoría activado o desactivado](turn-audit-log-search-on-or-off.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com)y el inicio de sesión con la cuenta de trabajo o escuela.
    
2. En la seguridad de Office 365 &amp; centro de cumplimiento, en el panel de navegación izquierdo, en **administración de amenaza**, elija **Directiva** \> **Los datos adjuntos seguros**. <br/>![En la seguridad &amp; centro de cumplimiento, elija Administración de amenaza \> directiva](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. Seleccione **Activar ATP para SharePoint, OneDrive y los equipos de Microsoft**.<br/>![Activar protección contra amenazas avanzadas para SharePoint Online, OneDrive para la empresa y los equipos de Microsoft](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. Haga clic en **Guardar**.
    
5. Revise (y, según corresponda, edite) [las directivas de los datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) y [las directivas de vínculos seguros](set-up-atp-safe-links-policies.md)de su organización.
    
6. (Recomendado) Como un administrador global o un administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con el parámetro **DisallowInfectedFileDownload** establecido en *true*. <br/>
      - Establecer el parámetro a *true* bloques todas las acciones (excepto eliminar) de los archivos detectados. Personas no se pueden abrir, mover, copiar o compartir archivos detectados.
      - Si el parámetro se establece en *false* , bloquea todas las acciones excepto eliminar y la descarga. Personas pueden optar por aceptar el riesgo y descargar un archivo detectado.  
   
7. Permitir hasta 30 minutos para que los cambios propagar a todos los centros de datos de Office 365.
    
8. (Recomendado) Continúe con para configurar alertas para los archivos detectados.
    
Para obtener más información acerca del uso de PowerShell con Office 365, vea [administrar Office 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). 

Para obtener más información acerca de la experiencia del usuario cuando se detecta un archivo como malintencionado, vea [qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o los equipos de Microsoft](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2). 
  
## <a name="set-up-alerts-for-detected-files"></a>Configurar alertas para archivos detectados

Para recibir una notificación cuando un archivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams se ha identificado como malintencionado, puede configurar una alerta.
  
1. En la [Office 365 seguridad &amp; centro de cumplimiento](https://protection.office.com), elija **alertas** \> **Administrar alertas**.
    
2. Elija **nueva directiva de alerta**.
    
3. Especifique un nombre para la alerta. Por ejemplo, puede escribir archivos malintencionados en bibliotecas.
    
4. Escriba una descripción de la alerta. Por ejemplo, podría escribir notifica a administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.
    
5. En la sección **Enviar esta alerta cuando...** , haga lo siguiente: 
    
    r. en la lista de **actividades** , elija **detectado malware en un archivo**.
    
    b. deje en blanco el campo de **los usuarios** . 
    
6. En la sección **Enviar esta alerta a...** , seleccione uno o varios de los administradores globales, los administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecta un archivo malintencionado. 
    
7. Haga clic en **Guardar**.
    
Para obtener más información acerca de las alertas, vea [crear alertas de actividad en la seguridad de Office 365 &amp; centro de cumplimiento](create-activity-alerts.md). 
  
## <a name="next-steps"></a>Pasos siguientes

1. [Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [Administrar mensajes en cuarentena y los archivos como un administrador en Office 365](manage-quarantined-messages-and-files.md)
    

  


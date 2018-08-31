---
title: Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
description: Cuando los clientes de EOP reciben correo no deseado, estos mensajes se mueven de forma predeterminada a la carpeta de correo no deseado del destinatario. Para que esta acción funcione en los buzones locales, debe configurar reglas de transporte de Exchange en los servidores de concentradores o perimetrales locales para encontrar los encabezados de correo no deseado que agregó EOP. Las reglas de transporte establecen el nivel de confianza contra correo no deseado (SCL) que usa la propiedad SclJunkThreshold (del cmdlet Set-OrganizationConfig) para que el correo no deseado se mueva a la carpeta de correo no deseado de cada buzón.
ms.openlocfilehash: 1b0a9e5ee39820baade714612ca0b0bdb7a81bb9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002859"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario

> [!IMPORTANT]
> Este tema solo se aplica a clientes de Exchange Online Protection (EOP) que hospedan buzones de correo localmente en una implementación híbrida. Los clientes de Exchange Online cuyos buzones se hospedan completamente en Office 365 no necesitan ejecutar estos comandos. 
  
Cuando los clientes de EOP reciben correo no deseado, estos mensajes se mueven de forma predeterminada a la carpeta de correo no deseado del destinatario. Para que esta acción funcione en los buzones locales, debe configurar reglas de transporte de Exchange en los servidores de concentradores o perimetrales locales para encontrar los encabezados de correo no deseado que agregó EOP. Las reglas de transporte establecen el nivel de confianza contra correo no deseado (SCL) que usa la propiedad SclJunkThreshold (del cmdlet Set-OrganizationConfig) para que el correo no deseado se mueva a la carpeta de correo no deseado de cada buzón. 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Para agregar reglas de transporte que hagan que el correo no deseado se mueva a la carpeta de correo no deseado mediante Windows PowerShell

1. Obtenga acceso al Shell de administración de Exchange de su servidor Exchange local. Para obtener información sobre cómo abrir el Shell de administración de Exchange en su organización local Exchange, vea **Open the Shell**.
    
2. Ejecute el siguiente comando para enrutar mensajes de correo no deseado de contenido filtrado a la carpeta de correo electrónico no deseado:
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    Donde  _NameForRule_ es el nombre de la regla nueva, por ejemplo, JunkContentFilteredMail. 
    
3. Ejecute el siguiente comando para enrutar mensajes marcados como correo no deseado antes de alcanzar el filtro de contenido en la carpeta de correo electrónico no deseado:
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    Donde  _NameForRule_ es el nombre de la regla nueva, por ejemplo, JunkMailBeforeReachingContentFilter. 
    
4. Ejecute el siguiente comando para asegurarse de que los mensajes de los remitentes que estén en una lista de bloqueados de la directiva de correo no deseado, como la de **remitentes bloqueados**, se enruten a la carpeta de correo no deseado: 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    Donde  _NameForRule_ es el nombre de la regla nueva, por ejemplo, JunkMailInSenderBlockList. 
    
Si no quiere usar la acción **Mover el mensaje a la carpeta de correo no deseado**, puede elegir otra acción en las directivas de filtro de contenido del Centro de administración de Exchange. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Para obtener más información sobre estos campos del encabezado del mensaje, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).
  
## <a name="see-also"></a>See also

[Cmdlet New-TransportRule](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)


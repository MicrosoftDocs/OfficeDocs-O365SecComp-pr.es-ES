---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Si el administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que enumera los mensajes enviados a su buzón que se identificaron como correo no deseado, en masa o de suplantación de identidad. Puede liberar o informar de los mensajes después de recibir la notificación.
ms.openlocfilehash: 7f68b70298fca7d8ed5f5e5b8dc9c727c3a6a6c1
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492729"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365

Si su administrador habilita las notificaciones de correo no deseado para los usuarios, recibirá un mensaje de notificación que enumera los mensajes dirigidos a su buzón que se identificaron como correo no deseado y que se ponen en cuarentena en su lugar.
  
> [!TIP]
> Si es administrador y desea habilitar esta característica, puede elegir la opción cuando [modifique una directiva contra correo no deseado predeterminada](https://go.microsoft.com/fwlink/?LinkId=800313). 
  
El mensaje que recibe incluye el número de mensajes de correo no deseado en cuarentena que tiene, y la fecha y la hora (en UTC universal coordinada o UTC) del último mensaje de la lista. En la lista se incluyen los siguientes elementos para cada mensaje:
  
- **Remitente** El nombre de envío y la dirección de correo electrónico del mensaje en cuarentena. 
    
- **Asunto** El texto de la línea de asunto del mensaje en cuarentena. 
    
- **Fecha** La fecha y hora (en UTC) en que el mensaje fue colocado en cuarentena. 
    
- **Tamaño** El tamaño del mensaje, en kilobytes (KB). 
    
Actualmente, hay dos acciones que puede llevar a cabo con un mensaje en cuarentena:
  
- **Liberar a bandeja de entrada** Elija esta opción para enviar el mensaje a su bandeja de entrada, donde puede verlo. 
    
- **Informar como correo deseado** Elija esta opción para enviar una copia del mensaje a Microsoft para su análisis. El equipo de correo no deseado evalúa y analiza el mensaje, y, según de los resultados del análisis, ajusta las reglas de filtro de correo no deseado para permitir que el mensaje pase. 
    
Tenga en cuenta lo siguiente:
  
- Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena. Solo se enumeran los mensajes en cuarentena de correo no deseado.
    
- Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.
    


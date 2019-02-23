---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: krowley
author: kccross
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
description: Si el administrador habilita las notificaciones para los usuarios, recibirá un mensaje de notificación que enumera los mensajes enviados a su buzón que se identificaron como correo no deseado, en masa o de suplantación de identidad. Puede liberar o informar de los mensajes después de recibir la notificación.
ms.openlocfilehash: eb51d8f73ff00781b74cfba4e580668710ce7a76
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216400"
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
    
- **Informar como correo deseado** Elija esta opción para enviar una copia del mensaje a Microsoft para su análisis. El equipo de correo no deseado evalúa y analiza el mensaje y, según los resultados del análisis, ajusta las reglas de filtro contra correo no deseado para permitir el paso del mensaje. 
    
Tenga en cuenta lo siguiente:
  
- Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena. Solo se muestran los mensajes de correo no deseado en cuarentena.
    
- Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.
    


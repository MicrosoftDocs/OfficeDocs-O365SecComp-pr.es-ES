---
title: Usar notificaciones de correo no deseado para el usuario para liberar y notificar mensajes de correo en cuarentena en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
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
ms.openlocfilehash: 887dab0df489e6f71266a6fdabfdd04f26a14ded
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598446"
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
    
Estas son las acciones que puede llevar a cabo con un mensaje en cuarentena:

- **Obtenga una vista previa** del mensaje si desea obtener una vista previa del contenido o encabezado antes de llevar a cabo la acción.

- **Descargue** el mensaje si desea revisar el mensaje y los datos adjuntos (si los hay) en el dispositivo antes de realizar la acción.

- **Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.

- **Versión & Permitir remitente** si el mensaje no es correo no deseado y desea que Office 365 agregue el remitente a la lista de remitentes seguros y destinatarios para futuros correos electrónicos. Tenga en cuenta que el administrador puede tener otras configuraciones de permitir o bloquear de toda la organización que invaliden la lista de remitentes seguros.

- **Libere & Informe**, si el mensaje no es correo no deseado y desea enviar el mensaje al buzón de correo y notificarlo a Microsoft para su análisis.

- **Bloquear** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.

Tenga en cuenta lo siguiente:
  
- Los mensajes que se ponen en cuarentena debido a que coinciden con una regla de flujo de correo no se incluyen en los mensajes de usuario en cuarentena. Solo se enumeran los mensajes en cuarentena de correo no deseado.
    
- Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.
    


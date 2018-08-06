---
title: Preguntas más frecuentes sobre la cuarentena
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: Este tema contiene preguntas frecuentes y respuestas sobre la cuarentena hospedada.
ms.openlocfilehash: 6aebeadc5155cbdb8cbeeb73e29c8b8cb0d53767
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027087"
---
# <a name="quarantine-faq"></a>Preguntas más frecuentes sobre la cuarentena

Este tema contiene preguntas frecuentes y respuestas sobre la cuarentena hospedada. Las respuestas son válidas para clientes de Microsoft Exchange Online y de Exchange Online Protection.
  
 **Pregunta: ¿cómo administrar mensajes en cuarentena de malware en cuarentena?**
  
Debe usar la seguridad &amp; centro de cumplimiento con el fin de ver y trabajar con los mensajes que se envían a cuarentena debido a que contienen malware. Para obtener más información, vea [los mensajes de correo electrónico de cuarentena en Office 365](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
 **P. ¿Cómo se configura el servicio para enviar mensajes de correo no deseado en cuarentena a la cuarentena?**
  
R. De manera predeterminada los mensajes de contenido filtrado se envían a los destinatarios de la carpeta de correo electrónico no deseado. Sin embargo, los administradores pueden configurar las directivas de filtro de contenido para enviar mensajes de correo no deseado en cuarentena a la cuarentena. Para obtener más información acerca de las diferentes acciones que pueden realizarse en los mensajes con filtrado de contenido, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
 **P. ¿Cuenta el servicio con administración de usuario final y administrador de los mensajes de correo no deseado puestos en cuarentena?**
  
R. Como administrador, puede buscar y ver detalles de los mensajes de correo electrónico en cuarentena en el Centro de administración de Exchange (EAC). Tras encontrar el mensaje, puede publicarlo a usuarios específicos y, opcionalmente, identificarlo como falso positivo (deseado) al equipo de análisis de correo no deseado de Microsoft. Para más información, vea [Buscar y liberar mensajes en cuarentena como un administrador](find-and-release-quarantined-messages-as-an-administrator.md).
  
Como usuario final, puede administrar sus propios mensajes de correo no deseado en cuarentena a través de: 
  
- La interfaz de usuario de cuarentena de correo no deseado. Para más información, vea [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
        
 **Q. ¿Cómo puede conceder acceso al correo no deseado en cuarentena a mis usuarios finales?**
  
A. para obtener acceso a la cuarentena de spam de usuario final, los usuarios finales debe tener un identificador válido de usuario de Office 365 y una contraseña. Los clientes de EOP protege los buzones locales deben ser usuarios de correo electrónico válida creados a través de la sincronización de Active directory o el CEF. Para obtener más información sobre cómo administrar usuarios, pueden hacer referencia a los administradores de elevación de privilegios para [Administrar usuarios de correo en EOP](eop/manage-mail-users-in-eop.md). Para los clientes de EOP independiente, se recomienda usar la sincronización de Active directory y la habilitación de Active Directory bloqueo perimetral basado en; Para obtener más información, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
 **P. ¿Se puede enviar otra cosa que no sea correo no deseado a la cuarentena?**
  
R. Los mensajes que coinciden con una regla de transporte también se pueden enviar a la cuarentena del administrador, si es la acción configurada. La cuarentena del usuario final es únicamente para correo no deseado.
  
 **P. ¿Durante cuánto tiempo se guardan los mensajes en cuarentena?**
  
A. De manera predeterminada, los mensajes de correo no deseado se mantienen en cuarentena durante 15 días, durante la cuarentena los mensajes que coinciden con una regla de transporte se mantienen en cuarentena durante 7 días. Finalizado este tiempo, los mensajes se eliminan y ya no se pueden recuperar. No se puede configurar el periodo de retención de los mensajes en cuarentena que coinciden con una regla de transporte. Sin embargo, es posible reducir el período de retención de los mensajes de correo no deseado en cuarentena mediante la configuración **Mantener el correo no deseado durante (días)** en las directivas de filtro de contenido. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
 **Q. ¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?**
  
A. La capacidad de liberar o informar sobre varios mensajes a la vez no está disponible actualmente en el EAC ni en el correo electrónico en cuarentena del usuario final. Sin embargo, los administradores pueden crear una secuencia de comandos de Windows PowerShell remoto para realizar esta tarea. Use el cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes y el cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) para liberarlos. 
  
 **P. ¿Se admiten caracteres comodín al buscar mensajes en cuarentena? ¿Puedo buscar mensajes en cuarentena para un dominio específico?**
  
A. No se admiten caracteres comodín al especificar los criterios de búsqueda en el Centro de administración de Exchange. Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa.
  
Con Windows PowerShell remoto, los administradores pueden especificar el cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes en cuarentena de un dominio específico (por ejemplo, contoso.com): 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

Los resultados se pueden transmitir al cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx). Incluya el parámetro -ReleaseToAll para liberar el mensaje a todos los destinatarios. Una vez que se libera un mensaje, no puede volver a liberarse. 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```



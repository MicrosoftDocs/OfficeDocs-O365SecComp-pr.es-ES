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
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: Este tema contiene preguntas frecuentes y respuestas sobre la cuarentena hospedada.
ms.openlocfilehash: 1473e682faab0471f5a6356e8d54a65a9baf291a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792501"
---
# <a name="quarantine-faq"></a><span data-ttu-id="264bb-103">Preguntas más frecuentes sobre la cuarentena</span><span class="sxs-lookup"><span data-stu-id="264bb-103">Quarantine FAQ</span></span>

<span data-ttu-id="264bb-p101">Este tema contiene preguntas frecuentes y respuestas sobre la cuarentena hospedada. Las respuestas son válidas para clientes de Microsoft Exchange Online y de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="264bb-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>
  
 <span data-ttu-id="264bb-106">**Pregunta: ¿cómo administrar mensajes en cuarentena de malware en cuarentena?**</span><span class="sxs-lookup"><span data-stu-id="264bb-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>
  
<span data-ttu-id="264bb-p102">Debe usar la seguridad &amp; centro de cumplimiento con el fin de ver y trabajar con los mensajes que se envían a cuarentena debido a que contienen malware. Para obtener más información, vea [los mensajes de correo electrónico de cuarentena en Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span><span class="sxs-lookup"><span data-stu-id="264bb-p102">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
 <span data-ttu-id="264bb-109">**P. ¿Cómo se configura el servicio para enviar mensajes de correo no deseado en cuarentena a la cuarentena?**</span><span class="sxs-lookup"><span data-stu-id="264bb-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>
  
<span data-ttu-id="264bb-p103">R. De manera predeterminada los mensajes de contenido filtrado se envían a los destinatarios de la carpeta de correo electrónico no deseado. Sin embargo, los administradores pueden configurar las directivas de filtro de contenido para enviar mensajes de correo no deseado en cuarentena a la cuarentena. Para obtener más información acerca de las diferentes acciones que pueden realizarse en los mensajes con filtrado de contenido, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="264bb-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="264bb-114">**P. ¿Cuenta el servicio con administración de usuario final y administrador de los mensajes de correo no deseado puestos en cuarentena?**</span><span class="sxs-lookup"><span data-stu-id="264bb-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>
  
<span data-ttu-id="264bb-p104">R. Como administrador, puede buscar y ver detalles de los mensajes de correo electrónico en cuarentena en el Centro de administración de Exchange (EAC). Tras encontrar el mensaje, puede publicarlo a usuarios específicos y, opcionalmente, identificarlo como falso positivo (deseado) al equipo de análisis de correo no deseado de Microsoft. Para más información, vea [Buscar y liberar mensajes en cuarentena como un administrador](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="264bb-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
  
<span data-ttu-id="264bb-119">Como usuario final, puede administrar sus propios mensajes de correo no deseado en cuarentena a través de:</span><span class="sxs-lookup"><span data-stu-id="264bb-119">As an end user, you can manage your own spam-quarantined messages via:</span></span> 
  
- <span data-ttu-id="264bb-p105">La interfaz de usuario de cuarentena de correo no deseado. Para más información, vea [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span><span class="sxs-lookup"><span data-stu-id="264bb-p105">The spam quarantine user interface. For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span></span>
        
 <span data-ttu-id="264bb-122">**Q. ¿Cómo puede conceder acceso al correo no deseado en cuarentena a mis usuarios finales?**</span><span class="sxs-lookup"><span data-stu-id="264bb-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>
  
<span data-ttu-id="264bb-p106">A. para obtener acceso a la cuarentena de spam de usuario final, los usuarios finales debe tener un identificador válido de usuario de Office 365 y una contraseña. Los clientes de EOP protege los buzones locales deben ser usuarios de correo electrónico válida creados a través de la sincronización de Active directory o el CEF. Para obtener más información sobre cómo administrar usuarios, pueden hacer referencia a los administradores de elevación de privilegios para [Administrar usuarios de correo en EOP](eop/manage-mail-users-in-eop.md). Para los clientes de EOP independiente, se recomienda usar la sincronización de Active directory y la habilitación de Active Directory bloqueo perimetral basado en; Para obtener más información, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span><span class="sxs-lookup"><span data-stu-id="264bb-p106">A. In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC. For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md). For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
 <span data-ttu-id="264bb-128">**P. ¿Se puede enviar otra cosa que no sea correo no deseado a la cuarentena?**</span><span class="sxs-lookup"><span data-stu-id="264bb-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>
  
<span data-ttu-id="264bb-p107">R. Los mensajes que coinciden con una regla de transporte también se pueden enviar a la cuarentena del administrador, si es la acción configurada. La cuarentena del usuario final es únicamente para correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="264bb-p107">A. Messages that match a transport rule can also be sent to the administrator quarantine, if that's the configured action. The end user quarantine is for spam only.</span></span>
  
 <span data-ttu-id="264bb-132">**P. ¿Durante cuánto tiempo se guardan los mensajes en cuarentena?**</span><span class="sxs-lookup"><span data-stu-id="264bb-132">**Q. For how long are messages kept in the quarantine?**</span></span>
  
<span data-ttu-id="264bb-p108">R. de forma predeterminada, los mensajes en cuarentena de correo no deseado se conservan en la cuarentena para 30 días, mientras los mensajes en cuarentena que coincide con una regla de transporte se conservan en la cuarentena de 7 días. Después de este período de tiempo de los mensajes se eliminan y no se puede recuperar. El período de retención para los mensajes en cuarentena que coincide con una regla de transporte no es configurable. Sin embargo, se puede reducir el período de retención de mensajes en cuarentena de correo no deseado a través de la opción de **conservar spam de (días)** en las directivas de filtro de contenido. Para obtener más información, vea [configurar sus directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="264bb-p108">A. By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a transport rule are kept in the quarantine for 7 days. After this period of time the messages are deleted and are not retrievable. The retention period for quarantined messages that matched a transport rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="264bb-139">**Q. ¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?**</span><span class="sxs-lookup"><span data-stu-id="264bb-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>
  
<span data-ttu-id="264bb-p109">A. La capacidad de liberar o informar sobre varios mensajes a la vez no está disponible actualmente en el EAC ni en el correo electrónico en cuarentena del usuario final. Sin embargo, los administradores pueden crear una secuencia de comandos de Windows PowerShell remoto para realizar esta tarea. Use el cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes y el cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="264bb-p109">A. The ability to release or report multiple messages at once is not currently available in the EAC or the end user spam quarantine. However, admins can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
  
 <span data-ttu-id="264bb-144">**P. ¿Se admiten caracteres comodín al buscar mensajes en cuarentena? ¿Puedo buscar mensajes en cuarentena para un dominio específico?**</span><span class="sxs-lookup"><span data-stu-id="264bb-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>
  
<span data-ttu-id="264bb-p110">A. No se admiten caracteres comodín al especificar los criterios de búsqueda en el Centro de administración de Exchange. Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="264bb-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>
  
<span data-ttu-id="264bb-148">Con Windows PowerShell remoto, los administradores pueden especificar el cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes en cuarentena de un dominio específico (por ejemplo, contoso.com):</span><span class="sxs-lookup"><span data-stu-id="264bb-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="264bb-p111">Los resultados se pueden transmitir al cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx). Incluya el parámetro -ReleaseToAll para liberar el mensaje a todos los destinatarios. Una vez que se libera un mensaje, no puede volver a liberarse.</span><span class="sxs-lookup"><span data-stu-id="264bb-p111">The results can be passed to the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```



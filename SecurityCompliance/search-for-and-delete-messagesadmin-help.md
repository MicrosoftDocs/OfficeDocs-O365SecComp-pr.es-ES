---
title: 'Buscar y eliminar mensajes: Ayuda para administradores'
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: Los administradores pueden usar el cmdlet Search-Mailbox para buscar en buzones de usuario y, después, eliminar mensajes de un buzón.
ms.openlocfilehash: c5f727d7772e23cc8723eee6a45e51e3ac074648
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002829"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="8c1f4-103">Buscar y eliminar mensajes: Ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="8c1f4-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="8c1f4-104">Los administradores pueden usar el cmdlet **Search-Mailbox** para buscar en buzones de usuario y, después, eliminar mensajes de un buzón.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="8c1f4-p101">Para buscar y eliminar los mensajes en un solo paso, ejecute el cmdlet **Search-Mailbox** con el modificador  _DeleteContent_. Sin embargo, cuando hace esto, no puede previsualizar los resultados de la búsqueda ni generar un registro de mensajes que será devuelto por la búsqueda y puede eliminar mensajes accidentalmente que pretendía conservar. Para previsualizar un registro de mensajes encontrados en la búsqueda antes de que se eliminen, ejecute el cmdlet **Search-Mailbox** con el modificador  _LogOnly_.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p101">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to. To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="8c1f4-p102">Como una protección adicional, primero puede copiar los mensajes en otro buzón con los parámetros  _TargetMailbox_ y  _TargetFolder_. Al hacer esto, guarda una copia de los mensajes eliminados en caso de que necesite obtener acceso a ellos nuevamente.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p102">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters. By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="8c1f4-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8c1f4-110">Before you begin</span></span>

- <span data-ttu-id="8c1f4-p103">Tiempo estimado para finalizar:  10 minutos. El tiempo real puede variar en función del tamaño del buzón y la consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p103">Estimated time to complete: 10 minutes. The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="8c1f4-p104">No puede usar el Centro de administración de Exchange (EAC) para realizar estos procedimientos. Debe usar el Shell.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p104">You can't use the Exchange admin center (EAC) to perform these procedures. You must use the Shell.</span></span>
    
- <span data-ttu-id="8c1f4-115">Tiene que tener asignados los siguientes roles de administración para buscar y eliminar los mensajes en los buzones de correo de los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8c1f4-115">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="8c1f4-p105">**Búsqueda de buzones**- este rol permite buscar mensajes a través de varios buzones en la organización. Los administradores no están asignados a esta función de forma predeterminada. Para asignar manualmente este rol para que puedan buscar los buzones de correo, agregar usted mismo como miembro del grupo de roles de administración de detección. Vea [Agregar un usuario al grupo de funciones de administración de detección](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p105">**Mailbox Search**- This role allows you to search for messages across multiple mailboxes in your organization. Administrators aren't assigned this role by default. To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group. See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="8c1f4-p106">**Buzón de correo importar exportar** - este rol le permite eliminar mensajes del buzón de un usuario. De forma predeterminada, esta función no está asignada a ningún grupo de funciones. Para eliminar los mensajes de los buzones de los usuarios, puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. Para obtener más información, vea la sección "Adición de una función a un grupo de roles" en [Administrar grupos de roles](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p106">**Mailbox Import Export** - This role allows you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group. For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="8c1f4-p107">Si el buzón desde el cual desea eliminar los mensajes tiene la recuperación de un solo elemento habilitada, primero debe deshabilitar la función. Para obtener más información, consulte [Habilitar o deshabilitar la recuperación de elementos individuales de un buzón de correo](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p107">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature. For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="8c1f4-p108">Si el buzón de correo desde la que desea eliminar los mensajes se pondrá en espera, se recomienda que compruebe con el departamento legal antes de quitar la suspensión y eliminar el contenido de los buzones o la administración de registros. Después de obtener aprobación, siga los pasos enumerados en el tema [Limpia seguridad de la carpeta elementos recuperables](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p108">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content. After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="8c1f4-p109">Puede buscar en un máximo de 10 000 buzones con el cmdlet **Search-Mailbox**. Si es Exchange Online de una organización y tiene más de 10 000 buzones, puede usar la característica Búsqueda de cumplimiento (o el cmdlet **New-ComplianceSearch** correspondiente) para buscar en un número ilimitado de buzones. Después, puede usar el cmdlet **New-ComplianceSearchAction** para eliminar los mensajes encontrados por una búsqueda de cumplimiento. Para obtener más información, vea [Buscar y eliminar mensajes de correo electrónico de la organización de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p109">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet. If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes. Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search. For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="8c1f4-p110">Si incluye una consulta de búsqueda (utilizando el parámetro  *SearchQuery*  ), el cmdlet **Search-Mailbox** devolverá un máximo de 10 000 elementos en los resultados de búsqueda. Por tanto, si incluye una consulta de búsqueda, es posible que deba ejecutar el comando **Search-Mailbox** varias veces para eliminar más de 10 000 elementos.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p110">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="8c1f4-p111">También se buscará en el buzón del usuario archivo cuando se ejecuta el cmdlet **Search-Mailbox** . De forma similar, los elementos en el buzón de archivo principal se eliminarán cuando se usa el cmdlet **Search-Mailbox** con el modificador _DeleteContent_ . Para evitar esto, puede incluir el modificador *DoNotIncludeArchive* . Además, se recomienda no usar el modificador _DeleteContent_ para eliminar los mensajes en Exchange Online buzones que tienen habilitado porque pueden producirse pérdidas de datos inesperadas el archivado ampliación automática.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p111">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet. Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. To prevent this, you can include the  *DoNotIncludeArchive*  switch. Also, we recommend that you don't use the  _DeleteContent_ switch to delete messages in Exchange Online mailboxes that have auto-expanding archiving enabled because unexpected data loss may occur.</span></span> 
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="8c1f4-138">Buscar mensajes y registrar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="8c1f4-138">Search messages and log the search results</span></span>

<span data-ttu-id="8c1f4-p112">En este ejemplo, se buscan mensajes que contengan la frase "Su extracto bancario" en el campo Asunto en el buzón de correo de April Stewart y se registra el resultado en la carpeta SearchAndDeleteLog en el buzón de correo del administrador. Los mensajes no se copian ni eliminar en el buzón de correo de destino.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p112">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox. Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="8c1f4-141">Este ejemplo busca en todos los buzones de la organización los mensajes que tienen cualquier tipo de archivo adjunto que contiene la palabra "Troyano" en el nombre de archivo y envía un mensaje de registro al buzón del administrador.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-141">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="8c1f4-142">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c1f4-142">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
 
## <a name="search-and-delete-messages"></a><span data-ttu-id="8c1f4-143">Buscar y eliminar mensajes</span><span class="sxs-lookup"><span data-stu-id="8c1f4-143">Search and delete messages</span></span>

<span data-ttu-id="8c1f4-p113">En este ejemplo, se buscan mensajes que contengan la frase "Su extracto bancario" en el asunto en el buzón de correo de Yolanda Sánchez y se eliminan los mensajes del buzón de correo de origen. Como se explicó anteriormente, tiene que tener asignado el rol de administración Importar o exportar buzones para eliminar los mensajes del buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p113">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder. As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c1f4-p114">Cuando usa el cmdlet **Search-Mailbox** con el modificador  _DeleteContent_, los mensajes se eliminan permanentemente del buzón origen. Antes de eliminar permanentemente los mensajes, le recomendamos que use el modificador  _LogOnly_ para generar un registro de los mensajes encontrados en la búsqueda antes de que se eliminen o que copie los mensajes en otro buzón antes de eliminarlo desde el buzón origen.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p114">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox. Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="8c1f4-148">En este ejemplo, se buscan mensajes que contengan la frase "Su extracto bancario" en el campo Asunto en el buzón de correo de April Stewart, se copian los resultados de la búsqueda en la carpeta AprilStewart-DeletedMessages en el buzón BackupMailbox y se eliminan los mensajes del buzón de April.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-148">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="8c1f4-149">Este ejemplo busca en todos los buzones de la organización los mensajes con el asunto "Descargar este archivo" y, a continuación, los elimina de forma definitiva.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-149">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="8c1f4-150">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c1f4-150">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>

## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="8c1f4-151">Usar el parámetro -LogLevel Full</span><span class="sxs-lookup"><span data-stu-id="8c1f4-151">Using the -LogLevel Full parameter</span></span>

<span data-ttu-id="8c1f4-p115">En algunos de los ejemplos anteriores, el parámetro  _LogLevel_ (con el valor  `Full`) se usa para registrar información detallada sobre los resultados encontrados por el cmdlet **Search-Mailbox**. Al incluir este parámetro, se crea un mensaje de correo electrónico y se envía al buzón especificado por el parámetro  _TargetMailbox_. El archivo de registro (que es un archivo con formato CSV llamado Search Results.csv) se adjunta a este mensaje de correo electrónico y se guarda en la carpeta especificada por el parámetro  _TargetFolder_. El archivo de registro contiene una fila por cada mensaje incluido en los resultados de la búsqueda al ejecutar el cmdlet **Search-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="8c1f4-p115">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet. When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter. The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter. The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 

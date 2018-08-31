---
title: Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Usar la seguridad de Office 365 &amp; centro de cumplimiento para habilitar buzones de archivo admitir la retención de mensajes de su organización, exhibición de documentos electrónicos y los requisitos de retención.
ms.openlocfilehash: 5ba578ba611f619194ac4f475121bd485b75f9e0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536287"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="23c57-103">Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="23c57-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="23c57-p101">Archivado en Office 365 (también denominado archivado en contexto) proporciona a los usuarios con el espacio de almacenamiento de buzones de correo adicionales. Después de activar buzones de archivo, los usuarios pueden obtener acceso y almacenar los mensajes en sus buzones de archivo mediante el uso de Microsoft Outlook y Outlook Web App a los usuarios también pueden mover o copiar mensajes entre su buzón principal y su buzón de archivo. También pueden recuperar los elementos eliminados de la carpeta elementos recuperables en su buzón de archivo mediante la herramienta de recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="23c57-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook Web App. Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="23c57-p102">Office 365 proporciona una cantidad ilimitada de almacenamiento de archivos con la característica de archivado ampliación automática. Cuando está activado el crecimiento automático de archivado y, a continuación, se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Office 365 agrega automáticamente espacio de almacenamiento adicional. Esto significa que los usuarios no se ejecutan fuera del espacio de almacenamiento de buzones de correo y no tendrá que administrar inicialmente nada después de habilitar el buzón de archivo y activar la ampliación automática de archivado para su organización. Para obtener más información, vea [información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="23c57-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="23c57-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="23c57-112">Before you begin</span></span>

<span data-ttu-id="23c57-p103">Se debe asignar el rol de destinatarios de correo en Exchange Online para habilitar o deshabilitar los buzones de archivo. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de destinatarios y administración de la organización en la página de **permisos** en el centro de administración de Exchange. Si no ve la página de **archivo** en la seguridad &amp; del centro de cumplimiento, pida al administrador que asigne los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="23c57-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="23c57-116">Habilitación de un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="23c57-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="23c57-117">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="23c57-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="23c57-118">Inicie sesión en Office 365 con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="23c57-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="23c57-119">En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **archivo**.</span><span class="sxs-lookup"><span data-stu-id="23c57-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="23c57-p104">Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="23c57-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="23c57-122">En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="23c57-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![Haga clic en habilitar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="23c57-124">En el panel de detalles para el usuario seleccionado, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="23c57-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="23c57-p105">Se muestra una advertencia que indica que, si habilita el buzón de archivo, se moverán los elementos en el buzón del usuario que sean más antiguos que la directiva de archivado asignada al buzón para el nuevo buzón de archivo. La directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de Exchange Online mueve los elementos en el buzón de archivo dos años después de la fecha en que el elemento se ha entregado al buzón o creados por el usuario. Para obtener más información, vea la sección **más información** de este artículo.</span><span class="sxs-lookup"><span data-stu-id="23c57-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="23c57-128">Haga clic en **Sí** para habilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="23c57-p106">Puede tardar unos minutos para crear el buzón de archivo. Cuando se crea, **buzón de archivo: habilitado** se muestra en el panel de detalles del usuario seleccionado. Es posible que deba haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="23c57-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="23c57-p107">También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="23c57-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="23c57-134">Deshabilitar un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="23c57-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="23c57-p108">También puede usar la página de **archivo** en la seguridad &amp; centro de cumplimiento para deshabilitar el buzón de archivo de un usuario. Después de deshabilitar un buzón de archivo, puede conectarse al buzón principal del usuario dentro de 30 días de deshabilitarla. En este caso, se restaura el contenido original del buzón de archivo. Después de 30 días, el contenido del buzón de archivo original se elimina permanentemente y no se puede recuperar. Por lo que si vuelve a habilitar el archivo de más de 30 días después de deshabilitarlo, se crea un nuevo buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="23c57-p109">Tenga en cuenta que la directiva de archivo predeterminado asignado a los buzones de los usuarios mueva los elementos en el buzón de archivo dos años después de la fecha del elemento se entrega. Si se deshabilita el buzón de archivo de un usuario, en los elementos del buzón no se llevará a cabo ninguna acción y permanecen en el buzón del usuario principal.</span><span class="sxs-lookup"><span data-stu-id="23c57-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="23c57-142">Para deshabilitar un buzón de archivo:</span><span class="sxs-lookup"><span data-stu-id="23c57-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="23c57-143">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="23c57-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="23c57-144">Inicie sesión en Office 365 con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="23c57-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="23c57-145">En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **archivo**.</span><span class="sxs-lookup"><span data-stu-id="23c57-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="23c57-p110">Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="23c57-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="23c57-148">En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="23c57-149">En el panel de detalles, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="23c57-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="23c57-150">Se muestra un mensaje de advertencia que indica que dispone de 30 días para volver a habilitar el buzón de archivo, y que después de 30 días, toda la información en el archivo se eliminarán permanentemente.</span><span class="sxs-lookup"><span data-stu-id="23c57-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="23c57-151">Haga clic en **Sí** para deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="23c57-p111">Puede tardar unos minutos para deshabilitar el buzón de archivo. Cuando está deshabilitada, **buzón de archivo: deshabilitado** se muestra en el panel de detalles del usuario seleccionado. Es posible que deba haga clic en **Actualizar** ![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="23c57-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="23c57-p112">También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="23c57-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="23c57-157">Más información</span><span class="sxs-lookup"><span data-stu-id="23c57-157">More information</span></span>
  
- <span data-ttu-id="23c57-p113">Buzones de archivo ayudan a usted y a sus usuarios para satisfacer la retención de la organización, exhibición de documentos electrónicos y los requisitos de retención. Por ejemplo, puede usar la directiva de retención de la organización Exchange para mover el contenido de buzón de correo al buzón de archivo de los usuarios. Al utilizar la herramienta de búsqueda de contenido en la seguridad &amp; también se buscará en el centro de cumplimiento para buscar el buzón de un usuario para contenido específico, buzón de archivo del usuario. Y, cuando se coloque un juicio o aplicar una directiva de retención de Office 365 para el buzón de un usuario, también se conservan los elementos en el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-p113">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="23c57-p114">Cuando se habilita un buzón de archivo, los usuarios pueden almacenar los mensajes en su buzón de archivo. Los usuarios pueden tener acceso a sus buzones de archivo mediante el uso de Microsoft Outlook y Outlook Web App mediante cualquiera de estas aplicaciones de cliente, los usuarios pueden ver los mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón principal y su buzón de archivo. Los usuarios también pueden recuperar elementos eliminados desde la carpeta elementos recuperables en su buzón de archivo mediante la herramienta de recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="23c57-p114">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook Web App. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="23c57-p115">Después de archivo están habilitados los buzones de correo, su organización puede aprovechar la predeterminada Exchange directiva de retención (también denominada directiva de administración de registros de mensajería o MRM) que se asigna automáticamente a todos los buzones. Cuando se habilita un buzón de archivo, la directiva de retención predeterminada Exchange automáticamente hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23c57-p115">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="23c57-168">Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-168">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="23c57-169">Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="23c57-169">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="23c57-170">Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, consulte:</span><span class="sxs-lookup"><span data-stu-id="23c57-170">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
  
  - [<span data-ttu-id="23c57-171">Buzones de archivo en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="23c57-171">Archive mailboxes in Exchange Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=404421)
    
  - [<span data-ttu-id="23c57-172">Etiquetas de retención y directivas de retención</span><span class="sxs-lookup"><span data-stu-id="23c57-172">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="23c57-173">Directiva predeterminada de retención en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="23c57-173">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="23c57-174">Configurar una directiva de eliminación y de archivo para los buzones de correo en la organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="23c57-174">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)

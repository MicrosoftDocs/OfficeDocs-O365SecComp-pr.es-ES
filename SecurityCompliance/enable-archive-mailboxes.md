---
title: Habilitar buzones de archivo en el centro de &amp; seguridad y cumplimiento de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Use el centro de seguridad &amp; y cumplimiento de Office 365 para permitir que los buzones de archivo admitan los requisitos de retención, exhibición de documentos electrónicos y conservación de mensajes de la organización.
ms.openlocfilehash: 763097925ed0910fe9a66e5c556b8a2995df74e6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296063"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="c5709-103">Habilitar buzones de archivo en el centro de &amp; seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="c5709-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="c5709-p101">El archivado en Office 365 (también conocido como archivo local) proporciona a los usuarios un espacio de almacenamiento de buzones adicional. Después de activar los buzones de archivo, los usuarios pueden tener acceso a los mensajes y almacenarlos en sus buzones de archivo con Microsoft Outlook y Outlook en la web (anteriormente conocido como Outlook Web App). Los usuarios también pueden mover o copiar mensajes entre su buzón de correo principal y su buzón de archivo. También pueden recuperar elementos eliminados de la carpeta elementos recuperables de su buzón de archivo mediante la herramienta recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="c5709-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App). Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c5709-p102">Office 365 proporciona una cantidad ilimitada de almacenamiento de archivo con la característica de archivado de expansión automática. Cuando el archivado de expansión automática está activado y, a continuación, se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Office 365 agrega automáticamente espacio de almacenamiento adicional. Esto significa que los usuarios no se quedarán sin espacio de almacenamiento en el buzón de correo y no tendrá que administrar nada después de habilitar inicialmente el buzón de archivo y activar el archivado de expansión automática para su organización. Para obtener más información, vea [información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c5709-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c5709-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c5709-112">Before you begin</span></span>

<span data-ttu-id="c5709-p103">Debe tener asignado el rol destinatarios de correo en Exchange Online para habilitar o deshabilitar buzones de archivo. De forma predeterminada, este rol se asigna a los grupos de roles administración de destinatarios y administración de la organización en la página **permisos** del centro de administración de Exchange. Si no ve la página **archivo** en el centro de &amp; seguridad y cumplimiento, pida al administrador que le asigne los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="c5709-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="c5709-116">Habilitación de un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="c5709-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="c5709-117">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="c5709-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c5709-118">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c5709-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="c5709-119">En el panel izquierdo del centro de &amp; seguridad y cumplimiento, haga clic en **archivo**de **gobierno** \> de datos.</span><span class="sxs-lookup"><span data-stu-id="c5709-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="c5709-p104">Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="c5709-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="c5709-122">En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="c5709-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![Haga clic en habilitar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo.](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="c5709-124">En el panel de detalles del usuario seleccionado, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="c5709-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="c5709-p105">Se muestra una advertencia que indica que si habilita el buzón de archivo, los elementos del buzón del usuario que sean más antiguos que la Directiva de archivado asignada al buzón de correo se moverán al nuevo buzón de archivo. La Directiva de archivo predeterminada que forma parte de la Directiva de retención asignada a los buzones de Exchange Online mueve los elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario. Para obtener más información, consulte la sección **más información** de este artículo.</span><span class="sxs-lookup"><span data-stu-id="c5709-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="c5709-128">Haga clic en **Sí** para habilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="c5709-p106">La creación del buzón de archivo puede tardar unos minutos en crearse. Cuando se crea, el **buzón de archivo: habilitado** se muestra en el panel de detalles del usuario seleccionado. Puede que tenga que hacer \*\*\*\* ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="c5709-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="c5709-p107">También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="c5709-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="c5709-134">Deshabilitar un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="c5709-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="c5709-p108">También puede usar la página **archivo** del centro de seguridad &amp; y cumplimiento para deshabilitar el buzón de archivo de un usuario. Después de deshabilitar un buzón de archivo, puede volver a conectarlo al buzón de correo principal del usuario en un plazo de 30 días a partir de la deshabilitación. En este caso, se restaura el contenido original del buzón de archivo. TransCurrido el plazo de 30 días, el contenido del buzón de archivo original se elimina permanentemente y no se puede recuperar. Por lo tanto, si vuelve a habilitar el archivo más de 30 días después de deshabilitarlo, se crea un nuevo buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="c5709-p109">Tenga en cuenta que la Directiva de archivo predeterminada asignada a los buzones de correo de los usuarios mueve los elementos al buzón de archivo dos años después de la fecha en que se entrega el artículo. Si deshabilita el buzón de archivo de un usuario, no se realizará ninguna acción en los elementos del buzón y permanecerán en el buzón de correo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5709-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="c5709-142">Para deshabilitar un buzón de archivo:</span><span class="sxs-lookup"><span data-stu-id="c5709-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="c5709-143">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="c5709-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c5709-144">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="c5709-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="c5709-145">En el panel izquierdo del centro de &amp; seguridad y cumplimiento, haga clic en **archivo**de **gobierno** \> de datos.</span><span class="sxs-lookup"><span data-stu-id="c5709-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="c5709-p110">Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="c5709-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="c5709-148">En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="c5709-149">En el panel de detalles, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="c5709-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="c5709-150">Se muestra un mensaje de advertencia que indica que tendrá 30 días para volver a habilitar el buzón de archivo y que, después de 30 días, toda la información del archivo se eliminará de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="c5709-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="c5709-151">Haga clic en **Sí** para deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="c5709-p111">La deshabilitación del buzón de archivo puede tardar algunos minutos en realizarse. Cuando está deshabilitado, el **buzón de archivo:** deshabilitado se muestra en el panel de detalles del usuario seleccionado. Puede que tenga que hacer \*\*\*\* ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="c5709-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="c5709-p112">También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="c5709-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="c5709-157">Usar Exchange Online PowerShell para habilitar o deshabilitar buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="c5709-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="c5709-p113">También puede usar Exchange Online PowerShell para habilitar los buzones de archivo. La razón principal para usar PowerShell es que puede habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="c5709-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="c5709-p114">El primer paso consiste en conectarse a Exchange Online PowerShell. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5709-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="c5709-162">Una vez que esté conectado a Exchange Online, puede ejecutar los comandos de las siguientes secciones para habilitar o deshabilitar los buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="c5709-163">Habilitar buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="c5709-163">Enable archive mailboxes</span></span>

<span data-ttu-id="c5709-164">Ejecute el siguiente comando para habilitar el buzón de archivo para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="c5709-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="c5709-165">Ejecute el siguiente comando para habilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo no está habilitado actualmente).</span><span class="sxs-lookup"><span data-stu-id="c5709-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="c5709-166">Deshabilitar los buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="c5709-166">Disable archive mailboxes</span></span>

<span data-ttu-id="c5709-167">Ejecute el siguiente comando para deshabilitar el buzón de archivo para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="c5709-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="c5709-168">Ejecute el siguiente comando para deshabilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo está habilitado actualmente).</span><span class="sxs-lookup"><span data-stu-id="c5709-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="c5709-169">Más información</span><span class="sxs-lookup"><span data-stu-id="c5709-169">More information</span></span>
  
- <span data-ttu-id="c5709-p115">Los buzones de archivo le ayudan a usted y a sus usuarios a cumplir los requisitos de retención, exhibición de documentos electrónicos y conservación de la organización. Por ejemplo, puede usar la Directiva de retención de Exchange de su organización para mover el contenido de los buzones de correo al buzón de archivo de los usuarios. Cuando use la herramienta de búsqueda de contenido en el &amp; centro de seguridad y cumplimiento para buscar contenido específico en el buzón de un usuario, también se buscará en el buzón de archivo del usuario. Y, al poner una retención por juicio o aplicar una directiva de retención de Office 365 en el buzón de un usuario, también se conservan los elementos del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="c5709-p116">Cuando se habilita un buzón de archivo, los usuarios pueden almacenar mensajes en su buzón de archivo. Los usuarios pueden tener acceso a sus buzones de archivo mediante Microsoft Outlook y Outlook en la Web. Mediante cualquiera de estas aplicaciones cliente, los usuarios pueden ver los mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón de correo principal y su buzón de archivo. Los usuarios también pueden recuperar elementos eliminados de la carpeta elementos recuperables de su buzón de archivo mediante la herramienta recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="c5709-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="c5709-p117">Una vez habilitados los buzones de archivo, su organización puede aprovechar la Directiva de retención de Exchange predeterminada (también denominada Directiva de administración de registros de mensajes o de MRM) que se asigna automáticamente a todos los buzones. Cuando se habilita un buzón de archivo, la Directiva de retención de Exchange predeterminada hace lo siguiente automáticamente:</span><span class="sxs-lookup"><span data-stu-id="c5709-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="c5709-180">Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="c5709-181">Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="c5709-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="c5709-182">Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, consulte:</span><span class="sxs-lookup"><span data-stu-id="c5709-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
  
    
  - [<span data-ttu-id="c5709-183">Etiquetas de retención y directivas de retención</span><span class="sxs-lookup"><span data-stu-id="c5709-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="c5709-184">Directiva de retención predeterminada en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c5709-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="c5709-185">Configurar una directiva de archivo y eliminación para los buzones de la organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="c5709-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)

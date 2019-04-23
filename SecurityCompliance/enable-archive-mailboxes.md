---
title: Habilitar buzones de archivo en el centro de seguridad & cumplimiento
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
description: Use el centro de seguridad & cumplimiento en Office 365 para habilitar los buzones de archivo para que admitan los requisitos de retención, exhibición de documentos electrónicos y conservación de mensajes de la organización.
ms.openlocfilehash: d363943910d970576976d8386196b450dd5694f3
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958311"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a><span data-ttu-id="33f72-103">Habilitar buzones de archivo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="33f72-103">Enable archive mailboxes in the Security & Compliance Center</span></span>
  
<span data-ttu-id="33f72-104">El archivado en Office 365 (también conocido como archivo local) proporciona a los usuarios un espacio de almacenamiento de buzones adicional.</span><span class="sxs-lookup"><span data-stu-id="33f72-104">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="33f72-105">Después de activar los buzones de archivo, los usuarios pueden tener acceso a los mensajes y almacenarlos en sus buzones de archivo con Microsoft Outlook y Outlook en la web (anteriormente conocido como Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="33f72-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="33f72-106">Los usuarios también pueden mover o copiar mensajes entre su buzón de correo principal y su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-106">Users can also move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="33f72-107">También pueden recuperar elementos eliminados de la carpeta elementos recuperables de su buzón de archivo mediante la herramienta recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="33f72-107">They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="33f72-108">Office 365 proporciona una cantidad ilimitada de almacenamiento de archivo con la característica de archivado de expansión automática.</span><span class="sxs-lookup"><span data-stu-id="33f72-108">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature.</span></span> <span data-ttu-id="33f72-109">Cuando el archivado de expansión automática está activado y, a continuación, se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Office 365 agrega automáticamente espacio de almacenamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="33f72-109">When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space.</span></span> <span data-ttu-id="33f72-110">Esto significa que los usuarios no se quedarán sin espacio de almacenamiento en el buzón de correo y no tendrá que administrar nada después de habilitar inicialmente el buzón de archivo y activar el archivado de expansión automática para su organización.</span><span class="sxs-lookup"><span data-stu-id="33f72-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="33f72-111">Para obtener más información, vea [Información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="33f72-111">For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="33f72-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="33f72-112">Before you begin</span></span>

<span data-ttu-id="33f72-113">Debe tener asignado el rol destinatarios de correo en Exchange Online para habilitar o deshabilitar buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="33f72-114">De forma predeterminada, este rol se asigna a los grupos de roles administración de destinatarios y administración de la organización en la página **permisos** del centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="33f72-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="33f72-115">Si no ve la página **archivo** en el centro de seguridad & cumplimiento, pida al administrador que le asigne los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="33f72-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="33f72-116">Habilitación de un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="33f72-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="33f72-117">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="33f72-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="33f72-118">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="33f72-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="33f72-119">En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en **archivo**de **gobierno** \> de datos.</span><span class="sxs-lookup"><span data-stu-id="33f72-119">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="33f72-120">Aparece la página **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="33f72-120">The **Archive** page is displayed.</span></span> <span data-ttu-id="33f72-121">La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-121">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="33f72-122">En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="33f72-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![Haga clic en habilitar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo.](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="33f72-124">En el panel de detalles del usuario seleccionado, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="33f72-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="33f72-125">Se muestra una advertencia que indica que si habilita el buzón de archivo, los elementos del buzón del usuario que sean más antiguos que la Directiva de archivado asignada al buzón de correo se moverán al nuevo buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-125">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="33f72-126">La Directiva de archivo predeterminada que forma parte de la Directiva de retención asignada a los buzones de Exchange Online mueve los elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-126">The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="33f72-127">Para obtener más información, consulte la sección **más información** de este artículo.</span><span class="sxs-lookup"><span data-stu-id="33f72-127">For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="33f72-128">Haga clic en **Sí** para habilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="33f72-129">El buzón de archivo puede tardar un poco en crearse.</span><span class="sxs-lookup"><span data-stu-id="33f72-129">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="33f72-130">Cuando se crea, el **buzón de archivo: habilitado** se muestra en el panel de detalles del usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="33f72-130">When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="33f72-131">Puede que tenga que hacer \*\*\*\* ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="33f72-131">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="33f72-p107">También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="33f72-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="33f72-134">Deshabilitar un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="33f72-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="33f72-135">También puede usar la página **archivo** del centro de seguridad & cumplimiento para deshabilitar el buzón de archivo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-135">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="33f72-136">Después de deshabilitar un buzón de archivo, puede volver a conectarlo al buzón de correo principal del usuario en un plazo de 30 días tras la deshabilitación.</span><span class="sxs-lookup"><span data-stu-id="33f72-136">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="33f72-137">En este caso se restaura el contenido original del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-137">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="33f72-138">Transcurridos los 30 días, el contenido del buzón de archivo original se elimina definitivamente y no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="33f72-138">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="33f72-139">Así pues, si vuelve a habilitar el archivo después de los 30 días posteriores a la deshabilitación, se crea un buzón de archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="33f72-139">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="33f72-140">Tenga en cuenta que la Directiva de archivo predeterminada asignada a los buzones de correo de los usuarios mueve los elementos al buzón de archivo dos años después de la fecha en que se entrega el artículo.</span><span class="sxs-lookup"><span data-stu-id="33f72-140">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="33f72-141">Si deshabilita el buzón de archivo de un usuario, no se realizará ninguna acción en los elementos del buzón y permanecerán en el buzón de correo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-141">If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="33f72-142">Para deshabilitar un buzón de archivo:</span><span class="sxs-lookup"><span data-stu-id="33f72-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="33f72-143">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="33f72-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="33f72-144">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="33f72-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="33f72-145">En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en **archivo**de **gobierno** \> de datos.</span><span class="sxs-lookup"><span data-stu-id="33f72-145">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="33f72-p110">Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="33f72-148">En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="33f72-149">En el panel de detalles, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="33f72-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="33f72-150">Se muestra un mensaje de advertencia que indica que tendrá 30 días para volver a habilitar el buzón de archivo y que, después de 30 días, toda la información del archivo se eliminará de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="33f72-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="33f72-151">Haga clic en **Sí** para deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="33f72-152">El buzón de archivo puede tardar un poco en deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="33f72-152">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="33f72-153">Cuando está deshabilitado, el **buzón de archivo:** deshabilitado se muestra en el panel de detalles del usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="33f72-153">When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="33f72-154">Puede que tenga que hacer \*\*\*\* ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="33f72-154">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="33f72-p112">También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="33f72-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="33f72-157">Usar Exchange Online PowerShell para habilitar o deshabilitar buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="33f72-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="33f72-158">También puede usar Exchange Online PowerShell para habilitar los buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-158">You can also use Exchange Online PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="33f72-159">La razón principal para usar PowerShell es que puede habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="33f72-159">The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="33f72-160">El primer paso consiste en conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33f72-160">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="33f72-161">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="33f72-161">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="33f72-162">Una vez que esté conectado a Exchange Online, puede ejecutar los comandos de las siguientes secciones para habilitar o deshabilitar los buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="33f72-163">Habilitar buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="33f72-163">Enable archive mailboxes</span></span>

<span data-ttu-id="33f72-164">Ejecute el siguiente comando para habilitar el buzón de archivo para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="33f72-165">Ejecute el siguiente comando para habilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo no está habilitado actualmente).</span><span class="sxs-lookup"><span data-stu-id="33f72-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="33f72-166">DesHabilitar buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="33f72-166">Disable archive mailboxes</span></span>

<span data-ttu-id="33f72-167">Ejecute el siguiente comando para deshabilitar el buzón de archivo para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="33f72-168">Ejecute el siguiente comando para deshabilitar el buzón de archivo para todos los usuarios de la organización (cuyo buzón de archivo está habilitado actualmente).</span><span class="sxs-lookup"><span data-stu-id="33f72-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="33f72-169">Más información</span><span class="sxs-lookup"><span data-stu-id="33f72-169">More information</span></span>
  
- <span data-ttu-id="33f72-170">Los buzones de archivo le ayudan a usted y a sus usuarios a cumplir los requisitos de retención, exhibición de documentos electrónicos y conservación de la organización.</span><span class="sxs-lookup"><span data-stu-id="33f72-170">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="33f72-171">Por ejemplo, puede usar la Directiva de retención de Exchange de su organización para mover el contenido de los buzones de correo al buzón de archivo de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="33f72-171">For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="33f72-172">Cuando use la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar contenido específico en el buzón de un usuario, también se buscará en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="33f72-172">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="33f72-173">Y, al poner una retención por juicio o aplicar una directiva de retención de Office 365 en el buzón de un usuario, también se conservan los elementos del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-173">And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="33f72-174">Cuando se habilita un buzón de archivo, los usuarios pueden almacenar mensajes en su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-174">When an archive mailbox is enabled, users can store messages in their archive mailbox.</span></span> <span data-ttu-id="33f72-175">Los usuarios pueden tener acceso a sus buzones de archivo mediante Microsoft Outlook y Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="33f72-175">Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web.</span></span> <span data-ttu-id="33f72-176">Mediante cualquiera de estas aplicaciones cliente, los usuarios pueden visualizar mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-176">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="33f72-177">Los usuarios también pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="33f72-177">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="33f72-178">Una vez habilitados los buzones de archivo, su organización puede aprovechar la Directiva de retención de Exchange predeterminada (también denominada Directiva de administración de registros de mensajes o de MRM) que se asigna automáticamente a todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="33f72-178">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="33f72-179">Cuando se habilita un buzón de archivo, la Directiva de retención de Exchange predeterminada hace lo siguiente automáticamente:</span><span class="sxs-lookup"><span data-stu-id="33f72-179">When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="33f72-180">Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="33f72-181">Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="33f72-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="33f72-182">Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, consulte:</span><span class="sxs-lookup"><span data-stu-id="33f72-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="33f72-183">Etiquetas de retención y directivas de retención</span><span class="sxs-lookup"><span data-stu-id="33f72-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="33f72-184">Directiva de retención predeterminada en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="33f72-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="33f72-185">Configurar una directiva de archivo y eliminación para los buzones de la organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="33f72-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)

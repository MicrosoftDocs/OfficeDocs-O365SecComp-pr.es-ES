---
title: Habilitar buzones de archivo en el Centro de seguridad y cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Usar el Centro de seguridad y cumplimiento en Office 365 para permitir que los buzones de archivo sean compatibles con los requisitos de retención de mensajes, eDiscovery y conservación de mensajes de su organización.
ms.openlocfilehash: 5cf399b311b6c342aff2d84477edaa945f8e0cd4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153292"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a><span data-ttu-id="e09a6-103">Habilitar buzones de archivo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e09a6-103">Enable archive mailboxes in the Security &  Compliance Center</span></span>
  
<span data-ttu-id="e09a6-104">El archivado en Office 365 (también denominado archivado local) proporciona a los usuarios espacio de almacenamiento adicional en el buzón.</span><span class="sxs-lookup"><span data-stu-id="e09a6-104">Archiving in Exchange Online (called In-Place Archiving) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="e09a6-105">Después de habilitar los buzones de archivo, los usuarios pueden obtener acceso a los mensajes y almacenarlos en los buzones de archivo con Microsoft Outlook y Outlook en la Web (anteriormente denominada Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="e09a6-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="e09a6-106">Los usuarios también pueden mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-106">Users can view an archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="e09a6-107">También pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="e09a6-107">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e09a6-108">Office 365 proporciona una cantidad ilimitada de almacenamiento de archivo con la característica de archivado de ampliación automática.</span><span class="sxs-lookup"><span data-stu-id="e09a6-108">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature.</span></span> <span data-ttu-id="e09a6-109">Cuando se activa el archivado de extensión automática y se alcanza la cuota de almacenamiento inicial en el buzón de archivo de un usuario, Office 365 agrega automáticamente espacio de almacenamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="e09a6-109">When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space.</span></span> <span data-ttu-id="e09a6-110">Esto significa que los usuarios no se quedan sin espacio de almacenamiento en el buzón y que no tendrá que administrar nada después de habilitar el buzón de archivo por primera vez y activar el archivado de ampliación automática para su organización.</span><span class="sxs-lookup"><span data-stu-id="e09a6-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="e09a6-111">Para obtener más información, vea [Información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="e09a6-111">For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="e09a6-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e09a6-112">Before you begin</span></span>

<span data-ttu-id="e09a6-113">Debe tener asignado el rol de Destinatarios de correo de Exchange Online para habilitar o deshabilitar los buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="e09a6-114">De manera predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Administración de destinatarios en la página **Permisos** del centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e09a6-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="e09a6-115">Si no ve la página **Archivo** en el Centro de seguridad y cumplimiento, pida al administrador que le asigne los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="e09a6-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="e09a6-116">Habilitación de un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="e09a6-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="e09a6-117">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e09a6-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="e09a6-118">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="e09a6-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="e09a6-119">En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Gobierno de datos** \> **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="e09a6-119">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="e09a6-120">Aparece la página **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="e09a6-120">The **Archive** page is displayed.</span></span> <span data-ttu-id="e09a6-121">La columna **Buzón de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-121">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="e09a6-122">En la lista de buzones de correo, seleccione el usuario para el que desea habilitar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![Haga clic en Activar en el panel de detalles del usuario seleccionado para habilitar el buzón de archivo.](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="e09a6-124">En el panel de detalles para el usuario seleccionado, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="e09a6-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="e09a6-125">Se muestra una advertencia que indica que, si habilita el buzón de archivo, los elementos en el buzón del usuario que sean más antiguos que la directiva de archivado asignada al buzón se moverán al nuevo buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-125">A warning is displayed saying that if you enable the archive mailbox, items in the user’s mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="e09a6-126">La directiva de archivo predeterminada que forma parte de la directiva de retención asignada a buzones de Exchange Online mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó al buzón o fue creado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-126">As previously explained, the default archive policy that is part of the retention policy assigned to ExchangeOnline mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="e09a6-127">Para más información, vea la sección **Más información** de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-127">For more information, see the  **Web fonts** section in this article.</span></span> 
    
6. <span data-ttu-id="e09a6-128">Haga clic en **Sí** para habilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="e09a6-129">Puede tardar unos momentos para crear el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-129">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="e09a6-130">Una vez creado, aparece **Buzón de archivo: habilitado** en el panel de detalles del usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e09a6-130">When it’s created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="e09a6-131">Es posible que deba hacer clic en **Actualizar** ![Icono de actualizar](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="e09a6-131">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="e09a6-p107">También puede habilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo deshabilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Habilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="e09a6-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="e09a6-134">Deshabilitar un buzón de archivo</span><span class="sxs-lookup"><span data-stu-id="e09a6-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="e09a6-135">También puede usar la página **Archivo** en el Centro de seguridad y cumplimiento para deshabilitar el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-135">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="e09a6-136">Después de deshabilitar un buzón de archivo, puede volver a conectarlo al buzón de correo principal del usuario en un plazo de 30 días tras la deshabilitación.</span><span class="sxs-lookup"><span data-stu-id="e09a6-136">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="e09a6-137">En este caso, se restaura el contenido original del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-137">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="e09a6-138">Transcurridos los 30 días, el contenido del buzón de archivo original se elimina definitivamente y no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="e09a6-138">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="e09a6-139">Así, si vuelve a habilitar el archivo después de los 30 días posteriores a la deshabilitación, se crea un buzón de archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-139">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="e09a6-140">Tenga en cuenta que la directiva de archivo predeterminada asignada a buzones de usuarios mueve elementos al buzón de archivo dos años después de la fecha en que el elemento se entregó.</span><span class="sxs-lookup"><span data-stu-id="e09a6-140">As previously explained, the default archive policy assigned to users’ mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="e09a6-141">Si deshabilita un buzón de archivo de un usuario, no se realizará ninguna acción en los elementos del buzón y permanecerán en el buzón principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-141">If you disable a user’s archive mailbox, no action will be taken on mailbox items and they will remain in the user’s primary mailbox.</span></span>
  
<span data-ttu-id="e09a6-142">Para deshabilitar un buzón de archivo:</span><span class="sxs-lookup"><span data-stu-id="e09a6-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="e09a6-143">Vaya a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e09a6-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="e09a6-144">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="e09a6-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="e09a6-145">En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Gobierno de datos** \> **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="e09a6-145">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="e09a6-p110">Aparece la página **Archivo**. La columna **Buzón de correo de archivo** indica si un buzón de archivo está habilitado o deshabilitado para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="e09a6-148">En la lista de buzones, seleccione el usuario para el que desea deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="e09a6-149">En el panel de detalles, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="e09a6-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="e09a6-150">Aparece un mensaje de advertencia que indica que tendrá 30 días para volver a habilitar el buzón de archivo y que, transcurridos esos 30 días, toda la información del archivo se eliminará permanentemente.</span><span class="sxs-lookup"><span data-stu-id="e09a6-150">A warning message is displayed saying that you'll have 30 days  to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="e09a6-151">Haga clic en **Sí** para deshabilitar el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="e09a6-152">El buzón de archivo puede tardar un poco en deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="e09a6-152">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="e09a6-153">Una vez deshabilitado, aparece **Buzón de archivo: deshabilitado** en el panel de detalles del usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e09a6-153">When it’s disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="e09a6-154">Es posible que deba hacer clic en **Actualizar** ![Icono de actualizar](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="e09a6-154">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="e09a6-p112">También puede deshabilitar buzones de archivo de forma masiva seleccionando varios usuarios con los buzones de archivo habilitados (use las teclas Mayús o Ctrl). Después de seleccionar varios buzones, haga clic en **Deshabilitar** en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="e09a6-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="e09a6-157">Usar PowerShell de Exchange Online para habilitar o deshabilitar buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="e09a6-158">También puede usar PowerShell de Exchange Online para habilitar buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-158">You can use the Exchange admin center (EAC) or Windows PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="e09a6-159">La razón principal para usar PowerShell es que permite habilitar rápidamente el buzón de archivo para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="e09a6-159">The primary reason to use Windows PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="e09a6-160">El primer paso es conectar al PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e09a6-160">The first step is to connect to your Exchange Online organization using Windows PowerShell.</span></span> <span data-ttu-id="e09a6-161">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e09a6-161">For instructions, see [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="e09a6-162">Una vez que esté conectado a Exchange Online, puede ejecutar los comandos de las secciones siguientes para habilitar o deshabilitar los buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="e09a6-163">Habilitar buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="e09a6-163">Enable archive mailboxes</span></span>

<span data-ttu-id="e09a6-164">Ejecute el comando siguiente para habilitar el buzón de archivo para un único usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="e09a6-165">Ejecute el comando siguiente para habilitar el buzón de archivo para todos los usuarios de su organización (cuyo buzón de archivo no está habilitado en este momento).</span><span class="sxs-lookup"><span data-stu-id="e09a6-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="e09a6-166">Deshabilitar los buzones de archivo</span><span class="sxs-lookup"><span data-stu-id="e09a6-166">Disable archive mailboxes</span></span>

<span data-ttu-id="e09a6-167">Ejecute el siguiente comando para deshabilitar el buzón de archivo de un único usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="e09a6-168">Ejecute el comando siguiente para deshabilitar el buzón de archivo para todos los usuarios de su organización (cuyo buzón de archivo está habilitado en este momento).</span><span class="sxs-lookup"><span data-stu-id="e09a6-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="e09a6-169">Más información</span><span class="sxs-lookup"><span data-stu-id="e09a6-169">More information</span></span>
  
- <span data-ttu-id="e09a6-170">Cuando un buzón de archivo está habilitado, los usuarios pueden almacenar mensajes en su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-170">When their archive mailbox  is enabled, users can store messages in their archive mailbox (also called an In-Place Archive).</span></span> <span data-ttu-id="e09a6-171">Los usuarios pueden obtener acceso a los buzones de archivo mediante Microsoft Outlook y Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="e09a6-171">Users can access their archive mailboxes by using Outlook and Outlook Web App.</span></span> <span data-ttu-id="e09a6-172">Mediante cualquiera de estas aplicaciones cliente, los usuarios pueden visualizar mensajes en su buzón de archivo y mover o copiar mensajes entre su buzón de correo principal y el buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-172">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="e09a6-173">Los usuarios también pueden recuperar elementos eliminados de la carpeta de Elementos recuperables en su buzón de archivo mediante la herramienta Recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="e09a6-173">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

   <span data-ttu-id="e09a6-174">Para obtener una lista de las licencias de Outlook que son compatibles con el archivado local, vea [Requisitos de licencia de Outlook para las funciones de Exchange](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span><span class="sxs-lookup"><span data-stu-id="e09a6-174">For a list of Outlook licenses that support In-Place Archiving, see [Outlook license requirements for Exchange features](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span></span>

- <span data-ttu-id="e09a6-175">Los buzones de archivo permiten que usted y sus usuarios cumplan con los requisitos de retención de mensajes de la organización, eDiscovery y conservación.</span><span class="sxs-lookup"><span data-stu-id="e09a6-175">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="e09a6-176">Por ejemplo, puede usar la directiva de retención de Exchange de su organización para mover el contenido del buzón al buzón de archivo de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e09a6-176">You can use your organization's mailbox retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="e09a6-177">Cuando se usa la herramienta de Búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar contenido específico en el buzón de un usuario, también se buscará en el buzón de archivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="e09a6-177">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="e09a6-178">Y, cuando se coloca una Retención por juicio o se aplica una directiva de retención de Office 365 en el buzón de un usuario, también se retienen los elementos del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-178">And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="e09a6-179">Cuando se habilitan los buzones de archivo, la organización puede beneficiarse de la directiva de retención de Exchange predeterminada (también llamada directiva de Administración de registros de mensajería o MRM) que se asigna automáticamente a todos los buzones.</span><span class="sxs-lookup"><span data-stu-id="e09a6-179">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="e09a6-180">Cuando se habilita un buzón de archivo, la directiva de retención de Exchange predeterminada hace automáticamente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e09a6-180">When an archive mailbox is enabled, the default retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="e09a6-181">Mueve los elementos que tienen dos años o más del buzón principal del usuario a su buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-181">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="e09a6-182">Mueve los elementos que tienen 14 días o más de la carpeta Elementos recuperables del buzón de correo principal del usuario a la carpeta Elementos recuperables del buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="e09a6-182">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="e09a6-183">Para obtener más información acerca de los buzones de archivo y las directivas de retención de Exchange, vea:</span><span class="sxs-lookup"><span data-stu-id="e09a6-183">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="e09a6-184">Etiquetas de retención y directivas de retención</span><span class="sxs-lookup"><span data-stu-id="e09a6-184">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - <span data-ttu-id="e09a6-185">[Directiva de retención predeterminada de Exchange Online ](https://go.microsoft.com/fwlink/?linkid=839418)</span><span class="sxs-lookup"><span data-stu-id="e09a6-185">[](https://go.microsoft.com/fwlink/?linkid=839418)Default Retention Policy in Exchange Online and Exchange Server</span></span>
    
  - [<span data-ttu-id="e09a6-186">Configurar una directiva de archivo y eliminación de buzones en la organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="e09a6-186">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)

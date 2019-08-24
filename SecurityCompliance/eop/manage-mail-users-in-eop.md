---
title: Administrar usuarios de correo en EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP).
ms.openlocfilehash: 69ed6460966a399ac5b1e3cf71bd985917bec82c
ms.sourcegitcommit: f57d411e06c955d648dfa1a2a473aa45416e1377
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "36620494"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="2d5bd-103">Administrar usuarios de correo en EOP</span><span class="sxs-lookup"><span data-stu-id="2d5bd-103">Manage mail users in EOP</span></span>

<span data-ttu-id="2d5bd-p101">La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP). Hay varios métodos para administrar usuarios en EOP:</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="2d5bd-106">Usar la sincronización de directorios para administrar usuarios de correo: si su empresa tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizarlas con Azure Active Directory (AD), donde se almacena una copia de las cuentas en la nube.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="2d5bd-107">Cuando sincroniza las cuentas de usuario existentes con Azure Active Directory, puede ver esos usuarios en el panel **Destinatarios** del Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="2d5bd-108">Se recomienda usar la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-108">Using directory synchronization is recommended.</span></span> 
    
- <span data-ttu-id="2d5bd-109">Usar el EAC para administrar usuarios de correo: agregar y administrar usuarios de correo directamente en el EAC.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="2d5bd-110">Es la manera más fácil de agregar usuarios de correo y resulta útil para agregar un usuario cada vez.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>
    
- <span data-ttu-id="2d5bd-111">Usar Windows PowerShell remoto para administrar usuarios de correo: agregar y administrar usuarios de correo ejecutando Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="2d5bd-112">Este método es útil para agregar varios registros y crear scripts.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-112">This method is useful for adding multiple records and creating scripts.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2d5bd-113">Puede Agregar usuarios en el centro de administración de Microsoft 365, pero estos usuarios no se pueden usar como destinatarios de correo.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2d5bd-114">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2d5bd-114">Before you begin</span></span>

- <span data-ttu-id="2d5bd-p105">Los procedimientos descritos en este tema requieren permisos específicos. Vea cada procedimiento para ver la información de permisos.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p105">Procedures in this topic require specific permissions. See each procedure for its permissions information.</span></span>
    
- <span data-ttu-id="2d5bd-117">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="2d5bd-p106">¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p106">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="2d5bd-121">Usar la sincronización de directorios para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="2d5bd-121">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="2d5bd-122">En esta sección se proporciona información sobre cómo administrar usuarios de correo mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-122">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2d5bd-123">Si usa la sincronización de directorios para administrar los destinatarios, puede seguir agregando y administrando usuarios en el centro de administración de Microsoft 365, pero no se sincronizarán con Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-123">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="2d5bd-124">Esto se debe a que la sincronización de directorios solo sincroniza los destinatarios de Active Directory local con la nube.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-124">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> 
  
> [!TIP]
>  <span data-ttu-id="2d5bd-125">Se recomienda usar la sincronización de directorios con las siguientes características: > **Listas de remitentes bloqueados y de remitentes seguros de Outlook**: cuando se sincronizan con el servicio, estas listas tienen prioridad sobre filtrado de correo no deseado del servicio.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-125">Using directory synchronization is recommended for use with the following features: > **Outlook safe sender and blocked sender lists** - When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="2d5bd-126">Esto permite a los usuarios administrar sus propias listas de remitentes seguros y remitentes bloqueados por usuario o por dominio.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-126">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span><span data-ttu-id="2d5bd-127"> > **Bloqueo perimetral basado en directorios (DBEB)**: para obtener más información sobre DBEB, vea [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-127"> > **Directory Based Edge Blocking (DBEB)** - For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span><span data-ttu-id="2d5bd-128"> > **Cuarentena de correo no deseado de usuarios finales**: para poder acceder a la cuarentena de correo no deseado de usuarios finales, los usuarios finales deben tener un identificador de usuario de Office 365 y una contraseña válidos.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-128"> > **End user spam quarantine** - In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="2d5bd-129">Los clientes de EOP que protejan los buzones locales deben ser usuarios de correo electrónico válidos.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-129">EOP customers protecting on-premises mailboxes must be valid email users.</span></span><span data-ttu-id="2d5bd-130"> > **Reglas de flujo de correo** : cuando se usa la sincronización de directorios, los usuarios y grupos de Active Directory existentes se cargan automáticamente en la nube y, a continuación, se pueden crear reglas de flujo de correo (también conocidas como reglas de transporte) dirigidas a usuarios específicos o grupos sin tener que agregarlos manualmente a través del EAC o PowerShell de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-130"> > **Mail flow rules** - When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="2d5bd-131">Tenga en cuenta que los [grupos de distribución dinámicos](https://go.microsoft.com/fwlink/?LinkId=507569) no se pueden sincronizar mediante la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-131">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span> 
  
 <span data-ttu-id="2d5bd-132">**Antes de empezar**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-132">**Before you begin**</span></span>
  
<span data-ttu-id="2d5bd-133">Obtenga los permisos necesarios y prepárese para la sincronización de directorios, tal como se describe en [Preparar la sincronización de directorios](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-133">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="2d5bd-134">Para sincronizar los directorios de usuario con Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="2d5bd-134">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="2d5bd-135">Para sincronizar los usuarios con Azure Active Directory (AAD), primero tiene que **activar la sincronización de directorios**, tal como se describe en activar la sincronización de [directorios](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-135">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="2d5bd-136">A continuación se encuentra la instalación y la configuración de un equipo local para ejecutar AAD Connect (si todavía no tiene una, merece la pena comprobar por adelantado el tiempo).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-136">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="2d5bd-137">En el artículo siguiente se indica cómo configurar y sincronizar las cuentas de forma local a Azure AD con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-137">The article below tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

[<span data-ttu-id="2d5bd-138">Configuración de AAD Connect, la manera Express.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-138">Setting up AAD Connect, the express way.</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-express)

<span data-ttu-id="2d5bd-139">Pero, antes de hacerlo, asegúrese de que se cumplen [usted cumple los requisitos previos] (https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-prerequisitesy [Elija el tipo de instalación](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-139">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-prerequisites, and [choose your installation type](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="2d5bd-140">El vínculo publicado anteriormente es un breve artículo para las instalaciones rápidas.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-140">The link posted above is to a short article for express installs.</span></span> <span data-ttu-id="2d5bd-141">También puede encontrar artículos en [instalaciones personalizadas](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-custom)o [la autenticación de paso a través](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-pta-quick-start) si es necesario.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-141">You can also find articles on [custom installations](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d5bd-142">Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-142">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="2d5bd-143">Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-143">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="2d5bd-144">Para que la sincronización de directorios funcione correctamente, asegúrese de que esté abierto TCP 443 en el servidor de sincronización de directorios local</span><span class="sxs-lookup"><span data-stu-id="2d5bd-144">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open</span></span> 

<span data-ttu-id="2d5bd-145">Una vez configurada la sincronización, asegúrese de comprobar que EOP se está sincronizando correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-145">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="2d5bd-146">En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-146">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
    
## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="2d5bd-147">Usar el EAC para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="2d5bd-147">Use the EAC to manage mail users</span></span>

<span data-ttu-id="2d5bd-148">En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo electrónico directamente en el EAC.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-148">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
 <span data-ttu-id="2d5bd-149">**Antes de empezar**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-149">**Before you begin**</span></span>
  
<span data-ttu-id="2d5bd-p113">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p113">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
  
### <a name="to-add-a-mail-user-in-the-eac"></a><span data-ttu-id="2d5bd-152">Para agregar un usuario de correo en el EAC</span><span class="sxs-lookup"><span data-stu-id="2d5bd-152">To add a mail user in the EAC</span></span>

1. <span data-ttu-id="2d5bd-153">Para crear un usuario de correo electrónico, vaya a **Destinatarios**\> **Contactos** en el EAC y después haga clic en **Nuevo +**.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>
    
2. <span data-ttu-id="2d5bd-154">En la página **Nuevo usuario de correo**, escriba la información del usuario, incluido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d5bd-154">On the **New mail user** page, enter the user's information, including the following:</span></span> 
    
   ****

|<span data-ttu-id="2d5bd-155">**Propiedad de usuario de correo**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-155">**Mail user property**</span></span>|<span data-ttu-id="2d5bd-156">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-156">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d5bd-157">**Nombre**, **Iniciales** y **Apellidos**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-157">**First name**, **Initials**, and **Last name**</span></span> <br/> |<span data-ttu-id="2d5bd-158">Escriba el nombre completo del usuario en los cuadros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-158">Type the user's full name in the appropriate boxes.</span></span>  <br/> |
|<span data-ttu-id="2d5bd-159">**Nombre para mostrar**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-159">**Display name**</span></span> <br/> |<span data-ttu-id="2d5bd-p114">Escriba un nombre con un máximo de 64 caracteres. De manera predeterminada, este cuadro muestra los nombres en los cuadros **Nombre**, **Iniciales** y **Apellidos** si hay alguno. El nombre para mostrar es un campo obligatorio.  </span><span class="sxs-lookup"><span data-stu-id="2d5bd-p114">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.  </span></span><br/> |
|<span data-ttu-id="2d5bd-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-163">**Alias**</span></span> <br/> |<span data-ttu-id="2d5bd-p115">Escriba un alias exclusivo, con un máximo de 64 caracteres, para el usuario. El alias es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p115">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>  <br/> |
|<span data-ttu-id="2d5bd-166">**Dirección de correo electrónico externa**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-166">**External email address**</span></span> <br/> |<span data-ttu-id="2d5bd-167">Escriba la dirección de correo electrónico externa del usuario.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-167">Type the external email address of the user.</span></span>  <br/> |
|<span data-ttu-id="2d5bd-168">**Id. de usuario**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-168">**User id**</span></span> <br/> |<span data-ttu-id="2d5bd-p116">Escriba el nombre que el usuario de correo usará para iniciar sesión en el servicio. El nombre de inicio de sesión del usuario consta de un nombre de usuario a la izquierda del símbolo arroba (@) y un sufijo a la derecha. Por lo general, el sufijo es el nombre de dominio en el que reside la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p116">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>  <br/> |
|<span data-ttu-id="2d5bd-172">**Contraseña nueva**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-172">**New password**</span></span> <br/> |<span data-ttu-id="2d5bd-p117">Escriba la contraseña que el usuario de correo usará para iniciar sesión en el servicio. Asegúrese de que la contraseña que proporciona cumple los requisitos de longitud, complejidad e historial de la contraseña del dominio en el que va a crear la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p117">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>  <br/> |
|<span data-ttu-id="2d5bd-175">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-175">**Confirm password**</span></span> <br/> |<span data-ttu-id="2d5bd-176">Vuelva a escribir la contraseña para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-176">Retype the password to confirm it.</span></span>  <br/> |
   
3. <span data-ttu-id="2d5bd-p118">Haga clic en **Guardar** para crear el nuevo usuario de correo. El nuevo usuario debe aparecer en la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p118">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span> 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a><span data-ttu-id="2d5bd-179">Para editar o quitar un usuario de correo en el EAC</span><span class="sxs-lookup"><span data-stu-id="2d5bd-179">To edit or remove a mail user in the EAC</span></span>

- <span data-ttu-id="2d5bd-180">En el EAC, vaya a **Destinatarios** \> **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="2d5bd-181">En la lista de usuarios, haga clic en el usuario que desea ver o modificar y, a continuación \*\*\*\* ![, seleccione Editar](../media/ITPro-EAC-EditIcon.gif) icono Editar para actualizar la configuración del usuario según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="2d5bd-182">Puede cambiar el nombre, el alias o la información de contacto del usuario, y puede registrar información detallada sobre el rol del usuario en la organización.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="2d5bd-183">También puede seleccionar un usuario y elegir **Quitar**![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif) para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-183">You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a><span data-ttu-id="2d5bd-184">Usar Windows PowerShell remoto para administrar usuarios de correo</span><span class="sxs-lookup"><span data-stu-id="2d5bd-184">Use remote Windows PowerShell to manage mail users</span></span>

<span data-ttu-id="2d5bd-185">En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
 <span data-ttu-id="2d5bd-186">**Antes de empezar**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-186">**Before you begin**</span></span>
  
- <span data-ttu-id="2d5bd-p120">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p120">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
    
- <span data-ttu-id="2d5bd-189">Tenga en cuenta que, al crear usuarios de correo mediante los cmdlets de PowerShell remoto, podría encontrarse con límites.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-189">Be aware that when creating mail users by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="2d5bd-190">Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-190">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="2d5bd-191">Para aprender cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Conectarse a Exchange Online Protection mediante PowerShell remoto](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-191">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
 <span data-ttu-id="2d5bd-192">**Para agregar un usuario de correo mediante PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-192">**To add a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="2d5bd-193">En este ejemplo, se usa el cmdlet [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) para crear una cuenta de usuario habilitada para correo para Jeffrey Zeng en EOP con los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="2d5bd-193">This example uses the [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span> 
  
- <span data-ttu-id="2d5bd-194">El nombre es Jeffrey y el apellido es Zeng.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-194">The first name is Jeffrey and the last name is Zeng.</span></span>
    
- <span data-ttu-id="2d5bd-195">El nombre es Jeffrey y el nombre para mostrar es Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-195">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>
    
- <span data-ttu-id="2d5bd-196">El alias es jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-196">The alias is jeffreyz.</span></span>
    
- <span data-ttu-id="2d5bd-197">La dirección de correo electrónico externa es jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-197">The external email address is jzeng@tailspintoys.com.</span></span>
    
- <span data-ttu-id="2d5bd-198">El nombre de inicio de sesión de Office 365 es jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-198">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>
    
- <span data-ttu-id="2d5bd-199">La contraseña es Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-199">The password is Pa$$word1.</span></span>
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 <span data-ttu-id="2d5bd-200">**Para comprobar que esto funcionó**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-200">**To verify that this worked**</span></span>
  
<span data-ttu-id="2d5bd-201">Ejecute el cmdlet [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) como se indica a continuación para mostrar información sobre el nuevo usuario de correo Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="2d5bd-201">Run the [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet as follows to display information about new mail user Jeffrey Zeng:</span></span> 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 <span data-ttu-id="2d5bd-202">**Para editar las propiedades de un usuario de correo mediante PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-202">**To edit the properties of a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="2d5bd-203">Use los cmdlets [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) y [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) para ver o cambiar las propiedades de los usuarios de correo.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-203">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlets to view or change properties for mail users.</span></span> 
  
<span data-ttu-id="2d5bd-204">Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-204">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="2d5bd-205">Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-205">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 <span data-ttu-id="2d5bd-206">**Para comprobar que esto funcionó**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-206">**To verify that this worked**</span></span>
  
<span data-ttu-id="2d5bd-p121">En el ejemplo anterior, donde cambiamos las propiedades del usuario de correo Pilar Pinilla, use el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) para comprobar los cambios. (Tenga en cuenta que puede ver varias propiedades de varios contactos de correo).</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p121">In the previous example where we changed the properties for mail user Pilar Pinella, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. (Note that you can view multiple properties for multiple mail contacts.)</span></span> 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

<span data-ttu-id="2d5bd-209">En el ejemplo anterior, donde la propiedad Empresa estaba configurada para Contoso para todos los usuarios de correo, ejecute el siguiente comando para comprobar los cambios:</span><span class="sxs-lookup"><span data-stu-id="2d5bd-209">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="2d5bd-210">Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-210">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span> 
  
 <span data-ttu-id="2d5bd-211">**Para quitar un usuario de correo mediante PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-211">**To remove a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="2d5bd-212">En este ejemplo se usa el cmdlet [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) para eliminar el usuario Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="2d5bd-212">This example uses the [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet to delete user Jeffrey Zeng:</span></span> 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="2d5bd-213">**Para comprobar que esto funcionó**</span><span class="sxs-lookup"><span data-stu-id="2d5bd-213">**To verify that this worked**</span></span>
  
<span data-ttu-id="2d5bd-p122">Ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) como se indica a continuación. Obtendrá un mensaje de error porque el usuario no existe.</span><span class="sxs-lookup"><span data-stu-id="2d5bd-p122">Run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows. You should get an error message since the user no longer exists.</span></span> 
  
```Powershell
Get-Recipient Jeffrey | fl
```



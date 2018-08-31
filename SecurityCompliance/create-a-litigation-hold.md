---
title: Crear una suspensión por litigio en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: 18b3b3a42e5671b1507522c89faaa4ae34198831
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536593"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="5fca5-102">Crear una suspensión por litigio en Office 365</span><span class="sxs-lookup"><span data-stu-id="5fca5-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="5fca5-p101">Puede colocar un buzón de correo en juicio para conservar todos los buzones de correo contenido, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Al colocar un buzón de usuario en suspensión por litigio, contenido en el buzón de archivo del usuario (si está habilitada) también se conserva. Cuando se crea una suspensión, puede especificar una duración de espera (también llamada una *retención basada en tiempo*) para que eliminen y elementos modificados se conservan durante un período especificado y, a continuación, elimina de manera permanente el buzón de correo. O simplemente puede conservar contenido indefinidamente (denominado una *espera infinita*) o hasta que se quite la suspensión por litigio. Si especifica un período de duración de retención, se calcula a partir de la fecha se recibe un mensaje o se crea un elemento de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="5fca5-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="5fca5-108">Aquí es lo que sucede cuando se crea un juicio.</span><span class="sxs-lookup"><span data-stu-id="5fca5-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="5fca5-109">Los elementos que se eliminan permanentemente por el usuario se conservan en la carpeta elementos recuperables en el buzón del usuario para la duración de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="5fca5-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="5fca5-110">Se conservan los elementos que se purgan de la carpeta elementos recuperables por el usuario para la duración de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="5fca5-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="5fca5-111">La cuota de almacenamiento de la carpeta elementos recuperables se incrementó de 30 GB a 110 GB.</span><span class="sxs-lookup"><span data-stu-id="5fca5-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="5fca5-112">Se conservan los elementos de principal del usuario y los buzones de correo de archivo</span><span class="sxs-lookup"><span data-stu-id="5fca5-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="5fca5-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5fca5-113">Before you begin</span></span>

- <span data-ttu-id="5fca5-p102">Para poner un buzón de Exchange Online en juicio, se debe asignar una licencia de Exchange Online Plan 2. Si un buzón se asigna una licencia de Exchange Online Plan 1, tendría asignarla a una licencia independiente de archivado de Exchange Online para poner en espera.</span><span class="sxs-lookup"><span data-stu-id="5fca5-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="5fca5-116">Colocar un buzón en suspensión por litigio en el centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="5fca5-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="5fca5-117">Estos son los pasos para colocar un buzones en suspensión por litigio mediante el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5fca5-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="5fca5-118">Vaya a https://portal.office.com/adminportal/home e iniciar sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5fca5-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="5fca5-119">Haga clic en **usuarios** > **usuarios activos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="5fca5-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="5fca5-120">Seleccione el usuario cuyo buzón de correo que desea colocar en suspensión por litigio.</span><span class="sxs-lookup"><span data-stu-id="5fca5-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="5fca5-121">En la página emergentes, haga clic en **configuración de correo**y, a continuación, haga clic en **Editar** junto a **la suspensión por litigio**.</span><span class="sxs-lookup"><span data-stu-id="5fca5-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="5fca5-122">En la página **juicio** , haga clic en la alternancia para activar la suspensión por litigio y completar la siguiente configuración opcional que se muestra:</span><span class="sxs-lookup"><span data-stu-id="5fca5-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    <span data-ttu-id="5fca5-p103">r. **duración de la retención (días)** -Utilice este cuadro para crear una suspensión basada en tiempo y especifique cuánto tiempo se conservan los elementos del buzón de correo cuando el buzón de correo se coloca en suspensión por litigio. La duración se calcula a partir la fecha de un elemento de buzón de correo se ha recibido o creado. Si deja este cuadro en blanco, se conservan los elementos indefinidamente o hasta que se ha quitado la suspensión. Use días para especificar la duración.</span><span class="sxs-lookup"><span data-stu-id="5fca5-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="5fca5-p104">b. **Nota** - Utilice este cuadro para informar al usuario su buzón se encuentra en suspensión por litigio. La nota aparecerá en la página de información de la cuenta en el buzón del usuario si está utilizando Outlook 2010 o posterior. Para obtener acceso a esta página, los usuarios pueden hacer clic en el **archivo** en Outlook.</span><span class="sxs-lookup"><span data-stu-id="5fca5-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="5fca5-p105">c. **página Web** - Utilice este cuadro para dirigir al usuario a un sitio Web para obtener más información acerca de la suspensión por litigio. Esta dirección URL aparece en la página de información de la cuenta en el buzón del usuario si usan Outlook 2010 o posterior. Para obtener acceso a esta página, los usuarios pueden hacer clic en el **archivo** en Outlook.</span><span class="sxs-lookup"><span data-stu-id="5fca5-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="5fca5-137">Haga clic en **Guardar** para crear el juicio.</span><span class="sxs-lookup"><span data-stu-id="5fca5-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="5fca5-138">Después de crear la suspensión, se muestra la configuración de correo en la página emergentes que juicio está activado para el usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5fca5-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

<span data-ttu-id="5fca5-140">Para obtener más información sobre la creación y administración de retenciones para litigios con y uso de Exchange Online PowerShell para creación masiva de retenciones para litigios con, vea [colocar un buzón en suspensión por litigio](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="5fca5-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>

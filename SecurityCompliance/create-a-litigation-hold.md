---
title: Crear una retención por juicio en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218660"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="04027-102">Crear una retención por juicio en Office 365</span><span class="sxs-lookup"><span data-stu-id="04027-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="04027-p101">Puede poner un buzón en retención por juicio para retener todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Cuando se pone un buzón de usuario en retención por juicio, también se conserva el contenido del buzón de archivo del usuario (si está habilitado). Al crear una suspensión, puede especificar una duración de retención (también denominada *retención basada en tiempo*) para que los elementos eliminados y modificados se conserven durante un período específico y, a continuación, se eliminen de forma permanente del buzón. O bien solo puede retener el contenido indefinidamente (denominado una *retención infinita*) o hasta que se quite la retención por juicio. Si especifica un período de duración de retención, se calcula a partir de la fecha en que se recibe un mensaje o se crea un elemento de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="04027-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="04027-108">Esto es lo que sucede cuando se crea una retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="04027-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="04027-109">Los elementos eliminados de forma permanente por el usuario se conservan en la carpeta elementos recuperables del buzón del usuario durante toda la retención.</span><span class="sxs-lookup"><span data-stu-id="04027-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="04027-110">Los elementos purgados de la carpeta elementos recuperables por el usuario se conservan durante toda la retención.</span><span class="sxs-lookup"><span data-stu-id="04027-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="04027-111">La cuota de almacenamiento de la carpeta elementos recuperables se ha incrementado de 30 GB a 110 GB.</span><span class="sxs-lookup"><span data-stu-id="04027-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="04027-112">Se conservan los elementos del buzón principal del usuario y los buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="04027-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="04027-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="04027-113">Before you begin</span></span>

- <span data-ttu-id="04027-p102">Para poner un buzón de correo de Exchange online en retención por juicio, se le debe asignar una licencia de Exchange Online (plan 2). Si un buzón tiene asignada una licencia de Exchange Online (plan 1), tendrá que asignarle una licencia de archivado de Exchange Online independiente para ponerla en espera.</span><span class="sxs-lookup"><span data-stu-id="04027-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="04027-116">Poner un buzón en retención por juicio en el centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="04027-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="04027-117">Estos son los pasos para poner un Maibox en retención por juicio mediante el centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="04027-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="04027-118">Vaya a https://portal.office.com/adminportal/home e inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="04027-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="04027-119">Haga clic en usuarios**activos** de **usuarios** > en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="04027-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="04027-120">Seleccione el usuario cuyo buzón quiera poner en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="04027-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="04027-121">En la página emergente, haga clic en **configuración de correo**y, a continuación, haga clic en **Editar** junto a retención por **juicio**.</span><span class="sxs-lookup"><span data-stu-id="04027-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="04027-122">En la página **retención por juicio** , haga clic en el botón de alternancia para activar la retención por juicio y complete los siguientes parámetros opcionales que se muestran:</span><span class="sxs-lookup"><span data-stu-id="04027-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1. png](media/O365-LitigationHold1.png)

    <span data-ttu-id="04027-p103">duración de **retención (días)** : Use este cuadro para crear una retención basada en tiempo y especificar cuánto tiempo se conservarán los elementos del buzón cuando el buzón de correo se coloca en retención por juicio. La duración se calcula a partir de la fecha en que se recibe o se crea un elemento de buzón. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se quite la retención. Use días para especificar la duración.</span><span class="sxs-lookup"><span data-stu-id="04027-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="04027-p104">b. **Nota** : Use este cuadro para informar al usuario de que su buzón de correo está en retención por juicio. La nota aparecerá en la página de información de cuenta del buzón de correo del usuario si usa Outlook 2010 o posterior. Para tener acceso a esta página, los usuarios pueden hacer clic en **archivo** en Outlook.</span><span class="sxs-lookup"><span data-stu-id="04027-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="04027-p105">c. **Página Web** : Use este cuadro para dirigir al usuario a un sitio web para obtener más información sobre la retención por juicio. Esta dirección URL aparece en la página de información de cuenta del buzón del usuario si usa Outlook 2010 o posterior. Para tener acceso a esta página, los usuarios pueden hacer clic en **archivo** en Outlook.</span><span class="sxs-lookup"><span data-stu-id="04027-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="04027-137">Haga clic en **Guardar** para crear la retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="04027-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="04027-138">Después de crear la retención, la configuración de correo de la página emergente muestra que la retención por juicio está activada para el usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="04027-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2. png](media/O365-LitigationHold2.png)

<span data-ttu-id="04027-140">Para obtener más información sobre la creación y la administración de suspensiones por juicio y el uso de Exchange Online PowerShell para crear de forma masiva reTenciones por juicio, vea [poner un buzón en retención por juicio](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="04027-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>

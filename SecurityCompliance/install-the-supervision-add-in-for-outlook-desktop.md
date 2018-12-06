---
title: Instalar el complemento de supervisión de Outlook para escritorio
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: Instalar el complemento de supervisión de Office 365 para la versión de escritorio de Outlook
ms.openlocfilehash: b0cb0d78ab5f8887628528dd53b49fb15de44126
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180870"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a><span data-ttu-id="406a2-103">Instalar el complemento de supervisión de Outlook para escritorio</span><span class="sxs-lookup"><span data-stu-id="406a2-103">Install the Supervision add-in for Outlook desktop</span></span>

<span data-ttu-id="406a2-p101">Para revisar las comunicaciones identificadas por una directiva de supervisión, uso de revisores el complemento de supervisión para Outlook y Outlook web app. El complemento se instala automáticamente en Outlook web app para todos los revisores especificados en la directiva. Sin embargo, deben ejecutar los revisores a través de algunos pasos para instalar en la versión de escritorio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="406a2-p101">To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.</span></span>
  
> [!NOTE]
> <span data-ttu-id="406a2-p102">Los usuarios supervisados por las directivas de supervisión deben tener una licencia de acceso E3 Enterprise de Office 365 con el complemento de cumplimiento avanzadas o estar incluidos en una suscripción a Office 365 Enterprise E5. Si no tiene un plan de empresa E5 existente y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="406a2-p102">Users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="406a2-109">Paso 1: Copiar la dirección para el buzón de supervisión</span><span class="sxs-lookup"><span data-stu-id="406a2-109">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="406a2-110">Para instalar el complemento para escritorio de Outlook, necesitará la dirección para el buzón de supervisión que se creó como parte de la configuración de directiva de supervisión.</span><span class="sxs-lookup"><span data-stu-id="406a2-110">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="406a2-111">Si otra persona creó la directiva, debe obtener esta dirección de ellas para instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="406a2-111">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>
 
 <span data-ttu-id="406a2-112">**Para buscar la dirección del buzón de correo de supervisión**</span><span class="sxs-lookup"><span data-stu-id="406a2-112">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="406a2-113">Inicie sesión en la [seguridad &amp; centro de cumplimiento](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="406a2-113">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>
    
2. <span data-ttu-id="406a2-114">Vaya a la **gobernanza de datos** \> **supervisión**.</span><span class="sxs-lookup"><span data-stu-id="406a2-114">Go to **Data governance** \> **Supervision**.</span></span>
    
3. <span data-ttu-id="406a2-115">Haga clic en la directiva de supervisión que está recopilando a las comunicaciones que desee revisar.</span><span class="sxs-lookup"><span data-stu-id="406a2-115">Click the supervision policy that's gathering the communications you want to review.</span></span>
    
4. <span data-ttu-id="406a2-116">En la directiva se detallan emergente, en \*\* buzón supervisión \*\*, copie la dirección.</span><span class="sxs-lookup"><span data-stu-id="406a2-116">In the policy details flyout, under \*\* Supervision mailbox \*\*, copy the address.</span></span><br/>![La sección 'Buzón de correo de supervisión' de emergente de detalles de una directiva de supervisión que muestra la dirección del buzón de correo de supervisión resaltada](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="406a2-118">Paso 2: Configurar el buzón de supervisión para el acceso al escritorio de Outlook</span><span class="sxs-lookup"><span data-stu-id="406a2-118">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="406a2-119">A continuación, los revisores tendrá que ejecutar los comandos de PowerShell en Exchange Online un par para que puedan conectarse a Outlook en el buzón de supervisión.</span><span class="sxs-lookup"><span data-stu-id="406a2-119">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="406a2-p103">Conectarse a Exchange Online PowerShell. [¿Cómo hacerlo?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="406a2-p103">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>
    
2. <span data-ttu-id="406a2-122">Ejecute los comandos siguientes, donde *SupervisoryReview{GUID}@domain.onmicrosoft.com* es la dirección que copió en el paso 1 más arriba, y el *usuario* es el nombre del revisor que van a conectar con el buzón de correo de supervisión en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="406a2-122">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>
    - ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```<br/>
    - ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```
    
3. <span data-ttu-id="406a2-123">Espere al menos una hora antes de pasar al paso 3 por debajo.</span><span class="sxs-lookup"><span data-stu-id="406a2-123">Wait at least an hour before moving on to Step 3 below.</span></span>
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="406a2-124">Paso 3: Crear un perfil de Outlook para conectar con el buzón de supervisión</span><span class="sxs-lookup"><span data-stu-id="406a2-124">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="406a2-125">Para el paso final, revisores será necesario crear un perfil de Outlook para conectar con el buzón de supervisión.</span><span class="sxs-lookup"><span data-stu-id="406a2-125">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>
 
> [!NOTE]
> <span data-ttu-id="406a2-p104">Para crear un nuevo perfil de Outlook, usará la configuración de correo en el Panel de Control de Windows. La ruta de acceso que hay que realizar para tener acceso a estas opciones es posible que dependen de qué sistema operativo de Windows (Windows 7, Windows 8 o Windows 10) utiliza y se instala la versión de Outlook.</span><span class="sxs-lookup"><span data-stu-id="406a2-p104">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="406a2-128">Abra el Panel de Control y, en el cuadro de **búsqueda** en la parte superior de la ventana, escriba **correo**.</span><span class="sxs-lookup"><span data-stu-id="406a2-128">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="406a2-p105">¿(No está seguro de cómo obtener el panel de Control? Vea [donde es el Panel de Control?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="406a2-p105">(Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="406a2-131">Abra la aplicación de **correo** .</span><span class="sxs-lookup"><span data-stu-id="406a2-131">Open the **Mail** app.</span></span>
    
3. <span data-ttu-id="406a2-132">En la **Configuración de correo - Outlook**, haga clic en **Mostrar perfiles**.</span><span class="sxs-lookup"><span data-stu-id="406a2-132">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="406a2-133">![La 'configuración de correo - Outlook' cuadro de diálogo con el botón 'Mostrar perfiles' resaltado](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="406a2-133">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="406a2-p106">En **correo**, haga clic en **Agregar**. A continuación, en **Nuevo perfil**, escriba un nombre para el buzón de correo de supervisión (por ejemplo, **supervisión**).</span><span class="sxs-lookup"><span data-stu-id="406a2-p106">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="406a2-136">![El cuadro de diálogo 'Nuevo perfil' que muestra el nombre 'Supervisión' en el cuadro Nombre del perfil](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="406a2-136">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="406a2-137">En **Outlook conectarse a Office 365**, haga clic en **Conectar a una cuenta diferente**.</span><span class="sxs-lookup"><span data-stu-id="406a2-137">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="406a2-138">![El mensaje 'Outlook conectarse a Office 365' con el vínculo 'Conectar con una cuenta diferente' resaltado](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="406a2-138">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="406a2-139">En la **Configuración automática de cuenta**, elija **el programa de instalación Manual o tipos de servidores adicionales**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="406a2-139">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="406a2-p107">En **Elija el tipo de cuenta**, elija **Office 365**. A continuación, en el cuadro **Dirección de correo electrónico** , escriba la dirección del buzón de supervisión que copió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="406a2-p107">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="406a2-142">![La página 'Elija su tipo de cuenta' del cuadro de diálogo 'Agregar cuenta' en Outlook que muestra el cuadro 'Dirección de correo electrónico' resaltado.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="406a2-142">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="406a2-143">Cuando se le solicite, escriba sus credenciales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="406a2-143">When prompted, enter your Office 365 credentials.</span></span>
    
9. <span data-ttu-id="406a2-144">Si tiene éxito, verá el \*\*supervisión - \<nombre de la directiva\> \*\* carpeta que aparecen en la vista lista de carpetas de Outlook.</span><span class="sxs-lookup"><span data-stu-id="406a2-144">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>
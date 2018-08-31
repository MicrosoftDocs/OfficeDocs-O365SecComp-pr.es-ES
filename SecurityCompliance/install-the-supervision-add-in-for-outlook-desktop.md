---
title: Instalar el complemento de supervisión de Outlook para escritorio
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/19/2017
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
ms.openlocfilehash: 0bddf305087bf0d9552c7671da5306db8352143f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535708"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a><span data-ttu-id="9dba9-103">Instalar el complemento de supervisión de Outlook para escritorio</span><span class="sxs-lookup"><span data-stu-id="9dba9-103">Install the Supervision add-in for Outlook desktop</span></span>

<span data-ttu-id="9dba9-p101">Para revisar las comunicaciones identificadas por una directiva de supervisión, uso de revisores el complemento de supervisión para Outlook y Outlook web app. El complemento se instala automáticamente en Outlook web app para todos los revisores especificados en la directiva. Sin embargo, deben ejecutar los revisores a través de algunos pasos para instalar en la versión de escritorio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="9dba9-p101">To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9dba9-p102">Uso de directivas de supervisión requiere una suscripción a Office 365 E5 para su organización. Si no tiene ese plan y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="9dba9-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="9dba9-109">Paso 1: Copiar la dirección para el buzón de supervisión</span><span class="sxs-lookup"><span data-stu-id="9dba9-109">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="9dba9-110">Para instalar el complemento para escritorio de Outlook, necesitará la dirección para el buzón de supervisión que se creó como parte de la configuración de directiva de supervisión.</span><span class="sxs-lookup"><span data-stu-id="9dba9-110">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9dba9-111">Si otra persona creó la directiva, debe obtener esta dirección de ellas para instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="9dba9-111">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span> 
  
 <span data-ttu-id="9dba9-112">**Para buscar la dirección del buzón de correo de supervisión**</span><span class="sxs-lookup"><span data-stu-id="9dba9-112">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="9dba9-113">Inicie sesión en la [seguridad &amp; centro de cumplimiento](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9dba9-113">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="9dba9-114">Vaya a la **gobernanza de datos** \> **supervisión**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-114">Go to **Data governance** \> **Supervision**.</span></span>
    
3. <span data-ttu-id="9dba9-115">Haga clic en la directiva de supervisión que está recopilando a las comunicaciones que desee revisar.</span><span class="sxs-lookup"><span data-stu-id="9dba9-115">Click the supervision policy that's gathering the communications you want to review.</span></span>
    
4. <span data-ttu-id="9dba9-116">En la directiva se detallan emergente, en ** buzón supervisión **, copie la dirección.</span><span class="sxs-lookup"><span data-stu-id="9dba9-116">In the policy details flyout, under ** Supervision mailbox **, copy the address.</span></span> 
    
    ![La sección 'Buzón de correo de supervisión' de emergente de detalles de una directiva de supervisión que muestra la dirección del buzón de correo de supervisión resaltada](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="9dba9-118">Paso 2: Configurar el buzón de supervisión para el acceso al escritorio de Outlook</span><span class="sxs-lookup"><span data-stu-id="9dba9-118">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="9dba9-119">A continuación, los revisores tendrá que ejecutar los comandos de PowerShell en Exchange Online un par para que puedan conectarse a Outlook en el buzón de supervisión.</span><span class="sxs-lookup"><span data-stu-id="9dba9-119">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="9dba9-p103">Conectarse a Exchange Online PowerShell. [¿Cómo hacerlo?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9dba9-p103">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>
    
2. <span data-ttu-id="9dba9-122">Ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="9dba9-122">Run the following commands.</span></span>
    
  ```
  Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccessSet-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false
  ```

    <span data-ttu-id="9dba9-123">Donde *SupervisoryReview{GUID}@domain.onmicrosoft.com* es la dirección que copió en el paso 1 más arriba, y el *usuario* es el nombre del revisor que van a conectar con el buzón de correo de supervisión en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="9dba9-123">Where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in the next step.</span></span> 
    
3. <span data-ttu-id="9dba9-124">Espere al menos una hora antes de pasar al paso 3 por debajo.</span><span class="sxs-lookup"><span data-stu-id="9dba9-124">Wait at least an hour before moving on to Step 3 below.</span></span>
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="9dba9-125">Paso 3: Crear un perfil de Outlook para conectar con el buzón de supervisión</span><span class="sxs-lookup"><span data-stu-id="9dba9-125">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="9dba9-126">Para el paso final, revisores será necesario crear un perfil de Outlook para conectar con el buzón de supervisión.</span><span class="sxs-lookup"><span data-stu-id="9dba9-126">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9dba9-p104">Para crear un nuevo perfil de Outlook, usará la configuración de correo en el Panel de Control de Windows. La ruta de acceso que hay que realizar para tener acceso a estas opciones es posible que dependen de qué sistema operativo de Windows (Windows 7, Windows 8 o Windows 10) utiliza y se instala la versión de Outlook.</span><span class="sxs-lookup"><span data-stu-id="9dba9-p104">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed.</span></span> 
  
1. <span data-ttu-id="9dba9-129">Abra el Panel de Control y, en el cuadro de **búsqueda** en la parte superior de la ventana, escriba **correo**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-129">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9dba9-p105">¿No está seguro de cómo obtener el panel de Control? Vea [donde es el Panel de Control?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span><span class="sxs-lookup"><span data-stu-id="9dba9-p105">Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span></span>
  
2. <span data-ttu-id="9dba9-132">Abra la aplicación de **correo** .</span><span class="sxs-lookup"><span data-stu-id="9dba9-132">Open the **Mail** app.</span></span> 
    
3. <span data-ttu-id="9dba9-133">En la **Configuración de correo - Outlook**, haga clic en **Mostrar perfiles**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-133">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span>
    
    ![La 'configuración de correo - Outlook' cuadro de diálogo con el botón 'Mostrar perfiles' resaltado](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. <span data-ttu-id="9dba9-p106">En **correo**, haga clic en **Agregar**. A continuación, en **Nuevo perfil**, escriba un nombre para el buzón de correo de supervisión (por ejemplo, **supervisión**).</span><span class="sxs-lookup"><span data-stu-id="9dba9-p106">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span>
    
    ![El cuadro de diálogo 'Nuevo perfil' que muestra el nombre 'Supervisión' en el cuadro Nombre del perfil](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. <span data-ttu-id="9dba9-138">En **Outlook conectarse a Office 365**, haga clic en **Conectar a una cuenta diferente**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-138">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span>
    
    ![El mensaje 'Outlook conectarse a Office 365' con el vínculo 'Conectar con una cuenta diferente' resaltado](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. <span data-ttu-id="9dba9-140">En la **Configuración automática de cuenta**, elija **el programa de instalación Manual o tipos de servidores adicionales**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-140">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9dba9-p107">En **Elija el tipo de cuenta**, elija **Office 365**. A continuación, en el cuadro **Dirección de correo electrónico** , escriba la dirección del buzón de supervisión que copió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9dba9-p107">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span> 
    
    ![La página 'Elija su tipo de cuenta' del cuadro de diálogo 'Agregar cuenta' en Outlook que muestra el cuadro 'Dirección de correo electrónico' resaltado.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. <span data-ttu-id="9dba9-144">Cuando se le solicite, escriba sus credenciales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9dba9-144">When prompted, enter your Office 365 credentials.</span></span>
    
9. <span data-ttu-id="9dba9-145">Si tiene éxito, verá el **supervisión - \<nombre de la directiva\> ** carpeta que aparecen en la vista lista de carpetas de Outlook.</span><span class="sxs-lookup"><span data-stu-id="9dba9-145">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span> 
    


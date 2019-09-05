---
title: Simulador de ataques en Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Como administrador global de Office 365, puede usar simulador de ataque para ejecutar escenarios de ataque realistas en su organización. Esto puede ayudarle a identificar y encontrar a los usuarios vulnerables antes de que un ataque real reconozca a su empresa.
ms.openlocfilehash: d0936e564104ae9c3b0fb00351c2c086386db5b0
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761636"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="0d097-104">Simulador de ataques en Office 365</span><span class="sxs-lookup"><span data-stu-id="0d097-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="0d097-105">**Resumen** Si es un administrador global de Office 365 o un administrador de seguridad y su organización tiene Office 365 el plan de protección contra amenazas avanzada 2, que incluye [capacidades de investigación y respuesta de amenazas](office-365-ti.md), puede usar simulador de ataque para ejecutar escenarios de ataque realistas en su organización.</span><span class="sxs-lookup"><span data-stu-id="0d097-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="0d097-106">Esto puede ayudarle a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a su conclusión.</span><span class="sxs-lookup"><span data-stu-id="0d097-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="0d097-107">Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0d097-107">Read this article to learn more.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="0d097-108">Los ataques</span><span class="sxs-lookup"><span data-stu-id="0d097-108">The Attacks</span></span>

<span data-ttu-id="0d097-109">Actualmente hay disponibles tres tipos de simulaciones de ataque:</span><span class="sxs-lookup"><span data-stu-id="0d097-109">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="0d097-110">Nombre para mostrar: ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="0d097-110">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)

- [<span data-ttu-id="0d097-111">Ataque rociado de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d097-111">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="0d097-112">Ataque de fuerza bruta con contraseña</span><span class="sxs-lookup"><span data-stu-id="0d097-112">Brute-force password attack</span></span>](#brute-force-password-attack)
    
<span data-ttu-id="0d097-113">Para que un ataque se inicie correctamente, asegúrese de que la cuenta que usa para ejecutar ataques simulados esté usando la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="0d097-113">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="0d097-114">Además, debe ser un administrador global de Office 365 o un administrador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0d097-114">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="0d097-115">(Para obtener más información acerca de los roles y los permisos, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)).</span><span class="sxs-lookup"><span data-stu-id="0d097-115">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
<span data-ttu-id="0d097-116">Para tener acceso al simulador de ataques &amp; , en el centro de seguridad y cumplimiento, elija **simulador de ataques**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0d097-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="0d097-117">Antes de comenzar...</span><span class="sxs-lookup"><span data-stu-id="0d097-117">Before you begin...</span></span>

<span data-ttu-id="0d097-118">Asegúrese de que usted y su organización cumplen con los siguientes requisitos para simuladores de ataques:</span><span class="sxs-lookup"><span data-stu-id="0d097-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="0d097-119">El correo electrónico de la organización se hospeda en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d097-119">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="0d097-120">(El simulador de ataque no está disponible para los servidores de correo electrónico locales).</span><span class="sxs-lookup"><span data-stu-id="0d097-120">(Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="0d097-121">Es administrador global de Office 365 o administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="0d097-121">You are an Office 365 global administrator or security administrator</span></span>
    
- <span data-ttu-id="0d097-122">La [autenticación multifactor/acceso condicional](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) está activada, por lo menos la cuenta de administrador global de Office 365 y los administradores de seguridad que van a usar el simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="0d097-122">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="0d097-123">(Idealmente, el acceso condicional/autenticación multifactor está activado para todos los usuarios de la organización).</span><span class="sxs-lookup"><span data-stu-id="0d097-123">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>
 
- <span data-ttu-id="0d097-124">Su organización tiene [el plan 2 de la protección contra amenazas avanzada de Office 365](office-365-atp.md), con el &amp; simulador de ataque visible en el centro de seguridad y cumplimiento (vaya a **simulador de ataque**de administración \> de **amenazas** )</span><span class="sxs-lookup"><span data-stu-id="0d097-124">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![Administración de amenazas: simulador de ataque](media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="0d097-126">Nombre para mostrar: ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="0d097-126">Display name spear-phishing attack</span></span>

<span data-ttu-id="0d097-127">La suplantación de identidad (phishing) es un término genérico para un conjunto amplio de ataques que se clasifican como un ataque de tipo de ingeniería social.</span><span class="sxs-lookup"><span data-stu-id="0d097-127">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="0d097-128">Este ataque se centra en la suplantación de identidad (phishing), un ataque más objetivo destinado a un grupo específico de personas o una organización.</span><span class="sxs-lookup"><span data-stu-id="0d097-128">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="0d097-129">Normalmente, se trata de un ataque personalizado con algún reconocimiento realizado y con un nombre para mostrar que generará confianza en el destinatario, como un mensaje de correo electrónico que parece que proviene de un ejecutivo de la organización.</span><span class="sxs-lookup"><span data-stu-id="0d097-129">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="0d097-130">Este ataque se centra en permitirle manipular a la que parece que el mensaje se ha originado cambiando el nombre para mostrar y la dirección de origen.</span><span class="sxs-lookup"><span data-stu-id="0d097-130">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="0d097-131">Cuando los ataques de "Spear phishing" son correctos, cyberattackers obtener acceso a las credenciales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0d097-131">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="0d097-132">Para simular un ataque de "Spear phishing"</span><span class="sxs-lookup"><span data-stu-id="0d097-132">To simulate a spear-phishing attack</span></span>

![Crear cuerpo de correo electrónico](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="0d097-134">Puede crear el editor HTML enriquecido directamente en el propio campo **del cuerpo del correo electrónico** o trabajar con el código fuente HTML.</span><span class="sxs-lookup"><span data-stu-id="0d097-134">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="0d097-135">En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija **simulador de ataque**de administración \> de **amenazas** .</span><span class="sxs-lookup"><span data-stu-id="0d097-135">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="0d097-136">Especifique un nombre de campaña significativo para el ataque o seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="0d097-136">Specify a meaningful campaign name for the attack or select a template.</span></span> 

    ![Página de inicio de phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="0d097-138">Especifique los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="0d097-138">Specify the target recipients.</span></span> <span data-ttu-id="0d097-139">Puede tratarse de personas o grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0d097-139">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="0d097-140">Cada destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="0d097-140">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> 

    ![Selección de destinatarios](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="0d097-142">Configure los detalles del correo de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0d097-142">Configure the Phishing email details.</span></span> 

    ![Configuración de detalles de correo electrónico](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
    
    <span data-ttu-id="0d097-144">El formato HTML puede ser tan complejo o básico como las necesidades de la campaña.</span><span class="sxs-lookup"><span data-stu-id="0d097-144">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="0d097-145">Como el formato de correo electrónico es HTML, puede insertar imágenes y texto para mejorar la increíble.</span><span class="sxs-lookup"><span data-stu-id="0d097-145">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="0d097-146">Tiene control sobre la apariencia que tendrá el mensaje recibido en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="0d097-146">You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="0d097-147">Especifique el texto para el campo **de (nombre)** .</span><span class="sxs-lookup"><span data-stu-id="0d097-147">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="0d097-148">Este es el campo que se muestra en el **nombre para mostrar** en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="0d097-148">This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="0d097-149">Especifique el texto o el campo **de** .</span><span class="sxs-lookup"><span data-stu-id="0d097-149">Specify text or the **From** field.</span></span> <span data-ttu-id="0d097-150">Se trata del campo que muestra la dirección de correo electrónico del remitente en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="0d097-150">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

    <span data-ttu-id="0d097-151">Puede escribir un espacio de nombres de correo electrónico existente dentro de la organización (al hacerlo, la dirección de correo electrónico se resolverá realmente en el cliente receptor, lo que facilitará un modelo de confianza muy alto) o puede escribir una dirección de correo electrónico externa.</span><span class="sxs-lookup"><span data-stu-id="0d097-151">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="0d097-152">La dirección de correo electrónico que especifique no tiene que existir realmente, pero necesita seguir el formato de una dirección SMTP válida, como `user@domainname.extension`.</span><span class="sxs-lookup"><span data-stu-id="0d097-152">The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as `user@domainname.extension`.</span></span> 
  
7. <span data-ttu-id="0d097-153">Mediante el selector de lista desplegable, seleccione una dirección URL del servidor de inicio de sesión de suplantación de identidad (phishing) que refleje el tipo de contenido que tendrá en el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-153">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="0d097-154">Se proporcionan varias URL con temas que puede elegir, como la entrega de documentos, técnicas, nóminas, etc. De hecho, se trata de la URL a la que se pide a los usuarios de destino que haga clic.</span><span class="sxs-lookup"><span data-stu-id="0d097-154">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="0d097-155">Especificar una dirección URL de la página de aterrizaje personalizada.</span><span class="sxs-lookup"><span data-stu-id="0d097-155">Specify a custom landing page URL.</span></span> <span data-ttu-id="0d097-156">Al usar esto, se redirigirá a los usuarios a una dirección URL que especifique al final de un ataque realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d097-156">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="0d097-157">Si tiene un entrenamiento de conciencia interno, por ejemplo, puede especificarlo aquí.</span><span class="sxs-lookup"><span data-stu-id="0d097-157">If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="0d097-158">Especifique el texto para el campo **Subject** .</span><span class="sxs-lookup"><span data-stu-id="0d097-158">Specify text for the **Subject** field.</span></span> <span data-ttu-id="0d097-159">Este es el campo que muestra el **nombre del sujeto** en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="0d097-159">This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="0d097-160">Redacte el **cuerpo del correo electrónico** que recibirá el destino.</span><span class="sxs-lookup"><span data-stu-id="0d097-160">Compose the **Email body** that the target will receive.</span></span> 

    <span data-ttu-id="0d097-161">`${username}`inserta el nombre de los destinos en el cuerpo del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0d097-161">`${username}` inserts the targets name into the Email body.</span></span> 

    <span data-ttu-id="0d097-162">`${loginserverurl}`inserta la dirección URL en la que desea que los usuarios de destino haga clic</span><span class="sxs-lookup"><span data-stu-id="0d097-162">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="0d097-163">Elija **siguiente y** luego **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-163">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="0d097-164">El mensaje de correo electrónico de "Spear phishing" se entrega a los buzones de los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="0d097-164">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="0d097-165">Ataque rociado de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d097-165">Password-spray attack</span></span>

<span data-ttu-id="0d097-166">Un ataque por pulverización de contraseña contra una organización suele usarse después de que un actor incorrecto haya adquirido correctamente una lista de usuarios válidos del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d097-166">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="0d097-167">El actor incorrecto conoce las contraseñas comunes que usan las personas.</span><span class="sxs-lookup"><span data-stu-id="0d097-167">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="0d097-168">Se trata de un ataque de uso generalizado, ya que es un ataque barato de ejecutar y más difícil de detectar que los enfoques de fuerza bruta.</span><span class="sxs-lookup"><span data-stu-id="0d097-168">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="0d097-169">Este ataque se centra en permitir que especifique una contraseña común en una base de usuarios de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="0d097-169">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="0d097-170">Para simular un ataque rociado de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d097-170">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="0d097-171">En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija **simulador de ataque**de administración \> de **amenazas** .</span><span class="sxs-lookup"><span data-stu-id="0d097-171">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="0d097-172">Especifique un nombre de campaña significativo para el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-172">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="0d097-173">Especifique los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="0d097-173">Specify the target recipients.</span></span> <span data-ttu-id="0d097-174">Puede tratarse de personas o grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0d097-174">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="0d097-175">Un destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="0d097-175">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="0d097-176">Especifique la contraseña que se va a usar para el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-176">Specify a password to use for the attack.</span></span> <span data-ttu-id="0d097-177">Por ejemplo, una contraseña común y relevante que podría probar es `Summer2019`.</span><span class="sxs-lookup"><span data-stu-id="0d097-177">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="0d097-178">Otro podría ser `Fall2019`o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="0d097-178">Another might be `Fall2019`, or `Password1`.</span></span>
    
5. <span data-ttu-id="0d097-179">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-179">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="0d097-180">Ataque de fuerza bruta con contraseña</span><span class="sxs-lookup"><span data-stu-id="0d097-180">Brute-force password attack</span></span>

<span data-ttu-id="0d097-181">Un ataque de fuerza bruta contra una organización se suele usar después de que un actor incorrecto haya adquirido correctamente una lista de usuarios clave del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d097-181">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="0d097-182">Este ataque se centra en probar un conjunto de contraseñas en una sola cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0d097-182">This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="0d097-183">Para simular un ataque de fuerza bruta de contraseña</span><span class="sxs-lookup"><span data-stu-id="0d097-183">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="0d097-184">En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija **simulador de ataque**de administración \> de **amenazas** .</span><span class="sxs-lookup"><span data-stu-id="0d097-184">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="0d097-185">Especifique un nombre de campaña significativo para el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-185">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="0d097-186">Especifique el destinatario de destino.</span><span class="sxs-lookup"><span data-stu-id="0d097-186">Specify the target recipient.</span></span> <span data-ttu-id="0d097-187">Un destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="0d097-187">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="0d097-188">Especifique un conjunto de contraseñas que se usarán para el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-188">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="0d097-189">Para ello, puede usar un archivo de texto (. txt) para la lista de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="0d097-189">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="0d097-190">El archivo de texto no puede superar los 10 MB en el tamaño del archivo.</span><span class="sxs-lookup"><span data-stu-id="0d097-190">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="0d097-191">Use una contraseña por línea y asegúrese de incluir un retorno de la última contraseña en la lista.</span><span class="sxs-lookup"><span data-stu-id="0d097-191">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="0d097-192">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-192">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="0d097-193">Nuevas características en el simulador de ataques</span><span class="sxs-lookup"><span data-stu-id="0d097-193">New features in Attack Simulator</span></span>

<span data-ttu-id="0d097-194">Las nuevas características se han agregado recientemente a simulador de ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-194">New features have recently been added to Attack Simulator.</span></span> <span data-ttu-id="0d097-195">Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0d097-195">These include:</span></span>

- <span data-ttu-id="0d097-196">Capacidades avanzadas de generación de informes.</span><span class="sxs-lookup"><span data-stu-id="0d097-196">Advanced reporting capabilities.</span></span> <span data-ttu-id="0d097-197">La capacidad de ver datos como el tiempo más rápido (o más lento) para abrir un mensaje de correo electrónico de simulación de ataques, el tiempo más rápido o más lento para hacer clic en un vínculo del mensaje y más visualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0d097-197">The ability to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more visualizations.</span></span>

- <span data-ttu-id="0d097-198">Editor de plantillas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0d097-198">Email template editor.</span></span> <span data-ttu-id="0d097-199">La capacidad de crear una plantilla de correo electrónico personalizada y reutilizable es que puede usar para simulaciones de ataque futuras.</span><span class="sxs-lookup"><span data-stu-id="0d097-199">The ability to create a custom, reusable email template's that you can use for future attack simulations.</span></span>

- <span data-ttu-id="0d097-200">Importación de destinatarios CSV.</span><span class="sxs-lookup"><span data-stu-id="0d097-200">CSV Recipient Import.</span></span> <span data-ttu-id="0d097-201">La capacidad de usar un archivo. csv para importar la lista de destinatarios de destino en lugar de usar el selector de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="0d097-201">The ability to use a .csv file to import your target recipient list instead of using the address book picker.</span></span>

<span data-ttu-id="0d097-202">Pronto estarán disponibles más características nuevas en el simulador de ataque.</span><span class="sxs-lookup"><span data-stu-id="0d097-202">More new features are coming soon to Attack Simulator.</span></span> <span data-ttu-id="0d097-203">Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0d097-203">These include:</span></span>

- <span data-ttu-id="0d097-204">Carga de los datos adjuntos simulación de phishing.</span><span class="sxs-lookup"><span data-stu-id="0d097-204">Attachment payload phishing simulation.</span></span> <span data-ttu-id="0d097-205">La capacidad de usar un archivo adjunto como carga útil para la simulación de suplantación de identidad en vez de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0d097-205">The ability to use an attachment as the payload for phishing simulation in place of a URL.</span></span>

<span data-ttu-id="0d097-206">Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver lo que se está desarrollando, lo que está implementando y lo que ya se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="0d097-206">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d097-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d097-207">See also</span></span>

[<span data-ttu-id="0d097-208">Descripción del servicio de Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="0d097-208">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="0d097-209">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="0d097-209">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)




---
title: Simulador de ataques en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
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
ms.openlocfilehash: ba5658dfa9075b5779f8ca09ccad3547dbddcbb5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216280"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="37de2-104">Simulador de ataques en Office 365</span><span class="sxs-lookup"><span data-stu-id="37de2-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="37de2-p102">**Resumen** Si es un administrador global de Office 365 y su organización tiene [office 365 Threat Intelligence](office-365-ti.md), puede usar simulaDor de ataque para ejecutar escenarios de ataque realistas en su organización. Esto puede ayudarle a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a su conclusión. Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="37de2-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37de2-p103">A partir de febrero de 2019 y la implementación en los próximos meses, Office 365 Threat Intelligence se convierte en Office 365 Advanced Threat Protection Plan 2, con capacidades adicionales de protección contra amenazas. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="37de2-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="37de2-110">Los ataques</span><span class="sxs-lookup"><span data-stu-id="37de2-110">The Attacks</span></span>

<span data-ttu-id="37de2-111">Actualmente hay disponibles tres tipos de simulaciones de ataque:</span><span class="sxs-lookup"><span data-stu-id="37de2-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="37de2-112">Nombre para mostrar: ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37de2-112">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="37de2-113">Ataque rociado de contraseñas</span><span class="sxs-lookup"><span data-stu-id="37de2-113">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="37de2-114">Ataque de fuerza bruta con contraseña</span><span class="sxs-lookup"><span data-stu-id="37de2-114">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="37de2-p104">Para que un ataque se inicie correctamente, use la autenticación multifactor en la cuenta que está usando para ejecutar ataques simulados. Además, debe ser un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="37de2-p104">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37de2-117">La compatibilidad con el acceso condicional estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="37de2-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="37de2-118">Para tener acceso al simulador de ataques &amp; , en el centro de seguridad y cumplimiento, elija simulador de **ataques**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="37de2-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="37de2-119">Antes de comenzar...</span><span class="sxs-lookup"><span data-stu-id="37de2-119">Before you begin...</span></span>

<span data-ttu-id="37de2-120">Asegúrese de que usted y su organización cumplen con los siguientes requisitos para simuladores de ataques:</span><span class="sxs-lookup"><span data-stu-id="37de2-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="37de2-p105">El correo electrónico de la organización se hospeda en Exchange Online. (El simulador de ataque no está disponible para los servidores de correo electrónico locales).</span><span class="sxs-lookup"><span data-stu-id="37de2-p105">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="37de2-123">Es un administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="37de2-123">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="37de2-124">Su organización usa la [autenticación multifactor para usuarios de Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="37de2-124">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="37de2-125">su organización tiene [Office 365 Threat Intelligence](office-365-ti.md), con simulador de ataque visible en &amp; el centro de seguridad y cumplimiento (vaya a simulador de **ataque**de **administración** \> de amenazas)</span><span class="sxs-lookup"><span data-stu-id="37de2-125">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="37de2-126">![Administración de amenazas: simulador de ataque](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="37de2-126">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="37de2-127">Nombre para mostrar: ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="37de2-127">Display name spear-phishing attack</span></span>

<span data-ttu-id="37de2-p106">La suPlantación de identidad (phishing) es un término genérico para un conjunto amplio de ataques que se clasifican como un ataque de tipo de ingeniería social. Este ataque se centra en la suplantación de identidad (phishing), un ataque más objetivo destinado a un grupo específico de personas o una organización. Normalmente, se trata de un ataque personalizado con algún reconocimiento realizado y con un nombre para mostrar que generará confianza en el destinatario, como un mensaje de correo electrónico que parece que proviene de un ejecutivo de la organización.</span><span class="sxs-lookup"><span data-stu-id="37de2-p106">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="37de2-p107">Este ataque se centra en permitirle manipular a la que parece que el mensaje se ha originado cambiando el nombre para mostrar y la dirección de origen. Cuando los ataques de "Spear-phishing" son correctos, los delincuentes pueden obtener acceso a las credenciales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="37de2-p107">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="37de2-133">Para simular un ataque de "Spear phishing"</span><span class="sxs-lookup"><span data-stu-id="37de2-133">To simulate a spear-phishing attack</span></span>

![Crear cuerpo de correo electrónico](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="37de2-135">Puede crear el editor HTML enriquecido directamente en el propio campo **del cuerpo del correo electrónico** o trabajar con el código fuente HTML.</span><span class="sxs-lookup"><span data-stu-id="37de2-135">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="37de2-136">En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija simulador de **ataque**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="37de2-136">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="37de2-137">Especifique un nombre de campaña significativo para el ataque o seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="37de2-137">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![Página de inicio de phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="37de2-p108">Especifique los destinatarios de destino. Puede tratarse de personas o grupos de la organización. Cada destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="37de2-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![Selección de destinatarios](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="37de2-143">Configure los detalles del correo de suPlantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="37de2-143">Configure the Phishing email details.</span></span> <br/>![Configuración de detalles de correo electrónico](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="37de2-p109">El formato HTML puede ser tan complejo o básico como las necesidades de la campaña. Como el formato de correo electrónico es HTML, puede insertar imágenes y texto para mejorar la increíble. Tiene control sobre la apariencia que tendrá el mensaje recibido en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="37de2-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="37de2-p110">Especifique el texto para el campo **de (nombre)** . Este es el campo que se muestra en el **nombre para mostrar** en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="37de2-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="37de2-p111">Especifique el texto o el campo **de** . Se trata del campo que muestra la dirección de correo electrónico del remitente en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="37de2-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="37de2-p112">Puede escribir un espacio de nombres de correo electrónico existente dentro de la organización (al hacerlo, la dirección de correo electrónico se resolverá realmente en el cliente receptor, lo que facilitará un modelo de confianza muy alto) o puede escribir una dirección de correo electrónico externa. La dirección de correo electrónico que especifique no tiene que existir realmente, pero necesita seguir el formato de una dirección SMTP válida, como usuario @ nombreDeDominio. extensión.</span><span class="sxs-lookup"><span data-stu-id="37de2-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="37de2-p113">Mediante el selector de lista desplegable, seleccione una dirección URL del servidor de inicio de sesión de suPlantación de identidad (phishing) que refleje el tipo de contenido que tendrá en el ataque. Se proporcionan varias URL con temas que puede elegir, como la entrega de documentos, técnicas, nóminas, etc. De hecho, se trata de la URL a la que se pide a los usuarios de destino que haga clic.</span><span class="sxs-lookup"><span data-stu-id="37de2-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="37de2-p114">Especificar una dirección URL de la página de aterrizaje personalizada. Al usar esto, se redirigirá a los usuarios a una dirección URL que especifique al final de un ataque realizado correctamente. Si tiene un entrenamiento de conciencia interno, por ejemplo, puede especificarlo aquí.</span><span class="sxs-lookup"><span data-stu-id="37de2-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="37de2-p115">Especifique el texto para \*\*\*\* el campo Subject. Este es el campo que muestra el **nombre del sujeto** en el cliente de correo electrónico de recepción.</span><span class="sxs-lookup"><span data-stu-id="37de2-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="37de2-161">Redacte el **cuerpo del correo electrónico** que recibirá el destino.</span><span class="sxs-lookup"><span data-stu-id="37de2-161">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="37de2-162">`${username}`inserta el nombre de los destinos en el cuerpo del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="37de2-162">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="37de2-163">`${loginserverurl}`inserta la dirección URL en la que desea que los usuarios de destino haga clic</span><span class="sxs-lookup"><span data-stu-id="37de2-163">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="37de2-p116">Elija **siguiente y** luego **Finalizar** para iniciar el ataque. El mensaje de correo electrónico de "Spear phishing" se entrega a los buzones de los destinatarios de destino.</span><span class="sxs-lookup"><span data-stu-id="37de2-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="37de2-166">Ataque rociado de contraseñas</span><span class="sxs-lookup"><span data-stu-id="37de2-166">Password-spray attack</span></span>

<span data-ttu-id="37de2-p117">Un ataque por pulverización de contraseña contra una organización suele usarse después de que un actor incorrecto haya adquirido correctamente una lista de usuarios válidos del espacio empresarial. El actor incorrecto conoce las contraseñas comunes que usan las personas. Se trata de un ataque de uso generalizado, ya que es un ataque barato de ejecutar y más difícil de detectar que los enfoques de fuerza bruta.</span><span class="sxs-lookup"><span data-stu-id="37de2-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="37de2-170">Este ataque se centra en permitir que especifique una contraseña común en una base de usuarios de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="37de2-170">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="37de2-171">Para simular un ataque rociado de contraseñas</span><span class="sxs-lookup"><span data-stu-id="37de2-171">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="37de2-172">En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija simulador de **ataque**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="37de2-172">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="37de2-173">Especifique un nombre de campaña significativo para el ataque.</span><span class="sxs-lookup"><span data-stu-id="37de2-173">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="37de2-p118">Especifique los destinatarios de destino. Puede tratarse de personas o grupos de la organización. Un destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="37de2-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="37de2-p119">Especifique la contraseña que se va a usar para el ataque. Por ejemplo, una contraseña común y relevante que podría probar es `Fall2017`. Otro podría ser `Spring2018`o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="37de2-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="37de2-180">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="37de2-180">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="37de2-181">Ataque de fuerza bruta con contraseña</span><span class="sxs-lookup"><span data-stu-id="37de2-181">Brute-force password attack</span></span>

<span data-ttu-id="37de2-p120">Un ataque de fuerza bruta contra una organización se suele usar después de que un actor incorrecto haya adquirido correctamente una lista de usuarios clave del espacio empresarial. Este ataque se centra en probar un conjunto de contraseñas en una sola cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="37de2-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="37de2-184">Para simular un ataque de fuerza bruta de contraseña</span><span class="sxs-lookup"><span data-stu-id="37de2-184">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="37de2-185">En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija simulador de **ataque**de **Administración** \> de amenazas.</span><span class="sxs-lookup"><span data-stu-id="37de2-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="37de2-186">Especifique un nombre de campaña significativo para el ataque.</span><span class="sxs-lookup"><span data-stu-id="37de2-186">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="37de2-p121">Especifique el destinatario de destino. Un destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="37de2-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="37de2-p122">Especifique un conjunto de contraseñas que se usarán para el ataque. Para ello, puede usar un archivo de texto (. txt) para la lista de contraseñas. El archivo de texto no puede superar los 10 MB en el tamaño del archivo. Use una contraseña por línea y asegúrese de incluir un retorno de la última contraseña en la lista.</span><span class="sxs-lookup"><span data-stu-id="37de2-p122">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="37de2-193">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="37de2-193">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="37de2-194">Nuevas características en el simulador de ataques</span><span class="sxs-lookup"><span data-stu-id="37de2-194">New features in Attack Simulator</span></span>

<span data-ttu-id="37de2-p123">Se han agregado nuevas características a simulador de ataque. Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="37de2-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="37de2-p124">**Capacidades avanzadas de generación de informes**. Podrá ver datos como el tiempo más rápido (o más lento) para abrir un mensaje de correo electrónico de simulación de ataque, el tiempo más rápido o más lento para hacer clic en un vínculo del mensaje, y más.</span><span class="sxs-lookup"><span data-stu-id="37de2-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="37de2-p125">**Editor de plantillas de correo electrónico**. Puede crear una plantilla de correo electrónico personalizada y reutilizable que puede usar para simulaciones de ataque futuras.</span><span class="sxs-lookup"><span data-stu-id="37de2-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="37de2-201">Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver lo que se está desarrollando, lo que está implementando y lo que ya se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="37de2-201">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>




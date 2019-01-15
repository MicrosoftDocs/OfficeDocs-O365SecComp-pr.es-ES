---
title: Simulator ataques en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/02/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: Como administrador global de Office 365, puede usar simulador de ataque para ejecutar los escenarios de ataque realista en su organización. Esto puede ayudar a identificar y buscar usuarios vulnerables antes de que un ataque real afecta a su negocio.
ms.openlocfilehash: 3449e29197aa5a7a0b63a805ad8cc429f8f8f81b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015042"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="344f4-104">Simulator ataques en Office 365</span><span class="sxs-lookup"><span data-stu-id="344f4-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="344f4-p102">**Resumen** Si usted es un administrador global de Office 365 y su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), puede usar simulador de ataque para ejecutar los escenarios de ataque realista en su organización. Esto puede ayudar a identificar y buscar usuarios vulnerables antes de que un ataque real afecta a la línea de la parte inferior. Lea este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="344f4-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="344f4-108">Los ataques</span><span class="sxs-lookup"><span data-stu-id="344f4-108">The Attacks</span></span>

<span data-ttu-id="344f4-109">Tres tipos de simulaciones de ataque están actualmente disponibles:</span><span class="sxs-lookup"><span data-stu-id="344f4-109">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="344f4-110">Mostrar los ataques de suplantación de identidad lanza de nombre</span><span class="sxs-lookup"><span data-stu-id="344f4-110">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="344f4-111">Ataque de contraseña spray</span><span class="sxs-lookup"><span data-stu-id="344f4-111">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="344f4-112">Ataque de contraseña por fuerza bruta</span><span class="sxs-lookup"><span data-stu-id="344f4-112">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="344f4-p103">Para que un ataque que se iniciará correctamente, se usa la autenticación multifactor en la cuenta que se usa para ejecutar ataques simulados. Además, debe ser un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="344f4-p103">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="344f4-115">Compatibilidad con el acceso condicional estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="344f4-115">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="344f4-116">Para obtener acceso a simulador de ataque, en la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="344f4-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="344f4-117">Antes de comenzar...</span><span class="sxs-lookup"><span data-stu-id="344f4-117">Before you begin...</span></span>

<span data-ttu-id="344f4-118">Asegúrese de que usted y su organización cumplen los siguientes requisitos de simulador de ataque:</span><span class="sxs-lookup"><span data-stu-id="344f4-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="344f4-p104">Correo electrónico de su organización se hospeda en Exchange Online. (Simulador de ataque no está disponible para los servidores de correo electrónico locales).</span><span class="sxs-lookup"><span data-stu-id="344f4-p104">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="344f4-121">Es un administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="344f4-121">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="344f4-122">Su organización usa [la autenticación multifactor para usuarios de Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="344f4-122">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="344f4-123">Su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), con simulador de ataque visible en la seguridad &amp; centro de cumplimiento (vaya a **administración de amenaza** \> **simulador de ataque**)</span><span class="sxs-lookup"><span data-stu-id="344f4-123">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="344f4-124">![Administración de amenaza - simulador de ataque](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="344f4-124">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="344f4-125">Mostrar los ataques de suplantación de identidad lanza de nombre</span><span class="sxs-lookup"><span data-stu-id="344f4-125">Display name spear-phishing attack</span></span>

<span data-ttu-id="344f4-p105">Suplantación de identidad es un término genérico para una amplia serie de ataques clasificados como un ataque de estilo de ingeniería social. Este ataque se centra en lanza de suplantación de identidad, un ataque dirigido más que está dirigido a un grupo específico de personas o de una organización. Normalmente, un ataque personalizado con algunos reconocimiento lleva a cabo y uso de un nombre para mostrar que se va a generar confianza en el destinatario, como un mensaje de correo electrónico que parece que proviene de un ejecutivo dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="344f4-p105">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="344f4-p106">Este ataque se centra en lo que le permite manipular que aparece el mensaje procede del cambiando la dirección de origen y de nombre para mostrar. Cuando los ataques de suplantación de identidad lanza son correctas, ciberdelincuentes obtienen acceso a las credenciales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="344f4-p106">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="344f4-131">Para simular un ataque de suplantación de identidad lanza</span><span class="sxs-lookup"><span data-stu-id="344f4-131">To simulate a spear-phishing attack</span></span>

![Redactar el cuerpo del correo electrónico](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="344f4-133">Puede crear el editor de HTML enriquecido directamente en el propio campo del **cuerpo del correo electrónico** o trabajar con código fuente HTML.</span><span class="sxs-lookup"><span data-stu-id="344f4-133">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="344f4-134">En la [seguridad &amp; centro de cumplimiento](https://protection.office.com), elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="344f4-134">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="344f4-135">Especifique un nombre de campaña significativa para el ataque o seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="344f4-135">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![Página de inicio de suplantación de identidad](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="344f4-p107">Especifique a los destinatarios de destino. Esto puede ser individuos o grupos de la organización. Cada destinatario dirigido debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="344f4-p107">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![Selección de destinatario](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="344f4-141">Configurar los detalles de correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="344f4-141">Configure the Phishing email details.</span></span> <br/>![Configurar detalles de correo electrónico](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="344f4-p108">El formato HTML puede ser tan complejos o básica como necesita la campaña de. Como el formato de correo electrónico es HTML, puede insertar imágenes y texto para mejorar believability. Tiene control sobre qué aspecto tendrá el mensaje recibido en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="344f4-p108">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="344f4-p109">Especifique texto para el campo **de (nombre)** . Este es el campo que se muestra en el **Nombre para mostrar** en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="344f4-p109">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="344f4-p110">Especifique el texto o el campo **desde** . Este es el campo que se muestra como la dirección de correo electrónico del remitente en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="344f4-p110">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="344f4-p111">Puede escribir un espacio de nombres de correo electrónico existente dentro de la organización (hacer esto convertirá la dirección de correo electrónico realmente resolver en el cliente receptor, facilitar un modelo de confianza muy alta), o puede escribir una dirección de correo electrónico externa. La dirección de correo electrónico que especifique no tiene que realmente existe, pero es necesario que sigue el formato de una dirección SMTP válida, como user@domainname.extension.</span><span class="sxs-lookup"><span data-stu-id="344f4-p111">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="344f4-p112">Mediante el selector de la lista desplegable, seleccione una dirección URL de servidor de inicio de sesión de suplantación de identidad que refleja el tipo de contenido que tendrá dentro de su ataque. Se proporcionan varias direcciones URL con temas para que pueda elegir, como nóminas técnica, de documento entrega, etcetera. Esto es en efecto la dirección URL que los usuarios de destino se le pida que haga clic en.</span><span class="sxs-lookup"><span data-stu-id="344f4-p112">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="344f4-p113">Especifique una dirección URL de página de inicio personalizado. Uso esto va a redirigir a los usuarios a una dirección URL especificada al final de un ataque con éxito. Si dispone de recursos de aprendizaje de conocimiento interna, por ejemplo, se puede especificar aquí.</span><span class="sxs-lookup"><span data-stu-id="344f4-p113">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="344f4-p114">Especifique texto para el campo **asunto** . Este es el campo que se muestra como el **Nombre de sujeto** en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="344f4-p114">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="344f4-159">Redactar el **cuerpo del correo electrónico** que va a recibir el destino.</span><span class="sxs-lookup"><span data-stu-id="344f4-159">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="344f4-160">`${username}`Inserta el nombre de los objetivos en el cuerpo del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="344f4-160">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="344f4-161">`${loginserverurl}`Inserta la dirección URL que se desea que los usuarios de destino haga clic en</span><span class="sxs-lookup"><span data-stu-id="344f4-161">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="344f4-p115">**Siguiente,** a continuación, elija **Finalizar** para iniciar el ataque. El mensaje de correo electrónico de suplantación de identidad lanza se entrega a los buzones de los destinatarios del destino.</span><span class="sxs-lookup"><span data-stu-id="344f4-p115">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="344f4-164">Ataque de contraseña spray</span><span class="sxs-lookup"><span data-stu-id="344f4-164">Password-spray attack</span></span>

<span data-ttu-id="344f4-p116">Un ataque de spray contraseña contra una organización se utiliza normalmente después de un actor bad ha adquirido correctamente una lista de los usuarios válidos desde el inquilino. El actor bad sabe acerca de las contraseñas comunes que usa la gente. Se trata de un ataque ampliamente utilizado, ya que es un ataque barato para ejecución y más difíciles de detectar que fuerza bruta enfoques.</span><span class="sxs-lookup"><span data-stu-id="344f4-p116">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="344f4-168">Este ataque se centra en lo que le permite especificar una contraseña común con una base de gran tamaño de destino de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="344f4-168">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="344f4-169">Para simular un ataque de contraseña spray</span><span class="sxs-lookup"><span data-stu-id="344f4-169">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="344f4-170">En la [seguridad &amp; centro de cumplimiento](https://protection.office.com), elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="344f4-170">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="344f4-171">Especifique un nombre de campaña significativa para el ataque.</span><span class="sxs-lookup"><span data-stu-id="344f4-171">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="344f4-p117">Especifique a los destinatarios de destino. Esto puede ser individuos o grupos de la organización. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="344f4-p117">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="344f4-p118">Especifique una contraseña que se usará para el ataque. Por ejemplo, una contraseña común y relevante podría intentar es `Fall2017`. Es posible que otro `Spring2018`, o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="344f4-p118">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="344f4-178">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="344f4-178">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="344f4-179">Ataque de contraseña por fuerza bruta</span><span class="sxs-lookup"><span data-stu-id="344f4-179">Brute-force password attack</span></span>

<span data-ttu-id="344f4-p119">Un ataque de contraseña por fuerza bruta contra una organización se utiliza normalmente después de un actor bad ha adquirido correctamente una lista de usuarios claves desde el inquilino. Este ataque se centra en intentar un conjunto de contraseñas en una única cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="344f4-p119">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="344f4-182">Para simular un ataque de contraseña por fuerza bruta</span><span class="sxs-lookup"><span data-stu-id="344f4-182">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="344f4-183">En la [seguridad &amp; centro de cumplimiento](https://protection.office.com), elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="344f4-183">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="344f4-184">Especifique un nombre de campaña significativa para el ataque.</span><span class="sxs-lookup"><span data-stu-id="344f4-184">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="344f4-p120">Especificar al destinatario de destino. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="344f4-p120">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="344f4-p121">Especificar un conjunto de contraseñas que se usará para el ataque. Para ello, puede usar un archivo de texto (.txt) para su lista de contraseñas. El archivo de texto no puede superar los 10 MB en tamaño del archivo. Usar una contraseña por línea y asegúrese de que incluir un retorno de carro después de la última contraseña en la lista.</span><span class="sxs-lookup"><span data-stu-id="344f4-p121">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="344f4-191">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="344f4-191">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="344f4-192">Nuevas características de simulador de ataque</span><span class="sxs-lookup"><span data-stu-id="344f4-192">New features in Attack Simulator</span></span>

<span data-ttu-id="344f4-p122">Se agregan nuevas características a simulador de ataque. Entre estos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="344f4-p122">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="344f4-p123">**Avanzadas capacidades de reporting**. Podrá ver los datos como la hora más rápida (o más lenta) para abrir un mensaje de correo electrónico de simulación de ataque, el tiempo más rápido (o más lento) que haga clic en un vínculo en el mensaje y mucho más.</span><span class="sxs-lookup"><span data-stu-id="344f4-p123">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="344f4-p124">**Editor de plantillas de correo electrónico**. Puede crear una plantilla de correo electrónico personalizados y reutilizables que se puede usar para simulaciones de ataque futuro.</span><span class="sxs-lookup"><span data-stu-id="344f4-p124">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="344f4-199">Visite la [Guía básica de 365 de Microsoft](https://www.microsoft.com/microsoft-365/roadmap) para ver las novedades en el desarrollo, ¿qué es implantar y lo que ya se inicia.</span><span class="sxs-lookup"><span data-stu-id="344f4-199">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>




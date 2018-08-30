---
title: Simulator ataques en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: Obtenga información sobre tres distintos tipos de ataques cibernéticos que puede ejecutar mediante simulador de ataque.
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535931"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="91eaa-103">Simulator ataques en Office 365</span><span class="sxs-lookup"><span data-stu-id="91eaa-103">Attack Simulator in Office 365</span></span>

<span data-ttu-id="91eaa-p101">Con simulador de ataque (incluido en [Office 365 amenaza inteligencia](office-365-ti.md)), si es un miembro del equipo de seguridad de su organización, puede ejecutar los escenarios de ataque realista en su organización. Esto puede ayudar a identificar y buscar usuarios vulnerables antes de que un ataque real afecta a la línea de la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p101">With Attack Simulator (included in [Office 365 Threat Intelligence](office-365-ti.md)), if you are a member of your organization's security team, you can run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="91eaa-106">Los ataques</span><span class="sxs-lookup"><span data-stu-id="91eaa-106">The Attacks</span></span>

<span data-ttu-id="91eaa-107">En la versión preview ofrecemos tres tipos de simulaciones de ataque que puede ejecutar:</span><span class="sxs-lookup"><span data-stu-id="91eaa-107">At preview release we offer three kinds of attack simulations that you can run:</span></span>
  
- [<span data-ttu-id="91eaa-108">Mostrar los ataques de suplantación de identidad lanza de nombre</span><span class="sxs-lookup"><span data-stu-id="91eaa-108">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="91eaa-109">Ataque de contraseña spray</span><span class="sxs-lookup"><span data-stu-id="91eaa-109">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="91eaa-110">Ataque de contraseña por fuerza bruta</span><span class="sxs-lookup"><span data-stu-id="91eaa-110">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="91eaa-111">Para que un ataque que se iniciará correctamente, la cuenta que se está ejecutando el ataque e inicie sesión debe usar la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="91eaa-111">For an attack to be successfully launched, the account that is running the attack and logged on must use multi-factor authentication.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91eaa-112">Compatibilidad con el acceso condicional estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="91eaa-112">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="91eaa-113">Para obtener acceso a simulador de ataque, en la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-113">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="91eaa-114">Antes de comenzar...</span><span class="sxs-lookup"><span data-stu-id="91eaa-114">Before you begin...</span></span>

<span data-ttu-id="91eaa-115">Asegúrese de que usted y su organización cumplen los siguientes requisitos de simulador de ataque:</span><span class="sxs-lookup"><span data-stu-id="91eaa-115">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
  
- <span data-ttu-id="91eaa-116">Su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), con simulador de ataque visible en la seguridad &amp; centro de cumplimiento (vaya a **administración de amenaza** \> **simulador de ataque**)</span><span class="sxs-lookup"><span data-stu-id="91eaa-116">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>
    
- <span data-ttu-id="91eaa-p102">Correo electrónico de su organización se hospeda en Exchange Online. (Simulador de ataque no está disponible para los servidores de correo electrónico locales).</span><span class="sxs-lookup"><span data-stu-id="91eaa-p102">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="91eaa-119">Es un administrador global de Office 365</span><span class="sxs-lookup"><span data-stu-id="91eaa-119">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="91eaa-120">Su organización usa [la autenticación multifactor para usuarios de Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span><span class="sxs-lookup"><span data-stu-id="91eaa-120">Your organization is using [Multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span></span>
    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="91eaa-121">Mostrar los ataques de suplantación de identidad lanza de nombre</span><span class="sxs-lookup"><span data-stu-id="91eaa-121">Display name spear-phishing attack</span></span>

<span data-ttu-id="91eaa-p103">Suplantación de identidad es un término genérico para una amplia serie de ataques clasificados como un ataque de estilo de ingeniería social. Este ataque se centra en lanza de suplantación de identidad, un ataque dirigido más que está dirigido a un grupo específico de personas o de una organización. Normalmente, un ataque personalizado con algunos reconocimiento lleva a cabo y uso de un nombre para mostrar que se va a generar confianza en el destinatario, como un mensaje de correo electrónico que parece que proviene de un ejecutivo dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p103">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="91eaa-p104">Este ataque se centra en lo que le permite manipular que aparece el mensaje procede del cambiando la dirección de origen y de nombre para mostrar. Cuando los ataques de suplantación de identidad lanza son correctas, ciberdelincuentes obtienen acceso a las credenciales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p104">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="91eaa-127">Para simular un ataque de suplantación de identidad lanza</span><span class="sxs-lookup"><span data-stu-id="91eaa-127">To simulate a spear-phishing attack</span></span>

![Redactar el cuerpo del correo electrónico](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="91eaa-p105">Puede crear el editor de HTML enriquecido directamente en el propio campo del **cuerpo del correo electrónico** o trabajar con código fuente HTML. Hay dos campos importantes para su inclusión en el código HTML:</span><span class="sxs-lookup"><span data-stu-id="91eaa-p105">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML:</span></span> 
  
1. <span data-ttu-id="91eaa-131">En la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-131">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="91eaa-132">Especifique un nombre de campaña significativa para el ataque o seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="91eaa-132">Specify a meaningful campaign name for the attack or select a template.</span></span>
    
    ![Página de inicio de suplantación de identidad](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="91eaa-p106">Especifique a los destinatarios de destino. Esto puede ser individuos o grupos de la organización. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p106">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
    ![Selección de destinatario](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="91eaa-138">Configurar los detalles de correo electrónico de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="91eaa-138">Configure the Phishing email details.</span></span>
    
    ![Configurar detalles de correo electrónico](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    <span data-ttu-id="91eaa-p107">El formato HTML puede ser tan complejos o básica como necesita la campaña de. Como es HTML, puede insertar imágenes y texto para mejorar believability. Tiene control sobre qué aspecto tendrá el mensaje recibido en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p107">The HTML formatting can be as complex or basic as your campaign needs. As it is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
1. <span data-ttu-id="91eaa-p108">Escriba texto para el campo **de (nombre)** . Este es el campo que se muestra en el **Nombre para mostrar** en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p108">Enter text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
2. <span data-ttu-id="91eaa-p109">Escriba el texto o el campo **desde** . Este es el campo que se muestra como la dirección de correo electrónico del remitente en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p109">Enter text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="91eaa-p110">Puede escribir un espacio de nombres de correo electrónico existente dentro de la organización (hacer esto convertirá la dirección de correo electrónico realmente resolver en el cliente receptor, facilitar un modelo de confianza muy alta), o puede escribir una dirección de correo electrónico externa. La dirección de correo electrónico que especifique no tiene que realmente existe, pero es necesario que sigue el formato de una dirección SMTP válida, como user@domainname.extension.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p110">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
3. <span data-ttu-id="91eaa-p111">Mediante el selector de la lista desplegable, seleccione una dirección URL de servidor de inicio de sesión de suplantación de identidad que refleja el tipo de contenido que tendrá dentro de su ataque. Se proporcionan varias direcciones URL con temas para que pueda elegir, como nóminas técnica, de documento entrega, etcetera. Esto es en efecto la dirección URL que los usuarios de destino se le pida que haga clic en.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p111">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
4. <span data-ttu-id="91eaa-p112">Escriba una dirección URL de página de inicio personalizado. Uso esto va a redirigir a los usuarios a una dirección URL especificada al final de un ataque con éxito. Si dispone de recursos de aprendizaje de conocimiento interna, por ejemplo, se puede especificar aquí.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p112">Enter a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
5. <span data-ttu-id="91eaa-p113">Escriba texto para el campo **asunto** . Este es el campo que se muestra como el **Nombre de sujeto** en el cliente de correo electrónico receptor.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p113">Enter text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
5. <span data-ttu-id="91eaa-156">Redactar el **cuerpo del correo electrónico** que va a recibir el destino.</span><span class="sxs-lookup"><span data-stu-id="91eaa-156">Compose the **Email body** that the target will receive.</span></span> 
  
 <span data-ttu-id="91eaa-157">**${username}** inserta el nombre de los objetivos en el cuerpo del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="91eaa-157">**${username}** inserts the targets name into the Email body</span></span> 
  
 <span data-ttu-id="91eaa-158">**${loginserverurl}** inserta la dirección URL que se desea que los usuarios de destino haga clic en</span><span class="sxs-lookup"><span data-stu-id="91eaa-158">**${loginserverurl}** inserts the URL we want target users to click</span></span> 
    
6. <span data-ttu-id="91eaa-p114">**Siguiente,** a continuación, elija **Finalizar** para iniciar el ataque. El mensaje de correo electrónico de suplantación de identidad lanza se entrega a los buzones de los destinatarios del destino.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p114">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="91eaa-161">Ataque de contraseña spray</span><span class="sxs-lookup"><span data-stu-id="91eaa-161">Password-spray attack</span></span>

<span data-ttu-id="91eaa-p115">Un ataque de spray contraseña contra una organización se utiliza normalmente después de un actor bad tiene enumeradas correctamente una lista de los usuarios válidos desde el inquilino, utilizando sus conocimientos de contraseñas comunes que se utilizan. Se utilizan ampliamente como es un ataque barato para ejecutar y, a continuación, más difíciles de detectar que fuerza bruta enfoques.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p115">A password spray attack against an organization is typically used after a bad actor has successfully enumerated a list of valid users from the tenant, utilizing their knowledge of common passwords used. It is utilized widely as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="91eaa-164">Este ataque se centra en lo que le permite especificar una contraseña común con una base de gran tamaño de destino de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="91eaa-164">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="91eaa-165">Para simular un ataque de contraseña spray</span><span class="sxs-lookup"><span data-stu-id="91eaa-165">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="91eaa-166">En la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-166">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="91eaa-167">Especifique un nombre de campaña significativa para el ataque.</span><span class="sxs-lookup"><span data-stu-id="91eaa-167">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="91eaa-p116">Especifique a los destinatarios de destino. Esto puede ser individuos o grupos de la organización. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p116">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="91eaa-p117">Especifique una contraseña que se usará para el ataque. Por ejemplo, una contraseña común y relevante podría intentar es `Fall2017`. Es posible que otro `Spring2018`, o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p117">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="91eaa-174">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="91eaa-174">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="91eaa-175">Ataque de contraseña por fuerza bruta</span><span class="sxs-lookup"><span data-stu-id="91eaa-175">Brute-force password attack</span></span>

<span data-ttu-id="91eaa-p118">Un ataque de contraseña por fuerza bruta contra una organización se utiliza normalmente después de un actor bad tiene enumeradas correctamente una lista de usuarios claves desde el inquilino. Este ataque se centra en lo que le permite especificar un conjunto de contraseñas de un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p118">A brute-force password attack against an organization is typically used after a bad actor has successfully enumerated a list of key users from the tenant. This attack focuses on letting you specify a set of passwords against a single user.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="91eaa-178">Para simular un ataque de contraseña por fuerza bruta</span><span class="sxs-lookup"><span data-stu-id="91eaa-178">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="91eaa-179">En la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-179">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="91eaa-180">Especifique un nombre de campaña significativa para el ataque.</span><span class="sxs-lookup"><span data-stu-id="91eaa-180">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="91eaa-p119">Especificar al destinatario de destino. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p119">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="91eaa-p120">Especificar un conjunto de contraseñas que se usará para el ataque. Por ejemplo, una contraseña común y relevante podría intentar es `Fall2017`. Es posible que otro `Spring2018`, o `Password1`.</span><span class="sxs-lookup"><span data-stu-id="91eaa-p120">Specify a set of passwords to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="91eaa-186">Elija **Finalizar** para iniciar el ataque.</span><span class="sxs-lookup"><span data-stu-id="91eaa-186">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="91eaa-187">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="91eaa-187">Related topics</span></span>

[<span data-ttu-id="91eaa-188">Inteligencia sobre amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="91eaa-188">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  


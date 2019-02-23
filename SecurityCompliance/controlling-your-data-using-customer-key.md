---
title: Controlar los datos en Office 365 con la clave de cliente
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar la clave de cliente de Office 365 para Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa. Con la clave de cliente, puede controlar las claves de cifrado de la organización y, después, configurar Office 365 para usarlas y cifrar los datos en reposo en los centros de datos de Microsoft.
ms.openlocfilehash: a14a213951bc87e4106e150c88c6b1461a5e685e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218760"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="8be0b-104">Controlar los datos en Office 365 con la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8be0b-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="8be0b-p102">Con la clave de cliente, puede controlar las claves de cifrado de la organización y, después, configurar Office 365 para usarlas y cifrar los datos en reposo en los centros de datos de Microsoft. Los datos en reposo incluyen datos de Exchange Online y Skype empresarial que se almacenan en buzones de correo y archivos que se almacenan en SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="8be0b-p103">Debe configurar Azure antes de poder usar la clave de cliente de Office 365. En este tema se describen los pasos que debe seguir para crear y configurar los recursos necesarios de Azure y, a continuación, se proporcionan los pasos para configurar la clave de cliente en Office 365. Una vez completada la configuración de Azure, determine qué directivas y, por lo tanto, qué claves asignar a los buzones de correo y los archivos de su organización. Los buzones de correo y los archivos para los que no se asigna una directiva usarán directivas de cifrado controladas y administradas por Microsoft. Para obtener más información acerca de la clave de cliente o para obtener una introducción general, consulte la [clave de cliente de preguntas más frecuentes sobre Office 365](service-encryption-with-customer-key-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8be0b-p104">Se recomienda encarecidamente seguir los procedimientos recomendados de este tema. Se les llama como **Tip** e **Important**. La clave de cliente le da control sobre las claves de cifrado raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que los errores realizados con estas claves pueden tener un gran impacto y pueden dar lugar a interrupciones en el servicio o la pérdida irrevocable de los datos.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="8be0b-116">Antes de comenzar a configurar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8be0b-116">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="8be0b-117"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-117"></span></span>

<span data-ttu-id="8be0b-p105">Antes de empezar, asegúrese de que dispone de la licencia adecuada para su organización. La clave de cliente en Office 365 se ofrece en Office 365 E5 o en la SKU de cumplimiento avanzada.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="8be0b-p106">A continuación, para comprender los conceptos y los procedimientos de este tema, debe revisar la documentación de [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Además, familiarícese con los términos que se usan en Azure, por ejemplo, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="8be0b-122">Para proporcionar comentarios sobre la clave de cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8be0b-122">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="8be0b-123">Información general sobre la configuración de la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="8be0b-123">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="8be0b-124"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-124"></span></span>

<span data-ttu-id="8be0b-p107">Para configurar la clave de cliente, deberá completar estas tareas. En el resto de este tema se proporcionan instrucciones detalladas para cada tarea o vínculos a más información para cada paso del proceso.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="8be0b-127">**En Azure y Microsoft FastTrack:**</span><span class="sxs-lookup"><span data-stu-id="8be0b-127">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="8be0b-p108">Completará la mayoría de estas tareas conectándose de forma remota a Azure PowerShell. Para obtener los mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="8be0b-130">Crear dos nuevas suscripciones de Azure</span><span class="sxs-lookup"><span data-stu-id="8be0b-130">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="8be0b-131">Registrar suscripciones de Azure para usar un período de retención obligatorio</span><span class="sxs-lookup"><span data-stu-id="8be0b-131">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="8be0b-132">El registro puede tardar de uno a cinco días hábiles.</span><span class="sxs-lookup"><span data-stu-id="8be0b-132">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="8be0b-133">Enviar una solicitud para activar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="8be0b-133">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="8be0b-p109">Una vez que haya creado las dos nuevas suscripciones de Azure, deberá enviar la solicitud de oferta de la clave de cliente correspondiente completando un formulario web hospedado en el portal de Microsoft FastTrack. **El equipo de FastTrack no proporciona asistencia con la clave de cliente. Office simplemente usa el portal de FastTrack para permitirle enviar el formulario y ayudar a hacer un seguimiento de las ofertas relevantes para la clave de cliente**.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. **The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="8be0b-p110">Una vez que haya enviado una oferta de clave de cliente, Microsoft revisa su solicitud y le notifica Cuándo puede continuar con el resto de las tareas de configuración. Este proceso puede tardar hasta cinco días hábiles.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="8be0b-138">Crear un almacén de claves Premium de Azure en cada suscripción</span><span class="sxs-lookup"><span data-stu-id="8be0b-138">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="8be0b-139">Asignar permisos a cada almacén clave</span><span class="sxs-lookup"><span data-stu-id="8be0b-139">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="8be0b-140">Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave</span><span class="sxs-lookup"><span data-stu-id="8be0b-140">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="8be0b-141">Agregar una clave a cada depósito clave creando o importando una clave</span><span class="sxs-lookup"><span data-stu-id="8be0b-141">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="8be0b-142">Comprobar el nivel de recuperación de las claves</span><span class="sxs-lookup"><span data-stu-id="8be0b-142">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="8be0b-143">Copia de seguridad de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-143">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="8be0b-144">Validar las opciones de configuración de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-144">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="8be0b-145">Obtener el URI para cada clave de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-145">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="8be0b-146">**En Office 365:**</span><span class="sxs-lookup"><span data-stu-id="8be0b-146">**In Office 365:**</span></span>
  
<span data-ttu-id="8be0b-147">Exchange Online y Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="8be0b-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="8be0b-148">Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="8be0b-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="8be0b-149">Asignar una DEP a un buzón</span><span class="sxs-lookup"><span data-stu-id="8be0b-149">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="8be0b-150">Validar el cifrado de buzones</span><span class="sxs-lookup"><span data-stu-id="8be0b-150">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="8be0b-151">SharePoint Online y OneDrive para la empresa:</span><span class="sxs-lookup"><span data-stu-id="8be0b-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="8be0b-152">Crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="8be0b-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="8be0b-153">Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="8be0b-153">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="8be0b-154">Completar las tareas en Azure Key Vault y Microsoft FastTrack para la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8be0b-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="8be0b-155"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-155"></span></span>

<span data-ttu-id="8be0b-p111">Complete estas tareas en Azure Key Vault para configurar la clave de cliente de Office 365. Deberá completar estos pasos independientemente de si desea configurar la clave de cliente para Exchange Online y Skype empresarial o SharePoint Online y OneDrive para la empresa, o para todos los servicios admitidos en Office 365.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="8be0b-158">Crear dos nuevas suscripciones de Azure</span><span class="sxs-lookup"><span data-stu-id="8be0b-158">Create two new Azure subscriptions</span></span>
<span data-ttu-id="8be0b-159"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-159"></span></span>

<span data-ttu-id="8be0b-p112">Se requieren dos suscripciones de Azure para la clave de cliente. Como práctica recomendada, Microsoft recomienda crear nuevas suscripciones de Azure para usarlas con la clave de cliente. Las claves de Azure Key Vault solo se pueden autorizar para aplicaciones en el mismo inquilino de Azure Active Directory (AAD), debe crear las nuevas suscripciones con el mismo inquilino de Azure AD que se usa con la organización de Office 365 donde se asignará la DEPs. Por ejemplo, con su cuenta profesional o educativa con privilegios de administrador global en su organización de Office 365. Para obtener los pasos detallados, consulte [registrarse para Azure como organización](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8be0b-p113">La clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como procedimiento recomendado, Microsoft recomienda que los miembros de la organización se configuren como una clave en cada suscripción. Además, estas suscripciones de Azure solo deben usarse para administrar claves de cifrado para Office 365. Esto protege a su organización en caso de que uno de sus operadores elimine accidentalmente, de forma intencionada, o de una mala administración de las claves de las que es responsable.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="8be0b-p114">Le recomendamos que configure nuevas suscripciones de Azure que solo se usan para administrar recursos de Azure Key Vault para usarlas con la clave de cliente. No hay ningún límite práctico en el número de suscripciones de Azure que puede crear para su organización. Siga estos procedimientos recomendados para minimizar el impacto de los errores humanos mientras ayuda a administrar los recursos usados por la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="8be0b-173">Enviar una solicitud para activar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="8be0b-173">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="8be0b-174"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-174"></span></span>

<span data-ttu-id="8be0b-p115">Una vez que haya completado los pasos de Azure, tendrá que enviar una solicitud de oferta en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Una vez que haya enviado una solicitud a través del portal web FastTrack, Microsoft comprueba los datos de configuración de Azure Key Vault y la información de contacto que ha proporcionado. Las selecciones que realice en el formulario de oferta en relación con los agentes autorizados de su organización son críticas y necesarias para completar el registro de la clave de cliente. Los agentes de la organización que seleccione en el formulario se usarán para garantizar la autenticidad de cualquier solicitud de revocar y destruir todas las claves utilizadas con una directiva de clave de cifrado de datos de cliente. Deberá realizar este paso una vez para activar la cobertura del cliente para la cobertura de Exchange Online y Skype empresarial, y una segunda vez para activar la clave de cliente de SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="8be0b-180">Para enviar una oferta para activar la clave de cliente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8be0b-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="8be0b-181">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8be0b-181">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="8be0b-182">Una vez que haya iniciado sesión, vaya al **Panel**.</span><span class="sxs-lookup"><span data-stu-id="8be0b-182">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="8be0b-183">Elija **ofertas**y revise la lista de ofertas actuales.</span><span class="sxs-lookup"><span data-stu-id="8be0b-183">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="8be0b-184">Elija más **información** para la oferta que se le aplique:</span><span class="sxs-lookup"><span data-stu-id="8be0b-184">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="8be0b-185">**Exchange Online y Skype empresarial:** Elija más **información** en la **clave de cliente de la oferta de Exchange** .</span><span class="sxs-lookup"><span data-stu-id="8be0b-185">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="8be0b-186">**SharePoint Online y OneDrive para la empresa:** Elija más **información** sobre la oferta de **clave de cliente para SharePoint y OneDrive para la empresa** .</span><span class="sxs-lookup"><span data-stu-id="8be0b-186">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="8be0b-187">En la página Detalles de la **oferta** , elija **crear solicitud**.</span><span class="sxs-lookup"><span data-stu-id="8be0b-187">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="8be0b-p116">ReLlene todos los detalles aplicables y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones de los funcionarios de su organización a los que desea conceder autorización para aprobar la destrucción permanente e irreversible de claves de cifrado y datos. Una vez que haya completado el formulario, elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="8be0b-191">Este proceso puede tardar hasta cinco días hábiles una vez que se haya notificado a Microsoft de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8be0b-191">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="8be0b-192">Continúe con la sección período de retención obligatorio a continuación.</span><span class="sxs-lookup"><span data-stu-id="8be0b-192">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="8be0b-193">Registrar suscripciones de Azure para usar un período de retención obligatorio</span><span class="sxs-lookup"><span data-stu-id="8be0b-193">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="8be0b-194"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-194"></span></span>

<span data-ttu-id="8be0b-p117">La pérdida temporal o permanente de las claves de cifrado raíz puede ser muy disruptiva o incluso catastróficas para el funcionamiento del servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección segura. Todos los recursos de Azure que se usan con la clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Las suscripciones de Azure se pueden etiquetar o registrar de manera que se evite la cancelación inmediata y irrevocable. Esto se conoce como registro de un período de retención obligatorio. Los pasos necesarios para registrar las suscripciones de Azure durante un período de retención obligatorio requieren la colaboración con el equipo de Office 365. Este proceso puede tardar de uno a cinco días laborables. Anteriormente, a veces se hacía referencia a esto como "no cancelar".</span><span class="sxs-lookup"><span data-stu-id="8be0b-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="8be0b-203">Antes de ponerse en contacto con el equipo de Office 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente:</span><span class="sxs-lookup"><span data-stu-id="8be0b-203">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="8be0b-p118">Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="8be0b-206">Ejecute el cmdlet Register-AzureRmProviderFeature para registrar sus suscripciones para usar un período de retención obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8be0b-206">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="8be0b-p119">Póngase en contacto con Microsoft para finalizar el proceso. Para el equipo de SharePoint y OneDrive para la empresa, póngase en contacto con [Spock@microsoft.com](mailto:spock@microsoft.com). Para Exchange Online y Skype empresarial, póngase en contacto con [exock@microsoft.com](mailto:exock@microsoft.com). El contrato de nivel de servicio (SLA) para completar este proceso es cinco días hábiles después de que Microsoft haya notificado (y comprobado) que ha registrado sus suscripciones para usar un período de retención obligatorio. Incluya lo siguiente en su correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="8be0b-212">**Asunto**: clave del cliente \<para *el nombre de dominio completo del espacio empresarial*\></span><span class="sxs-lookup"><span data-stu-id="8be0b-212">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="8be0b-213">**Cuerpo**: identificadores de suscripción para los que desea finalizar el período de retención obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8be0b-213">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="8be0b-214">Una vez que reciba la notificación de Microsoft de que se ha completado el registro, compruebe el estado del registro ejecutando el cmdlet Get-AzureRmProviderFeature de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-214">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="8be0b-215">Después de comprobar que la propiedad de **Estado de registro** del cmdlet Get-AzureRmProviderFeature devuelve un valor de **registrado**, ejecute el siguiente comando para completar el proceso:</span><span class="sxs-lookup"><span data-stu-id="8be0b-215">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="8be0b-216">Crear un almacén de claves Premium de Azure en cada suscripción</span><span class="sxs-lookup"><span data-stu-id="8be0b-216">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="8be0b-217"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-217"></span></span>

<span data-ttu-id="8be0b-218">Los pasos para crear un almacén de claves se documentan en [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que le guiará a través de la instalación y el inicio de Azure PowerShell, la conexión a su suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese Grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="8be0b-218">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="8be0b-p120">Al crear un almacén de claves, debe elegir una SKU: estándar o Premium. La SKU estándar permite que las claves de Azure Key Vault estén protegidas con software (no hay protección de clave de módulo de seguridad de hardware (HSM) y la SKU Premium permite usar los HSM para proteger las claves de la bóveda clave. La clave de cliente acepta almacenes clave que usan una SKU, pero Microsoft recomienda encarecidamente usar solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia de costo es el costo cada mes para cada clave protegida por HSM. Consulte [tarifas clave](https://azure.microsoft.com/pricing/details/key-vault/) de la bóveda para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8be0b-224">Use los almacenes clave de SKU Premium y las claves protegidas por HSM para los datos de producción y use únicamente las claves y los almacenes de claves de SKU estándar para fines de prueba y validación.</span><span class="sxs-lookup"><span data-stu-id="8be0b-224">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="8be0b-p121">Para cada servicio de Office 365 con el que va a usar la clave de cliente, cree un almacén de claves en cada una de las dos suscripciones de Azure que ha creado. Por ejemplo, solo para Exchange Online y Skype empresarial, o SharePoint Online y OneDrive para la empresa, solo se creará un par de depósitos. Para habilitar la clave de cliente para Exchange Online y SharePoint Online, deberá crear dos pares de depósitos clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="8be0b-p122">Use una Convención de nomenclatura para los depósitos clave que refleje el uso previsto de la DEP con la que va a asociar los almacenes. Consulte la sección procedimientos recomendados a continuación para conocer las recomendaciones de Convención de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="8be0b-p123">Cree un conjunto independiente y emparejado de depósitos para cada directiva de cifrado de datos. Para Exchange Online, el ámbito de una directiva de cifrado de datos se elige cuando se asigna la Directiva al buzón. Un buzón puede tener solo una directiva asignada y puede crear hasta 50 directivas. Para SharePoint Online el ámbito de una Directiva son todos los datos de una organización en una ubicación geográfica o geográfica.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="8be0b-p124">La creación de almacenes clave también requiere la creación de grupos de recursos de Azure, ya que las bóvedas clave necesitan capacidad de almacenamiento (aunque muy pequeña) y el registro de la bóveda clave, si está habilitado, también genera datos almacenados. Como procedimiento recomendado, Microsoft recomienda el uso de administradores independientes para administrar cada grupo de recursos, con la administración alineada con el conjunto de administradores que administrarán todos los recursos de clave de cliente relacionados.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8be0b-p125">Para maximizar la disponibilidad, los depósitos clave deben estar en regiones próximos a su servicio de Office 365. Por ejemplo, si su organización de Exchange Online está en Norteamérica, ubique sus depósitos clave en Norteamérica. Si su organización de Exchange Online está en Europa, ubique los depósitos clave en Europa.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="8be0b-p126">Use un prefijo común para los depósitos clave e incluya una abreviatura del uso y el alcance de las claves y el almacén de claves (por ejemplo, para el servicio de SharePoint de Contoso donde los almacenes se ubicarán en Norteamérica, un posible par de nombres es contoso-O365SP-NA-VaultA1 y Contoso-O365SP-NA-VaultA2. Los nombres de almacén son cadenas únicas de forma global dentro de Azure, por lo que es posible que deba probar variantes de sus nombres deseados en caso de que otros clientes de Azure ya hayan reclamado los nombres deseados. A partir de julio 2017 los nombres de almacén no se pueden cambiar, por lo que un procedimiento recomendado es tener un plan escrito para la configuración y usar una segunda persona para comprobar que el plan se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="8be0b-p127">Si es posible, cree sus depósitos en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad en todos los dominios de error de servicio. Por lo tanto, los pares regionales pueden considerarse como una región de copia de seguridad de cada uno. Esto significa que un recurso de Azure que se coloca en una región está obteniendo automáticamente la tolerancia a errores a través de la región emparejada. Por este motivo, la elección de regiones para dos almacenes usados en una DEP en la que las regiones están emparejadas significa que solo se usa un total de dos regiones de disponibilidad. La mayoría de las zonas geográficas solo tienen dos regiones, por lo que todavía no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para los dos almacenes usados con DEP. Esto beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, vea [continuidad empresarial y recuperación ante desastres (BCDR): regiones emparejadas de Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista actual de pares regionales.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="8be0b-251">Asignar permisos a cada almacén clave</span><span class="sxs-lookup"><span data-stu-id="8be0b-251">Assign permissions to each key vault</span></span>
<span data-ttu-id="8be0b-252"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-252"></span></span>

<span data-ttu-id="8be0b-p128">Para cada almacén de claves, tendrá que definir tres conjuntos de permisos distintos para la clave de cliente, según la implementación. Por ejemplo, tendrá que definir un conjunto de permisos para cada uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="8be0b-p129">**Administradores de la bóveda clave** que realizarán la administración cotidiana de su almacén clave para su organización. Estas tareas incluyen copia de seguridad, crear, obtener, importar, enumerar y restaurar.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8be0b-p130">El conjunto de permisos asignado a los administradores de la bóveda de claves no incluye el permiso para eliminar claves. Esto es intencionado y es un ejercicio importante. La eliminación de claves de cifrado no suele realizarse, ya que al hacerlo se destruyen los datos de forma permanente. Como procedimiento recomendado, no conceda este permiso a los administradores de la bóveda clave de forma predeterminada. En su lugar, Reserve esto para los colaboradores clave de la bóveda y asígnelo solo a un administrador a corto plazo una vez que comprenda claramente las consecuencias.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="8be0b-p131">Para asignar estos permisos a un usuario de su organización de Office 365, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="8be0b-264">Ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy para asignar los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8be0b-264">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="8be0b-265">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-265">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="8be0b-p132">Contribute de **key Vault** que puede cambiar los permisos en el propio almacén de claves de Azure. Tendrá que cambiar estos permisos a medida que los empleados abandonen o se unan a su equipo, o en la situación extremadamente inusual de que los administradores de la bóveda clave necesiten de forma legítima permiso para eliminar o restaurar una clave. Este conjunto de colaboradores clave del almacén debe tener concedido el \*\*\*\* rol colaborador en su almacén de claves. Puede asignar este rol mediante el administrador de recursos de Azure. Para obtener los pasos detallados, consulte [usar el control de acceso basado en roles para administrar el acceso a los recursos de suscripción de Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). El administrador que crea una suscripción tiene este acceso de forma implícita, así como la capacidad de asignar otros administradores al rol colaborador.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="8be0b-p133">Si tiene previsto usar la clave de cliente con Exchange Online y Skype empresarial, debe conceder permiso a Office 365 para usar el almacén de claves en nombre de Exchange Online y Skype empresarial. Del mismo modo, si tiene previsto usar la clave de cliente con SharePoint Online y OneDrive para la empresa, necesitará agregar el permiso para que la oficina 365 use el almacén de claves en nombre de SharePoint Online y OneDrive para la empresa. Para conceder permiso a Office 365, ejecute el cmdlet **set-AzureRmKeyVaultAccessPolicy** con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="8be0b-275">Donde:</span><span class="sxs-lookup"><span data-stu-id="8be0b-275">Where:</span></span>
    
  - <span data-ttu-id="8be0b-276">*vaultname* es el nombre del almacén de claves que ha creado.</span><span class="sxs-lookup"><span data-stu-id="8be0b-276">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="8be0b-277">Para Exchange Online y Skype empresarial, reemplace *Office 365 appID* por`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="8be0b-277">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="8be0b-278">Para SharePoint Online y OneDrive para la empresa, reemplace *Office 365 appID* por`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="8be0b-278">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="8be0b-279">Ejemplo: establecer permisos para Exchange Online y Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="8be0b-279">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="8be0b-280">Ejemplo: establecer permisos para SharePoint Online y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="8be0b-280">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="8be0b-281">Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave</span><span class="sxs-lookup"><span data-stu-id="8be0b-281">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="8be0b-282"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-282"></span></span>

<span data-ttu-id="8be0b-p134">Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio prolongada debido a claves eliminadas accidental o malintencionadamente. Debe habilitar esta configuración, que se conoce como eliminación temporal, para poder usar las claves con la clave de cliente. La habilitación de la eliminación temporal permite recuperar claves o depósitos en un plazo de 90 días de eliminación sin tener que restaurarlos a partir de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="8be0b-286">Para habilitar la eliminación temporal en los almacenes clave, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8be0b-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="8be0b-p135">Inicie sesión en su suscripción de Azure con Windows PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="8be0b-p136">Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . En este ejemplo, *vaultname* es el nombre del almacén de claves para el que se va a habilitar la eliminación temporal:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="8be0b-p137">Confirme que la eliminación de software está configurada para el almacén de claves mediante la ejecución del cmdlet **Get-AzureRmKeyVault** . Si la eliminación temporal está configurada correctamente para el almacén de claves, ¿está habilitada la eliminación temporal? Devuelve un valor de **true**:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="8be0b-293">Agregar una clave a cada depósito clave creando o importando una clave</span><span class="sxs-lookup"><span data-stu-id="8be0b-293">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="8be0b-294"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-294"></span></span>

<span data-ttu-id="8be0b-p138">Hay dos formas de agregar claves a un almacén de claves de Azure; puede crear una clave directamente en el almacén de claves, o puede importar una clave. La creación de una clave directamente en el almacén de claves es el método menos complicado, mientras que la importación de una clave proporciona un control total sobre la forma en que se genera la clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="8be0b-297">Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-297">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="8be0b-298">Donde:</span><span class="sxs-lookup"><span data-stu-id="8be0b-298">Where:</span></span>
  
-  <span data-ttu-id="8be0b-299">*vaultname* es el nombre del almacén de claves en el que desea crear la clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-299">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="8be0b-300">*keyName* es el nombre que desea asignar a la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-300">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8be0b-p139">Denomine claves con una Convención de nomenclatura similar, como se ha descrito anteriormente para los almacenes de claves. De este modo, en las herramientas que solo muestran el nombre de la clave, la cadena es autodescriptivo.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="8be0b-303">Si piensa proteger la clave con un HSM, asegúrese de especificar **HSM** como el valor del parámetro _Destination_ ; de lo contrario, especifique el **software**.</span><span class="sxs-lookup"><span data-stu-id="8be0b-303">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="8be0b-304">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="8be0b-304">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="8be0b-305">Para importar una clave directamente en el almacén de claves, debe tener un módulo de seguridad de hardware de Thales nShield.</span><span class="sxs-lookup"><span data-stu-id="8be0b-305">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="8be0b-306">Algunas organizaciones prefieren este enfoque para establecer la procedencia de sus claves y este método también ofrece lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8be0b-306">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="8be0b-307">El conjunto de herramientas usado para la importación incluye atestación de Thales de que la clave de intercambio de claves (KEK) que se usa para cifrar la clave que genera no es exportable y se genera dentro de un HSM genuino fabricado por Thales.</span><span class="sxs-lookup"><span data-stu-id="8be0b-307">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="8be0b-p140">El conjunto de herramientas incluye atestación de Thales que el mundo de seguridad de la clave de Azure también se generó en un HSM auténtico fabricado por Thales. Esta atestación le demuestra que Microsoft también usa hardware de Thales genuino.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="8be0b-p141">Consulte a su grupo de seguridad para determinar si se requieren las atestaciones anteriores. Para obtener instrucciones detalladas para crear una clave local e importarla en el almacén de claves, consulte [How to generaTE HSM-Protected Keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use las instrucciones de Azure para crear una clave en cada almacén de clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="8be0b-313">Comprobar el nivel de recuperación de las claves</span><span class="sxs-lookup"><span data-stu-id="8be0b-313">Check the recovery level of your keys</span></span>
<span data-ttu-id="8be0b-314"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-314"></span></span>

<span data-ttu-id="8be0b-p142">Office 365 requiere que la suscripción de Azure Key Vault esté definida como no cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación temporal. Para confirmarlo, consulte el nivel de recuperación de las claves.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="8be0b-317">Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzureKeyVaultKey de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="8be0b-318">Si la propiedad _nivel de recuperación_ devuelve cualquier cosa que no sea un valor recuperable **+ ProtectedSubscription**, tendrá que revisar este tema y asegurarse de que ha seguido todos los pasos para poner la suscripción en la lista no cancelar y que tiene habilitada la eliminación temporal en cada uno de los almacenes clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-318">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="8be0b-319">Copia de seguridad de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-319">Backup Azure Key Vault</span></span>
<span data-ttu-id="8be0b-320"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-320"></span></span>

<span data-ttu-id="8be0b-p143">Inmediatamente después de la creación o de cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. Las copias sin conexión no deben estar conectadas a ninguna red, como en un servicio de almacenamiento comercial o seguro físico. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda tener acceso en caso de desastre. Los blobs de copia de seguridad son los únicos medios de restaurar el material clave en caso de que una clave de almacén clave se destruya de forma permanente o no pueda ser procesada de forma inservible. Las claves externas a Azure Key Vault y que se importaron a Azure Key Vault no se califican como una copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existe con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para las operaciones de restauración con la clave de cliente. Por lo tanto, es fundamental realizar una copia de seguridad del almacén de claves de Azure una vez que se haya cargado o creado una clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="8be0b-328">Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-328">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="8be0b-329">Asegúrese de que el archivo de salida Use `.backup`el sufijo.</span><span class="sxs-lookup"><span data-stu-id="8be0b-329">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="8be0b-p144">El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar a la suscripción de Azure desde la que se realizó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="8be0b-p145">Para el archivo de salida, elija una combinación del nombre de la caja fuerte y el nombre de la clave. Esto hará que el nombre de archivo se describa automáticamente. También se asegurará de que los nombres de archivo de copia de seguridad no entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="8be0b-335">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-335">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="8be0b-336">Validar las opciones de configuración de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-336">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="8be0b-337"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-337"></span></span>

<span data-ttu-id="8be0b-p146">La validación antes de usar claves en un DEP es opcional, pero se recomienda encarecidamente. En particular, si usa los pasos para configurar las claves y los almacenes distintos de los que se describen en este tema, debe validar el estado de los recursos de Azure Key Vault antes de configurar la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="8be0b-340">Para comprobar que las claves tienen las operaciones GET, wrapKey y unwrapKey habilitadas:</span><span class="sxs-lookup"><span data-stu-id="8be0b-340">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="8be0b-341">Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-341">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="8be0b-p147">En el resultado, busque la Directiva de acceso y la identidad de Exchange Online (GUID) o la identidad de SharePoint Online (GUID) según corresponda. Los tres permisos anteriores deben mostrarse en permisos a claves.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="8be0b-344">Si la configuración de la Directiva de acceso no es correcta, ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-344">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="8be0b-345">Por ejemplo, para Exchange Online y Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="8be0b-345">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="8be0b-346">Por ejemplo, para SharePoint Online y OneDrive para la empresa:</span><span class="sxs-lookup"><span data-stu-id="8be0b-346">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="8be0b-347">Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-347">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="8be0b-p148">La clave de cliente no puede usar una clave expirada y las operaciones que se intentan con una clave expirada fallarán y, posiblemente, se producirá una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha distinta. Si se debe usar una clave que tenga establecida una fecha de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha distinta a 12/31/9999 no pasarán la validación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="8be0b-353">Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto de 12/31/9999, ejecute el cmdlet [set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-353">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="8be0b-354">No establezca fechas de expiración en las claves de cifrado que use con la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="8be0b-354">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="8be0b-355">Obtener el URI para cada clave de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-355">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="8be0b-356"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-356"></span></span>

<span data-ttu-id="8be0b-p149">Una vez que haya completado todos los pasos de Azure para configurar los almacenes clave y haya agregado las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de clave. Tendrá que usar estos URI cuando cree y asigne cada DEP más adelante, por lo que debe guardar esta información en un lugar seguro. Recuerde ejecutar este comando una vez para cada almacén de clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="8be0b-360">En Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8be0b-360">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8be0b-361">Office 365: configuración de la clave de cliente para Exchange Online y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="8be0b-361">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="8be0b-362"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-362"></span></span>

<span data-ttu-id="8be0b-p150">Antes de empezar, asegúrese de haber completado las tareas necesarias para configurar el almacén de claves de Azure. Vea la [clave de cliente completar tareas en Azure Key Vault y Microsoft FastTrack](controlling-your-data-using-customer-key.md#AzureSteps) para obtener información.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="8be0b-365">Para configurar la clave de cliente de Exchange Online y Skype empresarial, tendrá que realizar estos pasos conectándose de forma remota a Exchange Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8be0b-365">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="8be0b-366">Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="8be0b-366">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="8be0b-367"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-367"></span></span>

<span data-ttu-id="8be0b-p151">Un DEP está asociado a un conjunto de claves almacenadas en Azure Key Vault. Asigne un DEP a un buzón de correo en Office 365. Office 365 usará entonces las claves identificadas en la Directiva para cifrar el buzón. Para crear la DEP, necesita los URI de la bóveda de clave que obtuvo antes. Consulte [obtener el URI de cada clave de Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="8be0b-p152">Recuerde! Cuando se crea un DEP, se especifican dos claves que residen en dos depósitos de clave de Azure diferentes. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia geográfica.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="8be0b-376">Para crear la DEP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8be0b-376">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="8be0b-377">En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, [Conéctese a PowerShell de Exchange Online](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) abriendo Windows PowerShell y ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8be0b-377">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="8be0b-378">En el cuadro de diálogo solicitud de credenciales para Windows PowerShell, escriba la información de su cuenta profesional o educativa, haga clic en **Aceptar**y, a continuación, escriba el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8be0b-378">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="8be0b-379">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="8be0b-379">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="8be0b-380">Para crear un DEP, use el cmdlet New-DataEncryptionPolicy; para ello, escriba el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8be0b-380">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="8be0b-381">Donde:</span><span class="sxs-lookup"><span data-stu-id="8be0b-381">Where:</span></span>
    
   -  <span data-ttu-id="8be0b-p153">*PolicyName* es el nombre que desea usar para la Directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="8be0b-p154">*PolicyDescription* es una descripción sencilla para el usuario de la Directiva que le ayudará a recordar para qué sirve la Directiva. Puede incluir espacios en la descripción. Por ejemplo, clave raíz para buzones de correo en Estados Unidos y sus zonas de ventas.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="8be0b-p155">*KeyVaultURI1* es el URI para la primera clave de la Directiva. Por ejemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="8be0b-p156">*KeyVaultURI2* es el URI de la segunda clave de la Directiva. Por ejemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe los dos URI por una coma y un espacio.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="8be0b-393">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-393">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="8be0b-394">Asignar una DEP a un buzón</span><span class="sxs-lookup"><span data-stu-id="8be0b-394">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="8be0b-395"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-395"></span></span>

<span data-ttu-id="8be0b-p157">Asigne la DEP a un buzón mediante el cmdlet Set-Mailbox. Una vez asignada la Directiva, Office 365 puede cifrar el buzón con la clave designada en la DEP.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="8be0b-p158">Donde *MailboxIdParameter* especifica un buzón. Para obtener más información acerca del cmdlet Set-Mailbox, consulte [set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="8be0b-400">Validar el cifrado de buzones</span><span class="sxs-lookup"><span data-stu-id="8be0b-400">Validate mailbox encryption</span></span>
<span data-ttu-id="8be0b-401"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-401"></span></span>

<span data-ttu-id="8be0b-p159">El cifrado de un buzón puede tardar algún tiempo. Para la asignación de directivas primera vez, el buzón también debe completar el movimiento de una base de datos a otra antes de que el servicio pueda cifrar el buzón. Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar una DEP o la primera vez que asigna un DEP a un buzón.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="8be0b-405">Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.</span><span class="sxs-lookup"><span data-stu-id="8be0b-405">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="8be0b-406">La propiedad IsEncrypted devuelve un valor **true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado.</span><span class="sxs-lookup"><span data-stu-id="8be0b-406">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="8be0b-p160">El tiempo para completar los movimientos de buzones depende del número de buzones a los que se asigna la DEP por primera vez, así como del tamaño de los buzones. Si los buzones no se han cifrado después de una semana desde el momento en que se asignó la DEP, inicie un movimiento de buzón para los buzones sin cifrar mediante el cmdlet New-MoveRequest.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="8be0b-409">Office 365: configuración de la clave de cliente para SharePoint Online y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="8be0b-409">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="8be0b-410"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-410"></span></span>

<span data-ttu-id="8be0b-p161">Antes de empezar, asegúrese de haber completado las tareas necesarias para configurar el almacén de claves de Azure. Vea la [clave de cliente completar tareas en Azure Key Vault y Microsoft FastTrack](controlling-your-data-using-customer-key.md#AzureSteps) para obtener información.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="8be0b-413">Para configurar la clave de cliente de SharePoint Online y OneDrive para la empresa, necesitará realizar estos pasos conectándose de forma remota a SharePoint Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8be0b-413">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="8be0b-414">Crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="8be0b-414">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="8be0b-415"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-415"></span></span>

<span data-ttu-id="8be0b-p162">Un DEP está asociado a un conjunto de claves almacenadas en Azure Key Vault. Se aplica una DEP a todos los datos en una ubicación geográfica, también denominada geo. Si usa la característica multigeográfica de Office 365 (actualmente en versión preliminar), puede crear un DEP por geográfico. Si no usa la función multigeográfica, puede crear una DEP en Office 365 para usarla con SharePoint Online y OneDrive para la empresa. Office 365 usará entonces las claves identificadas en la DEP para cifrar los datos en esa geografía. Para crear la DEP, necesita los URI de la bóveda de clave que obtuvo antes. Consulte [obtener el URI de cada clave de Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="8be0b-p163">Recuerde! Cuando se crea un DEP, se especifican dos claves que residen en dos depósitos de clave de Azure diferentes. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia geográfica.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="8be0b-426">Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8be0b-426">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="8be0b-427">En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, [Conéctese a SharePoint Online PowerShell](https://technet.microsoft.com/library/fp161372.aspx).</span><span class="sxs-lookup"><span data-stu-id="8be0b-427">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="8be0b-428">En el shell de administración de Microsoft SharePoint Online, ejecute el cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-428">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="8be0b-p164">Cuando registra el DEP, el cifrado comienza en los datos de la geografía. Esto puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="8be0b-431">Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="8be0b-431">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="8be0b-432"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-432"></span></span>

<span data-ttu-id="8be0b-433">Puede comprobar el estado del cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-433">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="8be0b-434">El resultado de este cmdlet incluye:</span><span class="sxs-lookup"><span data-stu-id="8be0b-434">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="8be0b-435">URI de la clave principal.</span><span class="sxs-lookup"><span data-stu-id="8be0b-435">The URI of the primary key.</span></span>
    
- <span data-ttu-id="8be0b-436">URI de la clave secundaria.</span><span class="sxs-lookup"><span data-stu-id="8be0b-436">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="8be0b-p165">El estado de cifrado de la geografía. Los Estados posibles son:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="8be0b-439">No **registrado:** Aún no se ha aplicado el cifrado de clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="8be0b-439">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="8be0b-p166">**Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos se encuentran en proceso de cifrado. Si la geografía está en este estado, también se mostrará la información sobre el porcentaje de sitios en la geografía que se completa para que pueda supervisar el progreso del cifrado.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="8be0b-442">**Registrado:** Se ha aplicado el cifrado de clave de cliente y todos los archivos de todos los sitios se han cifrado.</span><span class="sxs-lookup"><span data-stu-id="8be0b-442">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="8be0b-p167">**Desplazamiento:** Hay un lanzamiento de clave en curso. Si la geografía está en este estado, también se mostrará la información sobre el porcentaje de sitios que han completado la operación de desplazamiento de claves para que pueda supervisar el progreso.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="8be0b-445">Administración de la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="8be0b-445">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="8be0b-446"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-446"></span></span>

<span data-ttu-id="8be0b-447">Una vez configurada la clave de cliente para Office 365, puede realizar estas tareas de administración adicionales.</span><span class="sxs-lookup"><span data-stu-id="8be0b-447">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="8be0b-448">Restaurar claves de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-448">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="8be0b-449">Desplazamiento o rotación de una clave en Azure Key Vault que se usa con la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8be0b-449">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="8be0b-450">Administrar permisos de almacén de claves</span><span class="sxs-lookup"><span data-stu-id="8be0b-450">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="8be0b-451">Determinación de la DEP asignada a un buzón</span><span class="sxs-lookup"><span data-stu-id="8be0b-451">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="8be0b-452">Restaurar claves de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-452">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="8be0b-453"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-453"></span></span>

<span data-ttu-id="8be0b-p168">Antes de realizar una restauración, use las capacidades de recuperación proporcionadas por la eliminación temporal. Todas las claves que se usan con la clave de cliente deben tener habilitada la eliminación temporal. La eliminación temporal actúa como una papelera de reciclaje y permite la recuperación de hasta 90 días sin necesidad de restaurarla. La restauración solo debe ser necesaria en circunstancias extremas o inusuales, por ejemplo, si se pierde la clave o el almacén de claves. Si necesita restaurar una clave para usarla con la clave de cliente, en Azure PowerShell, ejecute el cmdlet restore-AzureKeyVaultKey de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="8be0b-459">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-459">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="8be0b-p169">Si ya existe una clave con el mismo nombre en el almacén de claves, se producirá un error en la operación de restauración. Restore-AzureKeyVaultKey restaura todas las versiones principales y todos los metadatos de la clave, incluido el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="8be0b-462">Desplazamiento o rotación de una clave en Azure Key Vault que se usa con la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="8be0b-462">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="8be0b-463"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-463"></span></span>

<span data-ttu-id="8be0b-p170">Tanto la clave de Azure como la clave de cliente no requieren las claves de desplazamiento. Además, es prácticamente imposible poner en peligro las claves que están protegidas con HSM. Incluso si una clave raíz estaba en posesión de un actor malintencionado, no hay ningún medio viable de usarlo para descifrar datos, ya que solo el código de Office 365 sabe cómo usarlo. Sin embargo, la clave de cliente admite la rotación de una clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8be0b-p171">Haga solo una clave de cifrado que use con la clave de cliente cuando exista una razón técnica clara o cuando un requisito de cumplimiento exija que tenga que hacer roll? a la clave. Además, no elimine las claves que estén asociadas a directivas. Al revertir las claves, habrá contenido cifrado con las claves anteriores. Por ejemplo, los buzones activos se volverán a cifrar con frecuencia, los buzones inactivos, desconectados y deshabilitados pueden seguir cifrados con las claves anteriores. SharePoint Online realiza una copia de seguridad del contenido para restauración y recuperación, por lo que es posible que todavía haya contenido archivado con claves antiguas.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="8be0b-p172">Para garantizar la seguridad de sus datos, SharePoint Online permitirá que no haya más de una operación Roll Key en curso a la vez. Si desea aplicar ambas claves en un almacén de claves, tendrá que esperar a que se complete completamente la primera operación de rotación de clave. Nuestra recomendación es escalonar las operaciones de roll Key en diferentes intervalos, de modo que no se trata de un problema.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="8be0b-p173">Cuando se gira una clave, se solicita una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, use el mismo cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la misma sintaxis que usó para crear la clave en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="8be0b-478">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-478">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="8be0b-p174">En este ejemplo, dado que ya existe una clave llamada **contoso-O365EX-na-VaultA1-Key001** en el almacén **contoso-O365EX-na-VaultA1** , se creará una nueva versión de clave. La operación agrega una nueva versión de clave. Esta operación conserva las versiones anteriores de la clave en el historial de versiones de la clave, de modo que los datos cifrados anteriormente con esa clave todavía se pueden descifrar. Una vez que haya completado la desactivación de cualquier clave asociada a una DEP, debe ejecutar un cmdlet adicional para asegurarse de que la clave de cliente comienza a usar la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="8be0b-483">Habilitar Exchange Online y Skype empresarial para usar una clave nueva después de girar o rotar claves en Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-483">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="8be0b-484">Al aplicar las claves de Azure Key Vault asociadas con un DEP usado con Exchange Online y Skype empresarial, debe ejecutar el siguiente comando para actualizar el DEP y habilitar el inicio de Office 365 con la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-484">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="8be0b-485">Para indicar a la clave de cliente que use la nueva clave para cifrar buzones en Office 365 ejecute el cmdlet Set-DataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-485">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="8be0b-p175">En un plazo de 48 horas, los buzones activos cifrados con esta Directiva se asociarán con la clave actualizada. Siga los pasos descritos en [determinar el DEP asignado a un buzón de correo](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) para comprobar el valor de la propiedad DataEncryptionPolicyID del buzón. El valor de esta propiedad cambiará una vez se haya aplicado la clave actualizada.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="8be0b-489">Habilitar SharePoint Online y OneDrive para la empresa para usar una clave nueva después de girar o rotar claves en Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8be0b-489">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="8be0b-490">Cuando se revierte cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con SharePoint Online y OneDrive para la empresa, se debe ejecutar el cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) para actualizar el DEP y habilitar el inicio de Office 365 con la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="8be0b-490">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="8be0b-p176">Se iniciará la operación de desplazamiento de claves para SharePoint Online y OneDrive para la empresa. Esta acción no es inmediata. Para ver el progreso de la operación de desplazamiento de claves, ejecute el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8be0b-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="8be0b-494">Administrar permisos de almacén de claves</span><span class="sxs-lookup"><span data-stu-id="8be0b-494">Manage key vault permissions</span></span>
<span data-ttu-id="8be0b-495"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-495"></span></span>

<span data-ttu-id="8be0b-p177">Hay disponibles varios cmdlets que permiten ver y, si es necesario, quitar permisos de almacén de clave. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo.</span><span class="sxs-lookup"><span data-stu-id="8be0b-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="8be0b-498">Para ver los permisos de almacén de clave, ejecute el cmdlet Get-AzureRmKeyVault:</span><span class="sxs-lookup"><span data-stu-id="8be0b-498">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="8be0b-499">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-499">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="8be0b-500">Para quitar los permisos de un administrador, ejecute el cmdlet Remove-AzureRmKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="8be0b-500">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="8be0b-501">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8be0b-501">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="8be0b-502">Determinación de la DEP asignada a un buzón</span><span class="sxs-lookup"><span data-stu-id="8be0b-502">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="8be0b-503"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="8be0b-503"></span></span>

<span data-ttu-id="8be0b-p178">Para determinar la DEP asignada a un buzón, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="8be0b-p179">Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón. Para obtener más información acerca del cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8be0b-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="8be0b-508">Use el GUID para averiguar el nombre descriptivo de la DEP a la que está asignado el buzón de correo mediante la ejecución del siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8be0b-508">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="8be0b-509">Donde *GUID* es el GUID que devuelve el cmdlet Get-MailboxStatistics en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8be0b-509">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  


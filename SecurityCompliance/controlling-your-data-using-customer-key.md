---
title: Controlar los datos en Office 365 con la clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: Obtenga información sobre cómo configurar clave de cliente para Office 365 para Exchange Online, Skype para la empresa, SharePoint Online y OneDrive para la empresa. Con la clave de cliente, controlar las claves de cifrado de la organización y, a continuación, configurar Office 365 para usarlos para cifrar los datos en reposo en centros de datos de Microsoft.
ms.openlocfilehash: c4a59af49efad3bb8539b6c83b9ad9fd1c2d1f43
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723257"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="a04b6-104">Controlar los datos en Office 365 con la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a04b6-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="a04b6-p102">Con la clave de cliente, controlar las claves de cifrado de la organización y, a continuación, configurar Office 365 para usarlos para cifrar los datos en reposo en centros de datos de Microsoft. Datos en reposo incluyen los datos de Exchange Online y Skype para la empresa que se almacena en los buzones de correo y los archivos que se almacenan en SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="a04b6-p103">Debe configurar Azure para poder usar clave de cliente de Office 365. En este tema se describe los pasos que debe seguir para crear y configurar los recursos necesarios de Azure y luego se proporciona los pasos para la configuración de clave de cliente en Office 365. Después de haber completado el programa de instalación de Azure, determine qué directiva y, por lo tanto, qué teclas, para asignar a los buzones de correo y los archivos de la organización. Buzones de correo y los archivos para los que no asigne una directiva usará las directivas de cifrado que se controlan y administradas por Microsoft. Para obtener más información sobre la clave de cliente, o para obtener una descripción general, consulte la [Clave de cliente de preguntas más frecuentes de Office 365](service-encryption-with-customer-key-faq.md).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a04b6-p104">Se recomienda que siga los procedimientos recomendados en este tema. Estos se denominan como **Sugerencia** e **importante**. Cliente clave le proporciona que control sobre las claves de cifrado de raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que se cometen con estas claves puede tener un gran impacto y puede ocasionar que las interrupciones de servicio o pérdida irreparable de los datos.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="a04b6-116">Antes de comenzar la configuración de clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a04b6-116">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="a04b6-117"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-117"></span></span>

<span data-ttu-id="a04b6-p105">Antes de empezar, asegúrese de que tener la licencia adecuada para su organización. Clave de cliente en Office 365 está disponible en Office 365 E5 o la SKU de cumplimiento de normas avanzadas.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="a04b6-p106">A continuación, para comprender los conceptos y procedimientos descritos en este tema, debe revisar la documentación de la [Cámara de clave de Azure](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Además, a familiarizarse con los términos utilizados en Azure, por ejemplo, el [inquilino](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="a04b6-122">Para proporcionar comentarios en la clave del cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a04b6-122">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="a04b6-123">Información general de la configuración de clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="a04b6-123">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="a04b6-124"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-124"></span></span>

<span data-ttu-id="a04b6-p107">Para configurar la clave del cliente se realice estas tareas. El resto de este tema proporciona instrucciones detalladas para cada tarea o vínculos a para obtener más información para cada paso del proceso.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="a04b6-127">**En Azure y FastTrack de Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="a04b6-127">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="a04b6-p108">La mayoría de estas tareas se efectuarán mediante la conexión de forma remota a Azure PowerShell. Para obtener mejores resultados, utilice la versión 4.4.0 o una versión posterior de Windows Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="a04b6-130">Crear dos nuevas suscripciones de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-130">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="a04b6-131">Registrar las suscripciones de Azure para usar un período de retención obligatoria</span><span class="sxs-lookup"><span data-stu-id="a04b6-131">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="a04b6-132">El registro puede tardar de uno a cinco días laborables.</span><span class="sxs-lookup"><span data-stu-id="a04b6-132">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="a04b6-133">Enviar una solicitud para activar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="a04b6-133">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="a04b6-p109">Una vez que ha creado las dos suscripciones en Azure nuevo, debe enviar la solicitud de oferta de clave de cliente correspondiente al completar un formulario web que se hospeda en el portal de Microsoft FastTrack. **FastTrack el equipo no proporciona asistencia con clave de cliente. Office simplemente usa el portal de FastTrack para permitirle enviar el formulario y nos ayudará a realizar un seguimiento de las ofertas relevantes para la clave de cliente**.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. **The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="a04b6-p110">Una vez que se han enviado una oferta de clave de cliente, Microsoft revisa la solicitud y le notifica cuando puede continuar con el resto de las tareas del programa de instalación. Este proceso puede tardar hasta cinco días laborables.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="a04b6-138">Creación de una cámara de clave de Azure premium en cada suscripción</span><span class="sxs-lookup"><span data-stu-id="a04b6-138">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="a04b6-139">Asignar permisos a cada cámara clave</span><span class="sxs-lookup"><span data-stu-id="a04b6-139">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="a04b6-140">Habilitar y, a continuación, confirmar la eliminación de suave en los depósitos de clave</span><span class="sxs-lookup"><span data-stu-id="a04b6-140">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="a04b6-141">Agregar una clave a cada cámara clave ya sea mediante la creación o importar una clave</span><span class="sxs-lookup"><span data-stu-id="a04b6-141">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="a04b6-142">Compruebe el nivel de recuperación de las claves</span><span class="sxs-lookup"><span data-stu-id="a04b6-142">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="a04b6-143">Copia de seguridad cámara clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-143">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="a04b6-144">Validar los valores de configuración de cámara de clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-144">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="a04b6-145">Obtener el identificador URI para cada clave de cámara de clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-145">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="a04b6-146">**En Office 365:**</span><span class="sxs-lookup"><span data-stu-id="a04b6-146">**In Office 365:**</span></span>
  
<span data-ttu-id="a04b6-147">Exchange Online y Skype para la empresa:</span><span class="sxs-lookup"><span data-stu-id="a04b6-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="a04b6-148">Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="a04b6-149">Asignar una DEP a un buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a04b6-149">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="a04b6-150">Validar el cifrado de buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a04b6-150">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="a04b6-151">SharePoint Online y OneDrive para la empresa:</span><span class="sxs-lookup"><span data-stu-id="a04b6-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="a04b6-152">Crear una directiva de cifrado de datos (DEP) para cada OneDrive y SharePoint Online para profesionales geo</span><span class="sxs-lookup"><span data-stu-id="a04b6-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="a04b6-153">Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-153">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="a04b6-154">Completar las tareas en Azure clave cámara y Microsoft FastTrack para clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a04b6-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="a04b6-155"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-155"></span></span>

<span data-ttu-id="a04b6-p111">Completar estas tareas en Azure clave Vault para configurar la clave del cliente de Office 365. Debe completar estos pasos, independientemente de si piensa configurar clave de cliente para Exchange Online y Skype para empresas o SharePoint Online y OneDrive para la empresa o para todos los servicios compatibles de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="a04b6-158">Crear dos nuevas suscripciones de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-158">Create two new Azure subscriptions</span></span>
<span data-ttu-id="a04b6-159"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-159"></span></span>

<span data-ttu-id="a04b6-p112">Dos suscripciones Azure son necesarias para la clave de cliente. Como práctica recomendada, Microsoft recomienda crear nuevas suscripciones Azure para su uso con clave de cliente. Sólo se pueden autorizar Azure claves de cámara de clave para aplicaciones en el mismo arrendatario de Azure Active Directory (AAD), debe crear las suscripciones nuevo con el mismo arrendatario de Azure AD se utiliza con la organización de Office 365 donde se asignará la depós. Por ejemplo, con su cuenta de trabajo o escuela que tiene privilegios de administrador global de la organización de Office 365. Para obtener instrucciones detalladas, consulte [suscribirse a Azure como una organización](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a04b6-p113">Clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para poder realizar esta acción, debe crear dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda que tienen miembros independientes de la organización configurar una clave en cada suscripción. Además, estas suscripciones Azure sólo deben usarse para administrar las claves de cifrado para Office 365. Esto protege la organización en caso de que uno de los operadores de forma accidental, intencionadamente o intencionada elimina o mismanages en caso contrario, las claves para los que son responsables.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="a04b6-p114">Se recomienda que configure las nuevas suscripciones Azure que únicamente se utilizan para la administración de recursos de Azure clave Vault para su uso con clave de cliente. No hay ningún límite práctico para el número de Azure suscripciones que se pueden crear para su organización. Estos procedimientos recomendados se minimizar el impacto de los errores humanos al ayudar a administrar los recursos utilizados por clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="a04b6-173">Enviar una solicitud para activar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="a04b6-173">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="a04b6-174"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-174"></span></span>

<span data-ttu-id="a04b6-p115">Una vez que haya completado los pasos de Azure, debe enviar una solicitud de oferta en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Una vez que ha enviado una solicitud a través del portal de web FastTrack, Microsoft comprueba la cámara de clave de Azure configuración datos e información de contacto que ha proporcionado. Las selecciones que realice en el formulario oferta con respecto a los agentes autorizados de la organización es necesaria para la finalización de registro de la clave del cliente y no críticos. Los agentes de la organización que seleccione en el formulario que se usará para garantizar la autenticidad de cualquier solicitud para revocar y destruir todas las claves que se utiliza con una directiva de cifrado de datos de clave de cliente. Debe realizar este paso una vez para activar la clave de cliente para que Exchange Online y Skype para profesionales de cobertura y una segunda vez activar la clave de cliente para SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="a04b6-180">Para enviar una oferta para activar la clave de cliente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a04b6-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="a04b6-181">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a04b6-181">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="a04b6-182">Una vez que ha iniciado sesión, vaya al **panel**.</span><span class="sxs-lookup"><span data-stu-id="a04b6-182">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="a04b6-183">Elija **ofrece**y revise la lista de las ofertas de actuales.</span><span class="sxs-lookup"><span data-stu-id="a04b6-183">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="a04b6-184">Elija **Obtener más información** para la oferta que se aplica a usted:</span><span class="sxs-lookup"><span data-stu-id="a04b6-184">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="a04b6-185">**Exchange Online y Skype para la empresa:** Elija **Obtener más información** sobre la oferta de **Clave de cliente de Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a04b6-185">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="a04b6-186">**SharePoint Online y OneDrive para la empresa:** Eligió **Obtener más información** sobre la oferta de **Clave de cliente de SharePoint y OneDrive para la empresa** .</span><span class="sxs-lookup"><span data-stu-id="a04b6-186">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="a04b6-187">En la página **Detalles de la oferta** , elija **Crear una solicitud**.</span><span class="sxs-lookup"><span data-stu-id="a04b6-187">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="a04b6-p116">Rellene todos los detalles correspondientes y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones para que los agentes de la organización que desea autorizar para aprobar la destrucción permanente y irreversible de claves de cifrado y de datos. Una vez que haya completado el formulario, elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="a04b6-191">Este proceso puede tardar hasta cinco días de negocio una vez que Microsoft ha sido notificado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a04b6-191">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="a04b6-192">Continúe con la sección de período de retención obligatoria más adelante.</span><span class="sxs-lookup"><span data-stu-id="a04b6-192">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="a04b6-193">Registrar las suscripciones de Azure para usar un período de retención obligatoria</span><span class="sxs-lookup"><span data-stu-id="a04b6-193">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="a04b6-194"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-194"></span></span>

<span data-ttu-id="a04b6-p117">La pérdida temporal o permanente de las claves de cifrado de raíz puede ser muy perjudiciales o incluso tras errores graves a la operación de servicio y puede provocar una pérdida de datos. Por este motivo, los recursos que se utiliza con la clave de cliente requieren protección segura. Todos los recursos de Azure que se usan con clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Suscripciones de Azure pueden ser etiquetadas o registradas de forma que impiden la cancelación de inmediata y irrevocable. Esto se conoce como registro durante un período de retención obligatoria. Los pasos necesarios para registrar las suscripciones de Azure para un período de retención obligatoria requieren una colaboración con el equipo de Office 365. Este proceso puede tardar de uno a cinco días laborables. Anteriormente, esto se denomina a "No Cancelar".</span><span class="sxs-lookup"><span data-stu-id="a04b6-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="a04b6-203">Antes de ponerse en contacto con el equipo de Office 365, debe realizar los siguientes pasos para cada suscripción de Azure que usan con clave de cliente:</span><span class="sxs-lookup"><span data-stu-id="a04b6-203">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="a04b6-p118">Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="a04b6-206">Ejecute el cmdlet Register-AzureRmProviderFeature para registrar las suscripciones para usar un período de retención obligatoria.</span><span class="sxs-lookup"><span data-stu-id="a04b6-206">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="a04b6-p119">Póngase en contacto con Microsoft para que el proceso finalizando. Para SharePoint y OneDrive para el equipo de negocios, póngase en contacto con [spock@microsoft.com](mailto:spock@microsoft.com). Para Exchange Online y Skype para la empresa, póngase en contacto con [exock@microsoft.com](mailto:exock@microsoft.com). El contrato de nivel de servicio (SLA) para la finalización de este proceso es de cinco días de negocio una vez que Microsoft ha sido una notificación (y comprobado) que hayan registrado las suscripciones para usar un período de retención obligatoria. Incluir lo siguiente en su correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="a04b6-212">**Asunto**: clave del cliente para \< *nombre de dominio completo de su inquilino*\></span><span class="sxs-lookup"><span data-stu-id="a04b6-212">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="a04b6-213">**Cuerpo**: los identificadores de suscripción para la que desea que tengan el período finaliza una retención obligatoria.</span><span class="sxs-lookup"><span data-stu-id="a04b6-213">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="a04b6-214">Una vez que recibe la notificación de Microsoft que el registro es completado, compruebe el estado del registro ejecutando el cmdlet Get-AzureRmProviderFeature como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a04b6-214">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="a04b6-215">Después de comprobar que la propiedad de **Estado de registro** desde el cmdlet Get-AzureRmProviderFeature devuelve un valor de **Registered**, ejecute el siguiente comando para completar el proceso:</span><span class="sxs-lookup"><span data-stu-id="a04b6-215">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="a04b6-216">Creación de una cámara de clave de Azure premium en cada suscripción</span><span class="sxs-lookup"><span data-stu-id="a04b6-216">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="a04b6-217"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-217"></span></span>

<span data-ttu-id="a04b6-218">Los pasos para crear una clave cámara se documentan en [Getting Started with Azure clave Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que le guiará a través de la instalación e iniciar Windows Azure PowerShell, que se conectan a su suscripción de Azure, creación de un grupo de recursos y crear un depósito de clave en el que grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="a04b6-218">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="a04b6-p120">Cuando se crea una cámara clave, debe elegir un SKU: Standard o Premium. La SKU estándar permite claves de Azure clave Vault para estar protegidos con software - no hay ninguna protección de clave de módulo de seguridad de Hardware (HSM) - y la SKU Premium permite el uso de los HSM para la protección de las claves de cámara de clave. Clave de cliente acepta depósitos claves que usan cualquier SKU, aunque Microsoft recomienda encarecidamente que use sólo el SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia de costo es el costo por mes para cada clave protegida HSM. Para obtener más información, vea [clave de cámara de precios](https://azure.microsoft.com/pricing/details/key-vault/) .</span><span class="sxs-lookup"><span data-stu-id="a04b6-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a04b6-224">Utilice las teclas de protegida HSM y depósitos de SKU Premium claves para los datos de producción y usar sólo depósitos claves estándar SKU y claves con fines de prueba y validación.</span><span class="sxs-lookup"><span data-stu-id="a04b6-224">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="a04b6-p121">Para cada servicio de Office 365 con la que va a usar clave de cliente, cree una cámara clave en cada una de las dos suscripciones en Azure que ha creado. Por ejemplo, para Exchange Online y Skype para empresas sólo o SharePoint Online y OneDrive para la empresa solo, creará solo un par de depósitos. Para habilitar la clave de cliente para Exchange Online y SharePoint Online, va a crear dos pares de claves depósitos.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="a04b6-p122">Usar una convención de nomenclatura para depósitos claves que refleja el uso intencionado de la característica DEP a los que se asocian los depósitos. Vea la sección de procedimientos recomendados a continuación para recomendaciones de convención de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="a04b6-p123">Crear un conjunto de depósitos para cada directiva de cifrado de datos independiente y emparejado. Para Exchange Online, el ámbito de una directiva de cifrado de datos se elige por usted al asignar la directiva al buzón de correo. Un buzón de correo puede tener sólo una directiva asignada, y puede crear directivas de hasta cincuenta. Para SharePoint Online el ámbito de una directiva es todos los datos dentro de una organización en una ubicación geográfica o ubican.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="a04b6-p124">La creación de depósitos claves también requiere la creación de grupos de recursos de Azure, ya que depósitos claves necesitan la capacidad de almacenamiento de información (aunque muy pequeño) y cámara de clave de registro, si se habilita, también genera los datos almacenados. Como procedimiento recomendado Microsoft recomienda el uso de los administradores independientes para administrar cada grupo de recursos, con la administración que se alinea con el conjunto de los administradores que va a administrar todos los recursos relacionados de clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a04b6-p125">Para maximizar la disponibilidad, deben ser sus claves depósitos en regiones cerca de su servicio de Office 365. Por ejemplo, si la organización de Exchange Online está en Norteamérica, coloque los depósitos claves en Norteamérica. Si la organización de Exchange Online se encuentra en Europa, coloque las claves depósitos en Europa.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="a04b6-p126">Usar un prefijo común para depósitos claves e incluya una abreviatura del uso y el ámbito de las claves y cámara clave (por ejemplo, para el servicio de Contoso SharePoint donde se encuentran los depósitos en América del Norte, un par de nombres de posibles es Contoso-O365SP-NA-VaultA1 y Contoso-O365SP-NA-VaultA2. Nombres de cámara son cadenas globalmente únicas dentro de Azure, por lo que es posible que necesite para probar las variaciones de los nombres que desee en el caso de los nombres que desee ya se hayan solicitado por otros clientes de Azure. A partir de julio de 2017 cámara nombres no se puede cambiar, por lo que es una práctica recomendada tener un plan escrito para el programa de instalación y use una segunda persona para comprobar que el plan se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="a04b6-p127">Si es posible, cree los depósitos en regiones que no sean emparejada. Regiones de Azure emparejadas proporcionan una alta disponibilidad a través de dominios de errores de servicio. Por lo tanto, pares regionales pueden considerarse como región de copia de seguridad del otro. Esto significa que un recurso de Azure que se coloca en una región tiene automáticamente la tolerancia a errores a través de la región emparejada. Por este motivo, selección de regiones para dos depósitos usados en una DEP donde las regiones están emparejado significa que sólo un total de las dos regiones de disponibilidad están en uso. La mayoría de áreas geográficas sólo tienen dos regiones, por lo que no es posible seleccionar regiones no emparejados. Si es posible, elija dos regiones que no sean emparejados para los depósitos de dos que se utiliza con una dependencia Esto supone una ventaja de un total de cuatro áreas de disponibilidad. Para obtener más información, vea [recuperación ante desastres y continuidad del negocio (BCDR): áreas de Azure emparejada](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista de pares regionales.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="a04b6-251">Asignar permisos a cada cámara clave</span><span class="sxs-lookup"><span data-stu-id="a04b6-251">Assign permissions to each key vault</span></span>
<span data-ttu-id="a04b6-252"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-252"></span></span>

<span data-ttu-id="a04b6-p128">Para cada depósito de clave, debe definir tres conjuntos independientes de los permisos de clave de cliente, dependiendo de su implementación. Por ejemplo, debe definir un conjunto de permisos para cada una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="a04b6-p129">**Los administradores de cámara de clave** que se va a realizar la administración diaria de su cámara clave para su organización. Estas tareas incluyen la copia de seguridad, crean, obtengan, importación, lista y restauran.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a04b6-p130">El conjunto de permisos asignados a los administradores de la cámara clave no incluye el permiso para eliminar claves. Esto es intencionado y una práctica importante. Eliminación de las claves de cifrado normalmente no se realiza, ya que realiza entonces permanentemente destruye datos. Como procedimiento recomendado, no conceder este permiso a los administradores de la cámara clave de forma predeterminada. En su lugar, esto se reserva para los colaboradores de cámara clave y sólo asignarla a un administrador en una base de corto plazo una vez que se entiende una descripción clara de las consecuencias.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="a04b6-p131">Para asignar estos permisos a un usuario en la organización de Office 365, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="a04b6-264">Ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy para asignar los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="a04b6-264">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="a04b6-265">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-265">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="a04b6-p132">**Los colaboradores de cámara de clave** que se pueden cambiar los permisos en el depósito de clave de Azure propio. Debe cambiar estos permisos como empleados dejan o unirse a su equipo, o en la situación muy poco habitual que la clave vault administradores legítima necesitan permiso para eliminar o restaurar una clave. Este conjunto de las necesidades de los colaboradores de cámara clave tener el rol de **Colaborador** en su cámara clave. Puede asignar este rol mediante el Administrador de recursos de Azure. Para obtener instrucciones detalladas, consulte [Control de acceso de Use Role-Based para administrar el acceso a los recursos de suscripción de Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). El administrador que crea una suscripción a tiene este acceso de forma implícita, así como la capacidad para asignar a otros administradores al rol Colaborador.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="a04b6-p133">Si piensa usar clave de cliente con Exchange Online y Skype para la empresa, debe conceder permiso a Office 365 para utilizar la cámara clave en nombre de Exchange Online y Skype para la empresa. Del mismo modo, si piensa usar clave de cliente con SharePoint Online y OneDrive para la empresa, debe agregar permisos para Office 365 utilizar la cámara clave en nombre de SharePoint Online y OneDrive para la empresa. Para conceder permiso a Office 365, ejecute el cmdlet **Set-AzureRmKeyVaultAccessPolicy** mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="a04b6-275">Donde:</span><span class="sxs-lookup"><span data-stu-id="a04b6-275">Where:</span></span>
    
  - <span data-ttu-id="a04b6-276">*vaultname* es el nombre de la cámara clave que ha creado.</span><span class="sxs-lookup"><span data-stu-id="a04b6-276">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="a04b6-277">Para Exchange Online y Skype para la empresa, reemplace *appID de Office 365* con`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="a04b6-277">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="a04b6-278">Para SharePoint Online y OneDrive para la empresa, reemplace *appID de Office 365* con`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="a04b6-278">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="a04b6-279">Ejemplo: Configuración de permisos para Exchange Online y Skype para la empresa:</span><span class="sxs-lookup"><span data-stu-id="a04b6-279">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="a04b6-280">Ejemplo: Configuración de permisos para SharePoint Online y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-280">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="a04b6-281">Habilitar y, a continuación, confirmar la eliminación de suave en los depósitos de clave</span><span class="sxs-lookup"><span data-stu-id="a04b6-281">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="a04b6-282"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-282"></span></span>

<span data-ttu-id="a04b6-p134">Cuando se puede recuperar rápidamente las claves, es menos probable que a experimenta una interrupción del servicio ampliado debido a las claves eliminadas accidentalmente o de forma malintencionada. Debe habilitar esta configuración, que se conoce como eliminar suave, antes de poder utilizar las claves con clave de cliente. Habilitación de eliminar suave le permite recuperar claves o depósitos dentro de 90 días de eliminación sin tener que restaurarlos desde la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="a04b6-286">Para habilitar eliminar suave en los depósitos de clave, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a04b6-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="a04b6-p135">Inicie sesión en su suscripción de Azure con Windows Powershell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="a04b6-p136">Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . En este ejemplo, *vaultname* es el nombre de la cámara clave para la que va a habilitar eliminar suave:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="a04b6-p137">Confirmar eliminar suave está configurada para la cámara clave ejecutando el cmdlet **Get-AzureRmKeyVault** . ¿Si eliminar suave está configurado correctamente para el depósito de clave, el software eliminar habilitado? propiedad devuelve un valor de **True**:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="a04b6-293">Agregar una clave a cada cámara clave ya sea mediante la creación o importar una clave</span><span class="sxs-lookup"><span data-stu-id="a04b6-293">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="a04b6-294"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-294"></span></span>

<span data-ttu-id="a04b6-p138">Existen dos maneras de agregar las claves a una cámara de clave de Azure; puede crear una clave directamente en la clave de cámara, o puede importar una clave. Creación de una clave directamente en depósito de clave es el método menos complicado, mientras importar una clave proporciona un control total sobre cómo se genera la clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="a04b6-297">Para crear una clave directamente en su cámara clave, ejecute el cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-297">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="a04b6-298">Donde:</span><span class="sxs-lookup"><span data-stu-id="a04b6-298">Where:</span></span>
  
-  <span data-ttu-id="a04b6-299">*vaultname* es el nombre de la cámara clave en la que desea crear la clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-299">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="a04b6-300">*nombre de clave* es el nombre que desea dar a la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-300">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="a04b6-p139">Claves de nombre con una convención de nomenclatura similar, como se describió anteriormente para depósitos claves. De este modo, en herramientas que muestran sólo el nombre de clave, la cadena es autodescriptiva.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="a04b6-303">Si tiene la intención de proteger la clave con un HSM, asegúrese de que de lo contrario, especifique **HSM** como el valor del parámetro de _destino_ , especifique **Software**.</span><span class="sxs-lookup"><span data-stu-id="a04b6-303">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="a04b6-304">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="a04b6-304">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="a04b6-305">Para importar una clave directamente a su cámara clave, debe tener un nShield Thales módulo de seguridad de Hardware.</span><span class="sxs-lookup"><span data-stu-id="a04b6-305">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="a04b6-306">Algunas organizaciones prefieren este método para establecer la procedencia de sus claves y este método también proporciona lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a04b6-306">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="a04b6-307">El conjunto de herramientas utilizada para la importación incluye certificación de Thales que no es exportable la clave de Exchange de clave (KEK) que se usa para cifrar la clave que se genera y se genera dentro de un HSM original que se fabricó por Thales.</span><span class="sxs-lookup"><span data-stu-id="a04b6-307">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="a04b6-p140">El conjunto de herramientas incluye certificación de Thales que el mundo de la seguridad de Azure clave cámara también se generó en un auténtico HSM fabricado por Thales. La certificación demuestra a usted que Microsoft también está usando hardware de Thales original.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="a04b6-p141">Compruebe con su grupo de seguridad para determinar si son necesarias las declaraciones anteriores. Para que obtener instrucciones detalladas para crear una clave local y se importa a su cámara clave, vea [cómo generar y transferir claves protegida HSM para depósito de clave de Azure](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use las instrucciones de Azure para crear una clave en cada cámara clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="a04b6-313">Compruebe el nivel de recuperación de las claves</span><span class="sxs-lookup"><span data-stu-id="a04b6-313">Check the recovery level of your keys</span></span>
<span data-ttu-id="a04b6-314"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-314"></span></span>

<span data-ttu-id="a04b6-p142">Office 365 requiere que la suscripción de Azure clave cámara está establecida en no cancelar y que las teclas usadas por clave de cliente tienen suave eliminar habilitado. Puede confirmarlo mirando en el nivel de recuperación en las claves.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="a04b6-317">Para comprobar el nivel de recuperación de una clave, en Windows Azure PowerShell, ejecute el cmdlet Get-AzureKeyVaultKey como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="a04b6-318">Si la propiedad de _Nivel de recuperación_ devuelve nada que no sea un valor de **Recuperable + ProtectedSubscription**, necesitará revisar este tema y asegúrese de que ha seguido todos los pasos para colocar la suscripción en la lista no cancelar y que debe eliminar suave habilitado en cada uno de los depósitos de clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-318">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="a04b6-319">Copia de seguridad cámara clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-319">Backup Azure Key Vault</span></span>
<span data-ttu-id="a04b6-320"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-320"></span></span>

<span data-ttu-id="a04b6-p143">Inmediatamente después de la creación o cualquier cambio a una clave, realizar una copia de seguridad y almacenar copias de la copia de seguridad, en línea y sin conexión. Copias sin conexión deben no esté conectadas a cualquier red, por ejemplo, en un servicio de almacenamiento físico de seguros o comerciales. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación que sea accesible en el caso de un desastre. Los objetos binarios de copia de seguridad son los únicos medios de restauración de material de clave debe una clave de cámara de clave se destruye permanentemente o inoperativo en caso contrario. Claves que son externos a Azure clave cámara y se importaron a Azure clave cámara no cumple los requisitos como una copia de seguridad porque los metadatos necesarios para la clave del cliente usar la clave no existe con la clave externa. Sólo una copia de seguridad tomado de cámara de Azure clave se puede usar para operaciones de restauración con clave de cliente. Por lo tanto, es esencial que se realice una copia de seguridad de Azure clave cámara una vez que se cargan o creada una clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="a04b6-328">Para crear una copia de seguridad de una clave de cámara de clave de Azure, ejecute el cmdlet de [AzureKeyVaultKey de copia de seguridad](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a04b6-328">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="a04b6-329">Asegúrese de que el archivo de salida utiliza el sufijo de `.backup`.</span><span class="sxs-lookup"><span data-stu-id="a04b6-329">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="a04b6-p144">El archivo de salida resultante de este cmdlet se cifra y no se puede usar fuera de cámara de clave de Azure. Sólo para la suscripción de Azure desde la que se realizó la copia de seguridad se puede restaurar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="a04b6-p145">Para el archivo de salida, elija una combinación de su nombre de depósito y el nombre de la clave. Esto hará que el archivo nombre autodescriptiva. También asegurará que los nombres de archivo de copia de seguridad no entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="a04b6-335">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-335">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="a04b6-336">Validar los valores de configuración de cámara de clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-336">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="a04b6-337"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-337"></span></span>

<span data-ttu-id="a04b6-p146">Realizar la validación antes de usar claves en una DEP es opcional, pero se recomienda encarecidamente. En particular, si usa los pasos para configurar las claves y depósitos distinto de los que se describen en este tema, debe validar el estado de los recursos de Azure clave cámara antes de configurar la clave del cliente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="a04b6-340">Para comprobar que las claves tienen operaciones get, wrapKey y unwrapKey habilitadas:</span><span class="sxs-lookup"><span data-stu-id="a04b6-340">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="a04b6-341">Ejecute el cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-341">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="a04b6-p147">En el resultado, busque para la directiva de acceso y de la identidad de Exchange Online (GUID) o la identidad de SharePoint Online (GUID), según corresponda. Las tres de los permisos anteriores deben mostrarse en permisos para las claves.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="a04b6-344">Si la configuración de directiva de acceso no es correcta, ejecute el cmdlet Set-AzureRmKeyVaultAccessPolicy como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-344">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="a04b6-345">Por ejemplo, para Exchange Online y Skype para la empresa:</span><span class="sxs-lookup"><span data-stu-id="a04b6-345">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="a04b6-346">Por ejemplo, para SharePoint Online y OneDrive para la empresa:</span><span class="sxs-lookup"><span data-stu-id="a04b6-346">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="a04b6-347">Para comprobar que no se establece una fecha de caducidad para las claves que se ejecute el cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-347">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="a04b6-p148">No se puede usar una clave que han expirado por clave de cliente y se producirá un error en operaciones intentadas con una clave que han expirado y, posiblemente, provocar una interrupción del servicio. Se recomienda encarecidamente que las claves que se utiliza con la clave de cliente no tienen una fecha de caducidad. Una fecha de caducidad, una vez que el conjunto, no se pueden quitar, pero se puede cambiar a una fecha diferente. Si debe usar una clave que tenga una fecha de caducidad, cambie el valor de expiración a 31/12/9999. Claves con una fecha de caducidad se establece en una fecha distinta de 31/12/9999 no pasará la validación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="a04b6-353">Para cambiar una fecha de caducidad que se ha establecido en un valor distinto de 31/12/9999, ejecute el cmdlet [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-353">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="a04b6-354">No establecer fechas de caducidad en las claves de cifrado que se utiliza con la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-354">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="a04b6-355">Obtener el identificador URI para cada clave de cámara de clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-355">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="a04b6-356"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-356"></span></span>

<span data-ttu-id="a04b6-p149">Una vez que haya completado todos los pasos en Azure para configurar sus claves depósitos y agrega las claves, ejecute el siguiente comando para obtener el URI de la clave en cada cámara clave. Debe utilizar estos identificadores URI al crear y asignar cada DEP más adelante, por lo que guarde esta información en un lugar seguro. Recuerde que debe ejecutar este comando una vez para cada depósito de clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="a04b6-360">En Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a04b6-360">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="a04b6-361">Office 365: Configuración de clave de cliente para Exchange Online y Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-361">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="a04b6-362"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-362"></span></span>

<span data-ttu-id="a04b6-p150">Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar la cámara de clave de Azure. Para obtener información, vea [completar las tareas en Azure clave cámara y FastTrack de Microsoft para la clave de cliente](controlling-your-data-using-customer-key.md#AzureSteps) .</span><span class="sxs-lookup"><span data-stu-id="a04b6-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="a04b6-365">Para configurar la clave de cliente para Exchange Online y Skype para la empresa, debe realizar estos pasos mediante la conexión de forma remota a Exchange Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a04b6-365">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="a04b6-366">Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-366">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="a04b6-367"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-367"></span></span>

<span data-ttu-id="a04b6-p151">Una característica DEP está asociada con un conjunto de claves que se almacenan en Azure clave cámara. Asignar una DEP a un buzón en Office 365. Office 365, a continuación, usará las teclas identificadas en la directiva para cifrar el buzón de correo. Para crear la DEP, necesita a los URI de cámara clave obtenido anteriormente. Para obtener instrucciones, vea [obtener el identificador URI para cada clave de cámara de clave de Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .</span><span class="sxs-lookup"><span data-stu-id="a04b6-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="a04b6-p152">¡Recuerde! Cuando se crea una DEP, especifique dos claves que residen en dos diferentes depósitos de clave de Azure. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia de geo.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="a04b6-376">Para crear la DEP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a04b6-376">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="a04b6-377">En el equipo local, usando una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, [conectarse a Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) abrir Windows PowerShell y ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a04b6-377">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="a04b6-378">En el cuadro de diálogo solicitud de credenciales de Windows PowerShell, escriba su trabajo o escuela información de cuenta, haga clic en **Aceptar**y, a continuación, escriba el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a04b6-378">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="a04b6-379">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-379">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="a04b6-380">Para crear una DEP, use el cmdlet New-DataEncryptionPolicy escribiendo el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a04b6-380">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="a04b6-381">Donde:</span><span class="sxs-lookup"><span data-stu-id="a04b6-381">Where:</span></span>
    
   -  <span data-ttu-id="a04b6-p153">*PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="a04b6-p154">*PolicyDescription* es una descripción de usuario descriptivo de la directiva que le ayudarán a recordar cuál es la directiva. Puede incluir espacios en la descripción. Por ejemplo, raíz clave para los buzones de correo en Estados Unidos y sus territorios.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="a04b6-p155">*KeyVaultURI1* es el identificador URI para la primera clave en la directiva. Por ejemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="a04b6-p156">*KeyVaultURI2* es el identificador URI para la segunda clave en la directiva. Por ejemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe a los dos URI por una coma y un espacio.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="a04b6-393">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-393">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="a04b6-394">Asignar una DEP a un buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a04b6-394">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="a04b6-395"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-395"></span></span>

<span data-ttu-id="a04b6-p157">Asignar la DEP a un buzón de correo mediante el cmdlet Set-Mailbox. Una vez que asigne la directiva, Office 365 puede cifrar el buzón de correo con la clave designada en la DEP.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="a04b6-p158">Donde *MailboxIdParameter* especifica un buzón de correo. Para obtener más información acerca del cmdlet Set-Mailbox, consulte [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="a04b6-400">Validar el cifrado de buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a04b6-400">Validate mailbox encryption</span></span>
<span data-ttu-id="a04b6-401"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-401"></span></span>

<span data-ttu-id="a04b6-p159">Cifrar un buzón de correo puede tardar un poco. Para la primera asignación de directivas de tiempo, el buzón de correo también debe completar el traslado de una base de datos a otro antes de que el servicio puede cifrar el buzón de correo. Se recomienda que espere 72 horas antes de intentar validar cifrado después de cambiar una DEP o la primera vez se puede asignar una DEP a un buzón.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="a04b6-405">Use el cmdlet Get-MailboxStatistics para determinar si se cifra un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="a04b6-405">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="a04b6-406">La propiedad IsEncrypted devuelve un valor de **true** si se cifra el buzón de correo y el valor **false** si el buzón de correo no se cifra.</span><span class="sxs-lookup"><span data-stu-id="a04b6-406">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="a04b6-p160">El tiempo para completar movimientos de buzones depende del número de buzones a los que asignar la característica DEP por primera vez, así como el tamaño de los buzones de correo. Si no ha cifrado los buzones de correo después de una semana desde el momento en que asignó la DEP, iniciar un movimiento del buzón para los buzones de correo sin cifrar mediante el cmdlet New-MoveRequest.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="a04b6-409">Office 365: Configuración de clave de cliente para SharePoint Online y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-409">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="a04b6-410"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-410"></span></span>

<span data-ttu-id="a04b6-p161">Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar la cámara de clave de Azure. Para obtener información, vea [completar las tareas en Azure clave cámara y FastTrack de Microsoft para la clave de cliente](controlling-your-data-using-customer-key.md#AzureSteps) .</span><span class="sxs-lookup"><span data-stu-id="a04b6-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="a04b6-413">Para configurar la clave del cliente para SharePoint Online y OneDrive para la empresa, debe realizar estos pasos mediante la conexión de forma remota en SharePoint Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a04b6-413">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="a04b6-414">Crear una directiva de cifrado de datos (DEP) para cada OneDrive y SharePoint Online para profesionales geo</span><span class="sxs-lookup"><span data-stu-id="a04b6-414">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="a04b6-415"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-415"></span></span>

<span data-ttu-id="a04b6-p162">Una característica DEP está asociada con un conjunto de claves que se almacenan en Azure clave cámara. Aplicar una DEP para todos los datos en una ubicación geográfica, también denominado un geo. Si usa la característica de multi-ubican de Office 365 (actualmente en la vista previa), puede crear uno DEP por ubican. Si no está utilizando multi-ubican, puede crear uno DEP en Office 365 para su uso con SharePoint Online y OneDrive para la empresa. Office 365, a continuación, usará las teclas identificadas en la característica DEP para cifrar los datos en ese ubican. Para crear la DEP, necesita a los URI de cámara clave obtenido anteriormente. Para obtener instrucciones, vea [obtener el identificador URI para cada clave de cámara de clave de Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .</span><span class="sxs-lookup"><span data-stu-id="a04b6-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="a04b6-p163">¡Recuerde! Cuando se crea una DEP, especifique dos claves que residen en dos diferentes depósitos de clave de Azure. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia de geo.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="a04b6-426">Para crear una DEP, debe conectarse de forma remota en SharePoint Online mediante el uso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a04b6-426">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="a04b6-427">En el equipo local, usando una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, [conectarse a SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span><span class="sxs-lookup"><span data-stu-id="a04b6-427">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="a04b6-428">En la consola de administración de Microsoft en línea de SharePoint ejecute el cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-428">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="a04b6-p164">Cuando se registre la DEP, cifrado comienza en los datos en el ubican. Esto puede tardar un poco.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="a04b6-431">Validar el cifrado de sitios de grupo, sitios de grupo y OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="a04b6-431">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="a04b6-432"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-432"></span></span>

<span data-ttu-id="a04b6-433">Puede comprobar el estado de cifrado ejecutando el cmdlet Get-SPODataEncryptionPolicy como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a04b6-433">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="a04b6-434">El resultado de este cmdlet incluye:</span><span class="sxs-lookup"><span data-stu-id="a04b6-434">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="a04b6-435">El URI de la clave principal.</span><span class="sxs-lookup"><span data-stu-id="a04b6-435">The URI of the primary key.</span></span>
    
- <span data-ttu-id="a04b6-436">El URI de la clave secundaria.</span><span class="sxs-lookup"><span data-stu-id="a04b6-436">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="a04b6-p165">El estado de cifrado para el ubican. Los Estados posibles son:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="a04b6-439">**No registradas:** Cifrado de clave de cliente aún no se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="a04b6-439">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="a04b6-p166">**Registro:** Se ha aplicado el cifrado de clave de cliente y los archivos se encuentran en el proceso de cifrado. Si su geo se encuentra en este estado, se podrá también se mostrará información en qué porcentaje de sitios en la ubican están completas para que pueda supervisar el progreso de cifrado.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="a04b6-442">**Registrado:** Se ha aplicado el cifrado de clave de cliente, y se han cifrado todos los archivos en todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="a04b6-442">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="a04b6-p167">**Sucesivas:** Una clave roll está en curso. Si su geo se encuentra en este estado, se podrá también se mostrará información en qué porcentaje de sitios haya completado la operación roll clave para que se puede supervisar el progreso.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="a04b6-445">Administración de clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="a04b6-445">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="a04b6-446"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-446"></span></span>

<span data-ttu-id="a04b6-447">Después de que ha configurado la clave del cliente de Office 365, puede realizar estas tareas de administración adicionales.</span><span class="sxs-lookup"><span data-stu-id="a04b6-447">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="a04b6-448">Restaurar las claves de cámara de clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-448">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="a04b6-449">Constante o girar una clave en Azure depósito de clave que se utiliza con la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a04b6-449">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="a04b6-450">Administrar los permisos de la clave de cámara</span><span class="sxs-lookup"><span data-stu-id="a04b6-450">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="a04b6-451">Determinar la DEP asignada a un buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a04b6-451">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="a04b6-452">Restaurar las claves de cámara de clave de Azure</span><span class="sxs-lookup"><span data-stu-id="a04b6-452">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="a04b6-453"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-453"></span></span>

<span data-ttu-id="a04b6-p168">Antes de realizar una restauración, use las funciones de recuperación proporcionadas por eliminar suave. Todas las claves que se usan con clave de cliente se necesitan tener suave eliminar habilitado. Eliminar suave actúa como una Papelera de reciclaje y permite la recuperación de hasta 90 días sin necesidad de restaurar. Restauración sólo será necesario en circunstancias extremas o poco habituales, por ejemplo, si se pierde la clave o depósito de clave. Si debe restaurar una clave para su uso con clave de cliente, en Azure PowerShell, ejecute el cmdlet Restore-AzureKeyVaultKey como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="a04b6-459">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-459">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="a04b6-p169">Si ya existe una clave con el mismo nombre en la caja fuerte de clave, se producirá un error en la operación de restauración. AzureKeyVaultKey de restauración restaura todas las versiones de clave y todos los metadatos de la clave, incluido el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="a04b6-462">Constante o girar una clave en Azure depósito de clave que se utiliza con la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a04b6-462">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="a04b6-463"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-463"></span></span>

<span data-ttu-id="a04b6-p170">Constante de claves no es necesario por cualquier cámara de clave de Azure o por clave de cliente. Además, las claves que están protegidas con un HSM son prácticamente imposibles para poner en peligro. Incluso si una clave raíz estuvieron en posesión de un actor malintencionado no hay ningún medio viable de uso para descifrar los datos, ya que sólo el código de Office 365 sabe cómo usarla. Sin embargo, la aplicación de una clave es compatible con clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a04b6-p171">Aplicar sólo una clave de cifrado que utilice con clave de cliente cuando exista una razón desactive técnica o un requisito de cumplimiento de normas determina que se debe aplicar la clave. Además, no elimine las claves que están o se han asociado con directivas. Cuando restaure su claves, encontrará contenido cifrarse con las claves anteriores. Por ejemplo, mientras buzones activos se vuelva a cifrarán con frecuencia, como inactiva, buzones desconectados y deshabilitados aún se cifran con las claves anteriores. SharePoint Online realiza copia de seguridad de contenido para fines de restauración y recuperación, por lo que puede haber contenido archivado con las claves antiguas.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="a04b6-p172">Para garantizar la seguridad de los datos, SharePoint Online le permitirá no más de una operación de deshacer clave estén en curso en un momento. Si desea aplicar ambas de las claves en una cámara de clave, que necesitará para esperar a la primera operación roll clave totalmente completa. Nuestra recomendación es escalonar las operaciones clave roll en intervalos diferentes, por lo que no es un problema.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="a04b6-p173">Cuando restaure una clave, que va a solicitar una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, se usa el cmdlet mismo, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la misma sintaxis que usan para crear la clave en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="a04b6-478">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-478">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="a04b6-p174">En este ejemplo, dado que una clave denominada **Contoso-O365EX-NA-VaultA1-Key001** ya existe en la cámara **Contoso-O365EX-NA-VaultA1** , se creará una nueva versión de la clave. La operación agrega una nueva versión de la clave. Esta operación mantiene las versiones anteriores de clave en el historial de versiones de la clave, por lo que aún se pueden descifrar los datos cifrados anteriormente con esa clave. Una vez haya completado la constante cualquier tecla que está asociada con una DEP, a continuación, debe ejecutar un cmdlet adicional para asegurarse de que clave de cliente comienza con la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="a04b6-483">Habilitar Exchange Online y Skype para la empresa usar una nueva clave después de restaurar o girar claves en Azure clave de cámara</span><span class="sxs-lookup"><span data-stu-id="a04b6-483">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="a04b6-484">Cuando se lleve a cabo cualquiera de las claves de Azure clave depósito asociadas con una DEP se usan con Exchange Online y Skype para la empresa, debe ejecutar el siguiente comando para actualizar la característica DEP y habilitar Office 365 comenzar a usar la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-484">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="a04b6-485">Para indicar a la clave de cliente para usar la nueva clave para cifrar los buzones de correo en Office 365, ejecute el cmdlet Set-DataEncryptionPolicy como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-485">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="a04b6-p175">Dentro de 48 horas, los buzones de correo activa cifradas mediante esta directiva se asociará con la clave actualizada. Utilice los pasos en [Determine la DEP asignada a un buzón de correo](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) para comprobar el valor de la propiedad DataEncryptionPolicyID para el buzón de correo. Una vez que se ha aplicado la clave actualizada, se cambiará el valor de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="a04b6-489">Habilitar SharePoint Online y OneDrive para la empresa usar una nueva clave después de restaurar o girar claves en Azure clave de cámara</span><span class="sxs-lookup"><span data-stu-id="a04b6-489">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="a04b6-490">Cuando se lleve a cabo cualquiera de las claves de Azure clave depósito asociadas con una DEP se usan con SharePoint Online y OneDrive para la empresa, debe ejecutar el cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) para actualizar la característica DEP y habilitar Office 365 comenzar a usar la nueva clave.</span><span class="sxs-lookup"><span data-stu-id="a04b6-490">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="a04b6-p176">Esto se iniciará la operación roll clave para SharePoint Online y OneDrive para la empresa. Esta acción no es inmediata. Para ver el progreso de la clave de operación de deshacer, ejecute el cmdlet Get-SPODataEncryptionPolicy como sigue:</span><span class="sxs-lookup"><span data-stu-id="a04b6-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="a04b6-494">Administrar los permisos de la clave de cámara</span><span class="sxs-lookup"><span data-stu-id="a04b6-494">Manage key vault permissions</span></span>
<span data-ttu-id="a04b6-495"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-495"></span></span>

<span data-ttu-id="a04b6-p177">Varios cmdlets están disponibles que le permiten ver y, si es necesario, quitar los permisos de cámara clave. Es posible que necesite quitar permisos, por ejemplo, cuando un empleado deja el equipo.</span><span class="sxs-lookup"><span data-stu-id="a04b6-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="a04b6-498">Para ver los permisos de la clave de cámara, ejecute el cmdlet Get-AzureRmKeyVault:</span><span class="sxs-lookup"><span data-stu-id="a04b6-498">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="a04b6-499">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-499">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="a04b6-500">Para quitar permisos de un administrador, ejecute el cmdlet Remove-AzureRmKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="a04b6-500">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="a04b6-501">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a04b6-501">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="a04b6-502">Determinar la DEP asignada a un buzón de correo</span><span class="sxs-lookup"><span data-stu-id="a04b6-502">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="a04b6-503"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="a04b6-503"></span></span>

<span data-ttu-id="a04b6-p178">Para determinar la DEP asignada a un buzón de correo, use el cmdlet Get-MailboxStatistics. El cmdlet devuelve un identificador único (GUID).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="a04b6-p179">Donde *GeneralMailboxOrMailUserIdParameter* especifica un buzón de correo. Para obtener más información acerca del cmdlet Get-MailboxStatistics, vea [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a04b6-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="a04b6-508">Usar el GUID para averiguar el nombre descriptivo de la característica DEP al que está asignado el buzón de correo ejecutando el cmdlet siguiente.</span><span class="sxs-lookup"><span data-stu-id="a04b6-508">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="a04b6-509">Donde *GUID* es el GUID devuelto por el cmdlet Get-MailboxStatistics en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a04b6-509">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  


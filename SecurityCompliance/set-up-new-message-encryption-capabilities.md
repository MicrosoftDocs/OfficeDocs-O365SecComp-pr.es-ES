---
title: Configurar las nuevas capacidades de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Nuevas capacidades de cifrado de mensajes de Office 365 basadas en Azure Information Protection, su organización puede usar la comunicación de correo electrónico protegida con personas de dentro y fuera de la organización. Las nuevas capacidades de OME funcionan con otras organizaciones de Office 365, Outlook.com, gmail y otros servicios de correo electrónico.
ms.openlocfilehash: 90247a7e3cd7e5978eb144a2b6f66a9de21a8f96
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296193"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="1f5bc-104">Configurar las nuevas capacidades de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f5bc-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="1f5bc-p102">Las nuevas capacidades de cifrado de mensajes (OME) de Office 365 permiten que las organizaciones compartan correo electrónico protegido con cualquier usuario en cualquier dispositivo. Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son de Office 365 con Outlook.com, gmail y otros servicios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p102">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device. Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>


>[!NOTE]
><span data-ttu-id="1f5bc-p103">Este artículo está dirigido a administradores y profesionales de ti. Si es un usuario final, consulte la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) para obtener soluciones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p103">This article is intended for administrators and IT professionals. If you're an end-user, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) for appropriate solutions.</span></span>

<span data-ttu-id="1f5bc-109">Siga los pasos a continuación para asegurarse de que las nuevas capacidades de OME estén disponibles en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-109">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 tenant.</span></span> 

## <a name="verify-azure-rights-management-arm-is-active"></a><span data-ttu-id="1f5bc-110">Compruebe que Azure Rights Management (ARM) esté activo</span><span class="sxs-lookup"><span data-stu-id="1f5bc-110">Verify Azure Rights Management (ARM) is active</span></span>

>[!NOTE]
><span data-ttu-id="1f5bc-111">Las nuevas capacidades de OME aprovechan las características de protección de [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), la tecnología usada por [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="1f5bc-111">The new OME capabilities leverage the protection features in [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span></span>

<span data-ttu-id="1f5bc-p104">El único requisito previo para usar las nuevas capacidades de OME es que [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) debe activarse en el inquilino de Office 365. Si es así, Office 365 activa automáticamente las nuevas funciones de OME y no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p104">The only prerequisite for using the new OME capabilities is that [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your Office 365 tenant. If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span> 

<span data-ttu-id="1f5bc-p105">La ARM también se activa automáticamente en la mayoría de los planes elegibles, por lo que es probable que no tenga que hacer nada en este sentido. Vea [Activar Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) para obtener más.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p105">ARM is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either. See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1f5bc-p106">Si usa Active Directory Rights Management Service (AD RMS) con Exchange Online, debe [migrar a Azure Information Protection para](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) poder usar las nuevas funcionalidades de OME. AD RMS no es compatible con ARM.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p106">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities. AD RMS is not compatible with ARM.</span></span>  

<span data-ttu-id="1f5bc-118">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-118">For more, see:</span></span>

- <span data-ttu-id="1f5bc-119">[¿Qué suscripciones necesito para usar las nuevas capacidades de OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye ARM).</span><span class="sxs-lookup"><span data-stu-id="1f5bc-119">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes ARM).</span></span>   
-  <span data-ttu-id="1f5bc-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) para obtener información sobre cómo comprar una suscripción elegible.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-arm"></a><span data-ttu-id="1f5bc-121">Activar manualmente la ARM</span><span class="sxs-lookup"><span data-stu-id="1f5bc-121">Manually activating ARM</span></span>

<span data-ttu-id="1f5bc-122">Si ha deshabilitado la ARM o si no se activó automáticamente por algún motivo, puede activarla manualmente en:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-122">If you disabled ARM, or if it was not automatically activated for any reason, you can activated it manually in the :</span></span>

- <span data-ttu-id="1f5bc-123">**Centro de administración de office 365**: vea [Cómo activar Azure Rights Management desde el centro de administración de Office 365](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) para obtener instrucciones</span><span class="sxs-lookup"><span data-stu-id="1f5bc-123">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions</span></span>
- <span data-ttu-id="1f5bc-124">**Portal de Azure**: vea [Cómo activar Azure Rights Management desde Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-124">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span> 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="1f5bc-125">Configurar la administración de la clave de inquilino de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1f5bc-125">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="1f5bc-p107">Este paso es opcional. Permitir que Microsoft administre la clave raíz para Azure Information Protection es la configuración predeterminada y la mejor práctica recomendada para la mayoría de los inquilinos de Office 365. Si este es el caso, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p107">This is an optional step. Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants. If this is the case, you don't need to do anything.</span></span> 

<span data-ttu-id="1f5bc-p108">Hay muchas razones, por ejemplo, para los requisitos de cumplimiento, que pueden requerir que genere y administre su propia clave raíz (también denominada traer su propia clave (BYOK)). Si este es el caso, le recomendamos que complete los pasos necesarios antes de configurar las nuevas funciones de OME. Consulte [planeación e implementación de la clave de inquilino de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p108">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)). If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities. See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span> 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="1f5bc-132">Comprobar la nueva configuración de OME en Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f5bc-132">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="1f5bc-133">Puede comprobar que el inquilino de Office 365 está configurado correctamente para usar las nuevas funciones de OME en [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f5bc-133">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="1f5bc-134">[Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-134">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="1f5bc-135">Ejecute el cmdlet test-IRMConfiguration con la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="1f5bc-136">**Ejemplo**:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-136">**Example**:</span></span> 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - <span data-ttu-id="1f5bc-p109">La inclusión de un correo electrónico de remitente es opcional, pero obliga al sistema a realizar comprobaciones adicionales. Use la dirección de correo electrónico de cualquier usuario en el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p109">Providing a sender email is optional, but forces the system to perform additional checks. Use the email address of any user in your Office 365 tenant.</span></span> 
     
    <span data-ttu-id="1f5bc-139">Los resultados deben ser similares a:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-139">Your results should be similar to:</span></span>

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - <span data-ttu-id="1f5bc-140">El nombre de su organización de Office 365 reemplazará a *contoso*.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-140">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="1f5bc-p110">Los nombres de plantilla predeterminados pueden ser diferentes de los mostrados anteriormente. Consulte [configurar y administrar plantillas para Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p110">The default template names may be different from those displayed above. See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

3. <span data-ttu-id="1f5bc-143">Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="1f5bc-144">Actualizar las reglas de flujo de correo para usar las nuevas funciones de OME</span><span class="sxs-lookup"><span data-stu-id="1f5bc-144">Update mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="1f5bc-p111">Si ya hay reglas de flujo de correo configuradas [para cifrar el correo electrónico](define-mail-flow-rules-to-encrypt-email.md) en el inquilino de Office 365, debe actualizar estas reglas existentes para usar las nuevas funciones de OME. En el caso de implementaciones nuevas, este paso no es necesario en esta fase.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p111">If there are previously configured [mail flow rules to encrypt email](define-mail-flow-rules-to-encrypt-email.md) in your Office 365 tenant, you need to update these existing rules to use the new OME capabilities. For new deployments, this step is unnecessary at this stage.</span></span>   

>[!Note]
><span data-ttu-id="1f5bc-p112">Las reglas de flujo de correo definen las condiciones en las que se cifran los mensajes de correo electrónico y cuándo debe quitarse el cifrado. Consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-p112">Mail flow rules define the conditions under which email messages are encrypted, and when encryption should be removed. See [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md) for more.</span></span>

<span data-ttu-id="1f5bc-149">Para actualizar las reglas existentes para usar las nuevas capacidades de OME:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-149">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="1f5bc-150">En el centro de administración de Office 365, vaya a **centros de administración _GT_ Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-150">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>

2. <span data-ttu-id="1f5bc-151">En el centro de administración de Exchange, vaya a **reglas de flujo de correo >**.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-151">In the Exchange admin center, go to **Mail flow > Rules**.</span></span> 
3. <span data-ttu-id="1f5bc-152">Para cada regla, en **hacer lo siguiente**:</span><span class="sxs-lookup"><span data-stu-id="1f5bc-152">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="1f5bc-153">Seleccione **modificar la seguridad de los mensajes**.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-153">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="1f5bc-154">Seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-154">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="1f5bc-155">Seleccionar una plantilla RMS de la lista</span><span class="sxs-lookup"><span data-stu-id="1f5bc-155">Select an RMS template from the list</span></span>
    - <span data-ttu-id="1f5bc-156">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-156">Select **Save**.</span></span>
    - <span data-ttu-id="1f5bc-157">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-157">Select **OK**.</span></span>
  
>[!IMPORTANT]
><span data-ttu-id="1f5bc-158">Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior, en lugar de las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="1f5bc-158">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new OME capabilities.</span></span>

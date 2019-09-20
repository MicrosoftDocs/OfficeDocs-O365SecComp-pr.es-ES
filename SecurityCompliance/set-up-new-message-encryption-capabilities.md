---
title: Configurar las nuevas capacidades de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Con las nuevas capacidades de cifrado de mensajes de Office 365 creadas con base en Azure Information Protection, su organización puede usar la comunicación por correo electrónico protegida con personas de dentro y fuera de la organización. Las nuevas funcionalidades de OME funcionan con otras organizaciones de Office 365, Outlook.com, Gmail y otros servicios de correo electrónico.
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854804"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="9685f-104">Configurar las nuevas capacidades de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="9685f-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="9685f-105">Las nuevas funcionalidades de cifrado de mensajes de Office 365 (OME) permiten que las organizaciones compartan mensajes de correo electrónico protegidos con cualquier persona en cualquier dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9685f-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="9685f-106">Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son parte de Office 365 pero que usan Outlook.com, Gmail y otros servicios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9685f-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="9685f-107">Este artículo forma parte de una gran serie de artículos sobre el cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9685f-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="9685f-108">Este artículo está destinado a administradores y profesionales de TI.</span><span class="sxs-lookup"><span data-stu-id="9685f-108">This article is intended for  IT Pros.</span></span> <span data-ttu-id="9685f-109">Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en [Cifrado de mensajes de Office 365 (OME)](ome.md) y localice el artículo que mejor se adapta a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="9685f-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="9685f-110">Siga los pasos que se indican a continuación para asegurarse de que las nuevas funcionalidades de OME estén disponibles en su organización 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="9685f-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="9685f-111">Verificar que Azure Rights Management está habilitada</span><span class="sxs-lookup"><span data-stu-id="9685f-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="9685f-112">Las nuevas funcionalidades de OME aprovechan las características de protección de [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-information-protection), la tecnología usada por [Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms) para proteger los correos electrónicos y los documentos mediante controles de acceso y encriptación.</span><span class="sxs-lookup"><span data-stu-id="9685f-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="9685f-113">El único requisito previo para usar las nuevas funcionalidades de OME es que la funcionalidad [Azure Rights Management](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms) debe estar activada en el espacio empresarial de su organización.</span><span class="sxs-lookup"><span data-stu-id="9685f-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="9685f-114">Si lo está, Office 365 activa automáticamente las nuevas funcionalidades de OME y no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="9685f-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="9685f-115">Azure RMS también se activa automáticamente en la mayoría de los planes compatibles, por lo que probablemente tampoco tendrá que hacer nada al respecto.</span><span class="sxs-lookup"><span data-stu-id="9685f-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="9685f-116">Vea [Activar Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9685f-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9685f-117">Si usa los servicios de Active Directory Rights Management (AD RMS) con Exchange Online, tendrá que [migrar a Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/migrate-from-ad-rms-to-azure-rms) antes de poder usar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="9685f-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="9685f-118">OME no es compatible con AD RMS.</span><span class="sxs-lookup"><span data-stu-id="9685f-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="9685f-119">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="9685f-119">For more information, see:</span></span>

- <span data-ttu-id="9685f-120">[¿Qué suscripciones necesito para usar las nuevas funcionalidades de OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye la funcionalidad de Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="9685f-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="9685f-121">[Azure Information Protection](https://azure.microsoft.com/es-ES/services/information-protection/) para obtener información sobre cómo comprar una suscripción apta.</span><span class="sxs-lookup"><span data-stu-id="9685f-121">[Azure Information Protection](https://azure.microsoft.com/es-ES/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="9685f-122">Activar Azure Rights Management manualmente</span><span class="sxs-lookup"><span data-stu-id="9685f-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="9685f-123">Si deshabilitó Azure RMS, o si no se activó automáticamente por algún motivo, puede activarlo manualmente en:</span><span class="sxs-lookup"><span data-stu-id="9685f-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="9685f-124">**El Centro de administración de Microsoft 365**: vea [Cómo activar Azure Rights Management desde el centro de administración](https://docs.microsoft.com/es-ES/azure/information-protection/activate-office365) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9685f-124">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/es-ES/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="9685f-125">**Azure Portal**: vea [Cómo activar Azure Rights Management desde Azure Portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9685f-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="9685f-126">Configurar la administración del espacio empresarial de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9685f-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="9685f-127">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="9685f-127">This is an optional step.</span></span> <span data-ttu-id="9685f-128">Permitir que Microsoft administre la clave raíz de Azure Information Protection es la configuración predeterminada y el procedimiento recomendado para la mayoría de los espacios empresariales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9685f-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="9685f-129">Si este es el caso, no es necesario que realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="9685f-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="9685f-130">Hay muchos motivos, por ejemplo, los requisitos de cumplimiento, que pueden requerir la creación y administración de su propia clave raíz (también conocido como Bring your own key (BYOK)).</span><span class="sxs-lookup"><span data-stu-id="9685f-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="9685f-131">Si este es el caso, le recomendamos que complete los pasos requeridos antes de configurar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="9685f-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="9685f-132">Vea [Planificar e implementar la clave de espacio empresarial de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9685f-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="9685f-133">Comprobar la nueva configuración de OME en PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9685f-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="9685f-134">Puede comprobar que su espacio empresarial de Office 365 está configurado correctamente para usar las nuevas funcionalidades de OME en [Exchange Online PowerShell](https://docs.microsoft.com/es-ES/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9685f-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="9685f-135">[Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/es-ES/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su espacio empresarial de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9685f-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/es-ES/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="9685f-136">Ejecute el cmdlet Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9685f-136">Run the Get-SPOHubSite cmdlet.</span></span>

     <span data-ttu-id="9685f-137">Debería ver un valor $True para el parámetro AzureRMSLicensingEnabled, el cuál indica que OME está configurado en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="9685f-137">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="9685f-138">Si no lo está, utilice set-IRMConfiguration para establecer el valor de AzureRMSLicensingEnabled en $True para habilitar OME.</span><span class="sxs-lookup"><span data-stu-id="9685f-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="9685f-139">Ejecute el cmdlet test-IRMConfiguration usando la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="9685f-139">Run the script by using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="9685f-140">**Ejemplo**:</span><span class="sxs-lookup"><span data-stu-id="9685f-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="9685f-141">Proporcionar un correo electrónico del remitente es opcional, pero obliga al sistema a ejecutar comprobaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="9685f-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="9685f-142">Use la dirección de correo electrónico de cualquier usuario de su espacio empresarial de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9685f-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="9685f-143">Sus resultados deben ser similares a estos:</span><span class="sxs-lookup"><span data-stu-id="9685f-143">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="9685f-144">El nombre de su organización de Office 365 reemplazará a *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="9685f-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="9685f-145">Los nombres de las plantillas predeterminadas pueden diferir de los que se muestran arriba.</span><span class="sxs-lookup"><span data-stu-id="9685f-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="9685f-146">Vea [Configurar y administrar plantillas para Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/configure-policy-templates) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9685f-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="9685f-147">Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="9685f-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="9685f-148">Pasos siguientes: defina reglas de flujo de correo para usar las nuevas funcionalidades de OME</span><span class="sxs-lookup"><span data-stu-id="9685f-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="9685f-149">Si existen reglas de flujo de correo configuradas previamente para cifrar el correo electrónico de su organización de Office 365, debe actualizar las reglas existentes para usar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="9685f-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="9685f-150">Para las nuevas implementaciones, debe crear nuevas reglas de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="9685f-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9685f-151">Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado con el formato de archivo adjunto HTML anterior, en lugar de la nueva experiencia de OME de conexión directa.</span><span class="sxs-lookup"><span data-stu-id="9685f-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="9685f-152">Las reglas de flujo de correo determinan bajo qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar ese cifrado.</span><span class="sxs-lookup"><span data-stu-id="9685f-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="9685f-153">Al establecer una acción para una regla, todos los mensajes que coinciden con las condiciones de la regla se cifran al enviarse.</span><span class="sxs-lookup"><span data-stu-id="9685f-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="9685f-154">Para conocer los pasos para crear reglas de flujo de correo para OME, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="9685f-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="9685f-155">Para actualizar las reglas existentes para poder usar las nuevas funcionalidades de OME:</span><span class="sxs-lookup"><span data-stu-id="9685f-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="9685f-156">En el centro de administración de Microsoft 365, vaya a **Centros de administración > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="9685f-156">In the Microsoft 365 admin center, in the left pane, go to **Admin centersMicrosoft Search**</span></span>
2. <span data-ttu-id="9685f-157">En el centro de administración de Exchange, vaya a **Flujo de correo > Reglas**.</span><span class="sxs-lookup"><span data-stu-id="9685f-157">In the Exchange admin center (EAC), go to Mail flow  Rules.</span></span>
3. <span data-ttu-id="9685f-158">Para cada regla, en **Hacer lo siguiente**:</span><span class="sxs-lookup"><span data-stu-id="9685f-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="9685f-159">Seleccione **Modificar la seguridad de los mensajes**.</span><span class="sxs-lookup"><span data-stu-id="9685f-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="9685f-160">Seleccione **Aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.</span><span class="sxs-lookup"><span data-stu-id="9685f-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="9685f-161">Seleccione una plantilla RMS de la lista.</span><span class="sxs-lookup"><span data-stu-id="9685f-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="9685f-162">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9685f-162">Select **Save**.</span></span>
    - <span data-ttu-id="9685f-163">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9685f-163">Select **OK**.</span></span>

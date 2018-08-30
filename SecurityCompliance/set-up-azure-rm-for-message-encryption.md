---
title: Configurar Azure Rights Management para el Cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 'Cifrado de mensajes de Office 365 depende de Microsoft Azure Rights Management (anteriormente conocido como Windows Azure Active Directory Rights Management). '
ms.openlocfilehash: 99c8de49330cf99545d28d81e0c99c2138797356
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536246"
---
# <a name="set-up-azure-rights-management-for-office-365-message-encryption"></a><span data-ttu-id="c669b-103">Configurar Azure Rights Management para el Cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="c669b-103">Set up Azure Rights Management for Office 365 Message Encryption</span></span>

<span data-ttu-id="c669b-104">En este tema se describe los pasos que debe seguir para poder activar y, a continuación, establecer la seguridad de Azure Rights Management (RMS), parte de la protección de la información de Azure, para su uso con Office 365 Message Encryption (OME).</span><span class="sxs-lookup"><span data-stu-id="c669b-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with Office 365 Message Encryption (OME).</span></span>
  
## <a name="prerequisites-for-using-office-365-message-encryption"></a><span data-ttu-id="c669b-105">Requisitos previos para usar el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="c669b-105">Prerequisites for using Office 365 Message Encryption</span></span>
<span data-ttu-id="c669b-106"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="c669b-106"></span></span>

<span data-ttu-id="c669b-p101">Office 365 Message Encryption (OME), incluidos IRM, depende de Azure Rights Management (RMS Azure). RMS Azure es la tecnología de protección usada por la protección de la información de Azure. Para usar OME, la organización de Office 365 debe incluir una suscripción a Exchange Online o Exchange Online Protection que, a su vez, incluye una suscripción de Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="c669b-p101">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS). Azure RMS is the protection technology used by Azure Information Protection. To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="c669b-110">Si no está seguro de lo que incluye su suscripción, consulte las descripciones de servicio Exchange Online para [Directiva de mensajes, recuperación y cumplimiento de normas](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span><span class="sxs-lookup"><span data-stu-id="c669b-110">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>
    
- <span data-ttu-id="c669b-111">Si no tiene una suscripción de Azure RMS para Exchange Online o Exchange Online Protection, debe adquirir una suscripción y activarlo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="c669b-111">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>
    
    <span data-ttu-id="c669b-p102">Para obtener información acerca de cómo adquirir una suscripción a Azure Rights Management, vea [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). La siguiente sección proporciona información acerca de cómo activar Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="c669b-p102">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). The next section gives you information about activating Azure Rights Management.</span></span>
    
- <span data-ttu-id="c669b-114">Si tiene Azure Rights Management, pero no se ha configurado para Exchange Online o Exchange Online Protection, este artículo explica cómo activar Azure Rights Management y, a continuación, el se describe la mejor forma de configurar OME para que funcione con Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="c669b-114">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>
    
- <span data-ttu-id="c669b-p103">Si ya ha configurado OME para que funcione con Azure Rights Management para Exchange Online o Exchange Online Protection, función de la configuración de seguridad, es posible que listo para empezar a utilizar OME y sus nuevas capacidades de inmediato. Este artículo explica cómo determinar si se ha configurado OME correctamente, qué hacer si necesita cambiar el programa de instalación y ¿qué sucede si no desea cambiar el programa de instalación. Por ejemplo, para poder usar las nuevas capacidades, debe usar RMS de Azure con OME. No puede usar las nuevas capacidades con un RMS de Active Directory local activa.</span><span class="sxs-lookup"><span data-stu-id="c669b-p103">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away. This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup. For example, in order to use the new capabilities, you must use Azure RMS with OME. You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>
    
## <a name="activate-azure-rights-management-for-ome-in-office-365"></a><span data-ttu-id="c669b-119">Activar Azure Rights Management para OME en Office 365</span><span class="sxs-lookup"><span data-stu-id="c669b-119">Activate Azure Rights Management for OME in Office 365</span></span>
<span data-ttu-id="c669b-120"><a name="activatewarm"> </a></span><span class="sxs-lookup"><span data-stu-id="c669b-120"></span></span>

<span data-ttu-id="c669b-p104">Es necesario activar Azure Rights Management para que pueden aplicar la protección de información a los mensajes que envían los usuarios de su organización y abrir los mensajes y los archivos que han sido protegidos por el servicio de administración de derechos de Azure. Para obtener instrucciones, vea [Activar Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Una vez que haya completado la activación, regrese aquí y continuar con las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="c669b-p104">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service. For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="c669b-124">Configurar OME para usar RMS de Azure mediante la importación de dominios de publicación de confianza (publicación)</span><span class="sxs-lookup"><span data-stu-id="c669b-124">Set up OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>
<span data-ttu-id="c669b-125"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c669b-125"></span></span>

<span data-ttu-id="c669b-p105">Un TPD es un archivo XML que contiene información sobre la configuración de administración de derechos de la organización. Por ejemplo, el TPD contiene información sobre el certificado de emisor de licencias de servidor (SLC) utilizado para firmar y cifrar certificados y licencias, usan para emitir licencias y publicar las direcciones URL y así sucesivamente. Importar el TPD a la organización de Office 365 con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c669b-p105">A TPD is an XML file that contains information about your organization's rights management settings. For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on. You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c669b-p106">Anteriormente, podría elegir importar la publicación desde el servicio de administración de derechos de Active Directory (AD RMS) en la organización de Office 365. Sin embargo, si lo hace, se impide utilice las nuevas capacidades OME y no se recomienda. Si su organización es actualmente de Office 365 configurada de esta forma, Microsoft recomienda que cree un plan para migrar desde su RMS de Active Directory local activa a la protección de la información basada en la nube Azure. Para obtener más información, consulte [migración de AD RMS para protección de la información de Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). No podrá usar las nuevas capacidades OME hasta que haya completado la migración de protección de la información de Azure.</span><span class="sxs-lookup"><span data-stu-id="c669b-p106">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization. However, doing so will prevent you from using the new OME capabilities and is not recommended. If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection. For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span> 
  
 <span data-ttu-id="c669b-134">**Para importar la publicación de RMS de Azure**</span><span class="sxs-lookup"><span data-stu-id="c669b-134">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="c669b-135">[Conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c669b-135">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="c669b-136">Elija la dirección URL de la clave de uso compartido que corresponde a la ubicación geográfica de su organización de Office 365:</span><span class="sxs-lookup"><span data-stu-id="c669b-136">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>
    
|<span data-ttu-id="c669b-137">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="c669b-137">**Location**</span></span>|<span data-ttu-id="c669b-138">**Clave de uso compartido de dirección URL de la ubicación**</span><span class="sxs-lookup"><span data-stu-id="c669b-138">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c669b-139">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="c669b-139">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c669b-140">Unión Europea</span><span class="sxs-lookup"><span data-stu-id="c669b-140">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c669b-141">Asia</span><span class="sxs-lookup"><span data-stu-id="c669b-141">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c669b-142">Sudamérica</span><span class="sxs-lookup"><span data-stu-id="c669b-142">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c669b-143">Office 365 Administración Pública (nube de la comunidad de administración pública)</span><span class="sxs-lookup"><span data-stu-id="c669b-143">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="c669b-144">Esta ubicación de uso compartido de claves de RMS está reservada para los clientes que han adquirido Office 365 para las SKU de gobierno.</span><span class="sxs-lookup"><span data-stu-id="c669b-144">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="c669b-145">Configure la ubicación de uso compartido de clave ejecutando el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c669b-145">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="c669b-146">Por ejemplo, para configurar la clave de ubicación de uso compartido si su organización se encuentra en América del Norte:</span><span class="sxs-lookup"><span data-stu-id="c669b-146">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="c669b-147">Ejecute el cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con el modificador - RMSOnline para importar el TPD desde Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="c669b-147">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="c669b-p107">Donde *TPDName* es el nombre que desea usar para el TPD. Por ejemplo, "Contoso norteamericanos TPD".</span><span class="sxs-lookup"><span data-stu-id="c669b-p107">Where  *TPDName*  is the name you want to use for the TPD. For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="c669b-150">Para comprobar que se haya configurado correctamente su organización de Office 365 para usar el servicio de administración de derechos de Azure, ejecute el cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con el modificador - RMSOnline como sigue:</span><span class="sxs-lookup"><span data-stu-id="c669b-150">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="c669b-151">Entre otras cosas, este cmdlet comprueba la conectividad con el servicio de administración de derechos de Azure, descarga el TPD y comprueba su validez.</span><span class="sxs-lookup"><span data-stu-id="c669b-151">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="c669b-152">Ejecute el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) como se indica a continuación para deshabilitar las plantillas de Azure Rights Management esté disponible en Outlook en la web y de Outlook:</span><span class="sxs-lookup"><span data-stu-id="c669b-152">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="c669b-153">Ejecute el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) como se indica a continuación para habilitar Azure Rights Management para la organización de correo electrónico basada en la nube y configurarlo para usar Azure Rights Management Office 365 para cifrado de mensajes:</span><span class="sxs-lookup"><span data-stu-id="c669b-153">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="c669b-p108">Para comprobar que ha importado el TPD y habilitado Azure Rights Management, use el cmdlet Test-IRMConfiguration para probar la funcionalidad de Azure Rights Management. Para obtener información detallada, vea "Ejemplo 1" en [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c669b-p108">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="c669b-156">Tengo OME configurado con Active Directory Rights Management no protección de información de Azure, ¿qué puedo hacer?</span><span class="sxs-lookup"><span data-stu-id="c669b-156">I have OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="c669b-157"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c669b-157"></span></span>

<span data-ttu-id="c669b-p109">Puede continuar usar las reglas de flujo de correo de cifrado de mensajes de Office 365 existentes con Active Directory Rights Management, pero no se puede configurar o usar las nuevas capacidades OME. En su lugar, debe migrar a la protección de la información de Azure. Para obtener información sobre la migración y lo que significa para su organización, consulte [migración de AD RMS para protección de la información de Azure](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span><span class="sxs-lookup"><span data-stu-id="c669b-p109">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities. Instead, you need to migrate to Azure Information Protection. For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c669b-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c669b-161">Next steps</span></span>
<span data-ttu-id="c669b-162"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c669b-162"></span></span>

<span data-ttu-id="c669b-163">Una vez que haya completado el programa de instalación de Azure Rights Management, si desea habilitar las nuevas capacidades OME, vea [Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="c669b-163">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="c669b-164">Después de que ha configurado la organización para usar las nuevas capacidades OME, estará listo para [definir las reglas de flujo de correo para proteger los mensajes de correo electrónico con nuevas capacidades OME](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="c669b-164">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c669b-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c669b-165">Related topics</span></span>
<span data-ttu-id="c669b-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c669b-166"></span></span>

[<span data-ttu-id="c669b-167">Cifrado en Office 365</span><span class="sxs-lookup"><span data-stu-id="c669b-167">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="c669b-168">Información de referencia técnica sobre el cifrado en Office 365</span><span class="sxs-lookup"><span data-stu-id="c669b-168">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="c669b-169">¿Qué es Azure Rights Management?</span><span class="sxs-lookup"><span data-stu-id="c669b-169">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  


---
title: Establecer seguridad Mobile Device Management (MDM) en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: La administración de dispositivos móviles integrada para Office 365 le ayuda a proteger y administrar los dispositivos móviles como iPhone, iPad, Androids, los usuarios y teléfonos de Windows. Para empezar, siga estos pasos para activar y configurar la administración de dispositivos móviles para Office 365.
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272365"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a><span data-ttu-id="1da04-104">Establecer seguridad Mobile Device Management (MDM) en Office 365</span><span class="sxs-lookup"><span data-stu-id="1da04-104">Set up Mobile Device Management (MDM) in Office 365</span></span>

<span data-ttu-id="1da04-p102">La integrada Mobile Device Management (MDM) para Office 365 le ayuda a proteger y administrar los dispositivos móviles como iPhone, iPad, Androids, los usuarios y teléfonos de Windows. Puede crear y administrar las directivas de seguridad de dispositivo, remotamente borrar un dispositivo y ver los informes de detallada de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1da04-p102">The built-in Mobile Device Management (MDM) for Office 365 helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones. You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>
  
<span data-ttu-id="1da04-p103">¿Tiene preguntas? Hemos recopilado [una preguntas más frecuentes para ayudar a las preguntas más frecuentes de dirección](frequently-asked-questions-about-mdm.md). Tenga en cuenta que no se puede usar un [socios: administración delegada de oferta](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) para administrar la administración de dispositivos móviles para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1da04-p103">Have questions? We've put together [a FAQ to help address common questions](frequently-asked-questions-about-mdm.md). Be aware that you cannot use a [Partners: Offer delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) to manage Mobile Device Management for Office 365.</span></span> 
  
<span data-ttu-id="1da04-110">Administración de dispositivos es parte de la seguridad &amp; centro de cumplimiento, por lo que tendrá que ir allí para iniciar el programa de instalación MDM.</span><span class="sxs-lookup"><span data-stu-id="1da04-110">Device management is part of the Security &amp; Compliance Center so you'll need to go there to kick off MDM setup.</span></span>
  
<span data-ttu-id="1da04-111">Para configurar la administración de dispositivos móviles para Office 365 necesitará para:</span><span class="sxs-lookup"><span data-stu-id="1da04-111">To set up Mobile Device Management for Office 365 you'll need to:</span></span>
  
1. [<span data-ttu-id="1da04-112">Activar el servicio de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1da04-112">Activate the Mobile Device Management service</span></span>](#activate-the-mobile-device-management-service)  
2. [<span data-ttu-id="1da04-113">Configurar la administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1da04-113">Set up Mobile Device Management</span></span>](#set-up-mobile-device-management)
3. [<span data-ttu-id="1da04-114">Asegúrese de que los usuarios inscribirse sus dispositivos</span><span class="sxs-lookup"><span data-stu-id="1da04-114">Make sure users enroll their devices</span></span>](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a><span data-ttu-id="1da04-115">Activar el servicio de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1da04-115">Activate the Mobile Device Management service</span></span>

1. <span data-ttu-id="1da04-116">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="1da04-116">Sign in to Office 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="1da04-117">Vaya a [seguridad &amp; centro de cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="1da04-117">Go to [Security &amp; Compliance Center](https://protection.office.com).</span></span>
    
3. <span data-ttu-id="1da04-118">Navegue a la **prevención de pérdida de datos** \> **administración de dispositivos** y haga clic en **vamos a empezar** a iniciar el proceso de activación.</span><span class="sxs-lookup"><span data-stu-id="1da04-118">Navigate to **Data loss prevention** \> **Device management** and click **Let's get started** to kick off the activation process.</span></span> 
    
    ![Configuración de administración de dispositivos móviles para Office 365](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. <span data-ttu-id="1da04-p104">Hemos creado una directiva de seguridad predeterminada para ayudarle a empezar a trabajar. Actualizar el nombre de la directiva de seguridad en esta página y, a continuación, haga clic en **iniciar el programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="1da04-p104">We created a default security policy for you to help you get started. Update the name of the security policy on this page, and then click **Start setup**.</span></span>
    
    ![Establecer la directiva de seguridad de administración de dispositivos móviles](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. <span data-ttu-id="1da04-123">Verá la pantalla del programa de instalación que muestra el progreso de la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="1da04-123">You'll see the setup screen that shows progress on setting up the service.</span></span>
    
    ![Progreso de la instalación MDM](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> <span data-ttu-id="1da04-p105">También puede localizar **El programa de instalación de MDM** a través de la búsqueda. En el centro de administración de Office 365 \> página **principal** , administración de dispositivos móviles de tipo en el cuadro de **búsqueda** . > ![Búsqueda para administración de dispositivos móviles en el centro de administración](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)</span><span class="sxs-lookup"><span data-stu-id="1da04-p105">You can also locate **MDM Setup** through Search. In the Office 365 admin center \> **Home** page, type mobile device management in the **Search** box. > ![Search for mobile device management in the admin center](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)</span></span>
  
<span data-ttu-id="1da04-128">Puede tardar un poco para activar la administración de dispositivos móviles para Office 365, pero cuando termine, recibirá un correo electrónico que se explica los pasos que deben seguirse siguiente.</span><span class="sxs-lookup"><span data-stu-id="1da04-128">It can take some time to activate Mobile Device Management for Office 365, but when it finishes, you'll receive an email that explains the next steps to take.</span></span>
  
## <a name="set-up-mobile-device-management"></a><span data-ttu-id="1da04-129">Configurar la administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1da04-129">Set up Mobile Device Management</span></span>

<span data-ttu-id="1da04-p106">Cuando el servicio está listo, complete los siguientes cuatro pasos para finalizar la instalación. Es posible que necesite haga clic en [Administrar la configuración](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx) en la página de **administración de dispositivos** en la seguridad &amp; centro de cumplimiento para ver los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="1da04-p106">When the service is ready, complete the following four steps to finish setup. You may need to click [Manage settings](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx) on the **Device management** page in the Security &amp; Compliance Center to see the following settings.</span></span> 
  
![Configurar la administración de dispositivos móviles pasos necesarios y recomendados](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="1da04-133">Paso 1: Dominios configurar (obligatorio) para MDM</span><span class="sxs-lookup"><span data-stu-id="1da04-133">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="1da04-p107">Si no dispone de un dominio personalizado asociado con Office 365, o si no administra los dispositivos de Windows, puede omitir esta sección. De lo contrario, necesitará agregar registros DNS para el dominio en el host de DNS. Si ha agregado los registros ya, como parte de la configuración de su dominio con Office 365, está listo. Después de agregar los registros, se redirigen los usuarios de Office 365 en su organización que iniciar sesión en sus dispositivos de Windows con una dirección de correo electrónico que usa su dominio personalizado para inscribirse en MDM para Office 365.</span><span class="sxs-lookup"><span data-stu-id="1da04-p107">If you don't have a custom domain associated with Office 365 or if you're not managing Windows devices, you can skip this section. Otherwise, you'll need to add DNS records for the domain at your DNS host. If you've added the records already, as part of setting up your domain with Office 365, you're all set. After you add the records, Office 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in MDM for Office 365.</span></span>
  
<span data-ttu-id="1da04-p108">¿Necesita ayuda para configurar los registros? Busque al registrador de dominios en la lista proporcionada en [crear registros DNS para Office 365 al administrar sus registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) y seleccione el nombre de registrador para ir a ayuda paso a paso para la creación de registros DNS. Use las instrucciones para agregar los dos registros siguientes:</span><span class="sxs-lookup"><span data-stu-id="1da04-p108">Need help setting up the records? Find your domain registrar in the list provided in [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) and select the registrar name to go to step-by-step help for creating DNS records. Use those instructions to add the following two records:</span></span> 
  
|<span data-ttu-id="1da04-141">**Nombre de host**</span><span class="sxs-lookup"><span data-stu-id="1da04-141">**Host name**</span></span>|<span data-ttu-id="1da04-142">**Tipo de registro**</span><span class="sxs-lookup"><span data-stu-id="1da04-142">**Record type**</span></span>|<span data-ttu-id="1da04-143">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="1da04-143">**Address**</span></span>|<span data-ttu-id="1da04-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1da04-144">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1da04-145">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="1da04-145">EnterpriseEnrollment</span></span>  <br/> |<span data-ttu-id="1da04-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="1da04-146">CNAME</span></span>  <br/> |<span data-ttu-id="1da04-147">EnterpriseEnrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1da04-147">EnterpriseEnrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="1da04-148">3600</span><span class="sxs-lookup"><span data-stu-id="1da04-148">3600</span></span>  <br/> |
|<span data-ttu-id="1da04-149">EnterpriseRegistration</span><span class="sxs-lookup"><span data-stu-id="1da04-149">EnterpriseRegistration</span></span>  <br/> |<span data-ttu-id="1da04-150">CNAME</span><span class="sxs-lookup"><span data-stu-id="1da04-150">CNAME</span></span>  <br/> |<span data-ttu-id="1da04-151">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1da04-151">EnterpriseRegistration.windows.net</span></span>  <br/> |<span data-ttu-id="1da04-152">3600</span><span class="sxs-lookup"><span data-stu-id="1da04-152">3600</span></span>  <br/> |
   
<span data-ttu-id="1da04-153">Después de agregar los dos registros, vuelva a la seguridad &amp; centro de cumplimiento y navegue a **administración de dispositivos** \> **Administrar la configuración** para llevar a cabo el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="1da04-153">After you add the two records, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="1da04-154">Paso 2: (Obligatorio) Configure un certificado APN para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="1da04-154">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="1da04-155">Para administrar dispositivos iOS como iPad e iPhone, debe crear un certificado APN.</span><span class="sxs-lookup"><span data-stu-id="1da04-155">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>
  
<span data-ttu-id="1da04-156">Para ello, siga los pasos de los vínculos de **Configurar** en la **página de administración de dispositivo móvil del programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="1da04-156">To do this, follow the steps from the **Set up** links on the **Setup mobile device management page**.</span></span>
  
1. <span data-ttu-id="1da04-157">Junto a **configurar un certificado APN para dispositivos iOS**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="1da04-157">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="1da04-158">Seleccione **descargar el archivo CSR** y guarde la solicitud de firma de certificado a en algún lugar en el equipo que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="1da04-158">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![Instalar el cuadro de diálogo certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="1da04-160">Seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1da04-160">Select **Next**.</span></span>
    
4. <span data-ttu-id="1da04-161">Cree un certificado APN.</span><span class="sxs-lookup"><span data-stu-id="1da04-161">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="1da04-162">Seleccione **Apple APN Portal** para abrir el Portal de certificados de inserción de Apple.</span><span class="sxs-lookup"><span data-stu-id="1da04-162">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![Instalar el cuadro de diálogo de notificación APN cert con Apple APN Portal seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="1da04-164">Iniciar sesión con un identificador de Apple.</span><span class="sxs-lookup"><span data-stu-id="1da04-164">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1da04-p109">Use una compañía que Apple identificador asociado con una cuenta de correo electrónico que permanecerá con la organización, incluso si sale el usuario que administra la cuenta. Guarde este identificador porque debe usar el mismo identificador cuando es el momento de renovar el certificado.</span><span class="sxs-lookup"><span data-stu-id="1da04-p109">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="1da04-167">Seleccione **crear un certificado** y acepte los **Términos de uso**.</span><span class="sxs-lookup"><span data-stu-id="1da04-167">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="1da04-168">**Vaya** a la solicitud de firma de certificado descargado en el equipo de Office 365 y seleccione **cargar**.</span><span class="sxs-lookup"><span data-stu-id="1da04-168">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="1da04-169">**Descargar** el certificado APN creado por el Portal del certificado de inserción de Apple en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1da04-169">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="1da04-170">Si tiene problemas para descargar el certificado, actualice el explorador.</span><span class="sxs-lookup"><span data-stu-id="1da04-170">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="1da04-171">Vuelva a Office 365 y seleccione **siguiente** para ir a la página **cargar APN certificado** .</span><span class="sxs-lookup"><span data-stu-id="1da04-171">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="1da04-172">Busque el certificado APN que ha descargado desde el Portal de certificados de inserción de Apple.</span><span class="sxs-lookup"><span data-stu-id="1da04-172">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![Haga clic en el botón Examinar para seleccionar cert APN que descargó de Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="1da04-174">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1da04-174">Select **Finish**.</span></span>
    
<span data-ttu-id="1da04-175">Después de agregar APN certificado, vuelva a la seguridad &amp; centro de cumplimiento y navegue a **administración de dispositivos** \> **Administrar la configuración** para llevar a cabo el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="1da04-175">After you add APN Certificate, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="1da04-176">Paso 3: (Recomendado) configurar la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="1da04-176">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="1da04-p110">Si no ve la autenticación multifactor (MFA) en **los pasos recomendados**, puede omitir esta sección. Si esta opción está en la lista, se recomienda que activar MFA en el portal de Azure AD para aumentar la seguridad de la administración de dispositivos móviles para el proceso de inscripción de Office 365. Está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1da04-p110">If you don't see multi-factor authentication (MFA) under **Recommended steps**, you can skip this section. If this option is listed, we recommend you turn on MFA in the Azure AD portal to increase the security of the Mobile Device Management for Office 365 enrollment process. It is turned off by default.</span></span>
  
<span data-ttu-id="1da04-p111">MFA ayuda a proteger el iniciar sesión en Office 365 para inscripción del dispositivo móvil al requerir un segundo formulario de autenticación. Los usuarios son necesarios para confirmar una llamada telefónica, el mensaje de texto o la notificación de la aplicación en su dispositivo móvil después de escribir correctamente su contraseña de la cuenta de trabajo. Sólo puede inscribirse su dispositivo una vez finalizada esta segunda forma de autenticación. Después de que los dispositivos de los usuarios se inscriben en administración de dispositivos móviles para Office 365, los usuarios pueden tener acceso a los recursos de Office 365 con su cuenta del trabajo.</span><span class="sxs-lookup"><span data-stu-id="1da04-p111">MFA helps secure the sign in to Office 365 for mobile device enrollment by requiring a second form of authentication. Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password. They can only enroll their device after this second form of authentication is completed. After users' devices are enrolled in Mobile Device Management for Office 365, users can access Office 365 resources with just their work account.</span></span>
  
<span data-ttu-id="1da04-p112">Junto a **Configurar la autenticación multifactor**, seleccione **Configurar**. Para obtener información sobre cómo activar MFA en el portal de Azure AD, vea [Configurar la autenticación multifactor](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span><span class="sxs-lookup"><span data-stu-id="1da04-p112">Next to **Set up multi-factor authentication**, select **Set up**. To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>
  
<span data-ttu-id="1da04-186">Una vez configurado MFA, vuelva a la seguridad &amp; centro de cumplimiento y navegue a **administración de dispositivos** \> **Administrar la configuración** para llevar a cabo el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="1da04-186">After you set up MFA, go back to the Security &amp; Compliance Center and navigate to **Device management** \> **Manage settings** to complete the next step.</span></span> 
  
### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="1da04-187">Paso 4: Las directivas de seguridad de dispositivo administrar (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1da04-187">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="1da04-p113">El siguiente paso es crear e implementar directivas de seguridad de dispositivo para ayudar a proteger los datos de su organización de Office 365. Por ejemplo, puede ayudar a evitar la pérdida de datos si un usuario pierde su dispositivo mediante la creación de una directiva en los dispositivos de bloqueo después de 5 minutos de inactividad y tienen dispositivos limpiar después de errores de inicio de sesión 3.</span><span class="sxs-lookup"><span data-stu-id="1da04-p113">The next step is to create and deploy device security policies to help protect your Office 365 organization's data. For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after 5 minutes of inactivity and have devices wiped after 3 sign-in failures.</span></span>
  
<span data-ttu-id="1da04-190">En la **seguridad &amp; centro de cumplimiento**, vaya a **las directivas de seguridad** \> **las directivas de seguridad de dispositivo** para crear directivas de seguridad de dispositivo y las reglas de acceso.</span><span class="sxs-lookup"><span data-stu-id="1da04-190">In the **Security &amp; Compliance Center**, go to **Security policies** \> **Device security policies** to create device security policies and access rules.</span></span> 
  
![Agregar una directiva de seguridad de dispositivo](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
<span data-ttu-id="1da04-192">Para obtener instrucciones paso a paso acerca de cómo crear una nueva directiva, consulte [crear e implementar directivas de seguridad de dispositivo](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1da04-192">For step by step instructions on how to create a new policy, see [Create and deploy device security policies](create-device-security-policies.md).</span></span>
  
> [!TIP]
>  <span data-ttu-id="1da04-p114">Cuando se crea una nueva directiva, es posible que desee establecer la directiva para permitir infracción de directiva de acceso y el informe donde el dispositivo del usuario no es compatible con la directiva. Esto le permite ver cuántos dispositivos móviles se verá afectados por la directiva sin bloquear el acceso a Office 365. > Antes de implementar una nueva directiva a todos los usuarios de la organización, se recomienda que probarla en los dispositivos utilizados por un número reducido de usuarios. > También, antes de implementar las directivas, informar a su organización los impactos potenciales de inscripción de un dispositivo en MDM para Office 365. Dependiendo de cómo configurar las directivas, los dispositivos que no cumplen con ellos (que no son compatibles con dispositivos) podrían ser bloqueados el acceso a Office 365. También es posible que tienen dispositivos que no son compatibles con apps instaladas, fotografías y otra información personal que, en un dispositivo inscrito, puede eliminarse si se borra el dispositivo. Más información: [Borrar un dispositivo móvil en Office 365](wipe-a-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="1da04-p114">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user's device isn't compliant with the policy. This lets you see how many mobile devices would be impacted by the policy without blocking access to Office 365. >  Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users. >  Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in MDM for Office 365. Depending on how you set up the policies, devices that don't comply with them (non-compliant devices) could be blocked from accessing Office 365. Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped. More info: [Wipe a mobile device in Office 365](wipe-a-mobile-device.md).</span></span> 
  
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="1da04-200">Asegúrese de que los usuarios inscribirse sus dispositivos</span><span class="sxs-lookup"><span data-stu-id="1da04-200">Make sure users enroll their devices</span></span>

<span data-ttu-id="1da04-p115">Una vez que ha creado e implementado una directiva de administración de dispositivos móviles, cada usuario de Office 365 con licencia de la organización que se aplica la directiva de dispositivo recibirá un mensaje de inscripción la próxima vez que inicie sesión en Office 365 desde su dispositivo móvil. Deben completar los pasos de inscripción y activación antes de tener acceso a documentos y correo electrónico de Office 365. Vea [su dispositivo móvil para el trabajo o escuela de inscripción](enroll-your-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="1da04-p115">After you've created and deployed a mobile device management policy, each licensed Office 365 user in your organization that the device policy applies to will receive an enrollment message the next time they sign into Office 365 from their mobile device. They must complete the enrollment and activation steps before they can access Office 365 email and documents. See [Enroll your mobile device for work or school](enroll-your-mobile-device.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1da04-p116">Si el idioma preferido del usuario no es compatible con el proceso de inscripción, los usuarios pueden recibir notificación de inscripción y los pasos en sus dispositivos móviles en otro idioma. No todos los idiomas compatibles con Office 365 se admiten actualmente para el proceso de inscripción en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="1da04-p116">If a user's preferred language isn't supported by the enrollment process, users may receive enrollment notification and steps on their mobile devices in another language. Not all languages supported in Office 365 are currently supported for the enrollment process on mobile devices.</span></span> 
  
<span data-ttu-id="1da04-206">Los usuarios con dispositivos Android o iOS son necesarios para instalar la aplicación de Portal de la compañía como parte del proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="1da04-206">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1da04-207">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1da04-207">Related Topics</span></span>

[<span data-ttu-id="1da04-208">Capacidades de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1da04-208">Capabilities of Mobile Device Management</span></span>](capabilities-of-mobile-device-management.md)
  
[<span data-ttu-id="1da04-209">Crear e implementar directivas de seguridad de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1da04-209">Create and deploy device security policies</span></span>](create-device-security-policies.md)
  


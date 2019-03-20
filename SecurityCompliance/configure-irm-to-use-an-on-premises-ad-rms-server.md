---
title: Configurar IRM para usar un servidor de AD RMS local
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: En este tema se muestra cómo configurar IRM para usar un servidor de AD RMS.
ms.openlocfilehash: 1da66c5afa37c96c061a4bf25c0858e4e71e2313
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693039"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="0c731-103">Configurar IRM para usar un servidor de AD RMS local</span><span class="sxs-lookup"><span data-stu-id="0c731-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="0c731-104">Para su uso con implementaciones locales, Information Rights Management (IRM) en Exchange online usa Active Directory Rights Management Services (AD RMS), una tecnología de protección de la información en Windows Server 2008 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0c731-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="0c731-105">La protección de IRM se implanta en el correo electrónico mediante la aplicación de una plantilla de directiva de permisos de AD RMS a un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0c731-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="0c731-106">Los derechos se adjuntan al propio mensaje para que la protección se produzca en línea o sin conexión, y dentro y fuera del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="0c731-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="0c731-107">En este tema se muestra cómo configurar IRM para usar un servidor de AD RMS.</span><span class="sxs-lookup"><span data-stu-id="0c731-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="0c731-108">Para obtener información acerca del uso de las nuevas funciones de cifrado de mensajes de Office 365 con Azure Active Directory y Azure Rights Management, consulte las [preguntas más frecuentes sobre el cifrado de mensajes de office 365](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span><span class="sxs-lookup"><span data-stu-id="0c731-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span></span>
  
<span data-ttu-id="0c731-109">Para obtener más información sobre IRM en Exchange Online, consulte [Information Rights Management en Exchange Online](information-rights-management-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="0c731-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c731-110">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="0c731-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="0c731-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="0c731-111"></span></span>

- <span data-ttu-id="0c731-112">Tiempo estimado para finalizar esta tarea: 30 minutos</span><span class="sxs-lookup"><span data-stu-id="0c731-112">Estimated time to complete this task: 30 minutes</span></span>
    
- <span data-ttu-id="0c731-p103">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Information Rights Management" en el tema [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="0c731-p104">El servidor AD RMS debe estar ejecutando Windows Server 2008 o posterior. Para obtener información detallada sobre cómo implementar AD RMS, vea [Instalación de un clúster de AD RMS](https://go.microsoft.com/fwlink/?LinkId=210873).</span><span class="sxs-lookup"><span data-stu-id="0c731-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](https://go.microsoft.com/fwlink/?LinkId=210873).</span></span>
    
- <span data-ttu-id="0c731-117">Para obtener información detallada sobre cómo instalar y configurar Windows PowerShell y conectarlo al servicio, vea [Conectarse a Exchange Online mediante PowerShell remoto](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-117">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="0c731-118">Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="0c731-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="0c731-p105">¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="0c731-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="0c731-122">¿Cómo debe hacer esto?</span><span class="sxs-lookup"><span data-stu-id="0c731-122">How do you do this?</span></span>
<span data-ttu-id="0c731-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="0c731-123"></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="0c731-124">Paso 1: Use la consola AD RMS para exportar un dominio de publicación de confianza (TPD) desde un servidor AD RMS</span><span class="sxs-lookup"><span data-stu-id="0c731-124">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="0c731-p106">El primer paso es exportar un dominio de publicación de confianza (TPD) del servidor local AD RMS a un archivo XML. El dominio de publicación de confianza contiene las siguientes opciones de configuración que se necesitan para usar características RMS:</span><span class="sxs-lookup"><span data-stu-id="0c731-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span> 
  
- <span data-ttu-id="0c731-127">El certificado emisor de licencias de servidor (SLC) utilizado para firmar y cifrar certificados y licencias</span><span class="sxs-lookup"><span data-stu-id="0c731-127">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>
    
- <span data-ttu-id="0c731-128">Las direcciones URL utilizadas para emitir licencias y publicar</span><span class="sxs-lookup"><span data-stu-id="0c731-128">The URLs used for licensing and publishing</span></span>
    
- <span data-ttu-id="0c731-129">Las plantillas de directiva de permisos de AD RMS que se crearon con el certificado emisor de licencias de servidor específico para ese dominio de publicación de confianza</span><span class="sxs-lookup"><span data-stu-id="0c731-129">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>
    
<span data-ttu-id="0c731-130">Al importar el dominio de publicación de confianza, se almacena y se protege en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c731-130">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="0c731-131">Abra la consola de Active Directory Rights Management Services y, a continuación, expanda el clúster AD RMS.</span><span class="sxs-lookup"><span data-stu-id="0c731-131">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>
    
2. <span data-ttu-id="0c731-132">En el árbol de consola, expanda **Directivas de confianza** y, a continuación, haga clic en **Dominios de publicación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="0c731-132">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>
    
3. <span data-ttu-id="0c731-133">En el panel de resultados, seleccione el certificado para el dominio que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="0c731-133">In the results pane, select the certificate for the domain you want to export.</span></span>
    
4. <span data-ttu-id="0c731-134">En el panel **Acciones**, haga clic en **Exportar dominio de publicación de confianza**.</span><span class="sxs-lookup"><span data-stu-id="0c731-134">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>
    
5. <span data-ttu-id="0c731-p107">En el cuadro **Archivo de dominio de publicación**, haga clic en **Guardar como** para guardar el archivo en una ubicación concreta del equipo local. Escriba un nombre de archivo, asegúrese de especificar la extensión de nombre de archivo  `.xml` y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0c731-p107">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer. Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>
    
6. <span data-ttu-id="0c731-p108">En los cuadros **Contraseña** y **Confirmar contraseña**, escriba una contraseña segura que se va a usar para cifrar el archivo de dominio de publicación de confianza. Tendrá que especificar esta contraseña al importar el dominio de publicación de confianza a su organización de correo electrónico basada en nube.</span><span class="sxs-lookup"><span data-stu-id="0c731-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="0c731-139">Paso 2: use el Shell de administración de Exchange para importar el dominio de publicación de confianza a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0c731-139">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="0c731-p109">Una vez exportado el dominio de publicación de confianza a un archivo XML, tiene que importarlo a Exchange Online. Cuando se importa el dominio de publicación de confianza, también se importan las plantillas AD RMS. Cuando se importa el primer dominio de publicación de confianza, se convierte en el dominio de publicación de confianza predeterminado para su organización basada en nube. Si importa otro TPD, puede utilizar el parámetro **Predeterminado** para convertirlo en el TPD predeterminado disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c731-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="0c731-144">Para importar el TPD, ejecute el comando siguiente en Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c731-144">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="0c731-p110">Puede obtener los valores para los parámetros  _ExtranetLicensingUrl_ e  _IntranetLicensingUrl_ en la consola de Active Directory Rights Management Services. Seleccione el clúster AD RMS en el árbol de consola. Las direcciones URL de emisión de licencias aparecen en el panel de resultados. Los clientes de correo electrónico utilizan estas direcciones URL cuando el contenido tiene que ser descifrado y cuando Exchange Online necesita determinar qué dominio de publicación de confianza utilizar.</span><span class="sxs-lookup"><span data-stu-id="0c731-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span> 
  
<span data-ttu-id="0c731-p111">Al ejecutar este comando, se solicita una contraseña. Escriba la contraseña que especificó cuando exportó el TPD desde su servidor AD RMS.</span><span class="sxs-lookup"><span data-stu-id="0c731-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="0c731-p112">Por ejemplo, el siguiente comando importa el dominio de publicación de confianza, denominado Exported TPD, utilizando el archivo XML que exportó desde su servidor AD RMS y guardó en el escritorio de la cuenta de Administrador. El parámetro Name se utiliza para especificar un nombre para el dominio de publicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="0c731-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="0c731-153">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-153">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="0c731-154">¿Cómo sabe si este paso funcionó?</span><span class="sxs-lookup"><span data-stu-id="0c731-154">How do you know this step worked?</span></span>

<span data-ttu-id="0c731-p113">Para comprobar que el dominio de publicación de confianza se haya importado correctamente, ejecute el cmdlet **Get-RMSTrustedPublishingDomain** para recuperar los dominios de publicación de confianza de su organización de Exchange Online. Para obtener detalles, consulte los ejemplos en [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-p113">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="0c731-157">Paso 3: use el Shell de administración de Exchange para distribuir una plantilla de directiva de permisos AD RMS</span><span class="sxs-lookup"><span data-stu-id="0c731-157">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="0c731-158">Después de importar el dominio de publicación de confianza, debe asegurarse de que la plantilla de directiva de permisos AD RMS esté distribuida.</span><span class="sxs-lookup"><span data-stu-id="0c731-158">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="0c731-159">Una plantilla distribuida es visible para los usuarios de Outlook en la web (anteriormente conocido como Outlook Web App), que a su vez pueden aplicar las plantillas a un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0c731-159">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="0c731-160">Para obtener una lista de todas las plantillas que incluye el TPD predeterminado, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c731-160">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="0c731-161">Si el valor del parámetro  _Type_ es  `Archived`, la plantilla no está visible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0c731-161">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="0c731-162">Solo las plantillas distribuidas en el TPD predeterminado están disponibles en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="0c731-162">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>
  
<span data-ttu-id="0c731-163">Para distribuir una plantilla, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c731-163">To distribute a template, run the following command:</span></span>
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="0c731-164">Por ejemplo, el siguiente comando importa la plantilla Company Confidential.</span><span class="sxs-lookup"><span data-stu-id="0c731-164">For example, the following command imports the Company Confidential template.</span></span>
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="0c731-165">Para obtener más información acerca de la sintaxis y los parámetros, consulte [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) y [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-165">For detailed syntax and parameter information, see [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) and [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span></span>
  
 <span data-ttu-id="0c731-166">**Plantilla No reenviar**</span><span class="sxs-lookup"><span data-stu-id="0c731-166">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="0c731-p116">Cuando importa el dominio de publicación de confianza predeterminado desde la organización local en Exchange Online, se importa una plantilla de directiva de permisos AD RMS denominada **No reenviar**. De manera predeterminada, esta plantilla se distribuye al importar el dominio de publicación de confianza predeterminado. No puede usar el cmdlet **Set-RMSTemplate** para modificar la plantilla **No reenviar**.</span><span class="sxs-lookup"><span data-stu-id="0c731-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="0c731-p117">Cuando se aplica la plantilla **No reenviar** a un mensaje, solo los destinatarios del mensaje pueden leerlo. Además, los destinatarios no pueden hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c731-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span> 
  
- <span data-ttu-id="0c731-172">Reenviar el mensaje a otra persona.</span><span class="sxs-lookup"><span data-stu-id="0c731-172">Forward the message to another person.</span></span>
    
- <span data-ttu-id="0c731-173">Copiar el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c731-173">Copy content from the message.</span></span>
    
- <span data-ttu-id="0c731-174">Imprimir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c731-174">Print the message.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="0c731-175">La plantilla **No reenviar** no puede evitar que la información de un mensaje se copie con programas de captura de pantalla de otros fabricantes, con cámaras o que los usuarios transcriban la información manualmente.</span><span class="sxs-lookup"><span data-stu-id="0c731-175">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="0c731-p118">Puede crear plantillas de directiva de permisos AD RMS adicionales en el servidor de AD RMS de la organización local a fin de cumplir con los requisitos de protección de IRM. Si crea plantillas de directiva de permisos AD RMS adicionales, tiene que exportar de nuevo el dominio de publicación de confianza desde el servidor local AD RMS y actualizarlo en la organización de correo electrónico basada en nube.</span><span class="sxs-lookup"><span data-stu-id="0c731-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span> 
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="0c731-178">¿Cómo sabe si este paso funcionó?</span><span class="sxs-lookup"><span data-stu-id="0c731-178">How do you know this step worked?</span></span>

<span data-ttu-id="0c731-p119">Para comprobar que una plantilla de directiva de permisos AD RMS se distribuyó correctamente, ejecute el cmdlet **Get-RMSTemplate** para comprobar las propiedades de la plantilla. Para obtener detalles, consulte los ejemplos en [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-p119">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="0c731-181">Paso 4: use el Shell de administración de Exchange para habilitar IRM</span><span class="sxs-lookup"><span data-stu-id="0c731-181">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="0c731-182">Después de importar el dominio de publicación de confianza y distribuir una plantilla de directiva de permisos AD RMS, ejecute el siguiente comando para habilitar IRM para la organización de correo electrónico basada en nube.</span><span class="sxs-lookup"><span data-stu-id="0c731-182">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="0c731-183">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-183">For detailed syntax and parameter information, see [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="0c731-184">¿Cómo sabe si este paso funcionó?</span><span class="sxs-lookup"><span data-stu-id="0c731-184">How do you know this step worked?</span></span>

<span data-ttu-id="0c731-185">Para comprobar que IRM se haya habilitado correctamente, ejecute el cmdlet [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) para comprobar la configuración de IRM en la organización de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c731-185">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet to check IRM configuration in the Exchange Online organization.</span></span> 
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="0c731-186">¿Cómo sabe si esta tarea funcionó?</span><span class="sxs-lookup"><span data-stu-id="0c731-186">How do you know this task worked?</span></span>
<span data-ttu-id="0c731-187"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="0c731-187"></span></span>

<span data-ttu-id="0c731-188">Para comprobar si ha importado el TPD y ha habilitado IRM correctamente, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c731-188">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="0c731-p120">Use el cmdlet **Test-IRMConfiguration** para probar si IRM funciona. Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c731-p120">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality. For details, see "Example 1" in [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span></span>
    
- <span data-ttu-id="0c731-191">Redacte un nuevo mensaje en Outlook en la web y protéjalo con IRM seleccionando la opción **establecer permisos** en el menú extendido ( ![icono](media/ITPro-EAC-MoreOptionsIcon.gif)más opciones).</span><span class="sxs-lookup"><span data-stu-id="0c731-191">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
    


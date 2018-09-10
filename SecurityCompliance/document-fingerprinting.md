---
title: Creación de huella digital de documento
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: Trabajadores de la información de la organización controlan muchos tipos de información confidencial durante un día normal. Creación de huella digital de documento facilita proteger esta información mediante la identificación de los formularios estándar que se usan en toda la organización. En este tema se describe los conceptos de las huellas digitales de documento y cómo crear uno mediante el uso de PowerShell.
ms.openlocfilehash: d73b769e7a014f2642a0fcd66cc6a500c68c46c3
ms.sourcegitcommit: 4be502d1fc6cbaef4c72d599758d51efe3a173c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23867510"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="486ea-105">Creación de huella digital de documento</span><span class="sxs-lookup"><span data-stu-id="486ea-105">Document Fingerprinting</span></span>

<span data-ttu-id="486ea-p102">Trabajadores de la información de la organización controlan muchos tipos de información confidencial durante un día normal. En la seguridad &amp; centro de cumplimiento, las huellas digitales de documento facilita la para proteger esta información mediante la identificación de los formularios estándar que se usan en toda la organización. En este tema se describe los conceptos de las huellas digitales de documento y cómo crear uno mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486ea-p102">Information workers in your organization handle many kinds of sensitive information during a typical day. In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization. This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="486ea-109">Escenario básico para la creación de huella digital de documento</span><span class="sxs-lookup"><span data-stu-id="486ea-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="486ea-p103">Creación de huella digital de documento es una característica de prevención de pérdida de datos (DLP) que convierte un formulario estándar en un tipo de información confidencial, que puede usar en las reglas de las directivas de DLP. Por ejemplo, puede crear una huella digital de documento basada en una plantilla de patentes en blanco y, a continuación, crear una directiva de DLP que detecta y bloques de todas las plantillas de patentes salientes con contenido confidencial rellenan. Opcionalmente, puede configurar [sugerencias de directiva](use-notifications-and-policy-tips.md) para notificar a los remitentes que es posible que envío de información confidencial, y el remitente debe comprobar que los destinatarios son completo recibir las patentes. Este proceso funciona con cualquier formulario basado en texto utilizado en la organización. Algunos ejemplos adicionales de los formularios que se pueden cargar son:</span><span class="sxs-lookup"><span data-stu-id="486ea-p103">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies. For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in. Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents. This process works with any text-based forms used in your organization. Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="486ea-115">Formularios de gobierno</span><span class="sxs-lookup"><span data-stu-id="486ea-115">Government forms</span></span>
    
- <span data-ttu-id="486ea-116">Formularios de cumplimiento de Health Insurance Portability and Accountability Act (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="486ea-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="486ea-117">Formularios de información sobre empleados para los departamentos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="486ea-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="486ea-118">Formularios personalizados creados específicamente para la organización</span><span class="sxs-lookup"><span data-stu-id="486ea-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="486ea-p104">Idealmente, su organización ya tiene una práctica de negocio establecido del uso de determinados formularios para transmitir información confidencial. Después de cargar un formulario vacío para convertirse en una huella digital de documento y configurar una directiva correspondiente, el DLP detecta todos los documentos en el correo saliente que coinciden con esa huella digital.</span><span class="sxs-lookup"><span data-stu-id="486ea-p104">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information. After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="486ea-121">Funcionamiento de la creación de huella digital de documento</span><span class="sxs-lookup"><span data-stu-id="486ea-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="486ea-p105">Probablemente ya ha adivinar que los documentos no tienen huellas digitales de real, pero el nombre de la ayuda a explicar la característica. De la misma manera que las huellas digitales de una persona tienen patrones exclusivos, los documentos tienen patrones de palabra única. Cuando se carga un archivo, DLP identifica el patrón de word único en el documento, crea una huella digital de documento basándose en ese patrón y usa esa huella digital de documento para detectar los documentos de salida que contiene el mismo patrón. Que es la razón por la carga de un formulario o plantilla crea el tipo de forma más eficaz de huella digital de documento. Todas las personas que rellena el formulario usa el mismo conjunto original de palabras y, a continuación, agregan sus propias palabras al documento. Siempre y cuando el documento de salida no está protegido con contraseña y contiene todo el texto desde el formulario original, DLP puede determinar si el documento coincide con la huella digital de documento.</span><span class="sxs-lookup"><span data-stu-id="486ea-p105">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature. In the same way that a person's fingerprints have unique patterns, documents have unique word patterns. When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern. That's why uploading a form or template creates the most effective type of document fingerprint. Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document. As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="486ea-128">El siguiente ejemplo muestra qué sucede si crea una huella digital de documento con base en una plantilla de patente, pero puede usar cualquier formulario como base para crear una huella digital de documento.</span><span class="sxs-lookup"><span data-stu-id="486ea-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="486ea-129">**Ejemplo de documento de patente que coincide con una huella digital de documento de una plantilla de patente**</span><span class="sxs-lookup"><span data-stu-id="486ea-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
<span data-ttu-id="486ea-p106">La plantilla de patentes contiene los campos en blanco "Title sobre patentes", "Inventores," y "Descripción" y descripciones para cada uno de esos campos, que es el patrón de word. Cuando se carga la plantilla original sobre patentes, está en uno de los tipos de archivo admitidos y en texto sin formato. Convierte DLP este patrón de word en una huella digital de documento, que es una pequeña XML Unicode del archivo que contiene un valor hash único que representa el texto original y la huella digital se guarda como una clasificación de datos en Active Directory. (Como medida de seguridad, el propio documento original no está almacenado en el servicio; sólo el valor hash se almacena y el documento original no se pueden reconstruir desde el valor hash). La huella digital de patentes, a continuación, se convierte en un tipo de información confidencial que se puede asociar con una directiva de DLP. Después de asociar la huella digital de una directiva de DLP, DLP detecta los mensajes de correo electrónico salientes que contiene documentos que coinciden con la huella digital de patentes y ocupa según la política de su organización.</span><span class="sxs-lookup"><span data-stu-id="486ea-p106">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern. When you upload the original patent template, it's in one of the supported file types and in plain text. DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory. (As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy. After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="486ea-p107">Por ejemplo, es posible que desee configurar una directiva de DLP que impide que los empleados regulares enviar los mensajes salientes que contiene patentes. DLP usará la huella digital de patentes para detectar patentes y bloquear los mensajes de correo electrónico. Como alternativa, es posible que desee permitir que el departamento legal para poder enviar patentes a otras organizaciones debido a que tiene una necesidad empresarial para hacerlo. Puede permitir que los departamentos específicos enviar información confidencial mediante la creación de excepciones para aquellos departamentos en la directiva de DLP, o puede que puedan invalidar una sugerencia de directiva con una justificación comercial.</span><span class="sxs-lookup"><span data-stu-id="486ea-p107">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents. DLP will use the patent fingerprint to detect patents and block those emails. Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so. You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="486ea-140">Tipos de archivo admitidos</span><span class="sxs-lookup"><span data-stu-id="486ea-140">Supported file types</span></span>

<span data-ttu-id="486ea-p108">Creación de huella digital de documento admite los mismos tipos de archivo que son compatibles con las reglas de transporte. Para obtener una lista de tipos de archivo compatibles, vea [tipos de archivo compatibles para la inspección de contenido de reglas de flujo de correo](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una nota rápida acerca de los tipos de archivo: ni las reglas de transporte ni las huellas digitales de documento es compatible con el tipo de archivo .dotx, que puede resultar confusa ya que es un archivo de plantilla en Word. Cuando aparezca la palabra "plantilla" en este y otros temas de las huellas digitales de documento, hace referencia a un documento que ha establecido como un formulario estándar, no el tipo de archivo de plantilla.</span><span class="sxs-lookup"><span data-stu-id="486ea-p108">Document Fingerprinting supports the same file types that are supported in transport rules. For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). One quick note about file types: neither transport rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word. When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="486ea-145">Limitaciones de la creación de huella digital de documento</span><span class="sxs-lookup"><span data-stu-id="486ea-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="486ea-146">Creación de huella digital de documentos no detecta información confidencial en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="486ea-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="486ea-147">Archivos protegidos por contraseña</span><span class="sxs-lookup"><span data-stu-id="486ea-147">Password protected files</span></span>
    
- <span data-ttu-id="486ea-148">Archivos que solo contienen imágenes</span><span class="sxs-lookup"><span data-stu-id="486ea-148">Files that contain only images</span></span>
    
- <span data-ttu-id="486ea-149">Documentos que no contienen todo el texto del formulario original utilizado para crear la huella digital de documento</span><span class="sxs-lookup"><span data-stu-id="486ea-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="486ea-150">Uso de PowerShell para crear un paquete de la regla de clasificación en función de las huellas digitales de documento</span><span class="sxs-lookup"><span data-stu-id="486ea-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="486ea-p109">Tenga en cuenta que puede crear actualmente una huella digital de documento sólo mediante el uso de PowerShell en la seguridad &amp; centro de cumplimiento. Para conectarse, vea [Connect to Office 365 seguridad & PowerShell de centro de cumplimiento](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="486ea-p109">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center. To connect, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="486ea-p110">DLP utiliza paquetes de reglas de clasificación para detectar contenido confidencial. Para crear un paquete de la regla de clasificación en función de una huella digital de documento, use los cmdlets **New-DlpFingerprint** y **New-DlpSensitiveInformationType** . Debido a que no se almacenan los resultados de **Nuevo DlpFingerprint** fuera de la regla de clasificación de datos, ejecutar siempre **New-DlpFingerprint** y **New-DlpSensitiveInformationType** o **Set-DlpSensitiveInformationType** en el mismo Sesión de PowerShell. En el ejemplo siguiente se crea una nueva huella digital de documento basada en el archivo C:\My Documents\Contoso Employee Template.docx. Almacenar la huella digital de nuevo como una variable por lo que puede usar con el cmdlet **New-DlpSensitiveInformationType** en la misma sesión de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="486ea-p110">DLP uses classification rule packages to detect sensitive content. To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets. Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session. The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx. You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="486ea-158">Ahora, crearemos una nueva regla de clasificación de datos llamada "Contoso Employee Confidential" que usa la huella digital de documento del archivo C:\My Documents\Contoso Customer Information Form.docx.</span><span class="sxs-lookup"><span data-stu-id="486ea-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="486ea-159">Ahora puede usar el cmdlet **Get-DlpSensitiveInformationType** para buscar todos los paquetes de reglas de clasificación de datos DLP y, en este ejemplo, "Atención al cliente de Contoso Confidential" es parte de la lista de paquetes de regla de clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="486ea-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="486ea-p111">Por último, agregue el paquete de regla de clasificación de datos "Cliente de Contoso Confidential" a una directiva de DLP en la seguridad &amp; centro de cumplimiento. En este ejemplo se agrega una regla a una directiva de DLP existente denominada "ConfidentialPolicy".</span><span class="sxs-lookup"><span data-stu-id="486ea-p111">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center. This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="486ea-p112">También puede usar el paquete de regla de clasificación de datos en las reglas de transporte en Exchange Online, como se muestra en el siguiente ejemplo. Para ejecutar este comando, primero debe conectarse [a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Tenga en cuenta también que se tarda tiempo para el paquete de regla para la sincronización de la seguridad &amp; centro de cumplimiento para el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="486ea-p112">You can also use the data classification rule package in transport rules in Exchange Online, as shown in the following example. To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange Admin Center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="486ea-165">DLP ahora detecta los documentos que coinciden con la huella digital de documento Form.docx de atención al cliente de Contoso.</span><span class="sxs-lookup"><span data-stu-id="486ea-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="486ea-166">Para obtener información de la sintaxis y los parámetros, consulte:</span><span class="sxs-lookup"><span data-stu-id="486ea-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="486ea-167">Nueva DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="486ea-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="486ea-168">Nueva DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="486ea-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="486ea-169">Remove-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="486ea-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="486ea-170">Set-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="486ea-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="486ea-171">Get-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="486ea-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
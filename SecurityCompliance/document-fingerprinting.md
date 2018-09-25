---
title: Creación de huella digital de documento
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: Trabajadores de la información de la organización controlan muchos tipos de información confidencial durante un día normal. Creación de huella digital de documento facilita proteger esta información mediante la identificación de los formularios estándar que se usan en toda la organización. En este tema se describe los conceptos de las huellas digitales de documento y cómo crear uno mediante el uso de PowerShell.
ms.openlocfilehash: c33d7412fe4774b74efcd0928df4c99c7bcbb626
ms.sourcegitcommit: ede6230c2df398dc0a633e8f32ee0bfede0d5142
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25002653"
---
# <a name="document-fingerprinting"></a>Creación de huella digital de documento

Trabajadores de la información de la organización controlan muchos tipos de información confidencial durante un día normal. En la seguridad &amp; centro de cumplimiento, las huellas digitales de documento facilita la para proteger esta información mediante la identificación de los formularios estándar que se usan en toda la organización. En este tema se describe los conceptos de las huellas digitales de documento y cómo crear uno mediante el uso de PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Escenario básico para la creación de huella digital de documento

Creación de huella digital de documento es una característica de prevención de pérdida de datos (DLP) que convierte un formulario estándar en un tipo de información confidencial, que puede usar en las reglas de las directivas de DLP. Por ejemplo, puede crear una huella digital de documento basada en una plantilla de patentes en blanco y, a continuación, crear una directiva de DLP que detecta y bloques de todas las plantillas de patentes salientes con contenido confidencial rellenan. Opcionalmente, puede configurar [sugerencias de directiva](use-notifications-and-policy-tips.md) para notificar a los remitentes que es posible que envío de información confidencial, y el remitente debe comprobar que los destinatarios son completo recibir las patentes. Este proceso funciona con cualquier formulario basado en texto utilizado en la organización. Algunos ejemplos adicionales de los formularios que se pueden cargar son: 
  
- Formularios de gobierno
    
- Formularios de cumplimiento de Health Insurance Portability and Accountability Act (HIPAA)
    
- Formularios de información sobre empleados para los departamentos de recursos humanos
    
- Formularios personalizados creados específicamente para la organización
    
Idealmente, su organización ya tiene una práctica de negocio establecido del uso de determinados formularios para transmitir información confidencial. Después de cargar un formulario vacío para convertirse en una huella digital de documento y configurar una directiva correspondiente, el DLP detecta todos los documentos en el correo saliente que coinciden con esa huella digital.
  
## <a name="how-document-fingerprinting-works"></a>Funcionamiento de la creación de huella digital de documento

Probablemente ya ha adivinar que los documentos no tienen huellas digitales de real, pero el nombre de la ayuda a explicar la característica. De la misma manera que las huellas digitales de una persona tienen patrones exclusivos, los documentos tienen patrones de palabra única. Cuando se carga un archivo, DLP identifica el patrón de word único en el documento, crea una huella digital de documento basándose en ese patrón y usa esa huella digital de documento para detectar los documentos de salida que contiene el mismo patrón. Que es la razón por la carga de un formulario o plantilla crea el tipo de forma más eficaz de huella digital de documento. Todas las personas que rellena el formulario usa el mismo conjunto original de palabras y, a continuación, agregan sus propias palabras al documento. Siempre y cuando el documento de salida no está protegido con contraseña y contiene todo el texto desde el formulario original, DLP puede determinar si el documento coincide con la huella digital de documento.
  
El siguiente ejemplo muestra qué sucede si crea una huella digital de documento con base en una plantilla de patente, pero puede usar cualquier formulario como base para crear una huella digital de documento.
  
**Ejemplo de documento de patente que coincide con una huella digital de documento de una plantilla de patente**

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
La plantilla de patentes contiene los campos en blanco "Title sobre patentes", "Inventores," y "Descripción" y descripciones para cada uno de esos campos, que es el patrón de word. Cuando se carga la plantilla original sobre patentes, está en uno de los tipos de archivo admitidos y en texto sin formato. Convierte DLP este patrón de word en una huella digital de documento, que es una pequeña XML Unicode del archivo que contiene un valor hash único que representa el texto original y la huella digital se guarda como una clasificación de datos en Active Directory. (Como medida de seguridad, el propio documento original no está almacenado en el servicio; sólo el valor hash se almacena y el documento original no se pueden reconstruir desde el valor hash). La huella digital de patentes, a continuación, se convierte en un tipo de información confidencial que se puede asociar con una directiva de DLP. Después de asociar la huella digital de una directiva de DLP, DLP detecta los mensajes de correo electrónico salientes que contiene documentos que coinciden con la huella digital de patentes y ocupa según la política de su organización. 

Por ejemplo, es posible que desee configurar una directiva de DLP que impide que los empleados regulares enviar los mensajes salientes que contiene patentes. DLP usará la huella digital de patentes para detectar patentes y bloquear los mensajes de correo electrónico. Como alternativa, es posible que desee permitir que el departamento legal para poder enviar patentes a otras organizaciones debido a que tiene una necesidad empresarial para hacerlo. Puede permitir que los departamentos específicos enviar información confidencial mediante la creación de excepciones para aquellos departamentos en la directiva de DLP, o puede que puedan invalidar una sugerencia de directiva con una justificación comercial.
  
### <a name="supported-file-types"></a>Tipos de archivo admitidos

Creación de huella digital de documento admite los mismos tipos de archivo que son compatibles con las reglas de transporte. Para obtener una lista de tipos de archivo compatibles, vea [tipos de archivo compatibles para la inspección de contenido de reglas de flujo de correo](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una nota rápida acerca de los tipos de archivo: ni las reglas de transporte ni las huellas digitales de documento es compatible con el tipo de archivo .dotx, que puede resultar confusa ya que es un archivo de plantilla en Word. Cuando aparezca la palabra "plantilla" en este y otros temas de las huellas digitales de documento, hace referencia a un documento que ha establecido como un formulario estándar, no el tipo de archivo de plantilla.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitaciones de la creación de huella digital de documento

Creación de huella digital de documentos no detecta información confidencial en los siguientes casos:
  
- Archivos protegidos por contraseña
    
- Archivos que solo contienen imágenes
    
- Documentos que no contienen todo el texto del formulario original utilizado para crear la huella digital de documento
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Uso de PowerShell para crear un paquete de la regla de clasificación en función de las huellas digitales de documento

Tenga en cuenta que puede crear actualmente una huella digital de documento sólo mediante el uso de PowerShell en la seguridad &amp; centro de cumplimiento. Para conectarse, vea [Connect to Office 365 seguridad & PowerShell de centro de cumplimiento](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

DLP utiliza paquetes de reglas de clasificación para detectar contenido confidencial. Para crear un paquete de la regla de clasificación en función de una huella digital de documento, use los cmdlets **New-DlpFingerprint** y **New-DlpSensitiveInformationType** . Debido a que no se almacenan los resultados de **Nuevo DlpFingerprint** fuera de la regla de clasificación de datos, ejecutar siempre **New-DlpFingerprint** y **New-DlpSensitiveInformationType** o **Set-DlpSensitiveInformationType** en el mismo Sesión de PowerShell. En el ejemplo siguiente se crea una nueva huella digital de documento basada en el archivo C:\My Documents\Contoso Employee Template.docx. Almacenar la huella digital de nuevo como una variable por lo que puede usar con el cmdlet **New-DlpSensitiveInformationType** en la misma sesión de PowerShell. 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Ahora, crearemos una nueva regla de clasificación de datos llamada "Contoso Employee Confidential" que usa la huella digital de documento del archivo C:\My Documents\Contoso Customer Information Form.docx.
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Ahora puede usar el cmdlet **Get-DlpSensitiveInformationType** para buscar todos los paquetes de reglas de clasificación de datos DLP y, en este ejemplo, "Atención al cliente de Contoso Confidential" es parte de la lista de paquetes de regla de clasificación de datos. 
  
Por último, agregue el paquete de regla de clasificación de datos "Cliente de Contoso Confidential" a una directiva de DLP en la seguridad &amp; centro de cumplimiento. En este ejemplo se agrega una regla a una directiva de DLP existente denominada "ConfidentialPolicy".

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

También puede usar el paquete de regla de clasificación de datos en las reglas de transporte en Exchange Online, como se muestra en el siguiente ejemplo. Para ejecutar este comando, primero debe conectarse [a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Tenga en cuenta también que se tarda tiempo para el paquete de regla para la sincronización de la seguridad &amp; centro de cumplimiento para el centro de administración de Exchange.
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP ahora detecta los documentos que coinciden con la huella digital de documento Form.docx de atención al cliente de Contoso.
  
Para obtener información de la sintaxis y los parámetros, consulte:

- [Nueva DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [Nueva DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)

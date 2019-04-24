---
title: Creación de huella digital de documento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Los trabajadores de la información en su organización tratan con diversos tipos de información confidencial durante un día normal. La creación de huella digital de documento facilita la protección de esta información al identificar los formularios estándar que se usan en toda la organización. En este tema se describen los conceptos relacionados con la creación de huellas digitales de documentos y cómo crear una mediante PowerShell.
ms.openlocfilehash: 2b8e4fd6b286f2c1a5c67863957f2b04fbef31b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256908"
---
# <a name="document-fingerprinting"></a>Creación de huella digital de documento

Los trabajadores de la información en su organización tratan con diversos tipos de información confidencial durante un día normal. En el centro &amp; de seguridad y cumplimiento, la huella digital de documento facilita la protección de esta información mediante la identificación de formularios estándar que se usan en toda la organización. En este tema se describen los conceptos relacionados con la creación de huellas digitales de documentos y cómo crear una mediante PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Escenario básico para la creación de huella digital de documento

La huella digital de documento es una característica de prevención de pérdida de datos (DLP) que convierte un formulario estándar en un tipo de información confidencial, que se puede usar en las reglas de las directivas de DLP. Por ejemplo, puede crear una huella digital de documento con base en una plantilla de patente en blanco y después crear una directiva DLP que detecte y bloquee todas las plantillas de patente salientes que incluyan contenido confidencial. Opcionalmente, puede configurar sugerencias de [Directiva](use-notifications-and-policy-tips.md) para notificar a los remitentes que puedan enviar información confidencial y el remitente debe comprobar que los destinatarios están cualificados para recibir las patentes. Este proceso funciona con cualquier formulario basado en texto que se use en la organización. Algunos ejemplos adicionales de formularios que puede cargar son: 
  
- Formularios de gobierno
    
- Formularios de cumplimiento de Health Insurance Portability and Accountability Act (HIPAA)
    
- Formularios de información sobre empleados para los departamentos de recursos humanos
    
- Formularios personalizados creados específicamente para la organización
    
Idealmente, la organización ya tiene una práctica de negocios establecida sobre el uso de determinados formularios para transmitir información confidencial. Después de cargar un formulario vacío para convertirlo en una huella digital de documento y configurar una directiva correspondiente, DLP detecta los documentos en el correo saliente que coinciden con esa huella digital.
  
## <a name="how-document-fingerprinting-works"></a>Funcionamiento de la creación de huella digital de documento

Probablemente ya adivinó que los documentos no tienen huellas digitales reales, pero el nombre ayuda a explicar la característica. Del mismo modo que las huellas digitales de una persona tienen patrones únicos, los documentos tienen patrones de palabras únicos. Cuando se carga un archivo, DLP identifica el patrón de palabra único en el documento, crea una huella digital de documento basada en ese patrón y usa dicha huella digital de documento para detectar los documentos salientes que contengan el mismo patrón. Por ello, la carga de un formulario o plantilla crea el tipo más efectivo de huella digital de documento. Todas las personas que rellenan un formulario usan el mismo conjunto de palabras original y después agregan sus propias palabras al documento. Siempre que el documento de salida no esté protegido con contraseña y contenga todo el texto del formulario original, DLP puede determinar si el documento coincide con la huella digital de documento.
  
El siguiente ejemplo muestra qué sucede si crea una huella digital de documento con base en una plantilla de patente, pero puede usar cualquier formulario como base para crear una huella digital de documento.
  
**Ejemplo de documento de patente que coincide con una huella digital de documento de una plantilla de patente**

![Document_Fingerprinting_diagram. png](media/Document_Fingerprinting_diagram.png)
  
La plantilla de patente contiene los campos en blanco "título de patente", "inventoras" y "Descripción" y descripciones para cada uno de esos campos, que es la palabra pattern. Al cargar la plantilla de patentes original, se encuentra en uno de los tipos de archivo admitidos y en texto sin formato. DLP convierte este patrón de palabras en una huella digital de documento, que es un pequeño archivo XML Unicode que contiene un valor de hash único que representa el texto original y la huella digital se guarda como una clasificación de datos en Active Directory. (Como medida de seguridad, el documento original no se almacena en el servicio; solo se almacena el valor hash y no se puede reconstruir el documento original a partir del valor hash). La huella digital de patente se convierte en un tipo de información confidencial que puede asociar con una directiva de DLP. Después de asociar la huella digital con una directiva DLP, DLP detecta los mensajes de correo electrónico salientes que contienen documentos que coinciden con la huella digital de patente y se ocupan de ellos según la Directiva de la organización. 

Por ejemplo, es posible que quiera configurar una directiva DLP que impida a los empleados normales enviar mensajes salientes que contengan patentes. DLP usará la huella digital de patentes para detectar las patentes y bloquearlas. Como alternativa, es posible que desee que el departamento legal pueda enviar patentes a otras organizaciones porque tiene una necesidad empresarial de hacerlo. Puede permitir que departamentos específicos envíen información confidencial mediante la creación de excepciones para los departamentos de la Directiva DLP o puede permitirles invalidar una sugerencia de directiva con una justificación empresarial.
  
### <a name="supported-file-types"></a>Tipos de archivo compatibles

La huella digital de documento admite los mismos tipos de archivo que son compatibles con las reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener una lista de los tipos de archivo admitidos, consulte [tipos de archivos admitidos para la inspección del contenido de reglas de flujo de correo](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Una nota rápida sobre los tipos de archivo: ni las reglas de flujo de correo ni la huella digital de documento admiten el tipo de archivo. dotx, lo que puede resultar confuso porque es un archivo de plantilla en Word. Cuando ve la palabra "plantilla" en este y otros temas de creación de huella digital de documento, se refiere a un documento que se ha establecido como formulario estándar, no al tipo de archivo de plantilla.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitaciones de la creación de huella digital de documento

La huella digital de documento no detectará información confidencial en los siguientes casos:
  
- Archivos protegidos por contraseña
    
- Archivos que solo contienen imágenes
    
- Documentos que no contienen todo el texto del formulario original utilizado para crear la huella digital de documento
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Usar PowerShell para crear un paquete de reglas de clasificación basado en la creación de huellas digitales de documentos

Tenga en cuenta que actualmente puede crear una huella digital de documento solo con PowerShell en &amp; el centro de seguridad y cumplimiento. Para conectarse, vea [Connect to Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

DLP usa paquetes de reglas de clasificación para detectar contenido confidencial. Para crear un paquete de reglas de clasificación basado en una huella digital de documento, use los cmdlets **New-DlpFingerprint** y **New-DlpSensitiveInformationType** . Debido a que los resultados de **New-DlpFingerprint** no se almacenan fuera de la regla de clasificación de datos, siempre se ejecuta **New-DlpFingerprint** y **New-DlpSensitiveInformationType** o **set-DlpSensitiveInformationType** en el mismo Sesión de PowerShell. En el ejemplo siguiente se crea una huella digital de documento nueva a partir del archivo C:\My Documents\Contoso Employee Template.docx. La nueva huella digital se almacena como una variable para que se pueda usar con el cmdlet **New-DlpSensitiveInformationType** en la misma sesión de PowerShell. 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Ahora, crearemos una nueva regla de clasificación de datos llamada "Contoso Employee Confidential" que usa la huella digital de documento del archivo C:\My Documents\Contoso Customer Information Form.docx.
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Ahora puede usar el cmdlet **Get-DlpSensitiveInformationType** para buscar todos los paquetes de reglas de clasificación de datos DLP y, en este ejemplo, "Contoso Customer Confidential" forma parte de la lista de paquetes de reglas de clasificación de datos. 
  
Por último, agregue el paquete de reglas de clasificación de datos "Contoso Customer Confidential" a una directiva &amp; DLP en el centro de seguridad y cumplimiento. En este ejemplo se agrega una regla a una directiva DLP existente denominada "ConfidentialPolicy".

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

También puede usar el paquete de reglas de clasificación de datos en reglas de flujo de correo en Exchange Online, tal como se muestra en el ejemplo siguiente. Para ejecutar este comando, primero debe [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Además, tenga en cuenta que el paquete de reglas tarda tiempo en sincronizarse &amp; desde el centro de seguridad y cumplimiento hasta el centro de administración de Exchange.
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

Ahora, DLP detecta los documentos que coinciden con el formulario de clientes de contoso. la huella digital de documento docx.
  
Para obtener información acerca de la sintaxis y los parámetros, consulte:

- [New-DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)

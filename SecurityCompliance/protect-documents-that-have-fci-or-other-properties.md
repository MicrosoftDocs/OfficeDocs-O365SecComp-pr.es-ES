---
title: Crear una directiva DLP para proteger documentos con FCI u otras propiedades
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: 1b9e3c6c-4308-4a20-b11e-c37b8013e177
description: Muchas organizaciones ya tienen un proceso para identificar y clasificar la información confidencial mediante el uso de las propiedades de clasificación en la infraestructura de clasificación de archivo (FCI) de Windows Server, las propiedades de documentos de SharePoint o las propiedades del documento aplica un sistema de terceros. Si esto describe la organización, puede crear una directiva de DLP en Office 365 que reconoce las propiedades que se han aplicado a los documentos mediante Windows Server FCI u otro sistema, por lo que se puede aplicar la directiva de DLP en documentos de Office con FCI específico u otra valores de propiedad.
ms.openlocfilehash: 057cdad981249e39d6f39f231d8d60ab977e717a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013694"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Crear una directiva DLP para proteger documentos con FCI u otras propiedades

En Office 365, puede usar una directiva de prevención de pérdida de datos (DLP) para identificar, supervisar y proteger información confidencial. Muchas organizaciones disponen de un proceso para identificar y clasificar información confidencial mediante las propiedades de clasificación en la infraestructura de clasificación de archivos (FCI) de Windows Server, las propiedades del documento en SharePoint o las propiedades del documento aplicadas por un sistema de terceros. Si esto describe su organización, puede crear una directiva DLP en Office 365 que reconozca las propiedades que la FCI de Windows Server u otro sistema ha aplicado a documentos, de modo que se pueda aplicar la directiva DLP en documentos de Office con una FCI específica u otros valores de propiedad.
  
![Diagrama que muestra Office 365 y el sistema de clasificación externo](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
Por ejemplo, su organización podría usar Windows Server FCI para identificar los documentos con información de identificación personal (PII), como números de la seguridad social y, a continuación, clasificar el documento mediante la configuración de la **Información de identificación personal** propiedad en **alto**, **moderado**, **baja**, **pública**o **No PII** en función del tipo y número de repeticiones de PII que se encuentra en el documento. En Office 365, puede crear una directiva de DLP que identifica los documentos que tengan esa propiedad establecida en valores específicos, como el **alto** y **medio**y, a continuación, realiza una acción, como bloquear el acceso a dichos archivos. La misma directiva puede tener otra regla que toma una acción diferente si la propiedad se establece en **baja**, como el envío de una notificación de correo electrónico. De este modo, DLP en Office 365 se integra con Windows Server FCI y puede ayudar a proteger los documentos de Office cargan o compartido a Office 365 desde los servidores de archivos basados en Windows Server.
  
Una directiva DLP simplemente busca un par nombre-valor para una propiedad específica. Se puede usar cualquier propiedad de documento, siempre y cuando la propiedad tenga una propiedad administrada correspondiente para la búsqueda de SharePoint. Por ejemplo, una colección de sitios de SharePoint puede usar un tipo de contenido denominado **Informe de viaje** con un campo obligatorio denominado **Cliente**. Cuando una persona crea un informe de viaje, debe escribir el nombre del cliente. El par nombre-valor de esta propiedad también se puede usar en una directiva DLP. Por ejemplo, si desea que una regla bloquee el acceso al documento para los usuarios externos cuando el campo **Cliente** contiene **Contoso**.
  
Tenga en cuenta que si desea aplicar la directiva de DLP a contenido con etiquetas específicas de Office 365, no debe seguir los pasos descritos aquí. En su lugar, obtenga información sobre cómo [utilizar una etiqueta como una condición en una directiva de DLP](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).
  
## <a name="before-you-create-the-dlp-policy"></a>Antes de crear la directiva DLP

Antes de que puede usar una propiedad de Windows Server FCI u otra propiedad en una directiva de DLP, debe crear una propiedad administrada en el centro de administración de SharePoint. Estos son los motivos.
  
Ejemplos
  
Esto es importante porque DLP en Office 365 usa el rastreador de búsqueda para identificar y clasificar información confidencial en los sitios y después almacenar esa información confidencial en una parte segura del índice de búsqueda. Al cargar un documento en Office 365, SharePoint crea automáticamente propiedades rastreadas en función de las propiedades del documento. Pero para usar una FCI u otra propiedad en una directiva DLP, la propiedad rastreada debe asignarse a una propiedad administrada para que el contenido con esa propiedad se conserve en el índice.
  
Para obtener más información sobre la búsqueda y las propiedades administradas, vea [administrar el esquema de búsqueda en SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Paso 1: Cargar un documento con la propiedad necesaria en Office 365

Primero debe cargar un documento con la propiedad que desea hacer referencia en la directiva de DLP. Office 365 detectará la propiedad y crear automáticamente una propiedad rastreada de él. En el siguiente paso, podrá crear una propiedad administrada y, a continuación, asignar la propiedad administrada para esta propiedad rastreada.
  
### <a name="step-2-create-a-managed-property"></a>Paso 2: Crear una propiedad administrada

1. Inicie sesión en el Centro de administración de Office 365.
    
2. En el panel de navegación izquierdo, elija **centros de administración** \> **SharePoint**. Ahora está en el centro de administración de SharePoint.
    
3. En el panel de navegación izquierdo, haga clic en **búsqueda** \> en la página **administración de búsquedas** \> **Administrar el esquema de búsqueda**.
    
    ![Página de administración de búsqueda en el Centro de administración de SharePoint](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. En la página de **Propiedades administradas** \> **Nueva propiedad administrada**.
    
    ![Página de Propiedades administradas con el botón Nueva propiedad administrada resaltado](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. Escriba un nombre y una descripción para la propiedad. Este nombre es lo que aparecerá en las directivas DLP.
    
6. En **Tipo**, elija **Texto**. 
    
7. En **Características principales**, seleccione **Consultable** y **Recuperable**.
    
8. En **asignaciones a propiedades rastreadas** \> **Agregar una asignación**.
    
9. En el cuadro de diálogo **rastrea la selección de la propiedad** \> busque y seleccione la propiedad rastreada que corresponde a la propiedad de Windows Server FCI u otra propiedad que se va a usar en la directiva de DLP \> **Aceptar**.
    
    ![Cuadro de diálogo de selección de propiedades rastreadas](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. En la parte inferior de la página \> **Aceptar**.
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Crear una directiva DLP que use una propiedad de FCI u otra propiedad

En este ejemplo, una organización usa FCI en sus servidores de archivos basados en Windows Server; en concreto, utiliza la propiedad de clasificación FCI denominada **Información de identificación personal** con los posibles valores de **alto**, **moderado**, **baja**, **pública**y **No PII**. Ahora que desean sacar provecho de su clasificación FCI existente en sus directivas de DLP en Office 365.
  
En primer lugar, siguen los pasos anteriores para crear una propiedad administrada en SharePoint Online, que se asigna a la propiedad rastreada creada automáticamente a partir de la propiedad FCI.
  
A continuación, crea una directiva de DLP con dos reglas que utilicen la condición de **Propiedades del documento contienen alguno de estos valores**:
  
- **Contenido de PII FCI - alto, moderado** La primera regla restringe el acceso al documento si la propiedad de clasificación FCI **Información de identificación personal** es igual a **alta** o **moderado** y el documento se comparte con personas fuera de la organización. 
    
- **Contenido de PII FCI - baja** La segunda regla envía una notificación al propietario del documento si la propiedad de clasificación FCI **Información de identificación personal** es igual a **baja** y el documento se comparte con personas fuera de la organización. 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>Crear la directiva de DLP con PowerShell

Tenga en cuenta que la condición de **Propiedades del documento contienen alguno de estos valores** no está disponible temporalmente en la interfaz de usuario de la seguridad &amp; centro de cumplimiento, pero aún puede usar esta condición mediante el uso de PowerShell. Puede usar el `New\Set\Get-DlpCompliancePolicy` cmdlets para trabajar con una directiva de DLP y usar el `New\Set\Get-DlpComplianceRule` cmdlets con el `ContentPropertyContainsWords` parámetro para agregar la condición de **Propiedades del documento contienen alguno de estos valores**.
  
Para obtener más información sobre estos cmdlets, consulte [Office 365 seguridad &amp; centro de cumplimiento cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).
  
1. [Conectarse a la seguridad de Office 365 &amp; centro de cumplimiento de normas mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Crear la directiva mediante `New-DlpCompliancePolicy`.
    
    Este es un ejemplo de PowerShell que crea una directiva de DLP que se aplica a todas las ubicaciones.
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. Crear las dos reglas descritas anteriormente mediante el uso de `New-DlpComplianceRule`, donde es una regla para el valor de **baja** y otra regla es para los valores de **alto** y **moderado** . 
    
    Este es un ejemplo de PowerShell que crea estas dos reglas. Tenga en cuenta que los pares de nombre/valor de propiedad están entre comillas y un nombre de propiedad puede especificar varios valores separados por comas sin espacios, al igual que`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    Tenga en cuenta que Windows Server FCI incluye muchas propiedades integradas, incluida la **Información de identificación personal** usados en este ejemplo. Los valores posibles para cada propiedad pueden ser diferentes para cada organización. **Alto**, **moderado**y valores de **baja** utilizados aquí son sólo un ejemplo. Para su organización, puede ver las propiedades de clasificación de Windows Server FCI con sus valores posibles en el archivo de administrador de recursos del servidor en el servidor de archivos basados en Windows Server. Para obtener más información, vea [crear una propiedad de clasificación](http://go.microsoft.com/fwlink/p/?LinkID=627456).
    
Cuando haya terminado, la directiva debe tener dos nuevas reglas que utilizan la condición de **Propiedades del documento contienen alguno de estos valores** . Tenga en cuenta que esta condición no aparecerá en la interfaz de usuario, aunque las condiciones, acciones y configuración aparecerá. 
  
Tener acceso los bloques de una regla para contenido donde la propiedad de **Información de identificación personal** es igual a **alta** o **moderado**. Una segunda regla envía una notificación sobre el contenido donde la propiedad de **Información de identificación personal** es igual a **baja**.
  
![Cuadro de diálogo de nueva directiva DLP que muestra dos reglas recién creadas](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>Después de crear la directiva DLP

Realizar los pasos descritos en las secciones anteriores, va a crear una directiva de DLP detectará rápidamente contenido con esa propiedad, pero sólo si dicho contenido recién se carga (de modo que el contenido indizado), o si dicho contenido es anterior pero acaba de Editar (de modo que vuelva a indiza el contenido) .
  
Para detectar contenido con esa propiedad en todas partes, tal vez le convenga solicitar de forma manual que la biblioteca, sitio o colección de sitios se vuelva a indexar para que la directiva DLP tenga conocimiento de todo el contenido que incluye esa propiedad. En SharePoint Online, el contenido se rastrea automáticamente según una programación de rastreo definida. El rastreador toma el contenido que ha cambiado desde el último rastreo y actualiza el índice. Si necesita que la directiva DLP proteja contenido antes del siguiente rastreo programado, puede llevar a cabo estos pasos.
  
> [!CAUTION]
> Volver a indizar un sitio puede provocar una carga masiva en el sistema de búsqueda. No volver a indizar el sitio, a menos que su situación requiera. 
  
Para obtener más información, vea [solicitar manualmente el rastreo y volver a indizar un sitio, una biblioteca o una lista](http://go.microsoft.com/fwlink/p/?LinkID=627457).
  
### <a name="re-index-a-site-optional"></a>Volver a indexar un sitio (opcional)

1. En el sitio, elija **configuración** (icono de engranaje en la parte superior derecha) \> **Configuración del sitio**.
    
2. En la **búsqueda**, elija **búsqueda y la disponibilidad sin conexión** \> **reindizar sitio**.
    
## <a name="more-information"></a>Más información

- [Información general sobre directivas de prevención de pérdida de datos](data-loss-prevention-policies.md)
    
- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificaciones y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Inventario de tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
    


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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Muchas organizaciones disponen de un proceso para identificar y clasificar información confidencial mediante las propiedades de clasificación en la infraestructura de clasificación de archivos (FCI) de Windows Server, las propiedades del documento en SharePoint o las propiedades del documento aplicadas por un sistema de terceros. Si esto describe su organización, puede crear una directiva DLP en Office 365 que reconozca las propiedades que la FCI de Windows Server u otro sistema ha aplicado a documentos, de modo que se pueda aplicar la directiva DLP en documentos de Office con una FCI específica u otros valores de propiedad.
ms.openlocfilehash: d4468859781703012438a06ec782b75d1acce963
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410535"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Crear una directiva DLP para proteger documentos con FCI u otras propiedades

En Office 365, puede usar una directiva de prevención de pérdida de datos (DLP) para identificar, supervisar y proteger información confidencial. Muchas organizaciones disponen de un proceso para identificar y clasificar información confidencial mediante las propiedades de clasificación en la infraestructura de clasificación de archivos (FCI) de Windows Server, las propiedades del documento en SharePoint o las propiedades del documento aplicadas por un sistema de terceros. Si esto describe su organización, puede crear una directiva DLP en Office 365 que reconozca las propiedades que la FCI de Windows Server u otro sistema ha aplicado a documentos, de modo que se pueda aplicar la directiva DLP en documentos de Office con una FCI específica u otros valores de propiedad.
  
![Diagrama que muestra Office 365 y el sistema de clasificación externo](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
Por ejemplo, su organización puede usar la FCI de Windows Server para identificar los documentos con información de identificación personal (PII), como números de seguridad social, y después clasificar el documento mediante la configuración de la propiedad **Información de identificación personal** en **Alto**, **Moderado**, **Bajo**, **Público** o **No PII** según el tipo y el número de repeticiones de PII encontradas en el documento. En Office 365, puede crear una directiva DLP que identifique los documentos que tienen esa propiedad establecida en valores específicos, como **Alto** y **Medio** y que después realice una acción como bloquear el acceso a dichos archivos. La misma directiva puede tener otra regla que realice una acción diferente si la propiedad se establece en **Bajo**, por ejemplo, enviar una notificación por correo electrónico. De esta forma, DLP en Office 365 se integra con Windows Server FCI y puede ayudar a proteger los documentos de Office cargados o compartidos en Office 365 desde servidores de archivos basados en Windows Server.
  
Una directiva DLP simplemente busca un par nombre-valor para una propiedad específica. Se puede usar cualquier propiedad de documento, siempre y cuando la propiedad tenga una propiedad administrada correspondiente para la búsqueda de SharePoint. Por ejemplo, una colección de sitios de SharePoint puede usar un tipo de contenido denominado **Informe de viaje** con un campo obligatorio denominado **Cliente**. Cuando una persona crea un informe de viaje, debe escribir el nombre del cliente. El par nombre-valor de esta propiedad también se puede usar en una directiva DLP. Por ejemplo, si desea que una regla bloquee el acceso al documento para los usuarios externos cuando el campo **Cliente** contiene **Contoso**.
  
Tenga en cuenta que si desea aplicar la Directiva de DLP a contenido con etiquetas de Office 365 específicas, no debe seguir los pasos que se indican aquí. En su lugar, obtenga información sobre cómo [usar una etiqueta como condición en una directiva DLP](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).
  
## <a name="before-you-create-the-dlp-policy"></a>Antes de crear la directiva DLP

Para poder usar una propiedad de FCI de Windows Server u otra propiedad en una directiva DLP, debe crear una propiedad administrada en el centro de administración de SharePoint. Este es el motivo.
  
Ejemplos
  
Esto es importante porque DLP en Office 365 usa el rastreador de búsqueda para identificar y clasificar información confidencial en los sitios y después almacenar esa información confidencial en una parte segura del índice de búsqueda. Al cargar un documento en Office 365, SharePoint crea automáticamente propiedades rastreadas en función de las propiedades del documento. Pero para usar una FCI u otra propiedad en una directiva DLP, la propiedad rastreada debe asignarse a una propiedad administrada para que el contenido con esa propiedad se conserve en el índice.
  
Para obtener más información sobre las propiedades administradas y de búsqueda, vea [administrar el esquema de búsqueda en SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Paso 1: Cargar un documento con la propiedad necesaria en Office 365

Primero debe cargar un documento con la propiedad a la que desea hacer referencia en la directiva DLP. Office 365 detectará la propiedad y creará automáticamente una propiedad rastreada a partir de esta. En el paso siguiente, creará una propiedad administrada y, a continuación, asignará la propiedad administrada a esta propiedad rastreada.
  
### <a name="step-2-create-a-managed-property"></a>Paso 2: Crear una propiedad administrada

1. Inicie sesión en el Centro de administración de Office 365.
    
2. En el panel de navegación izquierdo, elija **centros** \> de administración **SharePoint**. Ahora está en el Centro de administración de SharePoint.
    
3. En el panel de navegación izquierdo, elija **Buscar** \> en la página \> **Administración de búsquedas** **administrar esquema de búsqueda**.
    
    ![Página de administración de búsqueda en el Centro de administración de SharePoint](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. En la página \> **propiedades administradas** , **nueva propiedad administrada**.
    
    ![Página de Propiedades administradas con el botón Nueva propiedad administrada resaltado](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. Escriba un nombre y una descripción para la propiedad. Este nombre es lo que aparecerá en las directivas DLP.
    
6. En **Tipo**, elija **Texto**. 
    
7. En **Características principales**, seleccione **Consultable** y **Recuperable**.
    
8. En **asignaciones a propiedades** \> rastreadas, **agregue una asignación**.
    
9. En el cuadro \> de diálogo **selección de propiedades rastreadas** , busque y seleccione la propiedad rastreada que corresponda a la propiedad de Windows Server FCI u otra propiedad que vaya a \> usar en la Directiva DLP **correcta**.
    
    ![Cuadro de diálogo de selección de propiedades rastreadas](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. En la parte inferior de la \> página **Aceptar**.
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Crear una directiva DLP que use una propiedad de FCI u otra propiedad

En este ejemplo, una organización usa FCI en sus servidores de archivos basados en Windows Server; concretamente, usan la propiedad de clasificación FCI denominada **información de identificación personal** con los valores posibles de **High**, **moderate**, **Low**, **Public**y **no PII**. Ahora quieren aprovechar su clasificación de FCI existente en sus directivas DLP en Office 365.
  
En primer lugar, siguen los pasos anteriores para crear una propiedad administrada en SharePoint Online, que se asigna a la propiedad rastreada creada automáticamente a partir de la propiedad FCI.
  
A continuación, crean una directiva DLP con dos reglas que usan las propiedades de documento de condición que **contienen cualquiera de estos valores**:
  
- **Contenido PII de FCI: alta, moderada** La primera regla restringe el acceso al documento si la propiedad de clasificación FCI **información de identificación personal** es igual a **alta** o **moderada** y el documento se comparte con personas de fuera de la organización. 
    
- **Contenido PII de FCI: bajo** La segunda regla envía una notificación al propietario del documento si la propiedad de clasificación FCI la **información de identificación personal** es **baja** y el documento se comparte con personas de fuera de la organización. 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>Crear la Directiva DLP mediante PowerShell

Tenga en cuenta que las propiedades de documento de condición **contienen alguno de estos valores** no está disponible temporalmente en la &amp; interfaz de usuario del centro de seguridad y cumplimiento, pero puede usar esta condición con PowerShell. Puede usar `New\Set\Get-DlpCompliancePolicy` los cmdlets para trabajar con una directiva DLP y usar `New\Set\Get-DlpComplianceRule` los cmdlets con el `ContentPropertyContainsWords` parámetro para agregar las propiedades del documento de condición que **contienen cualquiera de estos valores**.
  
Para obtener más información sobre estos cmdlets, consulte los cmdlets del [centro de seguridad &amp; y cumplimiento de Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).
  
1. [Conectarse al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Cree la Directiva con `New-DlpCompliancePolicy`el.
    
    A continuación, se muestra un ejemplo de PowerShell que crea una directiva DLP que se aplica a todas las ubicaciones.
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. Cree las dos reglas descritas anteriormente usando `New-DlpComplianceRule`, donde una regla es para el valor **bajo** , y otra regla es para los valores **alto** y **moderado** . 
    
    A continuación, se muestra un ejemplo de PowerShell que crea estas dos reglas. Tenga en cuenta que los pares nombre-valor de propiedad se incluyen entre comillas, y un nombre de propiedad puede especificar varios valores separados por comas sin espacios, como`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    Tenga en cuenta que Windows Server FCI incluye muchas propiedades integradas, incluida la **información de identificación personal** usada en este ejemplo. Los valores posibles para cada propiedad pueden ser diferentes para cada organización. Los valores **altos**, **moderados**y **bajos** que se usan aquí son solo un ejemplo. Para su organización, puede ver las propiedades de clasificación de FCI de Windows Server con sus valores posibles en el administrador de recursos del servidor de archivos en el servidor de archivos basado en Windows Server. Para obtener más información, vea [crear una propiedad de clasificación](http://go.microsoft.com/fwlink/p/?LinkID=627456).
    
Cuando termine, la Directiva debe tener dos reglas nuevas que usen las propiedades del documento y que contengan **cualquiera de estos valores de** condición. Tenga en cuenta que esta condición no aparecerá en la interfaz de usuario, aunque se mostrarán las demás condiciones, acciones y configuración. 
  
Una regla bloquea el acceso al contenido donde la propiedad **Información de identificación personal** es igual a **Alto** o **Moderado**. Una segunda regla envía una notificación sobre el contenido donde la propiedad **Información de identificación personal** es igual a **Bajo**.
  
![Cuadro de diálogo de nueva directiva DLP que muestra dos reglas recién creadas](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>Después de crear la directiva DLP

Si realiza los pasos descritos en las secciones anteriores, se creará una directiva de DLP que detectará rápidamente el contenido con esa propiedad, pero solo si el contenido se ha cargado recientemente (para que el contenido indizado), o si el contenido es antiguo, pero solo se ha editado (para que el contenido se vuelva a indizar) .
  
Para detectar contenido con esa propiedad en todas partes, tal vez le convenga solicitar de forma manual que la biblioteca, sitio o colección de sitios se vuelva a indexar para que la directiva DLP tenga conocimiento de todo el contenido que incluye esa propiedad. En SharePoint Online, el contenido se rastrea automáticamente según una programación de rastreo definida. El rastreador toma el contenido que ha cambiado desde el último rastreo y actualiza el índice. Si necesita que la directiva DLP proteja contenido antes del siguiente rastreo programado, puede llevar a cabo estos pasos.
  
> [!CAUTION]
> Volver a indexar un sitio puede provocar una carga masiva en el sistema de búsqueda. No vuelva a indizar el sitio a menos que su escenario lo requiera absolutamente. 
  
Para obtener más información, consulte [solicitar manualmente el rastreo y la nueva indización de un sitio, una biblioteca o una lista](http://go.microsoft.com/fwlink/p/?LinkID=627457).
  
### <a name="re-index-a-site-optional"></a>Volver a indexar un sitio (opcional)

1. En el sitio, elija **configuración** (icono de engranaje en la parte \> superior derecha) **configuración del sitio**.
    
2. En **Buscar**, elija reindizar el \> **sitio**de **disponibilidad de búsqueda y sin conexión** .
    
## <a name="more-information"></a>Más información

- [Información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md)
    
- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificaciones y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Inventario de tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
    


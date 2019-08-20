---
title: Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: 'Obtenga información sobre el correo electrónico y las propiedades de archivo que puede buscar en los buzones de Exchange Online y en los sitios de SharePoint o de OneDrive para la empresa mediante la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento.  '
ms.openlocfilehash: 5b3438537e2936fa140052c6869f84937e103746
ms.sourcegitcommit: 372691a3a886e5cc299961032ee334aef26fb904
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464713"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido

En este tema se describen las propiedades de correo electrónico y de documento que se pueden buscar en elementos de correo electrónico en Exchange Online y documentos almacenados en SharePoint y los sitios de OneDrive para la empresa mediante la característica de búsqueda de contenido en el centro de seguridad & cumplimiento. También puede usar los cmdlets ** \*-ComplianceSearch** en el PowerShell del centro de cumplimiento de & de seguridad para buscar estas propiedades. El tema también describe:   
  
- Usar operadores de búsqueda booleanos, condiciones de búsqueda y otras técnicas de consulta de búsqueda para refinar los resultados de la búsqueda.
    
- Buscar tipos de datos confidenciales y tipos de datos confidenciales personalizados en SharePoint y OneDrive para la empresa.
    
- Búsqueda de contenido de sitio compartido con usuarios fuera de la organización
    
Para obtener instrucciones paso a paso sobre cómo crear una búsqueda de contenido, consulte [búsqueda de contenido en Office 365](content-search.md).

  
> [!NOTE]
> Búsqueda de contenido en el centro de seguridad & cumplimiento y los cmdlets ** \*-ComplianceSearch** correspondientes en el centro de seguridad & cumplimiento de PowerShell use el lenguaje de consulta de palabras clave (KQL). Para obtener información más detallada, vea [referencia de sintaxis de lenguaje de consulta de palabras clave](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## <a name="searchable-email-properties"></a>Propiedades del correo electrónico que permiten búsquedas

En la siguiente tabla se enumeran las propiedades de los mensajes de correo electrónico que se pueden buscar usando la característica de búsqueda de contenido en el centro de seguridad & cumplimiento o con el **New-compliancesearch** o el cmdlet **set-ComplianceSearch** . La tabla incluye un ejemplo de la sintaxis  _propiedad:valor_ de cada propiedad y una descripción de los resultados de búsqueda devueltos por los ejemplos. Puede escribir estos `property:value` pares en el cuadro palabras clave para una búsqueda de contenido. 

> [!NOTE]
> Al buscar propiedades de correo electrónico, no es posible buscar elementos en los que la propiedad especificada está vacía o en blanco. Por ejemplo, si se usa el par *propiedad: valor* del **asunto: ""** para buscar mensajes de correo electrónico con una línea de asunto vacía, devolverá cero resultados. Esto también se aplica al buscar propiedades de sitio y contacto.
  
|**Propiedad**|**Descripción de la propiedad**|**Ejemplos**|**Resultados de la búsqueda devueltos por los ejemplos**|
|:-----|:-----|:-----|:-----|
|AttachmentNames|Los nombres de los archivos adjuntos a un mensaje de correo electrónico.|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*`|Los mensajes con un archivo adjunto denominado informeanual.ppt. En el segundo ejemplo, el uso del comodín devuelve los mensajes con la palabra "anual" en el nombre de un archivo adjunto.|
|Bcc|El campo CCO de un mensaje de correo electrónico. <sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|Todos los ejemplos devuelven los mensajes que incluyen a Pilar Pinilla en el campo CCO.|
|Category| Las categorías para buscar. Las categorías pueden ser definidas por los usuarios mediante Outlook o Outlook en la web (anteriormente conocido como Outlook Web App). Los valores posibles son:  <br/><br/>  azul  <br/>  verde  <br/>  naranja  <br/>  púrpura  <br/>  rojo  <br/>  amarillo|`category:"Red Category"`|Los mensajes a los que se ha asignado la categoría roja en los buzones de origen.|
|CC|El campo CC de un mensaje de correo electrónico. <sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|En ambos ejemplos, los mensajes con Pilar Pinilla especificados en el campo CC.|
|Folderid|IDENTIFICADOR de carpeta (GUID) de una carpeta de buzón de correo específica. Si usa esta propiedad, asegúrese de buscar el buzón en el que se encuentra la carpeta especificada. Solo se buscará en la carpeta especificada. No se buscará en las subcarpetas de la carpeta. Para buscar en subcarpetas, debe usar la propiedad folderId para la subcarpeta que desea buscar.  <br/> Para obtener más información acerca de la búsqueda de la propiedad folderId y el uso de un script para obtener los identificadores de carpeta de un buzón específico, vea [usar la búsqueda de contenido en Office 365 para las colecciones dirigidas](use-content-search-for-targeted-collections.md).|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|El primer ejemplo devuelve todos los elementos de la carpeta del buzón especificado. En el segundo ejemplo, se devuelven todos los elementos de la carpeta de buzón especificada enviados o recibidos por garthf@contoso.com.|
|De|El remitente de un mensaje de correo electrónico.<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|Los mensajes enviados por el usuario especificado o enviados desde un dominio especificado.|
|HasAttachment|Indica si un mensaje tiene datos adjuntos. Use los valores **true** o **false**.|`from:pilar@contoso.com AND hasattachment:true`|Mensajes enviados por el usuario especificado que tienen datos adjuntos.|
|Importance|La importancia de un mensaje de correo electrónico, que un remitente puede especificar al enviar un mensaje. De manera predeterminada, los mensajes se envían con importancia normal, a menos que el remitente establezca la importancia como **alta** o **baja**.  |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|Los mensajes que están marcados con importancia alta, importancia media o importancia baja.|
|IsRead|Indica si se han leído los mensajes. Use los valores **true** o **false**.|`isread:true`  <br/> `isread:false`|El primer ejemplo devuelve los mensajes con la propiedad IsRead establecida en **true**. El segundo ejemplo devuelve los mensajes con la propiedad IsRead establecida en **false**.|
|ItemClass|Use esta propiedad para buscar tipos de datos de terceros específicos que su organización ha importado a Office 365. Use la siguiente sintaxis para esta propiedad:`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|El primer ejemplo devuelve los elementos de Facebook que contienen la palabra "Contoso" en la propiedad Subject. El segundo ejemplo devuelve los elementos de Twitter que ha publicado Ann Beebe y que contienen la frase de palabra clave "Northwind Traders".  <br/> Para obtener una lista completa de los valores que se van a usar para los tipos de datos de terceros para la propiedad ItemClass, vea [usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).|
|Tipo| Tipo de mensaje de correo electrónico que se va a buscar. Valores posibles:  <br/>  contactos  <br/>  documentos  <br/>  correo electrónico  <br/>  externaldata  <br/>  faxes  <br/>  mensajería instantánea  <br/>  diarios  <br/>  reuniones  <br/>  Microsoft Teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams)  <br/>  notas  <br/>  entradas  <br/>  fuentes rss  <br/>  tareas  <br/>  correo de voz|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|El primer ejemplo devuelve los mensajes de correo electrónico que cumplen los criterios de búsqueda. En el segundo ejemplo, se devuelven mensajes de correo electrónico, conversaciones de mensajería instantánea (incluidas conversaciones y chats de Skype empresarial en Microsoft Teams) y mensajes de voz que cumplen los criterios de búsqueda. En el tercer ejemplo se devuelven elementos que se importaron a los buzones de Office 365 desde orígenes de datos de terceros, como Twitter, Facebook y Cisco Jabber, que cumplen los criterios de búsqueda. Para obtener más información, vea [archivar datos de terceros en Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).|
|Participantes|Todos los campos de personas en un mensaje de correo electrónico. Estos campos son from, to, CC y BCC.<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|Los mensajes enviados por o a garthf@contoso.com. El segundo ejemplo devuelve todos los mensajes enviados por o a un usuario en el dominio contoso.com.|
|Received|La fecha en la que un destinatario recibió un mensaje de correo electrónico.|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|Mensajes que se recibieron el 15 de abril de 2016. El segundo ejemplo devuelve todos los mensajes recibidos entre el 1 de enero de 2016 y el 31 de marzo de 2016.|
|Destinatarios|Todos los campos de destinatarios en un mensaje de correo electrónico. Estos campos son para, CC y CCO.<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|Los mensajes enviados a garthf@contoso.com. El segundo ejemplo devuelve los mensajes enviados a cualquier destinatario en el dominio contoso.com.|
|Sent|La fecha en la que un remitente envió un mensaje de correo electrónico.|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|Mensajes que se enviaron en la fecha especificada o que se enviaron dentro del intervalo de fechas especificado.|
|Size|El tamaño de un elemento, en bytes.|`size>26214400`  <br/> `size:1..1048567`|Mensajes de más de 25? Examina. El segundo ejemplo devuelve los mensajes que tienen un tamaño de entre 1 y 1 048 567 bytes (1 MB).|
|Subject|El texto en la línea de asunto de un mensaje de correo electrónico.  <br/> **Nota:** Cuando se usa la propiedad Subject en una consulta, la búsqueda devuelve todos los mensajes en los que la línea de asunto contiene el texto que se está buscando. En otras palabras, la consulta no devuelve solo los mensajes que tienen una coincidencia exacta. Por ejemplo, si busca `subject:"Quarterly Financials"`, los resultados incluirán los mensajes con el asunto "Quarterly financials 2018".|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|Mensajes que contienen la frase "finanzas trimestrales" en cualquier lugar del texto de la línea de asunto. El segundo ejemplo devuelve todos los mensajes que contienen la palabra northwind en la línea de asunto.|
|To|El campo Para de un mensaje de correo electrónico.<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|Todos los ejemplos devuelven mensajes en los que Ann Beebe está especificada en la línea Para.|
|||||
   
> [!NOTE]
> <sup>1</sup> para el valor de una propiedad de destinatario, puede usar la dirección de correo electrónico (también denominada *nombre principal del usuario* o UPN), nombre para mostrar o alias para especificar un usuario. Por ejemplo, para especificar el usuario Ann Beebe, puede usar annb@contoso.com, annb o "Ann Beebe".<br/><br/>Al buscar en cualquiera de las propiedades del destinatario (de, para, CC, CCO, participantes y destinatarios), Office 365 intenta ampliar la identidad de cada usuario buscando en Azure Active Directory.  Si el usuario se encuentra en Azure Active Directory, la consulta se expande para incluir la dirección de correo electrónico (o UPN), el alias, el nombre para mostrar y el LegacyExchangeDN del usuario.<br/><br/>Por ejemplo, una consulta como se `participants:ronnie@contoso.com` expande a `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`.<br/><br/>Para evitar la expansión de destinatarios, puede Agregar un carácter comodín (asterisco) al final de la dirección de correo electrónico en la consulta de búsqueda; por ejemplo, `participants:ronnie@contoso.com*`.

## <a name="searchable-site-properties"></a>Propiedades de sitio que se pueden buscar

En la siguiente tabla se enumeran algunas de las propiedades de SharePoint y OneDrive para la empresa en las que se puede buscar mediante la característica de búsqueda de contenido en el centro de seguridad & cumplimiento o mediante el **New-compliancesearch** o el **set-ComplianceSearch. **cmdlet. La tabla incluye un ejemplo de la sintaxis  _propiedad:valor_ de cada propiedad y una descripción de los resultados de búsqueda devueltos por los ejemplos. 
  
Para obtener una lista completa de las propiedades de SharePoint que se pueden buscar, vea [información general sobre las propiedades rastreadas y administradas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Se pueden buscar las propiedades marcadas con **sí** en la columna **consultable** . 
  
|**Propiedad**|**Descripción de la propiedad**|**Ejemplo**|**Resultados de la búsqueda devueltos por los ejemplos**|
|:-----|:-----|:-----|:-----|
|Autor|El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que la carga a SharePoint, el documento seguirá conservando el autor original. Asegúrese de usar el nombre para mostrar del usuario para esta propiedad.|`author:"Garth Fort"`|Todos los documentos que se han creado por Juan Casanova.|
|ContentType|El tipo de contenido de SharePoint de un elemento, como elemento, documento o vídeo.|`contenttype:document`|Se devolverán todos los documentos.|
|Created|La fecha en la que se crea un elemento.|`created\>=06/01/2016`|Todos los elementos creados el 1 de junio de 2016 o después.|
|CreatedBy|La persona que creó o cargó un elemento. Asegúrese de usar el nombre para mostrar del usuario para esta propiedad.|`createdby:"Garth Fort"`|Todos los elementos creados o cargados por Juan Casanova.|
|DetectedLanguage|El idioma de un elemento.|`detectedlanguage:english`|Todos los elementos en inglés.|
|DocumentLink|La ruta de acceso (dirección URL) de una carpeta específica en un sitio de SharePoint o de OneDrive para la empresa. Si usa esta propiedad, asegúrese de buscar en el sitio en el que se encuentra la carpeta especificada.  <br/> Para devolver los elementos que se encuentran en las subcarpetas de la carpeta que ha especificado para la propiedad documentlink, tiene\* que agregar o a la dirección URL de la carpeta especificada; por ejemplo,`documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>Para obtener más información sobre cómo buscar la propiedad documentlink y usar un script para obtener las direcciones URL de documentlink para las carpetas de un sitio específico, vea [usar la búsqueda de contenido en Office 365 para las colecciones dirigidas](use-content-search-for-targeted-collections.md).|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|El primer ejemplo devuelve todos los elementos de la carpeta de OneDrive para la empresa especificada. En el segundo ejemplo, se devuelven los documentos de la carpeta del sitio especificada (y todas las subcarpetas) que contienen la palabra "Confidential" en el nombre del archivo.|
|FileExtension|La extensión de un archivo; por ejemplo, docx, One, pptx o XLSX.|`fileextension:xlsx`|Todos los archivos de Excel (Excel 2007 y versiones posteriores)|
|FileName|El nombre de un archivo.|`filename:"marketing plan"`  <br/> `filename:estimate`|El primer ejemplo devuelve archivos con la frase exacta "plan de marketing" en el título. El segundo ejemplo devuelve archivos con la palabra "estimación" en el nombre del archivo.|
|LastModifiedTime|La fecha de la última modificación de un elemento.|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|El primer ejemplo devuelve los elementos que se cambiaron en o después del 1 de mayo de 2016. El segundo ejemplo devuelve los elementos modificados entre el 1 de mayo de 2016 y el 1 de junio de 2016.|
|ModifiedBy|La última persona que modificó un elemento. Asegúrese de usar el nombre para mostrar del usuario para esta propiedad.|`modifiedby:"Garth Fort"`|Todos los elementos que Juan Casanova modificó por última vez.|
|Ruta de acceso|Ruta de acceso (dirección URL) de un sitio específico en un sitio de SharePoint o de OneDrive para la empresa.  <br/> Para devolver los elementos que se encuentran en las carpetas del sitio que especifique para la propiedad Path, tiene que agregar\* o a la dirección URL del sitio especificado; por ejemplo,`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **Nota:** Usar la `Path` propiedad para buscar en ubicaciones de OneDrive no devolverá archivos multimedia, como archivos. png,. TIFF o. wav, en los resultados de la búsqueda. Use una propiedad de sitio diferente en la consulta de búsqueda para buscar archivos multimedia en las carpetas de OneDrive. <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|El primer ejemplo devuelve todos los elementos del sitio de OneDrive para la empresa especificado. En el segundo ejemplo, se devuelven los documentos del sitio especificado (y las carpetas del sitio) que contienen la palabra "Confidential" en el nombre del archivo.|
|SharedWithUsersOWSUser|Documentos que se han compartido con el usuario especificado y que se muestran en la página compartidos **conmigo** en el sitio de OneDrive para la empresa del usuario. Se trata de documentos que otros usuarios de la organización han compartido explícitamente con el usuario especificado. Cuando se exportan documentos que coinciden con una consulta de búsqueda que usa la propiedad SharedWithUsersOWSUser, los documentos se exportan desde la ubicación de contenido original de la persona que compartió el documento con el usuario especificado. Para obtener más información, consulte [búsqueda de contenido de sitio compartido dentro de la organización](#searching-for-site-content-shared-within-your-organization).|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|Ambos ejemplos devuelven todos los documentos internos que se han compartido explícitamente con Juan Fort y que aparecen en la página compartidos **conmigo** de la cuenta de OneDrive para la empresa de Juan Fort.|
|Site|La dirección URL de un sitio o grupo de sitios de la organización.|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|El primer ejemplo devuelve elementos de los sitios de OneDrive para la empresa para todos los usuarios de la organización. El segundo ejemplo devuelve los elementos de todos los sitios del equipo.|
|Size|El tamaño de un elemento, en bytes.|`size>=1`  <br/> `size:1..10000`|El primer ejemplo devuelve elementos mayores de 1 byte. El segundo ejemplo devuelve elementos que tienen un tamaño de entre 1 y 10 000 bytes.|
|Title|El título del documento. La propiedad title es metadatos que se especifican en los documentos de Microsoft Office. Es diferente del nombre de archivo del documento.|`title:"communication plan"`|Cualquier documento que contenga la frase "plan de comunicación" en la propiedad Título de metadatos de un documento de Office.|
|||||
   
## <a name="searchable-contact-properties"></a>Propiedades de contactos que permiten búsquedas

En la siguiente tabla se enumeran las propiedades de los contactos que se indizan y que se pueden buscar mediante la búsqueda de contenido. Estas son las propiedades que los usuarios pueden configurar para los contactos (también denominados contactos personales) que se encuentran en la libreta personal de direcciones del buzón de un usuario. Para buscar contactos, puede seleccionar los buzones para buscar y, a continuación, usar una o más propiedades de contacto en la consulta de palabras clave.
  
> [!TIP]
> Para buscar valores que contienen espacios o caracteres especiales, use comillas dobles ("") para incluir la frase; por ejemplo, `businessaddress:"123 Main Street"`. 
  
|**Propiedad**|**Descripción de la propiedad**|
|:-----|:-----|
|BusinessAddress|La dirección de la propiedad de la dirección de la **empresa** . La propiedad también se denomina dirección del **trabajo** en la página de propiedades del contacto.|
|BusinessPhone|El número de teléfono en cualquiera de las propiedades de número de **teléfono de trabajo** .|
|CompanyName|Nombre de la propiedad **Company** .|
|Departamento|Nombre de la propiedad **Department** .|
|DisplayName|El nombre para mostrar del contacto. Es el nombre que aparece en la propiedad **nombre completo** del contacto.|
|EmailAddress|La dirección de cualquier propiedad de dirección de correo electrónico del contacto. Los usuarios pueden agregar varias direcciones de correo electrónico a un contacto. El uso de esta propiedad devolvería los contactos que coinciden con cualquiera de las direcciones de correo electrónico del contacto.|
|FileAs|El **archivo como** propiedad. Esta propiedad se usa para especificar cómo aparece el contacto en la lista de contactos del usuario. Por ejemplo, un contacto puede aparecer como *FirstName, LastName* o *LastName, FirstName*.|
|GivenName|Nombre de la propiedad **First Name** .|
|HomeAddress|La dirección en cualquiera de las propiedades de la dirección **particular** .|
|HomePhone|El número de teléfono en cualquiera de las propiedades de número de teléfono **particular** .|
|Propiedad IMAddress|La propiedad de dirección de mensajería instantánea, que suele ser una dirección de correo electrónico que se usa para la mensajería instantánea.|
|MiddleName|Nombre de la propiedad de **segundo** nombre.|
|MobilePhone|El número de teléfono de la propiedad número de teléfono **móvil** .|
|Nickname|Nombre de la propiedad **nickname** .|
|OfficeLocation|El valor de **** la propiedad **Ubicación** de Office o Office.|
|OtherAddress|El valor de la propiedad **other** Address.|
|Apellido|Nombre de la propiedad **Last** Name.|
|Title|El título de la propiedad **cargo** .|
|||||

## <a name="searchable-sensitive-data-types"></a>Tipos de datos confidenciales que se pueden buscar

Puede usar la característica de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar datos confidenciales, como los números de tarjetas de crédito o los números de la seguridad social, que se almacenan en documentos en los sitios de SharePoint y OneDrive para la empresa. Para ello, use la `SensitiveType` propiedad y el nombre de un tipo de información confidencial en una consulta de palabra clave. Por ejemplo, la consulta `SensitiveType:"Credit Card Number"` devuelve documentos que contienen un número de tarjeta de crédito. La consulta `SensitiveType:"U.S. Social Security Number (SSN)"` devuelve documentos que contienen un número de la seguridad social de Estados Unidos. Para ver una lista de los tipos de datos confidenciales que se pueden buscar, vaya a **clasificación** \> de **tipos de información confidencial** en el centro de seguridad & cumplimiento. O bien, puede usar el cmdlet **Get-DlpSensitiveInformationType** en el PowerShell del centro de cumplimiento de & de seguridad para mostrar una lista de tipos de información confidencial. 
  
También puede usar la `SensitiveType` propiedad para buscar el nombre de un tipo personalizado de información confidencial que usted (u otro administrador) creado para su organización. Puede usar la columna **Publisher** en la página **tipos de información confidencial** en el centro de seguridad & cumplimiento (o la propiedad **Publisher** en PowerShell) para diferenciar entre los tipos de información confidencial integrados y personalizados. Para obtener más información, vea [crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md).
  
Para obtener más información acerca de la creación `SensitiveType` de consultas mediante la propiedad, vea el [formulario a Query para buscar datos confidenciales almacenados en sitios](form-a-query-to-find-sensitive-data-stored-on-sites.md).

> [!NOTE]
> No puede usar tipos de datos confidenciales `SensitiveType` y la propiedad Search para buscar datos confidenciales en el resto de los buzones de Exchange Online. Sin embargo, puede usar las directivas de prevención de pérdida de datos (DLP) para proteger los datos confidenciales de correo electrónico en tránsito. Para obtener más información, vea [información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md) y [Buscar y buscar datos personales](search-for-and-find-personal-data.md).
  
## <a name="search-operators"></a>Operadores de búsqueda

Los operadores de búsqueda booleanos, como **and**, **or**y **Not**, ayudan a definir búsquedas más precisas incluyendo o excluyendo palabras específicas en la consulta de búsqueda. Otras técnicas, como el uso de operadores de propiedades ( \>como = o..), las comillas, los paréntesis y los caracteres comodín, ayudan a refinar una consulta de búsqueda. En la siguiente tabla se muestran los operadores que puede usar para restringir o ampliar los resultados de la búsqueda. 
  
|**Operador**|**Uso**|**Descripción**|
|:-----|:-----|:-----|
|AND|palabra clave 1 AND palabra clave 2|Devuelve los elementos que incluyen todas las palabras clave especificadas o `property:value` expresiones. Por ejemplo, `from:"Ann Beebe" AND subject:northwind` se devolverán todos los mensajes enviados por Ann Beebe que contengan la palabra Northwind en la línea de asunto. <sup>segundo</sup>|
|+|palabra + palabra clave 2 + palabra clave 3|Devuelve elementos que contienen  *o*  `keyword2` o  `keyword3` *y*  que también contienen  `keyword1`. Por tanto, este ejemplo es equivalente a la consulta  `(keyword2 OR keyword3) AND keyword1`.  <br/> La consulta `keyword1 + keyword2` (con un espacio después del **+** símbolo) no es lo mismo que usar el operador * * y * *. This query would be equivalent to  `"keyword1 + keyword2"` and return items with the exact phase  `"keyword1 + keyword2"`.|
|OR|palabra clave 1 OR palabra clave 2|Devuelve los elementos que incluyen una o varias de las palabras clave `property:value` especificadas o expresiones. <sup>segundo</sup>|
|NOT|palabra clave 1 NOT palabra clave 2  <br/> NOT from:"Ann Beebe"  <br/> NO tipo: mensajería instantánea|Excluye los elementos especificados por una palabra clave `property:value` o una expresión. En el segundo ejemplo, se excluyen los mensajes enviados por Ann Beebe. En el tercer ejemplo se excluyen todas las conversaciones de mensajería instantánea, como las conversaciones de Skype empresarial que se guardan en la carpeta del buzón historial de conversaciones. <sup>segundo</sup>|
|-|palabra clave 1 - palabra clave 2|Igual que el operador **NOT**. Por lo tanto, esta consulta devuelve `keyword1` los elementos que contienen y excluye `keyword2`los elementos que contienen.|
|NEAR|palabra clave 1 NEAR(n) palabra clave 2|Devuelve los elementos con palabras cercanas entre sí, donde "n" indica el número de palabras que las separan. Por ejemplo, `best NEAR(5) worst` devuelve cualquier elemento en el que la palabra "peor" esté en cinco palabras de "mejor". Si no se especifica ningún número, la distancia predeterminada es de ocho palabras. <sup>segundo</sup>|
|ONEAR|palabra clave 1 ONEAR(n) palabra clave 2|Similar a **Near**, pero devuelve elementos con palabras cercanas en el orden especificado. Por ejemplo, `best ONEAR(5) worst` devuelve cualquier elemento donde la palabra "mejor" se produce antes de la palabra "peor" y las dos palabras están a menos de cinco palabras. Si no se especifica ningún número, la distancia predeterminada es de ocho palabras. <sup>segundo</sup> <br/> > [!NOTE]> el operador **ONEAR** no es compatible con la búsqueda en buzones. Solo funciona al buscar sitios de SharePoint y OneDrive para la empresa. Si va a buscar buzones y sitios en la misma búsqueda y la consulta incluye el operador **ONEAR** , la búsqueda devuelve los elementos del buzón como si estuviera usando el operador **Near** . Es decir, la búsqueda devuelve los elementos en los que las palabras especificadas están cercanas entre sí, independientemente del orden en que se produzcan las palabras.|
|:|propiedad:valor|Los dos puntos (:) en la `property:value` sintaxis especifica que el valor de la propiedad en la que se busca contiene el valor especificado. Por ejemplo,  `recipients:garthf@contoso.com` devuelve cualquier mensaje enviado a garthf@contoso.com.|
|=|propiedad = valor|Igual que el operador **:** .|
|\<|propiedad\<valor|Indica que la propiedad que se busca es menor que el valor especificado. <sup>1</sup>|
|\>|propiedad\>valor|Indica que la propiedad que se busca es mayor que el valor especificado.<sup>1</sup>|
|\<=|propiedad\<=valor|Indica que la propiedad que se busca es menor o igual que un valor especificado.<sup>1</sup>|
|\>=|propiedad\>=valor|Indica que la propiedad que se busca es mayor o igual que un valor especificado.<sup>1</sup>|
|..|propiedad: valor1.. valor1|Indica que la propiedad que se busca es mayor o igual que el valor 1 y menor o igual que el valor 2.<sup>1</sup>|
|"  "|"valor razonable"  <br/> subject:"Finanzas trimestrales"|Use comillas dobles ("") para buscar una frase o término exacto en la palabra clave `property:value` y consultas de búsqueda.|
|\*|cat\*  <br/> subject:set\*|Las búsquedas con caracteres comodín de prefijo (donde el asterisco se coloca al final de una palabra) coinciden con cero o más caracteres en palabras clave o consultas  `property:value`. Por ejemplo, `title:set*` devuelve documentos que contienen la palabra Set, setup y Setting (y otras palabras que comienzan con "SET") en el título del documento.  <br/><br/> **Nota:** Solo puede usar la búsqueda de caracteres comodín de prefijo; por ejemplo, **CAT\* ** o **set\***. No se admiten las búsquedas de sufijos (**\*CAT** ), las búsquedas infijas (**\*c t**) y las búsquedas de subcadenas (**\*CAT\***).|
|(  )| (razonable OR libre) AND from:contoso.com  <br/> (IPO OR inicial) AND (acciones OR cuotas)  <br/> (finanzas trimestrales)|Los paréntesis agrupan frases booleanas, elementos  `property:value` y palabras clave. Por ejemplo,  `(quarterly financials)` devuelve los elementos que contienen las palabras trimestral y finanzas.  |
|||||
   
> [!NOTE]
> <sup>1</sup> use este operador para las propiedades que tienen valores numéricos o de fecha.<br/> <sup>2</sup> los operadores de búsqueda booleanos deben estar en mayúsculas; por ejemplo, **y**. Si usa un operador en minúsculas, como **y**, se tratará como una palabra clave en la consulta de búsqueda. 
  
## <a name="search-conditions"></a>Condiciones de búsqueda

Puede agregar condiciones a una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta cuando se inicia la búsqueda.
  
[Condiciones para las propiedades comunes ](#conditions-for-common-properties)

[Condiciones para las propiedades de correo](#conditions-for-mail-properties)

[Condiciones para las propiedades de documento](#conditions-for-document-properties)

[Operadores usados con condiciones](#operators-used-with-conditions)

[Directrices para el uso de condiciones](#guidelines-for-using-conditions)

[Ejemplos](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Condiciones para las propiedades comunes

Cree una condición mediante propiedades comunes al buscar en buzones y sitios de la misma búsqueda. En la siguiente tabla se enumeran las propiedades disponibles que se deben usar al agregar una condición.
  
|**Condición**|**Descripción**|
|:-----|:-----|
|Fecha|Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. Para los documentos, la fecha en que se modificó por última vez un documento.|
|Remitente/autor|Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona mencionada en el campo del autor de documentos de Office. Puede escribir más de un nombre, separados por comas. Dos o más valores están conectados de forma lógica por el operador de **OR**.|
|Tamaño (en bytes)|Para los correos electrónicos y documentos, el tamaño del elemento (en bytes).|
|Asunto/título|Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. Como se ha explicado anteriormente, la propiedad title es metadatos especificados en los documentos de Microsoft Office. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de **OR**.|
|Etiqueta de cumplimiento|Para correo electrónico y documentos, etiquetas que se han asignado a mensajes y documentos automáticamente mediante etiquetas o directivas que los usuarios han asignado manualmente. Las etiquetas se usan para clasificar el correo electrónico y los documentos para el gobierno de datos y aplicar las reglas de retención en función de la clasificación definida por la etiqueta. Puede escribir parte del nombre de la etiqueta y usar un comodín o escribir el nombre completo de la etiqueta. Para obtener más información, vea [información general sobre las etiquetas en Office 365](labels.md).|
|||
  
### <a name="conditions-for-mail-properties"></a>Condiciones para las propiedades de correo

Cree una condición con las propiedades de correo al buscar buzones o carpetas públicas. En la siguiente tabla se enumeran las propiedades de correo electrónico que se pueden usar para una condición. Estas propiedades son un subconjunto de las propiedades de correo electrónico descritas anteriormente. Estas descripciones se repiten para su comodidad.
  
|**Condición**|**Descripción**|
|:-----|:-----|
|Tipo de mensaje| El tipo de mensaje para buscar. Se trata de la misma propiedad que la propiedad de correo electrónico Tipo. Valores posibles:  <br/><br/>  contactos  <br/>  documentos  <br/>  correo electrónico  <br/>  externaldata  <br/>  faxes  <br/>  mensajería instantánea  <br/>  diarios  <br/>  reuniones  <br/>  Microsoft Teams  <br/>  notas  <br/>  entradas  <br/>  fuentes rss  <br/>  tareas  <br/>  correo de voz|
|Participantes|Todos los campos de personas en un mensaje de correo electrónico. Estos campos son de, para, CC y CCO.|
|Tipo|La propiedad de clase de mensaje de un elemento de correo electrónico. Se trata de la misma propiedad que la propiedad de correo electrónico ItemClass. También es una condición de varios valores. Para seleccionar varias clases de mensaje, mantenga presionada la tecla **Ctrl** y, a continuación, haga clic en dos o más clases de mensajes en la lista desplegable que desea agregar a la condición. Cada clase de mensaje que seleccione en la lista estará conectada lógicamente mediante el operador **or** en la consulta de búsqueda correspondiente.  <br/> Para obtener una lista de las clases de mensaje (y el identificador de clase de mensaje correspondiente) que usa Exchange y que puede seleccionar en la lista de **clase de mensaje** , vea [tipos de elementos y clases de mensajes](https://go.microsoft.com/fwlink/?linkid=848143).|
|Received|La fecha en la que un destinatario recibió un mensaje de correo electrónico. Se trata de la misma propiedad que la propiedad de correo electrónico Recibido.|
|Destinatarios|Todos los campos de destinatarios en un mensaje de correo electrónico. Estos campos son para, CC y CCO.|
|Remitente|El remitente de un mensaje de correo electrónico.|
|Sent|La fecha en la que un remitente envió un mensaje de correo electrónico. Se trata de la misma propiedad que la propiedad de correo electrónico Enviado.|
|Subject|El texto en la línea de asunto de un mensaje de correo electrónico.|
|To|El destinatario de un mensaje de correo electrónico en el campo para.|
|||
  
### <a name="conditions-for-document-properties"></a>Condiciones para las propiedades de documento

Cree una condición con propiedades de documento al buscar documentos en sitios de SharePoint y OneDrive para la empresa. En la siguiente tabla se enumeran las propiedades de documento que se pueden usar para una condición. Estas propiedades son un subconjunto de las propiedades del sitio descritas anteriormente. Estas descripciones se repiten para su comodidad.
  
|**Condición**|**Descripción**|
|:-----|:-----|
|Autor|El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que la carga a SharePoint, el documento seguirá conservando el autor original.|
|Title|El título del documento. La propiedad Título son metadatos que se especifican en los documentos de Office. Es diferente del nombre de archivo del documento.|
|Created|La fecha en la que se creó el documento.|
|Última modificación|La fecha en la que el documento se modificó por última vez.|
|Tipo de archivo|La extensión de un archivo; por ejemplo, docx, One, pptx o XLSX. Se trata de la misma propiedad que la propiedad del sitio FileExtension.|
|||
  
### <a name="operators-used-with-conditions"></a>Operadores usados con condiciones

Cuando se agrega una condición, puede seleccionar un operador que sea pertinente para el tipo de propiedad de la condición. En la tabla siguiente se describen los operadores que se usan con condiciones y se enumera el equivalente que se usa en la consulta de búsqueda.
  
|**Operator**|**Equivalente de consulta**|**Descripción**|
|:-----|:-----|:-----|
|After|`property>date`|Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron después de la fecha especificada. |
|Antes|`property<date`|Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron antes de la fecha especificada.|
|Entre|`date..date`|Se usa con condiciones de fecha y tamaño. Cuando se usa con una condición de fecha, devuelve los elementos que se enviaron, recibieron o modificaron durante el intervalo de fechas especificado. Cuando se usa con una condición de tamaño, devuelve los elementos cuyo tamaño está dentro del intervalo especificado.|
|Contiene cualquiera de|`(property:value) OR (property:value)`|Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que contienen cualquier parte de uno o más valores de cadena especificados.|
|No contiene ninguno de|`-property:value`  <br/> `NOT property:value`|Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen ninguna parte del valor de cadena especificado.|
|No es igual a ninguno de|`-property=value`  <br/> `NOT property=value`|Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen la cadena especificada.|
|Igual a|`size=value`|Devuelve elementos que son iguales al tamaño especificado. <sup>1</sup>|
|Es igual a cualquiera de|`(property=value) OR (property=value)`|Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que coinciden exactamente con uno o más valores de cadena especificados.|
|Mayor|`size>value`|Devuelve los elementos en los que la propiedad especificada es mayor que el valor especificado. <sup>1</sup>|
|Mayor o igual|`size>=value`|Devuelve los elementos en los que la propiedad especificada es mayor o igual que el valor especificado. <sup>1</sup>|
|Mínima|`size<value`|Devuelve elementos que son mayores o iguales que el valor específico. <sup>1</sup>|
|Menor o igual|`size<=value`|Devuelve elementos que son mayores o iguales que el valor específico. <sup>1</sup>|
|No es igual|`size<>value`|Devuelve elementos que no son iguales al tamaño especificado. <sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup> este operador solo está disponible para las condiciones que usan la propiedad Size. 
  
### <a name="guidelines-for-using-conditions"></a>Directrices para el uso de condiciones

Tenga en cuenta lo siguiente al usar condiciones de búsqueda.
  
- Una condición se conecta lógicamente a la consulta de palabra clave (especificada en el cuadro de palabra clave) mediante el operador **AND**. Eso significa que los elementos tienen que satisfacer la consulta de palabra clave y la condición para que se incluyan en los resultados. De esta manera, las condiciones permiten restringir los resultados. 
    
- Si agrega dos o más condiciones únicas a una consulta de búsqueda (condiciones que especifican propiedades diferentes), las condiciones se conectan lógicamente mediante el operador **and** . Esto significa que solo se devuelven los elementos que satisfacen todas las condiciones (además de cualquier consulta de palabras clave). 
    
- Si agrega más de una condición a la misma propiedad, las condiciones se conectan lógicamente mediante el operador **OR**. Eso significa que se devuelven los elementos que satisfacen la consulta de palabras clave y cualquiera de las condiciones. Por lo tanto, los grupos de las mismas condiciones se conectan entre sí mediante el operador **OR** y, después, los conjuntos de condiciones únicas se conectan mediante el operador **AND**. 
    
- Si agrega varios valores (separados por comas o puntos y coma) a una única condición, esos valores están conectados por el operador **or** . Eso significa que se devuelven los elementos que contengan cualquiera de los valores especificados para la propiedad en la condición. 
    
- La consulta de búsqueda que se crea mediante el cuadro palabras clave y las condiciones se muestra en la página **búsqueda** , en el panel de detalles de la búsqueda seleccionada. En una consulta, todo a la derecha de la notación `(c:c)` indica las condiciones que se agregan a la consulta. 
    
- Las condiciones solo agregan propiedades a la consulta de búsqueda, no agregan operadores. Esta es la razón por la que la consulta mostrada en el panel de detalles no muestra `(c:c)` los operadores a la derecha de la notación. KQL agrega operadores lógicos (según las reglas explicadas anteriormente) al ejecutar la consulta. 
    
- Puede usar el control de arrastrar y colocar para reordenar el orden de las condiciones. Haga clic en el control para una condición y muévala hacia arriba o hacia abajo.
    
- Como se explicó anteriormente, algunas propiedades de condición permiten escribir varios valores. Cada valor se conecta lógicamente mediante el operador **OR**. Esto da como resultado la misma lógica que si se tuvieran varias instancias de la misma condición, donde cada una tiene un solo valor. En las ilustraciones siguientes se muestra un ejemplo de una condición única con varios valores y un ejemplo de varias condiciones (para la misma propiedad) con un único valor. Ambos ejemplos dan como resultado la misma consulta:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![Un mensaje debe coincidir con todas las condiciones de la regla. Si necesita alternar la coincidencia entre una condición y otra, use reglas independientes para cada condición. Por ejemplo, si desea agregar la misma declinación de responsabilidad a los mensajes con archivos adjuntos y a los mensajes cuyo contenido coincide con un patrón, cree una regla para cada condición. Puede copiar fácilmente una regla.](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Varias condiciones de búsqueda para la misma propiedad](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> Si una condición acepta varios valores, le recomendamos que use una sola condición y que especifique varios valores (separados por comas o por punto y coma). Esto ayuda a garantizar que la lógica de consulta que se aplica es la deseada. 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Ejemplos

En los ejemplos siguientes se muestra la versión basada en la interfaz gráfica de usuario de una consulta de búsqueda con condiciones, la sintaxis de la consulta de búsqueda que se muestra en el panel de detalles de la búsqueda seleccionada (también devuelta por el cmdlet **Get-ComplianceSearch** ) y la lógica del consulta de KQL correspondiente. 
  
#### <a name="example-1"></a>Ejemplo 1

En este ejemplo se devuelven los documentos de los sitios de SharePoint y OneDrive para la empresa que contienen un número de tarjeta de crédito y se modificaron por última vez antes del 1 de enero de 2016.
  
 **GUI**
  
![Primer ejemplo de condiciones de búsqueda](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **Sintaxis de la consulta de búsqueda**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **Lógica de la consulta de búsqueda**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>Ejemplo 2

Este ejemplo devuelve elementos de correo electrónico o documentos que contienen la palabra clave "informe", que se enviaron o crearon antes del 1 de abril de 2015 y que contienen la palabra "Northwind" en el campo de asunto de los mensajes de correo electrónico o en la propiedad Título de los documentos. La consulta excluye páginas web que cumplen los demás criterios de búsqueda. 
  
 **GUI**
  
![Segundo ejemplo de condiciones de búsqueda](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **Sintaxis de la consulta de búsqueda**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **Lógica de la consulta de búsqueda**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>Ejemplo 3
<a name="conditionexamples"> </a>

En este ejemplo se devuelven mensajes de correo electrónico o reuniones del calendario que se enviaron entre 12/1/2016 y 11/30/2016 y que contienen palabras que comienzan con "Phone" o "smartphone".
  
 **GUI**
  
![Tercer ejemplo de condiciones de búsqueda](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Sintaxis de la consulta de búsqueda**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **Lógica de la consulta de búsqueda**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>Búsqueda de contenido de sitio compartido con usuarios externos

También puede usar la característica de búsqueda de contenido en el centro de seguridad & cumplimiento para buscar documentos almacenados en SharePoint y los sitios de OneDrive para la empresa que se han compartido con usuarios fuera de la organización. Esto puede ayudarle a identificar información confidencial o de propiedad que esté compartiéndose fuera de su organización. Para ello, puede usar la `ViewableByExternalUsers` propiedad en una consulta de palabras clave. Esta propiedad devuelve documentos o sitios que se han compartido con usuarios externos mediante uno de los siguientes métodos de uso compartido: 
  
- Una invitación para uso compartido que requiere que los usuarios inicien sesión en su organización como un usuario autenticado.
    
- Un vínculo de invitado anónimo, que permite que cualquier usuario con este vínculo obtenga acceso al recurso sin tener que autenticarse.
    
Aquí le mostramos otros ejemplos:
  
- La consulta `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` devuelve todos los elementos que se han compartido con personas fuera de la organización y contienen un número de tarjeta de crédito. 
    
- La consulta `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` devuelve una lista de documentos en todos los sitios de grupo de la organización que se han compartido con usuarios externos. 
    
> [!TIP]
> Una consulta de búsqueda como `ViewableByExternalUsers:true AND ContentType:document` puede devolver una gran cantidad de archivos. aspx en los resultados de búsqueda. Para eliminar estos (u otros tipos de archivos), puede usar la `FileExtension` propiedad para excluir tipos de archivo específicos; por ejemplo `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`. 
  
¿Qué se considera contenido que se comparte con personas externas de su organización? Documentos de los sitios de SharePoint y OneDrive para la empresa de la organización que se comparten mediante el envío de una invitación de uso compartido o que se comparten en ubicaciones públicas. Por ejemplo, las siguientes actividades de usuario dan lugar a contenido que es visible para los usuarios externos:
  
- Un usuario comparte un archivo o una carpeta con una persona externa a su organización.
    
- Un usuario crea y envía un vínculo a un archivo compartido a una persona externa a su organización. Este vínculo permite al usuario externo ver (o editar) el archivo.
    
- Un usuario envía una invitación de uso compartido o un vínculo de invitado a una persona externa a su organización para ver (o editar) un archivo compartido.
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Problemas al usar la propiedad ViewableByExternalUsers

Aunque la `ViewableByExternalUsers` propiedad representa el estado de si un documento o sitio se comparte con usuarios externos, hay algunas advertencias sobre lo que esta propiedad hace y no refleja. En los siguientes escenarios, el valor de la `ViewableByExternalUsers` propiedad no se actualizará y los resultados de una consulta de búsqueda de contenido que use esta propiedad pueden ser imprecisos. 
  
- Cambios en la Directiva de uso compartido, como desactivar el uso compartido externo de un sitio o de la organización. La propiedad seguirá mostrando los documentos previamente compartidos como accesibles externamente, aunque el acceso externo podría haber sido revocado.
    
- Cambios en la pertenencia a grupos, como agregar o quitar usuarios externos a grupos de seguridad de Office 365 o grupos de Office 365. La propiedad no se actualizará automáticamente para los elementos a los que tiene acceso el grupo.
    
- Enviar invitaciones para uso compartido a usuarios externos en los que el destinatario no aceptó la invitación y, por lo tanto, todavía no tiene acceso al contenido.
    
En estos escenarios, la `ViewableByExternalUsers` propiedad no reflejará el estado de uso compartido actual hasta que se vuelva a rastrear y reindizar el sitio o la biblioteca de documentos. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Búsqueda de contenido de sitio compartido dentro de la organización

Como se ha explicado anteriormente, puede `SharedWithUsersOWSUser` usar la propiedad para buscar documentos que se han compartido entre las personas de su organización. Cuando una persona comparte un archivo (o una carpeta) con otro usuario dentro de la organización, aparece un vínculo al archivo compartido en la página compartidos **conmigo** en la cuenta de OneDrive para la empresa de la persona con la que se compartió el archivo. Por ejemplo, para buscar los documentos que se han compartido con Sara Davis, puede usar la consulta `SharedWithUsersOWSUser:"sarad@contoso.com"`. Si exporta los resultados de esta búsqueda, se descargarán los documentos originales (que se encuentran en la ubicación del contenido de la persona que compartió los documentos con Sara).
  
Los documentos deben compartirse explícitamente con un usuario específico para que se devuelvan `SharedWithUsersOWSUser` en los resultados de la búsqueda cuando se usa la propiedad. Por ejemplo, cuando una persona comparte un documento en su cuenta de OneDrive, tiene la opción de compartirlo con cualquier persona (dentro o fuera de la organización), compartirlo solo con los miembros de la organización o compartirlo con una persona específica. Esta es una captura de pantalla de la ventana **compartir** en OneDrive, que muestra las tres opciones de uso compartido. 
  
![En una consulta de búsqueda que usa la propiedad SharedWithUsersOWSUser solo se devolverán los archivos compartidos con personas específicas.](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Solo los documentos compartidos mediante la tercera opción (compartidos con **personas específicas**) se devolverán mediante una consulta de `SharedWithUsersOWSUser` búsqueda que use la propiedad. 

## <a name="searching-for-skype-for-business-conversations"></a>Buscar conversaciones de Skype empresarial

Puede usar la siguiente consulta de palabras clave para buscar específicamente contenido en las conversaciones de Skype empresarial:

```
kind:im
```

La consulta de búsqueda anterior también devuelve chats de Microsoft Teams. Para evitarlo, puede restringir los resultados de la búsqueda para incluir solo conversaciones de Skype empresarial con la siguiente consulta de palabras clave:

```
kind:im AND subject:conversation
```

La consulta de palabra clave anterior excluye chats en Microsoft Teams porque las conversaciones de Skype empresarial se guardan como mensajes de correo electrónico con una línea de asunto que comienza con la palabra "Conversation".

Para buscar conversaciones de Skype empresarial que se hayan producido dentro de un intervalo de fechas específico, use la siguiente consulta de palabra clave:

```
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>Trucos y sugerencias de búsqueda

- Las búsquedas de palabras clave no distinguen entre mayúsculas y minúsculas. Por ejemplo, tanto si escribe **gato** como **GATO**, obtendrá los mismos resultados. 
    
- Los operadores booleanos **and**, **or**, **Not**, **Near**y **ONEAR** deben estar en mayúsculas. 
    
- A space between two keywords or two  `property:value` expressions is the same as using **AND**. Por ejemplo, `from:"Sara Davis" subject:reorganization` devuelve todos los mensajes enviados por Sara Davis que contienen la palabra reorganización en la línea de asunto. 
    
- Use una sintaxis que coincida `property:value` con el formato. Los valores no distinguen mayúsculas de minúsculas y no pueden tener un espacio después del operador. Si hay un espacio, el valor previsto será una búsqueda de texto completo. Por ejemplo `to: pilarp` , busca "pilarp" como palabra clave, en lugar de para los mensajes que se enviaron a pilarp. 
    
- Al buscar una propiedad de destinatario, como Para, De, Cc o los destinatarios, puede utilizar una dirección SMTP, un alias o un nombre para mostrar para indicar un destinatario. Por ejemplo, puede utilizar pilarp@contoso.com, pilarp o "Pilar Pinilla".
    
- Solo puede usar la búsqueda de caracteres comodín de prefijo; por ejemplo, **CAT\* ** o **set\***. No se admiten las búsquedas de sufijos (**\*CAT**), las búsquedas infijas (**\*c t**) y las búsquedas de subcadenas (**\*CAT\***). 
    
- Al buscar una propiedad, use comillas dobles ("") si el valor de búsqueda consta de varias palabras. Por ejemplo `subject:budget Q1` , devuelve los mensajes que contienen **presupuesto** en la línea de asunto y que contienen el **primer trimestre** en cualquier lugar del mensaje o en cualquiera de las propiedades del mensaje. El `subject:"budget Q1"` uso de devuelve todos los mensajes que contienen **Budget Q1** en cualquier lugar de la línea de asunto. 
    
- Para excluir de los resultados de la búsqueda el contenido marcado con un valor de propiedad determinado, coloque un signo menos (-) delante del nombre de la propiedad. Por ejemplo, `-from:"Sara Davis"` excluye los mensajes enviados por Sara Davis.

- Algunos caracteres especiales no se incluyen en el índice de búsqueda y, por lo tanto, no se pueden buscar, entre ellos se incluyen los operadores para la búsqueda (+-=:) y los siguientes caracteres que se reemplazan por un $null o pueden producir errores si se buscan! @ #% ^ &; _ / ?

- Puede exportar elementos en función del tipo de mensaje. Por ejemplo, para exportar conversaciones y chats de Skype en Microsoft Teams, use `kind:im`la sintaxis. Para devolver solo los mensajes de correo electrónico, `kind:email`debe usar. Para devolver chats, reuniones y llamadas en Microsoft Teams, use `kind:microsoftteams`.

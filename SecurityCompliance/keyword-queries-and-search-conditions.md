---
title: Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: 'Obtenga información acerca de las propiedades de correo electrónico y el archivo que se pueden buscar en buzones de Exchange Online y en SharePoint o OneDrive para los sitios de negocio con la herramienta de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento.  '
ms.openlocfilehash: a797a8d6dd616616c5dc8606c3e3043530e873c3
ms.sourcegitcommit: 7675230c9cda25cbf7ad7d4cadf4372c03789cf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "24015361"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido

En este tema se describe las propiedades de correo electrónico y documentos que se pueden buscar en los elementos de correo electrónico en Exchange Online y los documentos almacenados en SharePoint y sitios de OneDrive para la empresa mediante el uso de la característica de búsqueda de contenido en la seguridad de Office 365 &amp; cumplimiento Centro. También puede usar el ** \*- ComplianceSearch** cmdlets en seguridad &amp; PowerShell de centro de cumplimiento para buscar estas propiedades. También se describe el tema:   
  
- Uso de operadores de búsqueda booleanos, condiciones de búsqueda y otras técnicas de consulta de búsqueda para restringir los resultados de búsqueda.
    
- Búsqueda de tipos de datos confidenciales y tipos de datos confidenciales personalizado en SharePoint y OneDrive para la empresa.
    
- Búsqueda de contenido de sitio que se comparte con usuarios externos a su organización
    
Para obtener instrucciones paso a paso sobre cómo crear una búsqueda de contenido, consulte [Búsqueda de contenido en Office 365](content-search.md). |

  
> [!NOTE]
> Búsqueda en la seguridad de contenido &amp; centro de cumplimiento y la correspondiente ** \*- ComplianceSearch** cmdlets en seguridad &amp; PowerShell de centro de cumplimiento usar el lenguaje de consulta de palabras clave (KQL). Para obtener información más detallada, vea [referencia de sintaxis de lenguaje de consulta de palabra clave](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## <a name="searchable-email-properties"></a>Propiedades del correo electrónico que permiten búsquedas

En la siguiente tabla se enumera las propiedades de mensaje de correo electrónico que se pueden buscar mediante la característica de búsqueda de contenido en la seguridad &amp; centro de cumplimiento o mediante el **Nuevo ComplianceSearch** o el cmdlet **Set-ComplianceSearch** . La tabla incluye un ejemplo de la sintaxis _: valor de la propiedad_ para cada propiedad y una descripción de los resultados de búsqueda devueltos por los ejemplos. Puede escribir estos `property:value` cuadro pares de las palabras clave para una búsqueda de contenido. 
  
|**Propiedad**|**Descripción de la propiedad**|**Ejemplos**|**Resultados de la búsqueda devueltos por los ejemplos**|
|:-----|:-----|:-----|:-----|
|AttachmentNames  <br/> |Los nombres de los archivos adjuntos a un mensaje de correo electrónico.  <br/> |`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual\*`  <br/> |Los mensajes con un archivo adjunto denominado informeanual.ppt. En el segundo ejemplo, el uso del comodín devuelve los mensajes con la palabra "anual" en el nombre de un archivo adjunto.  <br/> |
|Bcc  <br/> |El campo CCO de un mensaje de correo electrónico.<sup>1</sup> <br/> |`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`  <br/> |Todos los ejemplos devuelven los mensajes que incluyen a Pilar Pinilla en el campo CCO.  <br/> |
|Category  <br/> | Las categorías para buscar. Los usuarios pueden definir las categorías mediante Outlook o Outlook Web App. Los valores posibles son:  <br/><br/>  azul  <br/>  verde  <br/>  naranja  <br/>  púrpura  <br/>  rojo  <br/>  amarillo  <br/> |`category:"Red Category"`  <br/> |Los mensajes a los que se ha asignado la categoría roja en los buzones de origen.  <br/> |
|CC  <br/> |El campo CC de un mensaje de correo electrónico.<sup>1</sup> <br/> |`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`  <br/> |En ambos ejemplos, los mensajes que especifican a Pilar Pinilla en el campo CC.  <br/> |
|Folderid  <br/> |La carpeta identificador (GUID) de una carpeta de buzón específico. Si utiliza esta propiedad, asegúrese de buscar en el buzón que se encuentra la carpeta especificada en. Tenga en cuenta que se buscarán sólo la carpeta especificada. No se busca en todas las subcarpetas de la carpeta. Para buscar las subcarpetas, debe usar la propiedad Folderid para la subcarpeta que desea buscar.<br/> Para obtener más información acerca de la búsqueda para la propiedad Folderid y uso de una secuencia de comandos para obtener la carpeta identificadores para un buzón específico, vea [Usar la búsqueda de contenido en Office 365 para las colecciones de destinadas](use-content-search-for-targeted-collections.md).  <br/> |`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`  <br/> |El primer ejemplo devuelve todos los elementos en la carpeta de buzón de correo especificado. El segundo ejemplo, se devuelven todos los elementos en la carpeta de buzón de correo especificado que se han enviado o recibido por garthf@contoso.com.  <br/> |
|De  <br/> |El remitente de un mensaje de correo electrónico.<sup>1</sup> <br/> |`from:pilarp@contoso.com`  <br/> `from:contoso.com`  <br/> |Los mensajes enviados por el usuario especificado o enviados desde un dominio especificado.  <br/> |
|HasAttachment  <br/> |Indica si un mensaje tiene datos adjuntos. Use los valores **true** o **false**.<br/> |`from:pilar@contoso.com AND hasattachment:true`  <br/> |Mensajes enviados por el usuario especificado que tienen datos adjuntos.  <br/> |
|Importance  <br/> |La importancia de un mensaje de correo electrónico, que un remitente puede especificar al enviar un mensaje. De manera predeterminada, los mensajes se envían con importancia normal, a menos que el remitente establezca la importancia como **alta** o **baja**.  <br/> |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`  <br/> |Los mensajes que están marcados con importancia alta, importancia media o importancia baja.  <br/> |
|Estáleído  <br/> |Indica si los mensajes se han leído. Use los valores **true** o **false**.<br/> |`isread:true`  <br/> `isread:false`  <br/> |El primer ejemplo devuelve los mensajes con la propiedad estáleído establecida en **True**. El segundo ejemplo devuelve los mensajes con la propiedad estáleído establecida en **False**.<br/> |
|ItemClass  <br/> |Use esta propiedad para buscar los tipos de datos específicos de otro fabricante que su organización se importa a Office 365. Use la siguiente sintaxis para esta propiedad:`itemclass:ipm.externaldata.<third-party data type>*` <br/> |`itemclass:ipm.externaldata.Facebook\* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter\* AND from:"Ann Beebe" AND "Northwind Traders"`  <br/> |El primer ejemplo devuelve los elementos de Facebook que contienen la palabra "contoso" en la propiedad Subject. El segundo ejemplo devuelve elementos de Twitter que se contabilizaron por Ann Beebe y que contengan la frase de palabras clave "Northwind Traders".<br/> Para obtener una lista completa de los valores que se usará para tipos de datos de terceros para la propiedad ItemClass, vea [Usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).  <br/> |
|Tipo  <br/> | El tipo de mensaje de correo electrónico para buscar. Valores posibles:  <br/>  contactos  <br/>  documentos  <br/>  correo electrónico  <br/>  externaldata  <br/>  faxes  <br/>  mensajería instantánea  <br/>  diarios  <br/>  reuniones  <br/>  microsoftteams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams)  <br/>  notas  <br/>  entradas  <br/>  fuentes rss  <br/>  tareas  <br/>  correo de voz  <br/> |`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`  <br/> |El primer ejemplo devuelve los mensajes de correo electrónico que cumplen los criterios de búsqueda. El segundo ejemplo devuelve los mensajes de correo electrónico, las conversaciones de mensajería instantáneas y los mensajes de voz que cumplen los criterios de búsqueda. El tercer ejemplo devuelve los elementos que se han importado a buzones de correo en Office 365 de orígenes de datos de terceros, como Twitter, Facebook y Cisco Jabber, que cumplen los criterios de búsqueda. Para obtener más información, vea [datos de terceros de archivado en Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).<br/> |
|Participantes  <br/> |Todos los campos de personas en un mensaje de correo electrónico. Estos campos son De, Para, CC y CCO.<sup>1</sup> <br/> |`participants:garthf@contoso.com`  <br/> `participants:contoso.com`  <br/> |Los mensajes enviados por o a garthf@contoso.com. El segundo ejemplo devuelve todos los mensajes enviados por o a un usuario en el dominio contoso.com.  <br/> |
|Received  <br/> |La fecha en la que un destinatario recibió un mensaje de correo electrónico.  <br/> |`received:04/15/2016`  <br/> `received\>=01/01/2016 AND received\<=03/31/2016`  <br/> |Mensajes recibidos en el 15 de abril de 2016. El segundo ejemplo devuelve todos los mensajes recibidos entre el 1 de enero de 2016 y el 31 de marzo de 2016.  <br/> |
|Destinatarios  <br/> |Todos los campos de destinatarios en un mensaje de correo electrónico. Estos campos son Para, CC y CCO.<sup>1</sup> <br/> |`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`  <br/> |Los mensajes enviados a garthf@contoso.com. El segundo ejemplo devuelve los mensajes enviados a cualquier destinatario en el dominio contoso.com.  <br/> |
|Sent  <br/> |La fecha en la que un remitente envió un mensaje de correo electrónico.  <br/> |`sent:07/01/2016`  <br/> `sent\>=06/01/2016 AND sent\<=07/01/2016`  <br/> |Mensajes que se enviaron en la fecha especificada o que se enviaron dentro del intervalo de fechas especificado.  <br/> |
|Size  <br/> |El tamaño de un elemento, en bytes.  <br/> |`size\>26214400`  <br/> `size:1..1048567`  <br/> |Mensajes de más de 25?? MB. El segundo ejemplo devuelve los mensajes entre 1 y el tamaño de 1,048,567 bytes (1 MB).  <br/> |
|Subject  <br/> |El texto en la línea de asunto de un mensaje de correo electrónico.  <br/> **Nota:** Cuando se utiliza la propiedad Subject en una consulta, búsqueda ???the devuelve todos los mensajes en los que la línea de asunto contenga el texto que se va a buscar. En otras palabras, la consulta no devuelve sólo los mensajes que tienen una coincidencia exacta. Por ejemplo, si busca `subject:"Quarterly Financials"`, los resultados incluirán los mensajes con el asunto "2018 Financials trimestral".<br/> |`subject:"Quarterly Financials"`  <br/> `subject:northwind`  <br/> |Mensajes que contengan la frase "Finanzas trimestrales" en cualquier lugar en el texto de la línea de asunto. El segundo ejemplo devuelve todos los mensajes que contienen la palabra northwind en la línea de asunto.  <br/> |
|To  <br/> |El campo Para de un mensaje de correo electrónico.<sup>1</sup> <br/> |`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`  <br/> |Todos los ejemplos devuelven mensajes en los que Ann Beebe está especificada en la línea Para.  <br/> |
   
> [!NOTE]
> <sup>1</sup> para el valor de una propiedad de destinatario, puede usar la dirección de correo electrónico (también llamado *nombre principal de usuario* o UPN), nombre para mostrar o alias para especificar un usuario. Por ejemplo, puede usar para especificar el usuario Ann Beebe annb@contoso.com, annb o "Ana Díaz".<br/><br/>Al buscar en cualquiera de las propiedades del destinatario (From, To, Cc, CCO, los participantes y destinatarios), Office 365 intenta expandir la identidad de cada usuario mirando migrarlos copia de seguridad en Active Directory de Azure.  Si el usuario se encuentra en Azure Active Directory, la consulta se expande para incluir el usuario correo electrónico dirección (o UPN), alias, nombre para mostrar y LegacyExchangeDN.<br/><br/>Por ejemplo, una consulta como `participants:ronnie@contoso.com` se expande para `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`.

## <a name="searchable-site-properties"></a>Propiedades de sitio que se pueden buscar

En la siguiente tabla se enumera algunos de SharePoint y OneDrive para las propiedades de negocio que se pueden buscar mediante la característica de búsqueda de contenido en la seguridad &amp; centro de cumplimiento o mediante el **Nuevo ComplianceSearch** o la ** Set-ComplianceSearch** cmdlet. La tabla incluye un ejemplo de la sintaxis _: valor de la propiedad_ para cada propiedad y una descripción de los resultados de búsqueda devueltos por los ejemplos. 
  
Para obtener una lista completa de las propiedades de SharePoint que se puede buscar, consulte [Overview of rastreadas y propiedades administradas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Se pueden buscar propiedades marcadas con un **Sí** en la columna **consultable** . 
  
|**Propiedad**|**Descripción de la propiedad**|**Ejemplo**|**Resultados de la búsqueda devueltos por los ejemplos**|
|:-----|:-----|:-----|:-----|
|Author  <br/> |El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y los mensajes de correo electrónico a otra persona que, a continuación, se carga en SharePoint, el documento conservará al autor original. Asegúrese de usar el nombre para mostrar del usuario para esta propiedad.  <br/> |`author:"Garth Fort"`  <br/> |Todos los documentos que se han creado por Juan Casanova.  <br/> |
|ContentType  <br/> |El tipo de contenido de SharePoint de un elemento, como vídeo, documento o elemento.  <br/> |`contenttype:document`  <br/> |Se devolverán todos los documentos.  <br/> |
|creados  <br/> |La fecha en la que se crea un elemento.  <br/> |`created\>=06/01/2016`  <br/> |Todos los elementos creados en o después del 1 de junio de 2016.  <br/> |
|CreatedBy  <br/> |La persona que crea o carga un elemento. Asegúrese de usar el nombre para mostrar del usuario para esta propiedad.  <br/> |`createdby:"Garth Fort"`  <br/> |Todos los elementos creados o cargados por Juan Casanova.  <br/> |
|DetectedLanguage  <br/> |El idioma de un elemento.  <br/> |`detectedlanguage:english`  <br/> |Todos los elementos en inglés.  <br/> |
|FileExtension  <br/> |La extensión de un archivo; Por ejemplo, docx, uno, pptx o xlsx.  <br/> |`fileextension:xlsx`  <br/> |Todos los archivos de Excel (Excel 2007 y versiones posterior)  <br/> |
|FileName  <br/> |El nombre de un archivo.  <br/> |`filename:"marketing plan"`  <br/> `filename:estimate`  <br/> |El primer ejemplo devuelve archivos con la frase exacta "plan de marketing" en el título. El segundo ejemplo devuelve archivos con la palabra "estimación" en el nombre del archivo.  <br/> |
|LastModifiedTime  <br/> |La fecha de la última modificación de un elemento.  <br/> |`lastmodifiedtime\>=05/01/2016`  <br/> `lastmodifiedtime\>=05/10/2016 AND lastmodifiedtime\<=06/1/2016`  <br/> |El primer ejemplo devuelve los elementos que se han cambiado en o después del 1 de mayo de 2016. El segundo ejemplo devuelve los elementos que han cambiado entre el 1 de mayo de 2016 y el 1 de junio de 2016.  <br/> |
|ModifiedBy  <br/> |La persona que modificó por última vez un elemento. Asegúrese de usar el nombre para mostrar del usuario para esta propiedad.  <br/> |`modifiedby:"Garth Fort"`  <br/> |Todos los elementos que Juan Casanova modificó por última vez.  <br/> |
|Path  <br/> |La ruta de acceso (dirección URL) de una carpeta específica en un SharePoint o OneDrive para el sitio de negocio. Si utiliza esta propiedad, asegúrese de buscar en el sitio que se encuentra la carpeta especificada en.<br/> Para devolver los elementos ubicados en las subcarpetas de la carpeta que especifique para la propiedad de ruta de acceso, tiene que agregar /\* a la dirección URL de la carpeta especificada; Por ejemplo, `path: https://contoso.sharepoint.com/Shared Documents/*`.  <br/> <br/> **Nota:** Uso de la `Path` propiedad a OneDrive ubicaciones de búsqueda no devolverá los archivos multimedia, como archivos .png, .tiff o .wav, en los resultados de búsqueda. Use una propiedad de sitio diferente en la consulta de búsqueda para buscar archivos multimedia en las carpetas de OneDrive.<br/> <br/> Para obtener más información acerca de la búsqueda para la propiedad de ruta de acceso y uso de una secuencia de comandos para obtener las direcciones URL de ruta de acceso para las carpetas en un sitio específico, vea [Usar la búsqueda de contenido en Office 365 para las colecciones de destinadas](use-content-search-for-targeted-collections.md).  <br/> |`path:https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/\*" AND filename:confidential`  <br/> |El primer ejemplo devuelve todos los elementos en el OneDrive especificada para la carpeta Business. El segundo ejemplo devuelve documentos en la carpeta del sitio especificado (y todas las subcarpetas) que contienen la palabra "confidential" en el nombre de archivo.  <br/> |
|SharedWithUsersOWSUser  <br/> |Documentos que se han compartido con el usuario especificado y que se muestra en la página **compartidos conmigo** en OneDrive del usuario para el sitio de negocio. Estos son los documentos que se han explícitamente compartidos con el usuario especificado por otras personas en su organización. Al exportar documentos que coinciden con una consulta de búsqueda que se utiliza la propiedad SharedWithUsersOWSUser, los documentos se exportan desde la ubicación original del contenido de la persona que comparte el documento con el usuario especificado. Para obtener más información, consulte [búsqueda de contenido de sitio compartidos dentro de la organización](keyword-queries-and-search-conditions.md#internal).<br/> |`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`  <br/> |Ambos ejemplos devuelven todos los documentos internos que se han compartido explícitamente con Luis fuertes y que aparecen en la página **compartidos conmigo** en Luis fuertes OneDrive para la cuenta de empresa.  <br/> |
|Sitio  <br/> |La dirección URL de un sitio o grupo de sitios de la organización.  <br/> |`site:https://contoso-my.sharepoint.com`  <br/> `site:https://contoso.sharepoint.com/sites/teams`  <br/> |El primer ejemplo devuelve los elementos de la OneDrive para sitios de negocio para todos los usuarios de la organización. El segundo ejemplo devuelve los elementos de todos los sitios de grupo.  <br/> |
|Size  <br/> |El tamaño de un elemento, en bytes.  <br/> |`size\>=1`  <br/> `size:1..10000`  <br/> |El primer ejemplo devuelve elementos mayores de 1 byte. El segundo ejemplo devuelve elementos que tienen un tamaño de entre 1 y 10 000 bytes.  <br/> |
|Título  <br/> |El título del documento. La propiedad Title es metadatos que se especifican en documentos de Microsoft Office. Es diferente del nombre de archivo del documento.  <br/> |`title:"communication plan"`  <br/> |Cualquier documento que contenga la frase "plan de comunicación" en la propiedad Título de metadatos de un documento de Office.  <br/> |
   
## <a name="searchable-contact-properties"></a>Propiedades de contacto que permiten búsquedas

En la siguiente tabla se enumera las propiedades de contacto que están indizadas y que pueden buscar para el uso de búsqueda de contenido. Estas son las propiedades que están disponibles para los usuarios a configurar para los contactos (también denominados contactos personales) que se encuentran en la libreta de direcciones personales del buzón de un usuario. Para buscar contactos, puede seleccionar los buzones de correo para buscar y, a continuación, utilice una o más propiedades de contacto en la consulta de palabra clave.
  
> [!TIP]
> Para buscar los valores que contienen espacios, usar comillas dobles ("??") para que contengan la frase; Por ejemplo, `businessaddress:"123 Main Street"`. 
  
|**Propiedad**|**Descripción de la propiedad**|
|:-----|:-----|
|BusinessAddress  <br/> |La dirección en la propiedad de **Dirección de la empresa** . La propiedad también se denomina la dirección de **trabajo** en la página de propiedades de contacto.<br/> |
|BusinessPhone  <br/> |El número de teléfono en cualquiera del **Teléfono del trabajo** de número de propiedades.  <br/> |
|CompanyName  <br/> |El nombre de la propiedad de la **compañía** .  <br/> |
|Departamento  <br/> |El nombre de la propiedad de **departamento** .  <br/> |
|DisplayName  <br/> |El nombre para mostrar del contacto. Éste es el nombre de la propiedad de **Nombre completo** del contacto.<br/> |
|EmailAddress  <br/> |La dirección de cualquier propiedad de dirección de correo electrónico del contacto. Tenga en cuenta que los usuarios pueden agregar varias direcciones de correo electrónico de un contacto. Uso de esta propiedad devolvería los contactos que coinciden con cualquiera de las direcciones de correo electrónico del contacto.  <br/> |
|Archivar como  <br/> |La propiedad de **archivo como** . Esta propiedad se utiliza para especificar el modo en que el contacto se incluye en la lista de contactos del usuario. Por ejemplo, un contacto podría aparecer como *FirstName, LastName* o *LastName, FirstName* .<br/> |
|GivenName  <br/> |El nombre de la propiedad de **nombre** .  <br/> |
|HomeAddress  <br/> |La dirección en cualquiera de las propiedades de la dirección **principal** .  <br/> |
|HomePhone  <br/> |El número de teléfono en cualquiera de teléfono **particular** de número de propiedades.  <br/> |
|Propiedad IMAddress  <br/> |La propiedad de dirección de mensajería instantánea, que normalmente es una dirección de correo electrónico que se usa para la mensajería instantánea.  <br/> |
|MiddleName  <br/> |El nombre de la propiedad name **intermedio** .  <br/> |
|MobilePhone  <br/> |El número de teléfono en el teléfono **móvil** de número (propiedad).  <br/> |
|Nickname  <br/> |El nombre de la propiedad **alias** .  <br/> |
|OfficeLocation  <br/> |El valor de propiedad de **Office** o la **ubicación de la oficina** .  <br/> |
|OtherAddress  <br/> |El valor de la **otra** propiedad de dirección.  <br/> |
|Surname  <br/> |El nombre de la **última** propiedad de nombre.  <br/> |
|Título  <br/> |El título en la propiedad **título del trabajo** .  <br/> |
   

## <a name="searchable-sensitive-data-types"></a>Tipos de datos confidenciales que se pueden buscar

Puede usar la característica de búsqueda de contenido en la seguridad &amp; centro de cumplimiento para buscar datos confidenciales, como números de tarjeta de crédito o números de la seguridad social, que se almacenan en documentos en SharePoint y OneDrive para sitios de negocio. Puede hacerlo mediante el uso de la `SensitiveType` escriba (propiedad) y el nombre de una información confidencial en una consulta de palabra clave. Por ejemplo, la consulta `SensitiveType:"Credit Card Number"` devuelve documentos que contienen un número de tarjeta de crédito. La consulta `SensitiveType:"U.S. Social Security Number (SSN)"` devuelven documentos que contiene un número de seguridad social de Estados Unidos. Para ver una lista de los tipos de datos confidenciales que puede buscar, vaya a **las clasificaciones** \> de **tipos de información confidencial** en la seguridad &amp; centro de cumplimiento. O puede usar el cmdlet **Get-DlpSensitiveInformationType** en la seguridad &amp; PowerShell de centro de cumplimiento para mostrar una lista de tipos de información confidencial. 
  
También puede usar el `SensitiveType` (propiedad) para buscar el nombre de un tipo de información confidencial personalizada que usted (u otro administrador) creado para la organización. Tenga en cuenta que puede usar la columna de **Publisher** en la página **tipos de información confidencial** en la seguridad &amp; centro de cumplimiento (o la propiedad de **Publisher** en PowerShell) para diferenciar entre confidenciales integradas y personalizadas tipos de información. Para obtener más información, vea [crear un tipo de información confidencial personalizada](create-a-custom-sensitive-information-type.md).
  
Para obtener más información acerca de la creación de consultas con el `SensitiveType` (propiedad), vea el [formulario una consulta para buscar datos confidenciales almacenados en los sitios](form-a-query-to-find-sensitive-data-stored-on-sites.md).
  
## <a name="search-operators"></a>Operadores de búsqueda

Operadores de búsqueda booleanos, como **AND**, **OR**y **no**, le ayudará a definir búsquedas más precisas, incluir o excluir palabras específicas en la consulta de búsqueda. Otras técnicas, como el uso de operadores de propiedad (como \>= o..), comillas dobles, paréntesis y caracteres comodín, le ayudarán a perfeccionar una consulta de búsqueda. En la siguiente tabla se enumera los operadores que puede usar para restringir o ampliar los resultados de búsqueda. 
  
|**Operador**|**Uso**|**Descripción**|
|:-----|:-----|:-----|
|AND  <br/> |palabra clave 1 AND palabra clave 2  <br/> |Devuelve elementos que incluyen todas las palabras clave especificadas o `property:value` expresiones. Por ejemplo, `from:"Ann Beebe" AND subject:northwind` devolvería todos los mensajes enviados por Ann Beebe que contenía la northwind de word en la línea de asunto. <sup>2</sup> <br/> |
|+  <br/> |palabraclave1 + palabra clave 2 + palabra clave 3  <br/> |Devuelve elementos que contienen  *o*  `keyword2` o  `keyword3` *y*  que también contienen  `keyword1`. Por tanto, este ejemplo es equivalente a la consulta  `(keyword2 OR keyword3) AND keyword1`.  <br/> Tenga en cuenta que la consulta `keyword1 + keyword2` (con un espacio después de la **+** símbolo) no es lo mismo que usar el ** AND ** operador. Esta consulta sería equivalente a `"keyword1 + keyword2"` y devolver elementos con la fase exacta `"keyword1 + keyword2"`.<br/> |
|OR  <br/> |palabra clave 1 OR palabra clave 2  <br/> |Devuelve elementos que incluyen una o varias de las palabras clave especificadas o `property:value` expresiones. <sup>2</sup> <br/> |
|NOT  <br/> |palabra clave 1 NOT palabra clave 2  <br/> NOT from:"Ann Beebe"  <br/> NO tipo: mensajería instantánea  <br/> |Excluye los elementos especificados por una palabra clave o un `property:value` expresión. En el segundo ejemplo, excluyen los mensajes enviados por Ann Beebe. El tercer ejemplo excluye cualquier conversaciones de mensajería instantánea, como Skype para las conversaciones de negocio que se guardan en la carpeta de buzón de correo de historial de conversaciones. <sup>2</sup> <br/> |
|-  <br/> |palabra clave 1 - palabra clave 2  <br/> |El mismo que el operador **NOT** . Por tanto, esta consulta devuelve los elementos que contienen `keyword1` y podrían excluir los elementos que contienen `keyword2`.<br/> |
|NEAR  <br/> |palabra clave 1 NEAR(n) palabra clave 2  <br/> |Devuelve los elementos con las palabras que están cerca entre sí, donde n es igual al número de separación de palabras. Por ejemplo, `best NEAR(5) worst` devuelve cualquier elemento donde es la palabra "peor" dentro de cinco palabras de "el mejor". Si se especifica ningún número, la distancia predeterminada es ocho palabras. <sup>2</sup> <br/> |
|ONEAR  <br/> |palabra clave 1 ONEAR(n) palabra clave 2  <br/> |Es similar a **cerca**, pero devuelve los elementos con las palabras que están cerca entre sí en el orden especificado. Por ejemplo, `best ONEAR(5) worst` devuelve cualquier elemento donde se produce la palabra "buenas" antes de la palabra "peor" y las dos palabras están dentro de cinco palabras de cada uno de los otros. Si se especifica ningún número, la distancia predeterminada es ocho palabras. <sup>2</sup> <br/> > [!NOTE]> El operador **ONEAR** no se admite al buscar en los buzones de correo; sólo funciona cuando se busca sitios profesionales en SharePoint y OneDrive. Si va a buscar en la misma búsqueda de buzones de correo y los sitios y la consulta incluye el operador **ONEAR** , la búsqueda devolverá los elementos del buzón como si estuviera utilizando el operador **NEAR** . En otras palabras, la búsqueda devuelve los elementos en los que las palabras especificadas están cerca entre sí independientemente del orden en el que se producen las palabras.           |
|:  <br/> |propiedad:valor  <br/> |Los dos puntos (:) en el `property:value` sintaxis especifica que el valor de la propiedad que se busca contiene el valor especificado. Por ejemplo, `recipients:garthf@contoso.com` devuelve los mensajes enviados a garthf@contoso.com.<br/> |
|=  <br/> |propiedad=valor  <br/> |El mismo que el operador de **:** .  <br/> |
|\<  <br/> |propiedad\<valor  <br/> |Indica que la propiedad que se busca es menor que el valor especificado. <sup>1</sup> <br/> |
|\>  <br/> |propiedad\>valor  <br/> |Indica que la propiedad que se busca es mayor que el valor especificado.<sup>1</sup> <br/> |
|\<=  <br/> |propiedad\<=valor  <br/> |Indica que la propiedad que se busca es menor o igual que un valor especificado.<sup>1</sup> <br/> |
|\>=  <br/> |propiedad\>=valor  <br/> |Indica que la propiedad que se busca es mayor o igual que un valor especificado.<sup>1</sup> <br/> |
|..  <br/> |propiedad: valor1.. valor2  <br/> |Indica que la propiedad que se busca es mayor o igual que el valor 1 y menor o igual que el valor 2.<sup>1</sup> <br/> |
|"  "  <br/> |"valor razonable"  <br/> subject:"Finanzas trimestrales"  <br/> |Utilice las comillas dobles ("") para buscar una frase exacta o término de palabra clave y `property:value` las consultas de búsqueda.  <br/> |
|\*  <br/> |cat\*  <br/> subject:set\*  <br/> |Prefijo de búsquedas con caracteres comodín (donde se coloca el asterisco al final de una palabra) coincide con cero o más caracteres en palabras clave o `property:value` consultas. Por ejemplo, `title:set*` devuelve documentos que contienen el conjunto de word, el programa de instalación y configuración (y otras palabras que comiencen por "conjunto") en el título del documento.<br/><br/> **Nota:** Puede usar sólo las búsquedas de caracteres comodín prefijo; Por ejemplo, **cat\* ** o **establecer\***. Las búsquedas de sufijos ( ** \*cat** ), las búsquedas de infijo ( **c\*t** ) y las búsquedas de subcadenas ( ** \*cat\* ** ) no son compatibles.           |
|(  )  <br/> | (razonable OR libre) AND from:contoso.com  <br/> (IPO OR inicial) AND (acciones OR cuotas)  <br/> (finanzas trimestrales)  <br/> |Los paréntesis agrupan frases booleanas, elementos  `property:value` y palabras clave. Por ejemplo,  `(quarterly financials)` devuelve los elementos que contienen las palabras trimestral y finanzas.  <br/> |
   
> [!NOTE]
> <sup>1</sup> use este operador para las propiedades que tienen valores numéricos o de fecha.<br/> <sup>2</sup> operadores de búsqueda booleanos deben escribirse en mayúsculas; Por ejemplo, **AND**. Si utiliza un operador en minúsculas, como **y**, se tratará como una palabra clave en la consulta de búsqueda. 
  
## <a name="search-conditions"></a>Condiciones de búsqueda

Puede agregar condiciones a una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda de palabras clave que se crean y ejecutan cuando se inicia la búsqueda.
  
[Condiciones para las propiedades comunes ](#conditions-for-common-properties)

[Condiciones para las propiedades de correo](#conditions-for-mail-properties)

[Condiciones para las propiedades de documento](#conditions-for-document-properties)

[Operadores usados con condiciones](#operators-used-with-conditions)

[Directrices para el uso de condiciones](#guidelines-for-using-conditions)

[Ejemplos del uso de condiciones en consultas de búsqueda](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Condiciones para las propiedades comunes 

Crear una condición mediante propiedades comunes al buscar en los buzones de correo y los sitios en la misma búsqueda. En la siguiente tabla se enumera las propiedades disponibles para usar cuando se agrega una condición.
  
|**Condición**|**Descripción**|
|:-----|:-----|
|Fecha  <br/> |Para el correo electrónico, la fecha de un mensaje se ha recibido por un destinatario o enviado por el remitente. Para los documentos, la fecha en que se modificó por última vez un documento.  <br/> |
|Remitente/Autor  <br/> |Para el correo electrónico, la persona que envió un mensaje. Para los documentos, la persona citada en el campo autor de documentos de Office. Puede escribir más de un nombre, separado por comas. Dos o más valores están conectados lógicamente mediante el operador **OR** .<br/> |
|Tamaño (en bytes)  <br/> |Para los correos electrónicos y documentos, el tamaño del elemento (en bytes).  <br/> |
|Asunto/Título  <br/> |Para el correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. Como se explica anteriormente, la propiedad Title es metadatos especificados en los documentos de Microsoft Office. Puede escribir el nombre de más de un asunto o título, separado por comas. Dos o más valores están conectados lógicamente mediante el operador **OR** .<br/> |
|Etiqueta de cumplimiento  <br/> |Para correo electrónico y documentos, las etiquetas que se han asignado a los mensajes y documentos automáticamente por las directivas de etiqueta o etiquetas que se asignó manualmente por los usuarios. Las etiquetas se usan para clasificar el correo electrónico y documentos de gobierno de datos y aplicar las reglas de retención basadas en la clasificación definida por la etiqueta. Puede escriba parte del nombre de etiqueta y usar un carácter comodín o escriba el nombre de la etiqueta completa. Para obtener más información, vea [información general de las etiquetas en Office 365](labels.md).<br/> |
  
### <a name="conditions-for-mail-properties"></a>Condiciones para las propiedades de correo

Cree una condición usando las propiedades de correo cuando busque buzones o carpetas públicas. En la tabla siguiente, se enumeran las propiedades de correo electrónico que puede usar para una condición. Tenga en cuenta que estas propiedades son un subconjunto de las propiedades de correo electrónico que se han descrito anteriormente. Estas descripciones se repiten para su comodidad.
  
|**Condición**|**Descripción**|
|:-----|:-----|
|Tipo de mensaje  <br/> | El tipo de mensaje para buscar. Se trata de la misma propiedad como la propiedad Kind de correo electrónico. Valores posibles:  <br/><br/>  contactos  <br/>  documentos  <br/>  correo electrónico  <br/>  externaldata  <br/>  faxes  <br/>  mensajería instantánea  <br/>  diarios  <br/>  reuniones  <br/>  microsoftteams  <br/>  notas  <br/>  entradas  <br/>  fuentes rss  <br/>  tareas  <br/>  correo de voz  <br/> |
|Participants  <br/> |Todos los campos de personas en un mensaje de correo electrónico; estos campos son De, Para, CC y CCO.  <br/> |
|Tipo  <br/> |La propiedad de la clase de mensaje para un elemento de correo electrónico. Se trata de la misma propiedad como la propiedad de correo electrónico ItemClass. También es una condición de varios valor. Por lo tanto para seleccionar varias clases de mensaje, mantenga presionada la tecla **CTRL** y, a continuación, haga clic en dos o más clases de mensaje en la lista desplegable que desee agregar a la condición. Cada clase de mensaje que seleccione en la lista se conectará lógicamente por el operador **o** en la consulta de búsqueda correspondiente.<br/> Para obtener una lista de las clases de mensaje (y su correspondiente identificador de clase de mensaje) que se utilizan en Exchange y que se pueden seleccionar en la lista de **clase de mensaje** , vea [tipos de elementos y clases de mensajes](https://go.microsoft.com/fwlink/?linkid=848143).  <br/> |
|Received  <br/> |La fecha en la que un destinatario recibió un mensaje de correo electrónico. Se trata de la misma propiedad que la propiedad de correo electrónico Recibido.  <br/> |
|Destinatarios  <br/> |La persona un mensaje de correo electrónico se envió a. Se trata de la misma propiedad como la propiedad de correo electrónico para.  <br/> |
|Remitente  <br/> |El remitente de un mensaje de correo electrónico.  <br/> |
|Sent  <br/> |La fecha en la que se envió un mensaje de correo electrónico por el remitente. Se trata de la misma propiedad como la propiedad de correo electrónico enviados.  <br/> |
|Subject  <br/> |El texto en la línea de asunto de un mensaje de correo electrónico.  <br/> |
|To  <br/> |El destinatario de un mensaje de correo electrónico.  <br/> |
  
### <a name="conditions-for-document-properties"></a>Condiciones para las propiedades de documento

Crear una condición de uso de las propiedades de documento cuando se buscan documentos en SharePoint y OneDrive para sitios de profesionales. En la siguiente tabla se enumera las propiedades de documento que se pueden usar para una condición. Tenga en cuenta que estas propiedades son un subconjunto de las propiedades del sitio que se han descrito anteriormente; Estas descripciones se repiten para su comodidad.
  
|**Condición**|**Descripción**|
|:-----|:-----|
|Author  <br/> |El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y los mensajes de correo electrónico a otra persona que, a continuación, se carga en SharePoint, el documento conservará al autor original.  <br/> |
|Título  <br/> |El título del documento. La propiedad Title es metadatos que se especifican en documentos de Office. Es distinto del nombre de archivo del documento.  <br/> |
|creados  <br/> |La fecha en la que se creó el documento.  <br/> |
|Modificó por última vez  <br/> |La fecha en la que el documento se modificó por última vez.  <br/> |
|Tipo de archivo  <br/> |La extensión de un archivo; Por ejemplo, docx, uno, pptx o xlsx. Se trata de la misma propiedad como la propiedad del sitio FileExtension.  <br/> |
  
### <a name="operators-used-with-conditions"></a>Operadores usados con condiciones

Cuando se agrega una condición, puede seleccionar un operador que sea pertinente para el tipo de propiedad de la condición. En la tabla siguiente se describen los operadores que se usan con condiciones y se enumera el equivalente que se usa en la consulta de búsqueda.
  
|**Operador**|**Equivalente de consulta**|**Descripción**|
|:-----|:-----|:-----|
|Después  <br/> |`property\>date`  <br/> |Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron después de la fecha especificada.   <br/> |
|Antes  <br/> |`property\<date`  <br/> |Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron antes de la fecha especificada.  <br/> |
|Entre  <br/> |`date..date`  <br/> |Se utiliza con las condiciones de fecha y el tamaño. Cuando se usa con una condición de fecha, devuelve elementos que hay se han enviado, recibidos o modificados en el intervalo de fechas especificado. Cuando se usa con una condición de tamaño, devuelve los elementos cuyo tamaño está dentro del intervalo especificado.  <br/> |
|Contiene cualquiera de  <br/> |`(property:value) OR (property:value)`  <br/> |Se utiliza con las condiciones para las propiedades que especifican un valor de tipo string. Devuelve elementos que contengan cualquier parte de uno o más valores de la cadena especificada.  <br/> |
|No contiene ninguno de  <br/> |`-property:value`  <br/> `NOT property:value`  <br/> |Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen ninguna parte del valor de cadena especificado.  <br/> |
|No es igual a ninguno de
  <br/> |`-property=value`  <br/> `NOT property=value`  <br/> |Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen la cadena especificada.  <br/> |
|Igual a  <br/> |`size=value`  <br/> |Devuelve elementos que son iguales al tamaño especificado.<sup>1</sup> <br/> |
|Es igual a cualquiera de  <br/> |`(property=value) OR (property=value)`  <br/> |Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que coinciden exactamente con uno o más valores de cadena especificados.  <br/> |
|Mayor  <br/> |`size>value`  <br/> |Devuelve elementos en los que la propiedad especificada es mayor que el valor especificado.<sup>1</sup> <br/> |
|Mayor o igual  <br/> |`size>=value`  <br/> |Devuelve elementos en los que la propiedad especificada es mayor o igual que el valor especificado.<sup>1</sup> <br/> |
|Menor  <br/> |`size<value`  <br/> |Devuelve elementos que son mayores o iguales que el valor específico.<sup>1</sup> <br/> |
|Menor o igual  <br/> |`size<=value`  <br/> |Devuelve elementos que son mayores o iguales que el valor específico.<sup>1</sup> <br/> |
|No es igual  <br/> |`size<>value`  <br/> |Devuelve elementos que no son iguales al tamaño especificado.<sup>1</sup> <br/> |
   
> [!NOTE]
> <sup>1</sup> este operador está disponible sólo para las condiciones que utilice la propiedad Size. 
  
### <a name="guidelines-for-using-conditions"></a>Directrices para el uso de condiciones

Tenga en cuenta lo siguiente al usar condiciones de búsqueda.
  
- Una condición lógicamente está conectada a la consulta de palabras clave (especificada en el cuadro de palabra clave) por el operador **y** . Esto significa que los elementos tengan que satisfacer la consulta de palabra clave y la condición que se deben incluir en los resultados. Se trata de cómo ayudar a condiciones para limitar los resultados. 
    
- Si agrega dos o más condiciones únicas a una consulta de búsqueda (condiciones que especifican distintas propiedades), esas condiciones están conectadas lógicamente mediante el operador **AND** . Esto significa que se devuelven sólo los elementos que cumplen todas las condiciones (además de cualquier consulta de palabras clave). 
    
- Si agrega más de una condición para la misma propiedad, esas condiciones están conectadas lógicamente mediante el operador **OR** . Esto significa que se devuelven los elementos que se ajusten a la consulta de palabra clave y cualquiera de las condiciones. Por lo tanto, los grupos de las mismas condiciones están conectados entre sí por el operador **o** y, a continuación, los conjuntos de condiciones únicas conectados por el operador **y** . 
    
- Si agrega varios valores (separados por comas o punto y coma) a una única condición, esos valores están conectados por el operador **o** . Esto significa que se devuelven los elementos si contienen cualquiera de los valores especificados para la propiedad en la condición. 
    
- La consulta de búsqueda que se crea mediante el cuadro palabras clave y las condiciones se muestra en la página de **búsqueda** , en el panel de detalles para la búsqueda seleccionada. En una consulta, todo el contenido a la derecha de la notación `(c:c)` indica las condiciones que se agregan a la consulta. 
    
- Las condiciones sólo agregar propiedades a la consulta de búsqueda; el no agregar operadores. Esta es la razón por la consulta que se muestra en el panel de detalles no aparezca operadores a la derecha de la `(c:c)` notación. KQL agrega los operadores lógicos (de acuerdo con las reglas anteriormente explicadas) cuando la ejecución de la consulta. 
    
- Puede usar la operación de arrastrar y colocar el control para volver a secuenciar el orden de las condiciones. Simplemente haga clic en el control de una condición y moverla hacia arriba o hacia abajo.
    
- Como se explica anteriormente, algunas propiedades de condición permiten escribir varios valores. Cada valor está conectado lógicamente por el operador **o** . Esto da como resultado la misma lógica que tener varias instancias de la misma condición, donde cada uno tiene un único valor. En las ilustraciones siguientes se muestra un ejemplo de una condición único con varios valores y un ejemplo de varias condiciones (para la misma propiedad) con un valor único. Ambos ejemplos el resultado en la misma consulta:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![Una condición con múltiples valores](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Varias condiciones de búsqueda para la misma propiedad](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> Si una condición acepta varios valores, le recomendamos que use una sola condición y que especifique varios valores (separados por comas o por punto y coma). Esto ayuda a garantizar que la lógica de consulta que se aplica es la deseada. 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Ejemplos del uso de condiciones en consultas de búsqueda

Los siguientes ejemplos muestran la versión basada en la interfaz gráfica de usuario de una consulta de búsqueda con las condiciones, la sintaxis de consulta de búsqueda que se muestra en el panel de detalles de la búsqueda seleccionada (que también se devuelve mediante el cmdlet **Get-ComplianceSearch** ) y la lógica de la consulta de palabras clave correspondiente. 
  
#### <a name="example-1"></a>Ejemplo 1

En este ejemplo se devuelve documentos en SharePoint y OneDrive para los sitios de negocio que contienen un número de tarjeta de crédito y se modificó por última vez antes del 1 de enero de 2016.
  
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
  
 `report???(c:c)??????(date<2016-04-01)??????(subjecttitle:"northwind")??????(-filetype="aspx")???`
  
 **Lógica de la consulta de búsqueda**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>Ejemplo 3
<a name="conditionexamples"> </a>

En este ejemplo se devuelve los mensajes de correo electrónico o las reuniones de calendario que se han enviado entre 1/12/2016 y 30/11/2016 y que contienen las palabras que empiecen por "teléfono" o "smartphone".
  
 **GUI**
  
![Tercer ejemplo de condiciones de búsqueda](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Sintaxis de la consulta de búsqueda**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **Lógica de la consulta de búsqueda**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>Búsqueda de contenido de sitio compartido con usuarios externos

También puede usar la característica de búsqueda de contenido en la seguridad &amp; centro de cumplimiento para buscar documentos almacenados en SharePoint y OneDrive para los sitios de negocio que se han compartido con personas fuera de la organización. Esto puede ayudar a identificar información confidencial o de propiedad que se va a compartir fuera de su organización. Puede hacerlo mediante el uso de la `ViewableByExternalUsers` (propiedad) en una consulta de palabra clave. Esta propiedad devolverá documentos o sitios que se han compartido con usuarios externos mediante uno de los siguientes métodos de uso compartidos: 
  
- Una invitación para compartir que requiere que los usuarios iniciar sesión en su organización como un usuario autenticado.
    
- Un vínculo de invitado anónimo, que permite a cualquier persona con este vínculo para obtener acceso al recurso sin tener que ser autenticados.
    
Estos son algunos ejemplos:
  
- La consulta `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` devolverá todos los elementos que se han compartido con personas fuera de la organización y contienen un número de tarjeta de crédito. 
    
- La consulta `ViewableByExternalUsers:true AND ContentType:document AND Site:https://contoso.sharepoint.com/Sites/Teams` devolverá una lista de documentos en todos los sitios de equipo de la organización que han decidido compartir con los usuarios externos. 
    
> [!TIP]
> Una consulta de búsqueda como `ViewableByExternalUsers:true AND ContentType:document` puede devolver una gran cantidad de archivos .aspx en los resultados de búsqueda. Para eliminar estos (u otros tipos de archivos), puede usar el `FileExtension` (propiedad) para excluir determinados tipos de archivo; Por ejemplo `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`. 
  
¿Qué se considera el contenido que se comparte con personas fuera de su organización? Documentos de SharePoint y OneDrive de la organización para los sitios de negocio que se comparten con el envío de invitaciones de uso compartido o que se comparten en ubicaciones públicas. Por ejemplo, las siguientes actividades de usuario de resultados en el contenido que está visible para los usuarios externos:
  
- Un usuario comparte un archivo o una carpeta con una persona externa a su organización.

    
- Un usuario se crea y envía un vínculo a un archivo compartido a una persona fuera de su organización. Este vínculo permite al usuario externo ver (o editar) el archivo.
    
- Un usuario envía una invitación de uso compartido o un vínculo de invitado a una persona externa a su organización para ver (o editar) un archivo compartido.
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Problemas con la propiedad ViewableByExternalUsers

Mientras el `ViewableByExternalUsers` (propiedad) representa el estado de si se comparte un documento o un sitio con usuarios externos, hay algunas advertencias a lo que hace esta propiedad y doesn???t reflejar. En los siguientes escenarios, el valor de la `ViewableByExternalUsers` no se actualizan (propiedad), y los resultados de una consulta de búsqueda de contenido que usa esta propiedad pueden ser imprecisos. 
  
- Cambios realizados en la directiva, como desactivar el uso compartido externo para un sitio o para la organización de uso compartido. La propiedad seguirá mostrando documentos compartidos anteriormente como accesibles de forma externa, aunque es posible que se ha revocado el acceso externo.
    
- Cambios realizados en la pertenencia a grupos, como agregar o quitar los usuarios externos a los grupos de seguridad de Office 365 grupos u Office 365. La propiedad no se actualizan automáticamente para los elementos que el grupo tiene acceso a.
    
- Envío de las invitaciones para compartir a los usuarios externos, donde el destinatario aún no ha aceptado la invitación y, por lo tanto, aún no tienen acceso al contenido.
    
En estos escenarios, el `ViewableByExternalUsers` propiedad no reflejará el estado de uso compartido actual hasta el sitio o biblioteca de documentos se vuelven a rastrear y volver a indizar. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Búsqueda de contenido de sitio compartido dentro de la organización

Como se explica anteriormente, puede usar el `SharedWithUsersOWSUser` (propiedad) de modo que busque para los documentos que se han compartido entre las personas de su organización. Cuando una persona comparte un archivo (o carpeta) con otro usuario dentro de la organización, un vínculo en el archivo compartido aparece en la página **compartidos conmigo** en la OneDrive para la cuenta de empresa de la persona que el archivo se ha compartido con. Por ejemplo, para buscar los documentos que se han compartido con Sara Davis, puede usar la consulta `SharedWithUsersOWSUser:"sarad@contoso.com"`. Si exporta los resultados de esta búsqueda, se descargarán los documentos originales (que se encuentra en la ubicación del contenido de la persona que comparte los documentos con Marta).
  
Tenga en cuenta que se deben compartir documentos explícitamente con un usuario específico que se devuelve en los resultados de búsqueda cuando se usa el `SharedWithUsersOWSUser` (propiedad). Por ejemplo, cuando una persona comparte un documento en su cuenta de OneDrive, tiene la opción de compartir con cualquier usuario (dentro o fuera de la organización), compartir únicamente con personas dentro de la organización o compartir con una persona específica. Aquí es una captura de pantalla de la ventana del **recurso compartido** en OneDrive, que se muestra las tres opciones de uso compartidas. 
  
![Sólo los archivos compartidos con personas específicas será devuelto por una consulta de searcj que usa la propiedad SharedWithUsersOWSUser](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Sólo los documentos que se comparten mediante el uso de la tercera opción (compartida con **personas específicas**) será devuelto por una consulta de búsqueda que usa el `SharedWithUsersOWSUser` (propiedad). 

## <a name="search-tips-and-tricks"></a>Trucos y sugerencias de búsqueda

- Las búsquedas de palabras clave no distinguen mayúsculas de minúsculas. Por ejemplo, tanto si escribe **gato** como **GATO**, obtendrá los mismos resultados. 
    
- Los operadores booleanos **AND**, **OR**, **no**, **NEAR**y **ONEAR** deben escribirse en mayúsculas. 
    
- Un espacio entre dos palabras clave o dos `property:value` expresiones es lo mismo que usar **AND**. Por ejemplo, `from:"Sara Davis" subject:reorganization` devuelve todos los mensajes enviados por Sara Davis que contienen la reorganización de word en la línea de asunto. 
    
- Use una sintaxis que coincida con el `property:value` formato. Los valores no distinguen mayúsculas de minúsculas y no pueden tener un espacio después del operador. Si hay un espacio, su valor previsto sólo será una búsqueda de texto completo. Por ejemplo `to: pilarp` búsquedas para "pilarp" como una palabra clave, en lugar de los mensajes enviados a pilarp. 
    
- Al buscar una propiedad de destinatario, como Para, De, Cc o los destinatarios, puede utilizar una dirección SMTP, un alias o un nombre para mostrar para indicar un destinatario. Por ejemplo, puede utilizar pilarp@contoso.com, pilarp o "Pilar Pinilla".
    
- Puede usar sólo las búsquedas de caracteres comodín prefijo; Por ejemplo, **cat\* ** o **establecer\***. Las búsquedas de sufijos ( ** \*cat** ), las búsquedas de infijo ( **c\*t** ) y las búsquedas de subcadenas ( ** \*cat\* ** ) no son compatibles. 
    
- Al buscar en una propiedad, utilice las comillas dobles ("") si el valor de búsqueda consta de varias palabras. Por ejemplo `subject:budget Q1` devuelve los mensajes que contienen **presupuestado** en el en la línea de asunto y que contienen **T1** en cualquier lugar en el mensaje o en cualquiera de las propiedades del mensaje. Uso de `subject:"budget Q1"` devuelve todos los mensajes que contienen **presupuestado T1** en cualquier lugar en la línea de asunto. 
    
- Para excluir contenido marcado con un determinado valor de propiedad de los resultados de búsqueda, coloque un signo menos (-) delante del nombre de la propiedad. Por ejemplo, `-from:"Sara Davis"` excluirá todos los mensajes enviados por Sara Davis. 

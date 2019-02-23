---
title: Usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Use la herramienta búsqueda de contenido eDiscovery para buscar elementos que se importaron a los buzones en Office 365 desde un origen de datos de terceros. Puede crear una consulta para buscar todos los elementos importados o crear una consulta para buscar determinados tipos de datos de terceros. En este artículo se enumeran los valores que se pueden usar en una consulta de palabras clave para buscar en los tipos de datos de terceros que se pueden importar a Office 365.
ms.openlocfilehash: 793024f765aa1d016f7a043d14eb75ca6c2435c3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214880"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>Usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365

Puede usar la [herramienta de búsqueda de contenido eDiscovery](content-search.md) en el centro de &amp; seguridad y cumplimiento de Office 365 para buscar elementos que se importaron a los buzones en Office 365 desde un origen de datos de terceros. Puede crear una consulta para buscar en todos los elementos de datos de terceros importados o puede crear una consulta para buscar en elementos de datos específicos de terceros. Además, también puede crear una directiva de conservación basada en consultas o una conservación de exhibición de documentos electrónicos basada en consultas para conservar los datos de terceros en Office 365. 
  
Para obtener más información acerca de la importación de datos de terceros y una lista de los tipos de datos de terceros que se pueden importar a Office 365, vea [archivar datos de terceros en office 365](archiving-third-party-data.md). 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Crear una consulta para buscar en todos los datos de terceros

Para buscar (o poner en espera) cualquier tipo de datos de terceros que haya importado a Office 365, puede usar el `kind:externaldata` par propiedad-valor del mensaje en el cuadro palabra clave para una búsqueda de contenido o al crear una suspensión basada en consulta. Por ejemplo, para buscar elementos que se han importado de cualquier origen de datos de terceros y que contienen la palabra "Contoso" en la propiedad subJect del elemento importado, debe utilizar la siguiente consulta: 
  
```
kind:externaldata AND subject:contoso
```

En el ejemplo anterior de consulta de palabra clave se incluye la propiedad Subject. Para obtener una lista de otras propiedades de elementos de datos de terceros que se pueden incluir en una consulta de palabras clave, vea la sección "más información" en [archivar datos de terceros en Office 365](archiving-third-party-data.md#more-information).
  
Al crear consultas para buscar y conservar datos de terceros, también puede usar las condiciones para restringir los resultados de la búsqueda. Para obtener más información acerca de la creación de consultas de búsqueda de contenido, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Crear una consulta para buscar tipos específicos de datos de terceros

En lugar de buscar en todos los tipos de datos de terceros, puede crear consultas que solo busquen un tipo especificado de datos de terceros mediante el siguiente par de valores de propiedad y valor de mensaje en el cuadro de palabras clave para una búsqueda de contenido:
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

Por ejemplo, para buscar únicamente datos de Facebook que contengan la palabra "Contoso" en la propiedad subJect, debe utilizar la siguiente consulta:
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

En la siguiente tabla se enumeran los tipos de datos de terceros que se pueden buscar y el valor que se `itemclass:` debe usar para la propiedad Message para buscar específicamente ese tipo de datos de terceros. Tenga en cuenta que la sintaxis de consulta no distingue mayúsculas de minúsculas. 
  
|**Tipo de datos de terceros**|**Valor de `itemclass:` la propiedad**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL con cliente Pivot  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Marcador de posición de AXS  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|BearShare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|BlackBerry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Registros de llamadas de BlackBerry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|PIN BlackBerry  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|SMS de BlackBerry  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg Mail
  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Cuadro  <br/> | `ipm.externaldata.Box*` <br/> |
|Servidor de &amp; presencia de mensajería instantánea de Cisco  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud para Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Conexión directa  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr
  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+
  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|Conexiones IBM  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|Chat de ICE  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger
  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram
  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg
  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive
  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|COMUNICACIONES UNIFICAdas de Microsoft  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Idea  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype Empresarial  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|
Squawker
  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony
  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger
  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat
  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|Integrado  <br/> | `ipm.externaldata.YouTube*` <br/> |

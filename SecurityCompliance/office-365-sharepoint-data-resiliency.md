---
title: Resistencia de datos de SharePoint de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una descripción general de la resistencia de datos en SharePoint Online en Office 365.
ms.openlocfilehash: ba6259e8e582a4abcf0f184b162177119a57718f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536197"
---
# <a name="sharepoint-online-data-resiliency"></a>Resistencia de datos en línea de SharePoint
Un principio clave de SharePoint Online es no puede tener una única copia de cualquier parte de los datos. SharePoint Online utiliza la replicación de SQL Server, que es un conjunto de tecnologías para copiar y distribuir objetos de datos y la base de datos de una base de datos a otro y, a continuación, la sincronización entre bases de datos para mantener la coherencia. 

Por ejemplo, cuando un usuario guarda un archivo en SharePoint Online, el archivo es fragmentado, cifrado y almacenado en el almacenamiento de blobs de Azure. Servicio de Azure Blob proporciona mecanismos para garantizar la integridad de los datos tanto en los niveles de aplicación y de transporte. Esta entrada detalla estos mecanismos desde la perspectiva del cliente y de servicio. Comprobación de MD5 es opcional en las operaciones PUT y GET; Sin embargo, sí proporciona una función de comodidad para garantizar la integridad de los datos a través de la red cuando se utiliza HTTP. Además, dado que HTTPS proporciona seguridad de la capa de transporte adicionales MD5 comprobación no es necesario mientras se conecta a través de HTTPS, ya que es redundante. Servicio de Azure Blob proporciona un medio de almacenamiento resistente y usa su propia integridad de comprobación de los datos almacenados. Se proporcionan la MD5 que se utilizan al interactuar con una aplicación para la comprobación de la integridad de los datos cuando se transfieren los datos entre la aplicación y el servicio a través de HTTP. 

Para asegurar la integridad de datos el Blob de Azure servicio usa valores hash MD5 de los datos de dos formas diferentes:. Es importante comprender cómo se calcula, se transmiten, se almacenan y se aplican finalmente para diseñar correctamente la aplicación para utilizarlas para proporcionar la integridad de los datos estos valores. Para obtener más información, vea [Información general de Windows Azure Blob MD5](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx). 

Punteros al archivo y los metadatos se almacenan en una base de datos de SQL Server (la base de datos de contenido). Todos los fragmentos – archivos, fragmentos de archivos y diferencias de actualización – se almacenan como blobs en almacenamiento de Azure a los que se distribuyen de forma aleatoria a través de varias cuentas de almacenamiento de Azure. La base de datos SQL está hospedado en una matriz de almacenamiento RAID 10 que se refleja de forma sincrónica a otra matriz de almacenamiento RAID 10 en un bastidor independiente dentro del mismo centro de datos. A continuación, se utiliza el trasvase de registros asincrónica para replicar los datos a otra matriz de almacenamiento RAID 10 en un segundo centro de datos. Además de protección de datos con RAID 10 y replicación sincrónica y asincrónica, las copias de seguridad de datos programada se toman que también de forma asincrónica se replican en el segundo centro de datos. 

En SharePoint Online, las copias de seguridad de datos se realiza cada 12 horas y se conservan durante 14 días. SharePoint Online también usa un sistema de espera activo que incluye emparejados geográficamente separado los centros de datos en el mismo cliente ubicación región de datos (por ejemplo, Chicago y San Antonio para los clientes que ya aprovisionados a su inquilino en los Estados Unidos) configurado como activo/activo. Por ejemplo, hay usuarios live que tengan Chicago como centro de datos principal y San Antonio como un centro de datos de conmutación por error y Live Meeting a los usuarios que tienen San Antonio como su centro de datos principal y Chicago como sus centros de datos de conmutación por error. 
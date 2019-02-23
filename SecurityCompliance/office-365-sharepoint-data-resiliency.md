---
title: Resistencia de datos de SharePoint de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información general sobre la resistencia de datos en SharePoint Online en Office 365.
ms.openlocfilehash: 4fd17b50551639f6e11975acbc3822fb6ffa8bb2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214810"
---
# <a name="sharepoint-online-data-resiliency"></a>Resistencia de datos de SharePoint Online
Un principio clave para SharePoint Online es no tener nunca una única copia de ningún dato. SharePoint Online usa la replicación de SQL Server, que es un conjunto de tecnologías para copiar y distribuir datos y objetos de base de datos de una base de datos a otra y, a continuación, sincronizar entre bases de datos para mantener la coherencia. 

Por ejemplo, cuando un usuario guarda un archivo en SharePoint Online, el archivo se fragmenta, se cifra y se almacena en el almacenamiento de blobs de Azure. Azure BLOB Service proporciona mecanismos para garantizar la integridad de los datos en las capas de aplicación y transporte. Esta publicación detallará estos mecanismos desde el punto de vista del cliente y del servicio. La comprobación de MD5 es opcional tanto en las operaciones PUT como GET; sin embargo, proporciona una herramienta de comodidad para garantizar la integridad de los datos en la red al usar HTTP. Además, dado que HTTPS proporciona seguridad de la capa de transporte, no se necesita ninguna otra comprobación de MD5 mientras se conecta a través de HTTPS, ya que sería redundante. Azure BLOB Service proporciona un medio de almacenamiento duradero y usa su propia comprobación de integridad para los datos almacenados. Las MD5's que se usan al interactuar con una aplicación se proporcionan para comprobar la integridad de los datos cuando se transfieren datos entre la aplicación y el servicio mediante HTTP. 

Para garantizar la integridad de los datos, Azure BLOB Service usa hash MD5 de los datos en un par de diferentes modalidades. Es importante comprender cómo se calculan, transmiten, almacenan y finalmente se aplican estos valores para diseñar correctamente la aplicación con el fin de utilizarla para proporcionar integridad de datos. Para obtener más información, vea [información general sobre MD5 de Windows Azure BLOB](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx). 

Los metaDatos y los punteros al archivo se almacenan en una base de datos de SQL Server (la base de datos de contenido). Todos los fragmentos (archivos, fragmentos de archivos y deltas de actualización) se almacenan como blobs en Azure Storage que se distribuyen de forma aleatoria en varias cuentas de almacenamiento de Azure. La base de datos SQL está hospedada en una matriz de almacenamiento RAID 10 que se refleja de forma sincrónica en otra matriz de almacenamiento RAID 10 en un rack independiente dentro del mismo centro de datos. A continuación, se usa el trasvase de registros asincrónico para replicar los datos en otra matriz de almacenamiento RAID 10 en un centro de datos secundario. Además de proteger los datos con RAID 10 y la replicación sincrónica y asincrónica, las copias de seguridad de datos programadas se llevan a cabo, que también se replican de forma asincrónica en el segundo centro de datos. 

En SharePoint Online, las copias de seguridad de datos se realizan cada 12 horas y se conservan durante 14 días. SharePoint Online también usa un sistema de espera activa que incluye centros de datos emparejados geográficamente separados dentro de la misma región de ubicación de datos del cliente (por ejemplo, Chicago y San Antonio para los clientes que han aprovisionado su inquilino en Estados Unidos) configurado como activo/activo. Por ejemplo, hay usuarios activos que tienen Chicago como centro de recursos principal y San Antonio como centro de recursos de conmutación por error, y usuarios activos que tienen San Antonio como centro de recursos principal y Chicago como su centro de recursos de conmutación por error. 
---
title: Descargar trabajos de exportación
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56ed8eac259974b43ca0cd26b2bd0c339a5fc05b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155152"
---
# <a name="download-export-jobs"></a>Descargar trabajos de exportación

Todos los datos exportados se agregan a un BLOB de Microsoft Azure. Esto proporciona varias opciones para controlar los datos de forma descendente. Hay varias formas de tener acceso a un BLOB de Azure. Un método es usar el explorador de almacenamiento de Azure. Este método admite conexión simple, exploración y descarga. Para obtener más información, visite<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer>

1.  Para descargar contenido después de completar un trabajo de exportación, vaya a la pestaña exportaciones y seleccione un trabajo de exportación.

2.  Copie el texto en la sección "ubicaciones" del control flotante.

![](../media/eDiscoExportJob.png)

3.  Abra el explorador de Azure Storage y haga clic en el botón "conectar"

![](../media/AzureStorageConnect.png)

4.  Seleccione "usar un URI de firma de acceso compartido" y haga clic en siguiente.

![](../media/AzureStorageConnect2.png)

5.  Pegue el texto de ubicación en el cuadro de texto URI y haga clic en siguiente.

![](../media/AzureStorageConnect3.png)

6.  Haga clic en conectar

![](../media/AzureStorageConnect4.png)

Esto agregará la exportación como un objeto en las cuentas de almacenamiento, los servicios de datos adjuntos de SAS o los contenedores de blobs. Podrá explorar la exportación y descargar todas o parte de la exportación.

![](../media/AzureStorageConnect5.png)
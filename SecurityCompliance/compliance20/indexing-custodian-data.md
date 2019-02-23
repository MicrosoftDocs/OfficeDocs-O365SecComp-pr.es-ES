---
title: Clasificación avanzada de los datos de administración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8f1a92f001bf8f9e23f54bbb05fbbcf443bf4b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218670"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación avanzada de los datos de administración

Cuando se agrega un custodio a un caso de exhibición avanzada de documentos electrónicos (versión preliminar), cualquier contenido de Office 365 que se considere indizado parcialmente se vuelve a procesar para que pueda ser buscado por completo.  Este proceso se denomina *indizaCión avanzada*. El contenido se puede indizar parcialmente por varios motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.  Para obtener más información acerca de los elementos parcialmente indizados, vea [elementos parcialmente indizados en la búsqueda de contenido en Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).

## <a name="viewing-advanced-indexing-results"></a>Ver resultados de indización avanzada

Una vez completado el proceso de indización avanzado, puede comprender la efectividad del procesamiento.  En la vista de indización del custodio, el gráfico muestra todos los elementos agregados al *Índice híbrido*.  El índice híbrido es donde la exhibición avanzada de documentos electrónicos (vista previa) almacena el contenido que se ha vuelto a procesar.

El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).

## <a name="updating-advanced-indexes-for-custodians"></a>Actualización de índices avanzados para custodios

Cuando se agrega un custodio a un caso de eDiscovery avanzado (vista previa), todos los elementos parcialmente indizados se vuelven a procesar. Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Cuando sea necesario, puede actualizar los índices.

> [!NOTE]
> La actualización de los índices de custodios es un proceso de ejecución prolongada. Se recomienda no actualizar índices más de una vez al día en un caso.

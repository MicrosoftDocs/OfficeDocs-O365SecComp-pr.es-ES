---
title: Clasificación avanzada de los datos de administración
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
ms.openlocfilehash: be163d3272dbe027cb0f4b4b4fe379bf28fa5a85
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151762"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación avanzada de los datos de administración

Cuando se agrega un custodio a un caso de exhibición avanzada de documentos electrónicos, cualquier contenido de Office 365 que se considere indizado de forma parcial se reprocesa para que pueda ser buscado por completo.  Este proceso se denomina *indización avanzada*. El contenido se puede indizar parcialmente por varios motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización.

Para obtener más información acerca de la compatibilidad de procesamiento en Office 365 y elementos parcialmente indizados, vea:

- [Tipos de archivo admitidos en eDiscovery avanzado](supported-filetypes-ediscovery20.md)
- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)
- [Formatos de archivo indizados por la búsqueda de Exchange](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Ver resultados de indización avanzada

Una vez completado el proceso de indización avanzado, puede comprender la efectividad del procesamiento.  En la vista de indización del custodio, el gráfico muestra todos los elementos agregados al *Índice híbrido*.  El índice híbrido es donde la exhibición avanzada de documentos electrónicos almacena el contenido que se ha vuelto a procesar.

El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).

## <a name="updating-advanced-indexes-for-custodians"></a>Actualización de índices avanzados para custodios

Cuando se agrega un custodio a un caso de eDiscovery avanzado, todos los elementos parcialmente indizados se vuelven a procesar. Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Cuando sea necesario, puede actualizar los índices.

> [!NOTE]
> La actualización de los índices de custodios es un proceso de ejecución prolongada. Se recomienda no actualizar índices más de una vez al día en un caso.

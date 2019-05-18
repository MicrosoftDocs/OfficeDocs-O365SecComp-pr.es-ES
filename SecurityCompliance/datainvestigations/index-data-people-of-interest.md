---
title: Indización avanzada de datos para una investigación
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
ms.openlocfilehash: 2e2077fa5ee5333a563470d5bcbb140364bc0ba2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150782"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>Indización avanzada de datos para una investigación

El contenido del sistema activo se puede indizar parcialmente por una serie de motivos, como la existencia de imágenes, tipos de archivo no admitidos o cuando se encuentran límites de tamaño de archivo de indización. Cuando se trata de un derrame de datos de riesgo alto, desea asegurarse de que la búsqueda capturó todos los datos que desea investigar. Cuando se agrega una persona de interés a una investigación de datos, cualquier contenido de Office 365 que se consideró tal y como se consideraba parcialmente indizada se vuelve a procesar para que sea posible realizar búsquedas por completo. Este proceso se denomina *indización avanzada*. 

Para obtener más información acerca de la compatibilidad de procesamiento en Office 365 y elementos parcialmente indizados, vea:

- [Tipos de archivo admitidos en investigaciones de datos](supported-filetypes-datainvestigations.md)

- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [Formatos de archivo indizados por la búsqueda de Exchange](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Ver resultados de indización avanzada

Una vez completado el proceso de indización avanzado, puede comprender la efectividad del procesamiento.  En la vista de indización de personas de interés, el gráfico muestra todos los elementos agregados al *Índice híbrido*.  El índice híbrido es donde las investigaciones de datos (vista previa) almacenan el contenido reprocesado.

El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de errores al procesar datos](error-remediation.md).

## <a name="updating-advanced-indexes-for-people-of-interest"></a>Actualización de índices avanzados para personas de interés

Cuando se agrega una persona de interés a una investigación de datos, todos los elementos parcialmente indizados se vuelven a procesar. Sin embargo, a medida que pasa el tiempo, se pueden agregar más elementos indizados parcialmente al buzón de un usuario o a una cuenta de OneDrive.  Cuando sea necesario, puede actualizar los índices.

> [!NOTE]
> La actualización de personas de índices de interés es un proceso de ejecución prolongada. Se recomienda no actualizar índices más de una vez al día en una investigación.

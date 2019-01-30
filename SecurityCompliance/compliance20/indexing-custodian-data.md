---
title: Clasificación de datos de custodia avanzada
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 158af8acf4acdb8ad6650c377a23b44ed28c6f54
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608332"
---
# <a name="advanced-indexing-of-custodian-data"></a>Clasificación de datos de custodia avanzada

Cuando se agrega una custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa), cualquier contenido en Office 365 que se consideró como parcialmente indizados se vuelve a procesar para hacer que permite realizar búsquedas.  Este proceso se denomina *indización avanzada*. Contenido se puede indizar parcialmente para una serie de razones, incluida la existencia de imágenes, tipos de archivo no compatibles o cuando se encuentran la indización de los límites de tamaño de archivo.  Para obtener más información acerca de los elementos indizados parcialmente, vea [parcialmente indizar los elementos de búsqueda de contenido en Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).

## <a name="viewing-advanced-indexing-results"></a>Ver los resultados de indización avanzados

Después de que se complete el proceso de indización avanzado, puede obtener una descripción de la eficacia de volver a procesar.  En la vista de indización de custodia, el gráfico enumera todos los elementos que se agregan al *índice híbrida*.  El índice de híbrido es donde exhibición de documentos electrónicos avanzada (vista previa) almacena el contenido vuelve a procesar.

El gráfico también incluye el número de elementos que requieren corrección y otro gráfico de errores por tipo de archivo. Para obtener más información, vea [corrección de Error al procesar los datos](error-remediation.md).

## <a name="updating-advanced-indexes-for-custodians"></a>Actualización de índices avanzada de custodia

Cuando se agrega una custodia a un caso de exhibición de documentos electrónicos avanzada (vista previa), se vuelve a procesar todos los elementos indizados parcialmente. Sin embargo, como el paso del tiempo, los elementos indizados más parcialmente pueden agregarse a un cuenta del usuario buzón de correo o OneDrive.  Cuando es necesario, puede actualizar los índices.

> [!NOTE]
> Actualización de índices de custodia es un proceso de larga ejecución. Se recomienda que no se actualizan los índices más de una vez al día en un caso.

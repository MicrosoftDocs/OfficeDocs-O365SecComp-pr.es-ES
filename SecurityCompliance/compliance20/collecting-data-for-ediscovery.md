---
title: Recopilar datos para un caso en eDiscovery avanzado (versión preliminar)
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fb4b36841394576c44667f9677507c5655179e45
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455422"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a>Recopilar datos para un caso en eDiscovery avanzado (versión preliminar)

Una vez que haya identificado los custodios y los orígenes de datos que sean de interés para su caso, es el momento de identificar el conjunto de documentos en los que profundizar. Puede usar la herramienta de búsqueda en la exhibición avanzada de documentos electrónicos (versión preliminar) para identificarlos de las instalaciones y las que no son de custodia en Office 365.

Después de ejecutar una búsqueda, podrá ver las estadísticas de los elementos recuperados, como las ubicaciones en las que la mayoría de los elementos coinciden con la consulta de búsqueda. También puede obtener una vista previa de un subconjunto de los resultados. Cuando haya identificado el conjunto de documentos que desea examinar con más detalle, puede Agregar los resultados de la búsqueda a un conjunto de trabajo para recopilar y procesar.

## <a name="create-a-search"></a>Create a search

Si hace clic en **nueva búsqueda** en la ficha **búsquedas** , se iniciará un asistente que le guiará a través de la creación de una búsqueda. Para obtener información detallada sobre cómo crear una búsqueda, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).

Una vez creada la búsqueda, se muestra una página de control flotante con los detalles. Tenga en cuenta que los botones **estadísticas** y **vista previa** aparecen inicialmente atenuados porque la búsqueda todavía no se ha completado. Puede realizar un seguimiento del progreso de la búsqueda en la ficha **búsquedas** .

## <a name="view-search-results-and-statistics"></a>Ver los resultados de la búsqueda y las estadísticas
Hay dos componentes de una búsqueda de contenido: Statistics (Estimations) y preView. Cuando se completen todos estos componentes, verá que el estado mostrado en las columnas correspondientes de la ficha **búsquedas** cambia desde **enviado** a **en curso** a **completado**.

Una vez completada la estimación de búsqueda, haga clic en la búsqueda para mostrar la página de control flotante, que mostrará algunas estadísticas de alto nivel sobre los resultados de la búsqueda. En este momento, el botón **estadísticas** estará activo. Puede hacer clic en él para ver las estadísticas de búsqueda, como:

- Resumen
- Principales ubicaciones
- Queries

Para obtener más información acerca de las estadísticas de búsqueda, vea [estadísticas de búsqueda](search-statistics.md).

Una vez completada la vista previa, el botón **vista previa** estará activo. Haga clic en él para obtener una vista previa de un subconjunto muestreado de los resultados.

## <a name="adding-search-results-to-a-working-set"></a>Adición de resultados de búsqueda a un conjunto de trabajo

Cuando esté listo para recopilar y procesar los resultados completos de una búsqueda, puede hacerlo si lo agrega a un conjunto de trabajo. Para obtener más información, consulte [Agregar datos a un conjunto de trabajo](add-data-to-working-set.md). 
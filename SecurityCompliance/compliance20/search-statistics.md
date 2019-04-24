---
title: Estadísticas de búsqueda
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: a2234d0a0e94e3fbb15f8fac8f6e49cc7b26cfb2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240972"
---
# <a name="search-statistics"></a>Estadísticas de búsqueda

Una forma de validar los resultados de la búsqueda es ver las estadísticas de los resultados para asegurarse de que se ajustan a sus expectativas. Una vez finalizada la búsqueda, se muestran las estadísticas de alto nivel en el control flotante de detalles de búsqueda:
- Número y volumen de los elementos recuperados por la búsqueda
- Número y volumen de elementos parcialmente indizados o sin indexar que se encontraron en las ubicaciones de búsqueda
- Número de buzones y ubicaciones que se han buscado.
Para ver estadísticas más detalladas, haga clic en "estadísticas" en el control flotante de detalles de búsqueda.

## <a name="summary"></a>Resumen

En la vista de Resumen, puede ver los resultados de la búsqueda desglosados por tipo de ubicación (por ejemplo, Exchange). Para cada tipo de ubicación, puede ver:
- Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda
- Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda
- Volumen total de elementos que coinciden con las condiciones de búsqueda.

## <a name="top-locations"></a>Principales ubicaciones

En la vista de ubicaciones superiores, verá las ubicaciones individuales con más coincidencias. Para cada ubicación, verá:
- Nombre de la ubicación (por ejemplo, dirección URL de SharePoint)
- Tipo de ubicación
- Número de elementos que coinciden con las condiciones de búsqueda
- Volumen total de elementos que coinciden con las condiciones de búsqueda.

## <a name="queries"></a>Queries

Si ha usado (c:s) palabra clave o filas de palabra clave en la consulta, puede ver el desglose de la consulta en la vista consultas por tipo de ubicación. Para cada tipo de ubicación, verá:

- Parte: esta columna tendrá la palabra "principal" o "palabra clave". "Principal" significa que la fila presenta estadísticas sobre toda la consulta, mientras que "palabra clave" se refiere a uno de los componentes de consulta.

- Consulta: el componente de consulta real al que hace referencia la fila. Si la parte es "principal", será toda la consulta; Si la parte es "keyword", verá uno de los componentes de consulta aquí.
  
  - Cuando busca en todo el contenido de los buzones de correo (sin especificar ninguna palabra clave), la consulta real es (Size > = 0) para que se devuelvan todos los elementos.
  
  - Al buscar sitios de SharePoint Online y OneDrive para la empresa, se agregan los dos componentes siguientes:
    
    - NO IsExternalContent: 1-excluye el contenido de una organización de SharePoint local
    
    - NO isOneNotePage: 1: excluye todos los archivos de OneNote porque serían duplicados de cualquier documento que coincida con la consulta de búsqueda.

- Número de ubicaciones que tenían elementos que coincidían con las condiciones de búsqueda.

- Número de elementos de estas ubicaciones que coinciden con las condiciones de búsqueda.

- Volumen total de elementos que coinciden con las condiciones de búsqueda.
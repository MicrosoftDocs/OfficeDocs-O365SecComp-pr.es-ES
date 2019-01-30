---
title: Estadísticas de búsqueda
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: c5b7caff3550d42d84408d6b4e966655b8341123
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608386"
---
# <a name="search-statistics"></a>Estadísticas de búsqueda
Una forma puede validar los resultados de búsqueda es consultar las estadísticas alrededor de los resultados para asegurarse de que se alinean con sus expectativas. Cuando se completa una búsqueda, se muestran las estadísticas de alto nivel en la barra flotante detalles de búsqueda:
- Número y volumen de elementos recuperados por la búsqueda
- Número y volumen de parcialmente indizan o no indexados los elementos que se han encontrado en las ubicaciones de búsqueda
- Busca en el número de buzones de correo y ubicaciones. Para ver estadísticas más detalladas, haga clic en "Estadísticas" del elemento de detalles de la búsqueda.

## <a name="summary"></a>Resumen
En la vista de resumen, puede ver los resultados de búsqueda desglosados por tipo de ubicación (por ejemplo, Exchange). Para cada tipo de ubicación, vea:
- Número de ubicaciones que tenían los elementos que coincidan con las condiciones de búsqueda
- Número de elementos desde estas ubicaciones que coincidieron con las condiciones de búsqueda
- Volumen total de los elementos que coincidan con las condiciones de búsqueda.

## <a name="top-locations"></a>Ubicaciones principales
En la vista de ubicaciones principales, verá las ubicaciones individuales con más coincidencias. Para cada ubicación, verá:
- Nombre de la ubicación (por ejemplo, dirección URL de SharePoint)
- Tipo de ubicación
- Número de elementos que coinciden con las condiciones de búsqueda
- Volumen total de los elementos que coincidan con las condiciones de búsqueda.

## <a name="queries"></a>Consultas
Si ha usado la palabra clave (c:s) o las filas de la palabra clave en su consulta, a continuación, puede ver el desglose de la consulta en la vista de consultas por tipo de ubicación. Para cada tipo de ubicación, verá:
- Parte: esta columna tendrá la palabra "Principal" o "Palabras clave". "Principal" significa que la fila presenta estadísticas de la consulta completa, mientras que "la palabra clave" significa uno de los componentes de consulta.
- Consulta: el componente de consulta real la fila hace referencia a. Si el elemento es "Principal", se trata de toda la consulta; Si el elemento era "Palabras clave", verá uno de los componentes de consulta aquí.
  - Al buscar en todos los buzones de contenidoedición (si no se especifica ninguna palabra clave), la consulta real es (tamaño > = 0) para que se devuelvan todos los elementos
  - Al buscar SharePoint Online y OneDrive para sitios de negocio, se agregan los siguientes dos componentes:
    - NO IsExternalContent:1 - excluye cualquier contenido de una organización de SharePoint local
    - NO isOneNotePage: 1 - excluye todos los archivos de OneNote debido a que estos sería duplicados de cualquier documento que coincide con la consulta de búsqueda.
- Número de ubicaciones que tenían los elementos que coincidan con las condiciones de búsqueda
- Número de elementos desde estas ubicaciones que coincidieron con las condiciones de búsqueda
- Volumne total de elementos que coinciden con las condiciones de búsqueda.

## <a name="refiners"></a>Refinadores
Para los buzones de Exchange, la vista refinadores ofrece adicionales interrupciones por ItemClass, el remitente y el destinatario. Para cada valor de ubicación y refinador, puede ver cuántos documentos se han devuelto en la búsqueda.
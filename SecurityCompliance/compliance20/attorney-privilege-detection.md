---
title: Configuración de la detección de privilegios de clientes de abogado en eDiscovery avanzado
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155192"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a>Configurar un abogado-detección de privilegios de cliente (versión preliminar) en eDiscovery avanzado

Un aspecto importante y costoso de la parte de revisión de cualquier proceso de detección es la revisión del contenido privilegiado. EDiscovery avanzado proporciona una detección de contenido privilegiado basada en AI en su caso, de modo que pueda hacer que este proceso sea más eficaz. Como esta característica está actualmente en versión beta, un administrador de eDiscovery tiene que participar en la característica para usarla.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Con la característica activada, al analizar un conjunto de revisión en un caso, todos los documentos se ejecutan a través del modelo de detección de privilegios de clientes de abogados. El modelo examina dos cosas:

- Contenido: el modelo de ML determina la probabilidad de que el contenido del documento sea legal por naturaleza.

- Participantes: si hay una lista de abogados cargados por el usuario para el inquilino, el modelo compara los participantes del documento con la lista para determinar si el documento tiene al menos un participante abogado.
El modelo da como resultado tres valores para cada documento, todos los cuales se pueden buscar en un conjunto de revisión:

- Puntuación del contenido: la probabilidad de que el documento sea legal por naturaleza (puntuación entre 0 y 1)

- Tiene un abogado: true si uno de los participantes se encuentra en la lista de abogados cargados; de lo contrario, es false o si no hay ninguna lista de abogados.

-  Potencialmente privilegiado: true si la puntuación del contenido es superior al umbral o tiene un participante abogado; de lo contrario, es false.

## <a name="opting-into-attorney-client-privilege-detection"></a>Optar a abogado-detección de privilegios de clientes

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a>Paso 1: participar en la detección de privilegios de cliente (eDiscovery admin)

Como abogado-la detección de privilegios de cliente es una característica de vista previa, el administrador de eDiscovery debe participar para que la característica esté disponible en sus casos.

- Vaya a "configurar características experimentales" en la página exhibición avanzada de documentos electrónicos.

- Haga clic en "administrar abogado-detección de privilegios de cliente".

- Haga clic en el botón de alternancia para activar la característica.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Paso 2: cargar una lista de abogados (opcional)

Para aprovechar todas las ventajas de la detección de privilegios de clientes y abogados, le recomendamos que proporcione una lista de abogados o personas jurídicas que trabajan para la empresa. La lista debe ser un CSV sin encabezado, con una dirección de correo electrónico por línea.

## <a name="leveraging-attorney-client-privilege-detection"></a>Aprovechamiento de la detección de privilegios de clientes de abogados 

### <a name="step-1-analyze-a-review-set"></a>Paso 1: analizar un conjunto de revisión

Al analizar el conjunto de revisión, también se ejecutará la detección de privilegios de clientes de abogados. Para obtener más información acerca del análisis de datos en el conjunto de revisiones, consulte [analizar datos en un conjunto de revisiones en EDiscovery avanzado](analyzing-data-in-review-set.md).

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Paso 2: crear un grupo de etiquetas inteligentes con un modelo de detección de privilegios de clientes de abogados

Una de las principales formas en que puede consumir los resultados de la detección de privilegios de clientes de abogados en el proceso de revisión consiste en usar un grupo de etiquetas inteligentes. Los grupos de etiquetas inteligentes toman los resultados de un modelo de ML y muestran los resultados del modelo en línea junto a las etiquetas, de modo que puede consumir fácilmente los resultados del modelo cuando sea relevante y usar las etiquetas en el proceso de revisión como lo haría con cualquier otra etiqueta del panel de etiquetado. Para obtener más información, consulte [Configurar etiquetas inteligentes para la revisión asistida por ml en EDiscovery avanzado](smart-tags.md) .

- En "administrar etiquetas", haga clic en "agregar sección de etiquetas inteligentes".

- Seleccione "abogado-detección de privilegios de clientes". Verá que se han creado un grupo de etiquetas y dos etiquetas, correspondientes a los resultados posibles del modelo.

- Cambie el nombre del grupo de etiquetas y las etiquetas según sus propias revisiones.

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a>Paso 3: usar el grupo de etiquetas inteligentes para la revisión de privilegios

Al revisar un documento, si el modelo ha determinado que el documento tiene potencialmente privilegios, la etiqueta inteligente correspondiente expondrá el resultado:

- Si el documento tiene contenido que puede ser legal por naturaleza, aparecerá una etiqueta de "contenido legal" junto a la etiqueta inteligente correspondiente.

- Si el documento tiene un participante que se encuentra en la lista de abogados cargados, aparecerá una etiqueta "abogado" junto a la etiqueta inteligente correspondiente.
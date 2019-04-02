---
title: Revisar datos en evidencia
ms.author: markjjo
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
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030528"
---
# <a name="review-data-in-evidence"></a>Revisar datos en evidencia

**Evidence** es una instantánea de los resultados de búsqueda que ha recopilado. Cuando se agregan resultados de búsqueda a Evidence, se desencadena un proceso para extraer archivos, metadatos y texto. A continuación, el sistema crea un nuevo índice de todos los datos y agrega a **prueba**. 

Para cualquier incidente que tenga en cuenta el tiempo, esto le permite incluir rápidamente el entorno al eliminar datos en las ubicaciones originales mientras investiga la evidencia que se ha vuelto a crear en un entorno en cuarentena. Una vez recopilada la evidencia, puede revisar documentos individuales en su formato nativo, formato de texto o un formato casi nativo. Además, puede ejecutar consultas para restringir los datos por intervalo de tiempo, tipos de archivo, propietarios de datos y muchas otras tarjetas de condición. Mediante el uso de las tarjetas de condición de autor/remitente/destinatario, puede examinar rápidamente quién está implicado en el derrame y si ha habido recursos compartidos externos. Para más información, visite:

  - [Consultar los datos en evidencia](evidence-query.md)

Para agrupar documentos y obtener más ayuda para su revisión, haga clic en **administrar evidencias**. En el mosaico **Analytics** , haga clic en **analizar**. De esta forma, se ejecutarán análisis avanzados, como la detección de duplicados, el procesamiento de correo electrónico y el análisis de temas. Posteriormente, puede ver los temas generales de los datos y también organizar los documentos por conversaciones de correo electrónico, duplicados exactos y duplicados cercanos para facilitar su investigación. Para más información, visite:

  - [Ejecutar análisis para investigar con mayor rapidez](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a>Ver documentos en prueba

La investigación de datos (versión preliminar) muestra el contenido a través de varios visores cada uno con fines distintos. Se pueden usar los distintos visores haciendo clic en cualquier documento en **evidencia**. Los visores que se proporcionan actualmente son:

- Metadatos de archivo
- Vista nativa
- Vista de texto
- Vista de anotar
- Vista convertida

## <a name="file-metadata"></a>Metadatos de archivo

Este panel puede activarse o desactivarse para mostrar varios metadatos asociados con el documento. Aunque la cuadrícula de resultados de búsqueda se puede personalizar para Mostrar metadatos específicos, hay casos en los que el desplazamiento horizontal puede resultar difícil mientras se revisan los datos. El panel metadatos de archivo permite al usuario alternar una vista dentro del visor.

![Panel metadatos de archivo
](../media/Reviewimage2.png)

## <a name="native-view"></a>Vista nativa

El visor nativo muestra la vista más completa de un documento. Admite cientos de tipos de archivo y está destinado a mostrar la experiencia más auténtica posible a la experiencia nativa. Para los archivos de Microsoft Office, por ejemplo, el visor aprovecha Office online para mostrar contenido como comentarios del documento, fórmulas de Excel, filas o columnas ocultas, notas de PowerPoint, etc. Para obtener más información acerca de los visores de Office Online, \[visite aquí necesita vínculo\]

![Vista nativa
](../media/Reviewimage3.png)

## <a name="text-view"></a>Vista de texto

El visor de texto proporciona una vista del texto extraído de un archivo. Ignora las imágenes incrustadas y el formato, pero será una vista eficaz si un usuario intenta comprender el contenido rápidamente. La vista de texto también incluye otras características:

  - El contador de línea hace que sea más fácil hacer referencia a partes específicas de un documento

  - Buscar el resaltado de referencias que resaltará los términos dentro del documento, así como la barra de desplazamiento

  - La vista de diferencias proporciona una vista de comparación que resalta las diferencias textuales al ver documentos con duplicados Near

![Vista de texto
](../media/Reviewimage4.png)

![Vista de diferencias
](../media/Reviewimage5.png)

## <a name="annotate-view"></a>Vista de anotar

La vista anotar proporciona características que permiten a los usuarios aplicar marcas en un documento durante la investigación, incluidos:

  - Redacciones de área: los usuarios pueden dibujar un cuadro en el documento con el fin de ocultar contenido confidencial.

  - Lápiz: los usuarios pueden dibujarse en un documento de forma gratuita para atraer la atención sobre determinadas partes de un documento.

  - Seleccionar anotaciones: los usuarios pueden seleccionar anotaciones en un documento para poder eliminar

  - Alternar transparencia de anotación: hace que las anotaciones sean semitransparentes para poder ver el contenido detrás de la anotación

  - Página anterior: se desplaza a la página anterior

  - Página siguiente: se desplaza a la página siguiente.

  - Ir a la página: el usuario puede escribir un número de página específico para navegar

  - Zoom: establece el nivel de zoom para la vista anotar

  - Girar: el usuario puede girar el documento en sentido horario

  - Buscar: el usuario puede buscar en un documento y desplazarse a los distintos aciertos dentro del documento
    
    ![Vista de anotar
    ](../media/Reviewimage1.png)

Tenga en cuenta que estas anotaciones se encuentran en datos recopilados como evidencia, no en su ubicación original en el sistema activo. 

## <a name="more-information"></a>Más información

En la siguiente tabla se enumeran los límites de evidencia en las investigaciones de datos (versión preliminar).  Los elementos que excedan los máximos de un solo archivo se mostrarán como errores de procesamiento.
    
  |**Descripción del límite**|**Límite**|
  |:-----|:-----|
  |Número máximo de colecciones de evidencias  <br/> |50  <br/> |
  |Número total de documentos que se pueden recopilar en un caso (para todas las colecciones de evidencias en la investigación)  <br/> |1 millón  <br/> |
  |Tamaño total de archivo por carga  <br/> |100 GB  <br/> |
  |Tamaño máximo de un solo archivo   <br/> |100 MB  <br/> |
  |Número máximo de caracteres extraídos de un único archivo  <br/> |10 millones  <br/> |
  |Profundidad de los elementos insertados en un documento  <br/> |IVA  <br/> |
  
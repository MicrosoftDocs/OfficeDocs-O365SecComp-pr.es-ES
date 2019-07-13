---
title: Revisar las conversaciones en eDiscovery avanzado
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
ms.openlocfilehash: 62f0dc9e32e89954b2838b70757d3a7c17d79cc4
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2019
ms.locfileid: "35672993"
---
# <a name="review-conversations-in-advanced-ediscovery"></a>Revisar las conversaciones en eDiscovery avanzado 

La mensajería instantánea es una forma cómoda de plantear preguntas, compartir ideas o comunicarse rápidamente a través de grandes audiencias. A medida que las plataformas de mensajería instantánea, como Microsoft Teams, se convierten en las principales de colaboración empresarial, las organizaciones deben evaluar cómo el flujo de trabajo de eDiscovery aborda estas nuevas formas de comunicación y colaboración. 

La característica de reconstrucción de conversaciones en eDiscovery avanzado está diseñada para ayudarle a identificar el contenido contextual y producir vistas de conversación distintas. Esta función le permite revisar de forma rápida y eficaz las conversaciones de mensajes instantáneos completa (también denominadas *conversaciones*encadenadas) que se generan en plataformas como Microsoft Teams.

Con la reconstrucción de conversaciones, puede usar capacidades integradas para reconstruir, revisar y exportar conversaciones encadenadas. Use la reconstrucción avanzada de conversaciones de exhibición de documentos electrónicos para:

- Conserve los metadatos exclusivos en el nivel de mensaje en todos los mensajes de una conversación.

- Recopilar mensajes contextuales alrededor de los resultados de búsqueda.

- Revisar, anotar y censurar conversaciones encadenadas.

- Exportar mensajes individuales o conversaciones encadenadas

## <a name="terminology"></a>Terminología

Estas son algunas definiciones para ayudarle a empezar a usar la reconstrucción de conversaciones.

- **Mensajes:** Representan la unidad más pequeña de una conversación. Los mensajes pueden variar en tamaño, estructura y metadatos. 

- **Conversación:** Representa una agrupación de uno o más mensajes. En las distintas aplicaciones, las conversaciones pueden representarse de formas diferentes. En algunas aplicaciones, hay una acción explícita que se produce al responder a un mensaje existente. Las conversaciones se crean de forma explícita como resultado de esta acción del usuario. Por ejemplo, aquí se muestra una captura de pantalla de una conversación de canal en Microsoft Teams.

   ![Conversación de canal de Microsoft Teams](../media/threadedchat.png)

   En otras aplicaciones (como los mensajes de chat de 1xN en Microsoft Teams), no hay una cadena de respuestas formales y en su lugar los mensajes aparecen como una "río plano de mensajes" en un único subproceso. En estas aplicaciones de tipos, las conversaciones se deducen de un grupo de mensajes que se producen en un momento determinado. Esta "agrupación flexible" de mensajes (a diferencia de una cadena de respuesta) representa la conversación "hacia delante y hacia atrás" sobre un tema específico de interés. 

## <a name="step-1-run-a-search"></a>Paso 1: ejecutar una búsqueda

Una vez que haya identificado los custodios y las ubicaciones de contenido relevantes, puede crear una búsqueda para encontrar contenido potencialmente relevante. En la ficha **búsquedas** en el caso de exhibición avanzada de documentos electrónicos, puede crear una búsqueda haciendo clic en **nueva búsqueda** y siguiendo el asistente. Para obtener información sobre cómo se puede crear una búsqueda, crear una consulta de búsqueda y ver los resultados de la búsqueda, vea [recopilar datos para un caso](create-search-to-collect-data.md).

## <a name="step-2-create-a-conversation-review-set"></a>Paso 2: crear un conjunto de revisión de conversación

En un conjunto de revisiones, puede buscar, etiquetar, anotar y censurar documentos, mensajes de correo electrónico y conversaciones de chat. En la exhibición avanzada de documentos electrónicos, puede personalizar la revisión de las conversaciones, en función de mensajes individuales o conversaciones encadenadas. Esto lo determina el tipo de conjunto de revisión que agrega los resultados de la búsqueda creada en el paso 1 a. Hay dos tipos diferentes de conjuntos de revisión: 
  
  - **Conjuntos de revisión estándar:** Los mensajes en conversaciones se procesan y se muestran como elementos individuales. 
  
  -  **Conjuntos de revisión de conversación:** Los mensajes en conversaciones se procesan de forma individual, pero se muestran en una vista de conversación. En un conjunto de revisión de conversación, puede anotar, etiquetar y censurar mensajes en una vista de conversación encadenada. 

Para obtener más información acerca de cómo revisar y administrar el contenido de un conjunto de revisión, consulte [Manage Review sets](managing-review-sets.md). 

## <a name="step-3-enable-conversation-retrieval-options"></a>Paso 3: habilitar las opciones de recuperación de conversaciones

Una vez que haya revisado y finalizado la consulta de búsqueda, puede Agregar los resultados de la búsqueda a un conjunto de revisión. Cuando se agregan los resultados de la búsqueda a un conjunto de revisión, los datos originales se copian en un área de almacenamiento de Azure para facilitar el proceso de revisión y análisis. Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisiones, consulte [Agregar resultados de búsqueda a un conjunto de revisiones](add-data-to-review-set.md). 

Al agregar datos de conversaciones a un conjunto de revisión, puede usar las opciones de recuperación de conversaciones para expandir la búsqueda e incluir mensajes contextuales. Después de establecer las opciones de recuperación de conversaciones, pueden ocurrir las siguientes cosas:

  ![Recuperación de conversaciones](../media/messagesandconversations.png)
  
1. Mediante una consulta de palabra clave y un intervalo de fechas, la búsqueda devolvió un error en el *mensaje 3*. Este mensaje formaba parte de una conversación más amplia, ilustrada por *CRC1*. 
  
2. Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, la exhibición avanzada de documentos electrónicos se revertirá y recopilará otros elementos en *CRC1*. 
  
3. Una vez agregados los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*. 



Para habilitar la recuperación de conversaciones:
  
1. En la pestaña **búsquedas** en el caso de eDiscovery avanzado, seleccione una búsqueda y, a continuación, haga clic en **Agregar a conjunto de revisiones** en la página de flotante.
  
2. Seleccione un conjunto de revisiones existente o cree un conjunto de revisión. Puede configurar las opciones de recuperación al agregar resultados de búsqueda a un conjunto de revisión estándar o de conversación.
  
3. Configure las opciones de recuperación de conversaciones para los orígenes de contenido que desea expandir en la búsqueda y, a continuación, haga clic en **Agregar** para iniciar el proceso.  
  
4. Una vez finalizado el trabajo **Agregar a la definición de revisión** en la ficha **trabajos** , puede iniciar la revisión de las conversaciones.

## <a name="step-4-review-conversations-in-the-review-set"></a>Paso 4: revisar las conversaciones en el conjunto de revisiones

Una vez que el contenido se ha procesado y agregado al conjunto de revisiones, puede iniciar la revisión de los datos en el conjunto de revisión. Las capacidades de revisión son diferentes en función de si el contenido se agregó a un conjunto de revisión estándar o un conjunto de revisión de conversación. 

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revisión de conversaciones en un conjunto de revisión estándar

En un conjunto de revisiones estándar, los mensajes se procesan y se muestran como elementos individuales, de manera similar a como se almacenan en una carpeta de buzón de correo. En este flujo de trabajo, cada mensaje se procesa como un elemento independiente. Como resultado, las opciones de exportación y Resumen encadenados no están disponibles en un conjunto de revisión estándar. 

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revisar conversaciones en un conjunto de revisión de conversación

En un conjunto de revisión de conversación, los mensajes individuales se enlazan juntos y se presentan como conversaciones. Esto le permite revisar y exportar conversaciones contextuales. En las siguientes secciones se describe cómo revisar y exportar conversaciones en un conjunto de revisión de conversación.

#### <a name="reviewing-conversations"></a>Revisión de conversaciones

En un conjunto de revisión de conversación, puede usar las siguientes opciones para facilitar el proceso de revisión.

- **Agrupar por conversación:** Agrupa mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión. 

- **Vista de Resumen:** Muestra la conversación encadenada. En esta vista, puede ver la conversación completa y también tener acceso a los metadatos de cada mensaje individual.  
  
   - Ver metadatos de mensajes individuales
   
   - Descargar mensajes individuales

- **Vista de texto:** Proporciona el texto extraído de toda la conversación. 

- **Vista de anotar:** Permite marcar una vista encadenada de la conversación. Todos los mensajes de la conversación comparten el mismo documento con comentarios.

- **Etiqueta:** Al ver conversaciones en un conjunto de revisiones, puede ver y aplicar etiquetas haciendo clic en el **Panel de codificación**.

- **Volver a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear las vistas de Resumen y anotaciones de conversaciones. Si se produce un error en el trabajo de reconstrucción de conversaciones, puede volver a ejecutar el trabajo de conversión haciendo clic en **acción > crear una conversación en PDF** en el conjunto de revisión.


#### <a name="exporting-conversations"></a>Exportar conversaciones

En un conjunto de revisión de conversación, puede establecer las siguientes opciones para exportar conversaciones:

![Exportar](../media/export.png)

a. Opciones de metadatos

   - **Cargar archivo:** Los metadatos se incluyen para cada mensaje, correo electrónico y documento individual. Hay una fila por cada mensaje en una conversación. 

   - **Etiquetas:** Las etiquetas del proceso de revisión se incluyen en el archivo de metadatos. Los mensajes de una conversación comparten las mismas etiquetas. 

b. Opciones de conversación
  
   - **Archivos de conversación:** Cuando se exportan archivos de conversación, la vista anotada se convierte en un archivo PDF y se descarga en la carpeta de exportación. Los mensajes de un archivo de conversación apuntan a la versión PDF del mismo archivo de conversación.  
  
   - **Mensajes de chat individuales:** Cuando se exportan mensajes individuales, cada mensaje único de la conversación se exporta como un elemento independiente. El archivo se exporta en el mismo formato en el que se guardó como en el buzón. Para una conversación específica, recibe varios archivos. msg. 

     >[!NOTE]
     > Si ha aplicado anotaciones en el archivo de conversación, estas anotaciones no se transferirán a los mensajes individuales. 

c. Otras opciones

   - **Generar archivos de texto para todo el contenido exportado:** Genera un archivo de texto para cada conversación exportada desde el conjunto de revisión. 

   - **Reemplazar el contenido exportado con documentos PDF censurados:** Si se generan archivos de conversación censurados durante el proceso de revisión, estos archivos estarán disponibles durante la exportación. Puede decidir si desea exportar sólo los archivos nativos (no selecciona esta opción) o reemplazar los archivos nativos con las versiones censuradas de los archivos nativos (seleccionando esta opción), que se exportan como archivos PDF.

## <a name="more-information"></a>Más información

Para obtener más información sobre cómo revisar los datos de casos en la exhibición avanzada de documentos electrónicos, vea los siguientes artículos:

- [Ver datos de casos](view-documents-in-review-set.md) 

- [Analizar datos de casos](analyzing-data-in-review-set.md)

- [Exportar datos de casos](exporting-data-ediscover20.md)

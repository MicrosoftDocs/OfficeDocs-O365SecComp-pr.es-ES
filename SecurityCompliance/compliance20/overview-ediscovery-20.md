---
title: Información general de eDiscovery avanzada (vista previa) en Microsoft 365
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
description: En este artículo se describe la nueva versión de avanzada exhibición de documentos electrónicos (vista previa) en Microsoft 365.
ms.openlocfilehash: aed4739db02ffda83319ada5b1c5fdf20426a1fa
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608345"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a>Información general de eDiscovery avanzada (vista previa) en Microsoft 365

Microsoft acaba de lanzar una versión de vista previa de la herramienta de exhibición de documentos electrónicos avanzada actualizada que se basa en las capacidades de exhibición de documentos electrónicos existentes en Office 365. Esta versión de vista previa, denominada *exhibición de documentos electrónicos avanzada (vista previa)*, proporciona un flujo de trabajo de extremo a otro para conservar, recopilar, revisar, analizar y exportar el contenido que responde a las investigaciones internas y externas de su organización. 

## <a name="alignment-with-edrm"></a>Alineación con EDRM

El flujo de trabajo integrado de exhibición de documentos electrónicos avanzada (vista previa) se alinea con el proceso de exhibición de documentos electrónicos descrito por el modelo de referencia de detección electrónica (EDRM). 

![El modelo de referencia de descubrimiento electrónico (EDRM)](../media/EDRMv1.png)

(Origen de la imagen cortesía de edrm.net. La imagen de origen se puso a disposición en Creative Commons atribución 3.0 Unported licencia.)

En un nivel alto, eDiscovery cómo avanzada del aquí (vista previa) es compatible con el flujo de trabajo EDRM:

- **Identificación** : después de identificar las posibles personas que le interesen en una investigación, puede agregarlos como custodia (también denominado *custodia de datos*, ya que poseen información que es relevante para la investigación) a un avanzado caso de exhibición de documentos electrónicos (vista previa). Después de que los usuarios se agregan como custodia, es fácil conservar, recopilar y revisar los documentos de custodia.

- **Conservación** - a conservar y proteger los datos que es relevantes para una investigación avanzada exhibición de documentos electrónicos (vista previa) le permite que situar una suspensión legal en los orígenes de datos que están asociados con la custodia en un caso. También puede colocar datos que no sean custodia en espera. Además, exhibición de documentos electrónicos avanzada (vista previa) tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de una suspensión legal a custodia y realizar un seguimiento de sus confirmaciones.

- **Colección** - una vez identificado (y conserva) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integradas en busca de exhibición de documentos electrónicos avanzada (vista previa) y recopilar datos activos de los orígenes de datos de custodia (y que no sean custodia orígenes de datos, si procede) que pueden ser pertinentes para el caso.

- **Procesamiento** - después de que ha recopilado todos los datos relevantes para el caso, el siguiente paso es procesarlo para el análisis y revisión posterior. En Opciones avanzada exhibición de documentos electrónicos (vista previa), esto significa que los datos en el lugar que ha identificado en la fase de recopilación se copian en la ubicación de almacenamiento de Azure (llama a un *conjunto de trabajo*), que le proporciona una vista estática de los datos de escenario. 
 
- Conjunto de **revisión** - después de datos se ha agregado a un trabajo, puede ver documentos específicos y ejecutar consultas adicionales a  
 
- **Análisis** - avanzada de exhibición de documentos electrónicos (vista previa) proporciona herramientas de análisis integrado que le ayuda a seleccionamos datos desde el conjunto de trabajo que determine que no es relevante para la investigación. Además de reducir el volumen de los datos relevantes, avance exhibición de documentos electrónicos (vista previa) también le ayuda a ahorrar costos de revisión legal, por lo que le permite organizar el contenido para facilitar el proceso de revisión y más eficaces.

- **Producción** y **presentación** - cuando esté listo, puede exportar documentos de un conjunto de trabajo para su revisión legal. Puede exportar documentos en su formato nativo o en un formato especificado EDRM por lo que se pueden importar a las aplicaciones de revisión de otro fabricante.

## <a name="advanced-ediscovery-preview-workflow"></a>Flujo de trabajo de exhibición de documentos electrónicos avanzada (vista previa)

Las secciones siguientes describen cada paso del flujo de trabajo integrados en la exhibición de documentos electrónicos avanzada (vista previa). La siguiente captura de pantalla muestra la ficha **página principal** de un caso de denominado *2019002 de responsabilidad de producto*. Tenga en cuenta que las fichas de flujo de trabajo en la parte superior de la página se ordenan para alinear con el proceso de EDRM. 

Para obtener más información sobre el flujo de trabajo de extremo a otro en la exhibición de documentos electrónicos avanzada (vista previa), vea este [Vídeo de mecánica de Microsoft](https://go.microsoft.com/fwlink/?linkid=2066133). 

![Las fichas en la exhibición de documentos electrónicos avanzada (vista previa) siguen el flujo de trabajo EDRM](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>Administración de custodia

Utilice la ficha de **custodia** para agregar y administrar las personas que ha identificado como las personas que le interesen en las mayúsculas y minúsculas. Cuando agrega custodia, rápidamente se pueden realizar acciones relacionadas con la custodia como colocar un procedimiento legal en orígenes de datos de custodia, como sus buzones de correo y OneDrive para la cuenta, comunicarse con custodia y búsqueda de los orígenes de datos de custodia para recopilar contenido que es relevante para el caso. Como el progreso de casos, es fácil agregar a nuevo custodia o la última versión a custodia de las mayúsculas y minúsculas. Para obtener más información, vea [trabajar con custodia de exhibición de documentos electrónicos avanzada (vista previa)](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Gestionar notificaciones de retención legal

Use la ficha **comunicaciones** para administrar el proceso de la comunicación con la custodia en las mayúsculas y minúsculas. Un aviso de retención legal indica custodia para conservar cualquier contenido que puede ser relevante para el caso. Equipos legales deben poder realizar un seguimiento que avisos se han recibido, leer y confirmar por custodia. El flujo de trabajo de comunicaciones en la exhibición de documentos electrónicos avanzada (vista previa) permite crear y enviar notificaciones iniciales, avisos, versión avisos y escalaciones si se producirá un error en custodia confirmar una notificación de espera. Para obtener más información, vea [trabajar con las comunicaciones de exhibición de documentos electrónicos avanzada (vista previa)](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Administrar la conservación del contenido

Cuando se agrega una custodia a un caso, tiene la opción de colocar una suspensión en custodia datos. Use la ficha **contiene** para administrar la suspensión creada al agregar a custodia y administrar adicionales con fines legales contiene asociada con el caso; Por ejemplo, puede identificar y colocar una suspensión en orígenes de datos que no sean custodia. También puede editar cualquier espera en el caso y convertirla en una espera basada en consultas para que sólo el contenido que coincide con la consulta se pondrá en espera; Por ejemplo, podría agregar un intervalo de fechas a la suspensión para que sólo el contenido que se creó en una fecha específica que se iban en conserva. También puede obtener estadísticas de contenido que se encuentra en suspensión, quitar la suspensión después cuando ya no es relevante para el caso o eliminarla. Para obtener más información, vea [Administrar suspensiones de exhibición de documentos electrónicos avanzada (vista previa)](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indización de custodia de datos

Cuando se agrega una custodia y los orígenes de datos de custodia correspondiente a un caso, cualquier elemento indizado parcialmente desde un origen de datos de custodia se indiza a volver a (mediante un proceso denominado *indización avanzada*). Esto permitirá custodia contenido, como imágenes, tipos de archivo no compatibles y otro contenido potencialmente no indizado se que permite realizar búsquedas cuando se ejecute búsquedas para recopilar datos que es relevantes para el caso. Utilice la ficha **de procesamiento** para supervisar el estado de indización avanzada y la corrección de procesamiento de errores (mediante una calle de proceso *corrección de error*). Para obtener más información, vea [fijación de procesamiento de errores en la exhibición de documentos electrónicos avanzada (vista previa)](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Recopilar datos de casos

Use la ficha **búsquedas** para crear búsquedas para buscar en contexto custodia y orígenes de datos que no sean custodia en Office 365 para el contenido que es relevante para el caso. Puede crear y ejecutar búsquedas basada en consultas (mediante las palabras clave y condiciones) para identificar un mensajes de correo electrónico de conjunto y documentos que son relevantes para el caso y en la que desean aún más la revisión y analizar en los siguientes pasos en el flujo de trabajo de exhibición de documentos electrónicos. Puede crear una o varias búsquedas asociadas con el caso. Además, puede usar la herramienta de búsqueda para obtener una vista previa de documentos de muestra y ver las estadísticas de búsqueda que pueden ayudar a refinar y mejoran los resultados de búsqueda. Una vez que esté satisfecho que los resultados de búsqueda contienen todos los datos relevantes para el caso, agregar los resultados de búsqueda a un conjunto de trabajo para una revisión posterior, análisis y si es necesario, la selección. Para obtener más información, vea la [recopilación de datos para un caso de exhibición de documentos electrónicos avanzada (vista previa)](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzig-case-data"></a>Revisar y analyzig los datos de casos

Utilice la ficha **conjuntos de trabajo** o revisar y analizar el contenido que se ha recopilado desde el sistema de live y agregado a un conjunto de trabajo. Un *conjunto de trabajo* es una colección estática (es decir, una copia sin conexión de rápido) de datos custodia (y si procede, los datos que no sean custodia) que recopilan en la fase anterior del flujo de trabajo de exhibición de documentos electrónicos. Cuando se agrega los resultados de búsqueda a un conjunto de trabajo, se desencadena un proceso que extrae los archivos de contenedores, extrae metadatos y extrae el texto. Una vez completado este proceso, el sistema crea un nuevo índice de todos los datos recopilados de custodia y se agregó para el conjunto de trabajo. Una vez que los datos se agregan al conjunto de trabajo, puede ejecutar consultas adicionales para restringir los datos de los casos, ver los datos como texto o en el formato de archivo nativo y puede incluir anotaciones, censurar y establecer etiquetar documentos en el trabajo. Además, puede realizar análisis avanzados, como identificar documentos duplicados, los subprocesos de correo electrónico y los temas. Una vez que haya efectuadas los datos a solo lo que es relevante para el caso, puede descargar documentos de descarga directamente o exportarlos junto con los metadatos de archivo, las anotaciones y las etiquetas. Para obtener más información, vea:

  - [Revisión de los datos de casos de exhibición de documentos electrónicos avanzada (vista previa)](reviewing-data-in-working-set.md)
  - [Analizar datos en un conjunto de trabajo en la exhibición de documentos electrónicos avanzada (vista previa)](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Exportación de datos para su revisión y presentación

Después de exportar los datos de un conjunto de trabajo, use la ficha **exportaciones** para administrar un trabajo de exportación y descargar los datos de un conjunto de trabajo. Al exportar un conjunto de trabajo, los datos se cargan en una ubicación de almacenamiento de Azure y, a continuación, está disponibles para ser descargado en un equipo local. Puede obtener la ubicación y evaluación de almacenamiento de información clave es necesario descargar los datos exportados en la ficha de **exportaciones** . Para obtener más información, vea [exportar los datos de casos de exhibición de documentos electrónicos avanzada (vista previa)](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Administración de trabajos

Utilice la ficha **trabajos** para supervisar los procesos de larga duración para tareas relacionadas con el caso de que se ha iniciado, las búsquedas como volver a indizar, las búsquedas y exportaciones. Por ejemplo, podría crear una nueva búsqueda en la ficha de **búsquedas** que incluye un gran número de orígenes de datos. El estado de este proceso de búsqueda se muestra en la ficha **trabajos** . Para obtener más información, vea [Administrar trabajos en la exhibición de documentos electrónicos avanzada (vista previa)](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configuración de opciones de mayúsculas y minúsculas

Utilice la ficha **configuración** para configurar las opciones del caso. Esto incluye la adición de miembros a un caso, cierre o eliminación de un caso y configuración de búsqueda y análisis de comportamiento. Para obtener más información, vea [configuración de las opciones casos de exhibición de documentos electrónicos avanzada (vista previa)](configuring-case-settings-ediscovery20.md).


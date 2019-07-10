---
title: Información general sobre la solución de exhibición de documentos electrónicos avanzada en Microsoft 365
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
description: En este artículo se describe la nueva versión de eDiscovery avanzado en Microsoft 365.
ms.openlocfilehash: 45c7a35a27fea3891270ee72b1fd528a357ad825
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598736"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Información general sobre la solución de exhibición de documentos electrónicos avanzada en Microsoft 365

La solución Advanced eDiscovery de Microsoft 365 se basa en las capacidades existentes de eDiscovery y de análisis en Office 365. Esta nueva solución, denominada *exhibición avanzada*de documentos electrónicos, proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. También permite a los equipos jurídicos administrar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores involucrados en un caso. 

## <a name="alignment-with-edrm"></a>Alineación con EDRM

El flujo de trabajo integrado de eDiscovery avanzado se alinea con el proceso de eDiscovery descrito por el modelo de referencia de detección electrónica (EDRM). 

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

(Origen de la imagen por cortesía de edrm.net. La imagen de origen estaba disponible en la licencia no desported de Creative Commons Atribution 3,0.)

En un nivel alto, a continuación se muestra cómo la exhibición avanzada de documentos electrónicos admite el flujo de trabajo EDRM:

- **Identificación** : después de identificar las posibles personas de interés en una investigación, puede agregarlas como custodios (también denominados custodios de *datos*, ya que pueden poseer información relevante para la investigación) a un avanzado caso de exhibición de documentos electrónicos. Una vez que los usuarios se agregan como custodios, es fácil preservar, recopilar y revisar los documentos de custodios.

- **Conservación** : para preservar y proteger los datos relevantes para una investigación, la exhibición avanzada de documentos electrónicos le permite realizar una retención legal en los orígenes de datos asociados con los custodios en un caso. También puede poner los datos que no son de Private en espera. EDiscovery avanzado también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de retención legal a los custodios y realizar un seguimiento de sus confirmaciones.

- **Colección** : después de identificar (y conservar) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en la búsqueda avanzada de exhibición de documentos electrónicos y recopilar datos en directo de los orígenes de datos (y orígenes de datos que no sean de Private). , si procede, que puede ser relevante para el caso.

- **Procesamiento** : una vez que haya recopilado todos los datos relevantes para el caso, el siguiente paso es procesarlo para revisión y análisis adicionales. En la exhibición avanzada de documentos electrónicos, los datos locales que identificó en la fase de recopilación se copian en una ubicación de Azure Storage (denominada un *conjunto de revisión*), que proporciona una vista estática de los datos de caso. 
 
- **Revisión** : una vez agregados los datos a un conjunto de revisión, puede ver documentos específicos y ejecutar otras consultas para reducir los datos a lo que sea más importante en el caso. Además, puede anotar y etiquetar documentos específicos.
 
- **Analysis** : Advanced eDiscovery proporciona herramientas de análisis integradas que le ayudarán a deshacer más los datos del conjunto de revisión que determine que no es relevante para la investigación. Además de reducir el volumen de datos relevantes, la exhibición avanzada de documentos electrónicos también le ayuda a ahorrar costos legales de revisión permitiéndole organizar el contenido para que el proceso de revisión sea más fácil y eficaz.

- **Producción** y **presentación** : cuando esté listo, puede exportar documentos de un conjunto de revisión para su revisión legal. Puede exportar documentos en su formato nativo o en un formato especificado por el EDRM para que se puedan importar en aplicaciones de revisión de terceros.

## <a name="advanced-ediscovery-workflow"></a>Flujo de trabajo avanzado de eDiscovery

En las secciones siguientes se describe cada paso del flujo de trabajo integrado en eDiscovery avanzado. En la siguiente captura de pantalla se muestra la pestaña **Inicio** de un caso denominado *pasivo del producto 2019002*. Nota las pestañas de flujo de trabajo en la parte superior de la página se ordenan para alinearse con el proceso EDRM. 

Para obtener más información acerca del flujo de trabajo de un extremo a otro en la exhibición avanzada de documentos electrónicos, vea este [vídeo de Microsoft](https://go.microsoft.com/fwlink/?linkid=2066133). 

![Las pestañas en eDiscovery avanzado siguen el flujo de trabajo de EDRM](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>Administración de custodios

Use la **** ficha custodios para agregar y administrar las personas que ha identificado como personas de interés en el caso. Al agregar custodios, puede realizar rápidamente acciones relacionadas con el custodio, como colocar una retención legal en fuentes de datos de custodios, comunicarse con custodios y buscar fuentes de datos de custodios para recopilar contenido relevante para el caso. A medida que avanza el caso, es fácil agregar custodios nuevos o liberar los custodios del caso. Para obtener más información, consulte [work with custodios in Advanced eDiscovery](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Administración de notificaciones de retención legal

Use la pestaña **comunicaciones** para administrar el proceso de comunicación con los custodios en el caso. Un aviso de suspensión legal instruye a los custodios para que conserven el contenido relevante para el caso. Los equipos jurídicos deben ser capaces de realizar un seguimiento de los avisos recibidos, leídos y reconocidos por los custodios. El flujo de trabajo de comunicaciones en eDiscovery avanzado permite crear y enviar notificaciones iniciales, recordatorios, avisos de versión y escalamientos si los custodios no reconocen una notificación de retención. Para obtener más información, consulte [trabajar con comunicaciones en la exhibición avanzada de](managing-custodian-communications.md)documentos electrónicos.

## <a name="managing-content-preservation"></a>Administración de la conservación de contenido

Cuando agrega un custodio a un caso, puede poner una retención en los datos de Private. Use la **** pestaña suspensiones para administrar la suspensión creada al agregar custodios y para administrar otras retenciones legales asociadas con el caso; por ejemplo, puede identificar y poner una retención en orígenes de datos que no sean de Private. También puede editar cualquier suspensión en el caso y convertirlo en una retención basada en consulta para conservar solo el contenido que coincida con la consulta. Por ejemplo, puede Agregar un intervalo de fechas a la suspensión para que solo se conserve el contenido creado en un intervalo de fechas específico. También puede obtener estadísticas de contenido que está en suspensión, quitar la retención después de que ya no sea relevante para el caso o eliminarla. Para obtener más información, consulte [Administrar suspensiones en EDiscovery avanzado](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indización de datos del custodio

Cuando se agrega un custodio y los orígenes de datos Private correspondientes a un caso, cualquier elemento parcialmente indizado de un origen de datos de custodio se vuelve a indexar mediante un proceso denominado *indización avanzada*. Esto permite que el contenido de apoyo como imágenes, tipos de archivo no admitidos y otro contenido no indexado se pueda buscar por completo al ejecutar búsquedas para recopilar datos en el caso. Use la ficha **procesamiento** para supervisar el estado de la indización avanzada y corregir los errores de procesamiento mediante un proceso denominado *corrección de errores*. Para obtener más información, vea [corregir errores de procesamiento en la exhibición avanzada de](processing-data-for-case.md)documentos electrónicos.

## <a name="collecting-case-data"></a>Recopilar datos de casos

Use la ficha **búsquedas** para crear búsquedas para buscar en los orígenes de datos de la custodia y no Private en Office 365 el contenido relevante para el caso. Puede crear y ejecutar búsquedas basadas en consultas (usando palabras clave y condiciones) para identificar un conjunto de mensajes de correo electrónico y documentos que sean relevantes para el caso y que desee revisar y analizar en los siguientes pasos del flujo de trabajo de eDiscovery. Puede crear una o más búsquedas asociadas con el caso. También puede usar la herramienta de búsqueda para obtener una vista previa de los documentos de ejemplo y ver estadísticas de búsqueda para ayudarle a refinar y mejorar los resultados de la búsqueda. Una vez que haya comprobado que los resultados de la búsqueda contienen todos los datos relevantes para el caso, agregue los resultados de la búsqueda a un conjunto de revisión para la revisión, el análisis y la selección adicionales. Para obtener más información, vea [recopilar datos para un caso en EDiscovery avanzado](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Revisión y análisis de datos de casos

Use la pestaña **conjuntos de revisiones** para revisar y analizar el contenido que ha recopilado desde el sistema activo y que se ha agregado a un conjunto de revisión. Un *conjunto de revisiones* es una colección estática de los datos (es decir, una copia sin conexión de datos) de los datos de Private (y, si procede, de datos no de Private) que haya recopilado en la fase anterior del flujo de trabajo de eDiscovery. Cuando se agregan los resultados de la búsqueda a un conjunto de revisión, se desencadena un proceso que extrae los archivos de los contenedores, extrae los metadatos y extrae el texto. Cuando se completa este proceso, el sistema crea un nuevo índice de todos los datos recopilados por los custodios y los agrega al conjunto de revisión. Una vez que los datos se agregan al conjunto de revisión, puede ejecutar más consultas para acotar los datos de mayúsculas y minúsculas, ver datos como texto o en el formato de archivo nativo, y anotar, censurar y etiquetar documentos en el conjunto de revisión. También puede realizar análisis avanzados, como identificar la duplicación de documentos, los subprocesos de correo electrónico y los temas. Una vez que haya seleccionado los datos solo para lo que sea relevante para el caso, puede descargar los documentos directamente o exportarlos junto con los metadatos de archivo, las anotaciones y cualquier etiqueta. Para obtener más información, vea:

- [Revisar los datos de casos en eDiscovery avanzado](reviewing-data-in-review-set.md)
- [Analizar datos en un conjunto de revisión en eDiscovery avanzado](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Exportar datos para revisión y presentación

Después de exportar los datos de un conjunto de revisión, use la pestaña **exportaciones** para administrar un trabajo de exportación y descargar datos de un conjunto de revisión. Al exportar un conjunto de revisión, los datos se cargan en una ubicación de almacenamiento de Azure y, a continuación, se pueden descargar en un equipo local. Puede obtener la clave de evaluación de almacenamiento necesaria para descargar los datos exportados en la pestaña **exportaciones** . Para obtener más información, vea [exportar datos de casos en EDiscovery avanzado](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Administración de trabajos

Use la ficha **trabajos** para supervisar procesos de ejecución prolongada para las tareas relacionadas con casos que haya iniciado. Algunos ejemplos de trabajos son los relacionados con la reindización, la búsqueda y la exportación de datos de casos. Por ejemplo, si crea una búsqueda en la ficha **búsquedas** que incluye muchos orígenes de datos, el estado de este proceso de búsqueda se mostrará en la ficha **trabajos** . Para obtener más información, consulte [administrar trabajos en EDiscovery avanzado](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configuración de los casos

Use la pestaña **configuración** para establecer la configuración de casos. Esto incluye agregar miembros a un caso, cerrar o eliminar un caso y configurar las opciones de búsqueda y análisis. Para obtener más información, vea [Configure Case Settings in Advanced eDiscovery](configuring-case-settings-ediscovery20.md).

---
title: Introducción a la exhibición avanzada de documentos electrónicos (versión preliminar) en Microsoft 365
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
description: En este artículo se describe la nueva versión de eDiscovery avanzado (versión preliminar) en Microsoft 365.
ms.openlocfilehash: 2296f4ee1867cacc90eada9e5f12888a8ea0d242
ms.sourcegitcommit: 13c601ea11ce6a3c71036fdafda059061c6998d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2019
ms.locfileid: "30313156"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a>Introducción a la exhibición avanzada de documentos electrónicos (versión preliminar) en Microsoft 365

Microsoft ha lanzado recientemente una versión preliminar de la herramienta actualizada eDiscovery avanzada que se basa en las capacidades existentes de eDiscovery en Office 365. Esta versión preliminar, denominada *exhibición avanzada*de documentos electrónicos (versión preliminar), proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. 

## <a name="alignment-with-edrm"></a>Alineación con EDRM

El flujo de trabajo integrado de la exhibición avanzada de documentos electrónicos (versión preliminar) se alinea con el proceso de eDiscovery descrito por el modelo de referencia de detección electrónica (EDRM). 

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

(Origen de la imagen por cortesía de edrm.net. La imagen de origen estaba disponible en la licencia no desported de Creative Commons Atribution 3,0.)

En un nivel alto, esta es la manera en que eDiscovery avanzado (versión preliminar) admite el flujo de trabajo de EDRM:

- **Identificación** : después de identificar las posibles personas de interés en una investigación, puede agregarlas como custodios (también denominados custodios de *datos*, ya que pueden poseer información relevante para la investigación) a un avanzado eDiscovery (versión preliminar). Una vez que los usuarios se agregan como custodios, es fácil preservar, recopilar y revisar los documentos de custodios.

- **Preservación** : para preservar y proteger los datos relevantes para una investigación, la exhibición avanzada de documentos electrónicos (vista previa) le permite realizar una retención legal en los orígenes de datos asociados con los custodios en un caso. También puede poner los datos que no son de Private en espera. Además, la exhibición avanzada de documentos electrónicos (versión preliminar) tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar una notificación de suspensión legal a los custodios y realizar un seguimiento de sus confirmaciones.

- **Colección** : después de identificar (y conservar) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en eDiscovery avanzado (vista previa) para buscar y recopilar datos activos de los orígenes de datos de Private (y de los que no son de apoyo orígenes de datos, si procede, que puedan ser relevantes para el caso.

- **Procesamiento** : una vez que haya recopilado todos los datos relevantes para el caso, el paso siguiente es procesarlo para su posterior revisión y análisis. En la exhibición avanzada de documentos electrónicos (versión preliminar), esto significa que los datos locales identificados en la fase de recopilación se copian en una ubicación de almacenamiento de Azure (llamada un *conjunto de trabajo*), lo que proporciona una vista estática de los datos de caso. 
 
- **Revisión** : una vez que se han agregado los datos a un conjunto de trabajo, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo que sea más relevante en el caso. Además, puede anotar y etiquetar documentos específicos.
 
- **Analysis** -Advanced EDiscovery (versión preliminar) proporciona herramientas de análisis integradas que le ayudarán a decidir más datos del conjunto de trabajo que determine que no es relevante para la investigación. Además de reducir el volumen de datos relevantes, la exhibición avanzada de documentos electrónicos (vista previa) también le ayuda a ahorrar costos legales de revisión, ya que permite organizar el contenido para que el proceso de revisión sea más fácil y eficaz.

- **Producción** y **presentación** : cuando esté listo, puede exportar documentos de un conjunto de trabajo para revisión legal. Puede exportar documentos en su formato nativo o en un formato especificado por el EDRM para que se puedan importar en aplicaciones de revisión de terceros.

## <a name="advanced-ediscovery-preview-workflow"></a>Flujo de trabajo de eDiscovery avanzado (vista previa)

En las secciones siguientes se describe cada paso del flujo de trabajo integrado en la exhibición avanzada de documentos electrónicos (vista previa). En la siguiente captura de pantalla se muestra la pestaña **Inicio** de un caso denominado *pasivo del producto 2019002*. Nota las pestañas de flujo de trabajo en la parte superior de la página se ordenan para alinearse con el proceso EDRM. 

Para obtener más información acerca del flujo de trabajo de un extremo a otro en la exhibición avanzada de documentos electrónicos (versión preliminar), vea este [vídeo de Microsoft mecánicos de Microsoft](https://go.microsoft.com/fwlink/?linkid=2066133). 

![Pestañas en eDiscovery avanzado (versión preliminar), siga el flujo de trabajo de EDRM](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>Administrar los administradores

Use la **** ficha custodios para agregar y administrar las personas que ha identificado como personas de interés en el caso. Al agregar custodios, puede realizar rápidamente acciones relacionadas con el custodio, como colocar una retención legal en orígenes de datos de custodios, como su buzón de correo y su cuenta de OneDrive, comunicarse con custodios y buscar orígenes de datos de custodios para recopilar contenido eso es relevante para el caso. A medida que avanza el caso, es fácil agregar custodios nuevos o liberar los custodios del caso. Para obtener más información, consulte [work with custodios in Advanced eDiscovery (Preview)](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Administración de notificaciones de retención legal

Use la pestaña **comunicaciones** para administrar el proceso de comunicación con los custodios en el caso. Un aviso de suspensión legal instruye a los custodios para que conserven cualquier contenido que pueda ser relevante para el caso. Los equipos jurídicos deben ser capaces de realizar un seguimiento de que los custodios han recibido, leído y confirmado los avisos. El flujo de trabajo de comunicaciones en la exhibición avanzada de documentos electrónicos (versión preliminar) permite crear y enviar notificaciones iniciales, recordatorios, avisos de versión y escalamientos si los custodios no reconocen una notificación de retención. Para obtener más información, vea [trabajar con comunicaciones en la exhibición avanzada de documentos electrónicos (vista previa)](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Administración de la conservación de contenido

Al agregar un custodio a un caso, tiene la opción de retener los datos de Private. Use la **** pestaña suspensiones para administrar la suspensión creada al agregar custodios y para administrar retenciones legales adicionales asociadas al caso (por ejemplo, puede identificar y poner una retención en orígenes de datos que no sean de privación). También puede editar cualquier suspensión en el caso y convertirlo en una suspensión basada en consulta para que solo se coloque en retención el contenido que coincida con la consulta. Por ejemplo, puede Agregar un intervalo de fechas a la suspensión para que solo se conserve el contenido creado en un intervalo de fechas específico. También puede obtener estadísticas de contenido que está en suspensión, quitar la retención después de que ya no sea relevante para el caso o eliminarla. Para obtener más información, vea [Administrar suspensiones en EDiscovery avanzado (versión preliminar)](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indización de datos del custodio

Cuando se agrega un custodio y los orígenes de datos Private correspondientes a un caso, cualquier elemento parcialmente indizado de un origen de datos de custodio se reindiza (por un proceso denominado *indizaCión avanzada*). Esto permite que el contenido de apoyo como imágenes, tipos de archivo no admitidos y otro contenido no indizado se pueda buscar por completo al ejecutar búsquedas para recopilar datos en el caso. Use la ficha **procesamiento** para supervisar el estado de la indización avanzada y solucionar errores de procesamiento (mediante un proceso denominado *corrección de errores*). Para obtener más información, vea [corregir errores de procesamiento en la exhibición avanzada de documentos electrónicos (versión preliminar)](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Recopilar datos de casos

Use la ficha **búsquedas** para crear búsquedas para buscar en los orígenes de datos de la custodia y no privaTe en Office 365 el contenido relevante para el caso. Puede crear y ejecutar búsquedas basadas en consultas (usando palabras clave y condiciones) para identificar un conjunto de mensajes de correo electrónico y documentos que sean relevantes para el caso y que desee revisar y analizar en los siguientes pasos del flujo de trabajo de eDiscovery. Puede crear una o más búsquedas asociadas con el caso. Además, puede usar la herramienta de búsqueda para obtener una vista previa de los documentos de ejemplo y ver estadísticas de búsqueda que pueden ayudarle a refinar y mejorar los resultados de la búsqueda. Una vez que haya comprobado que los resultados de la búsqueda contienen todos los datos relevantes para el caso, agregue los resultados de la búsqueda a un conjunto de trabajo para la revisión, el análisis y, si es necesario, el sacrificio. Para obtener más información, vea [recopilar datos para un caso en EDiscovery avanzado (versión preliminar)](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Revisión y análisis de datos de casos

Use la ficha **conjuntos de trabajo** para revisar y analizar el contenido que ha recopilado desde el sistema activo y que se ha agregado a un conjunto de trabajo. Un *conjunto de trabajo* es una colección estática de esos datos (en otras palabras, una copia sin conexión de datos) de datos de Private (y, si procede, datos no de Private) que haya recopilado en la fase anterior del flujo de trabajo de eDiscovery. Cuando se agregan resultados de búsqueda a un conjunto de trabajo, se desencadena un proceso que extrae los archivos de los contenedores, extrae los metadatos y extrae el texto. Cuando se completa este proceso, el sistema crea un nuevo índice de todos los datos recopilados de los custodios y agregados al conjunto de trabajo. Una vez agregados los datos al conjunto de trabajo, puede ejecutar consultas adicionales para restringir los datos de mayúsculas y minúsculas, ver datos como texto o en el formato de archivo nativo, y anotar, censurar y etiquetar documentos en el conjunto de trabajo. Además, puede realizar análisis avanzados, como identificar la duplicación de documentos, los subprocesos de correo electrónico y los temas. Una vez que haya seleccionado los datos solo para lo que sea relevante para el caso, puede descargar los documentos directamente o exportarlos junto con los metadatos de archivo, las anotaciones y cualquier etiqueta. Para obtener más información, vea:

  - [Revisar los datos de casos en eDiscovery avanzado (versión preliminar)](reviewing-data-in-working-set.md)
  - [Analizar datos en un conjunto de trabajo en eDiscovery avanzado (versión preliminar)](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Exportar datos para revisión y presentación

Después de exportar los datos de un conjunto de trabajo, use la pestaña **exportaciones** para administrar un trabajo de exportación y descargar datos de un conjunto de trabajo. Cuando se exporta un conjunto de trabajo, los datos se cargan en una ubicación de almacenamiento de Azure y, a continuación, se pueden descargar en un equipo local. Puede obtener la clave de evaluación de almacenamiento y ubicación necesaria para descargar los datos exportados en la ficha **exportaciones** . Para obtener más información, vea [exportar datos de casos en EDiscovery avanzado (versión preliminar)](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Administrar trabajos

Use la ficha **trabajos** para supervisar procesos de ejecución prolongada para las tareas relacionadas con casos que haya iniciado. Por ejemplo, los trabajos incluyen los relacionados con la nueva indexación, búsquedas y exportaciones. Por ejemplo, puede crear una nueva búsqueda en la ficha **búsquedas** que incluya un gran número de orígenes de datos. El estado de este proceso de búsqueda se muestra en la pestaña **trabajos** . Para obtener más información, vea [Manage Jobs in Advanced eDiscovery (Preview)](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configurar los ajustes de casos

Use la pestaña **configuración** para establecer la configuración de casos. Esto incluye agregar miembros a un caso, cerrar o eliminar un caso y configurar el comportamiento de búsqueda y análisis. Para obtener más información, vea [Configure Case Settings in Advanced eDiscovery (Preview)](configuring-case-settings-ediscovery20.md).

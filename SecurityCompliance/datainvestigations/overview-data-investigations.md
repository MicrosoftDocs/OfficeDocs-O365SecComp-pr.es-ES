---
title: Información general sobre las investigaciones de datos (versión preliminar) en Microsoft 365
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
description: En este artículo se describe la herramienta nueva investigación de datos (versión preliminar) en Microsoft 365.
ms.openlocfilehash: 1e7621d577d8d08fd27dc7e20e6b8e7a3491236f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150682"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Información general sobre las investigaciones de datos (versión preliminar) en Microsoft 365

La reescritura de datos se produce cuando un documento que contiene contenido confidencial, confidencial o malintencionado se suelta en un entorno que no es de confianza. Cuando se detecta una reescritura de datos, es importante que contenga rápidamente el entorno, evalúe el tamaño y las ubicaciones del derrame, examine las actividades de los usuarios que lo rodean y, a continuación, elimine los datos derramados del servicio. Mediante la herramienta nueva investigación de datos (versión preliminar), puede buscar datos confidenciales, malintencionados o mal colocados en Office 365, investigar qué ha sucedido y realizar las acciones adecuadas para corregir el derrame.  

En este artículo se describe el uso de las funciones de la nueva herramienta de investigaciones de datos (vista previa) para tratar un escenario de derrame de datos.

## <a name="data-investigations-preview-workflow"></a>Flujo de trabajo de investigaciones de datos (vista previa) 

En las secciones siguientes se describe cada paso del flujo de trabajo integrado en investigaciones de datos (versión preliminar). En la siguiente captura de pantalla se muestra la pestaña **Inicio** de una investigación llamada *High Risk: Finance Documents fuga*. 

![Flujo de trabajo en la herramienta investigaciones de datos](../media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>Buscar datos confidenciales, malintencionados o mal colocados

Use la ficha **búsquedas** para crear búsquedas para buscar el Office 365 para los datos que desea corregir. Puede crear y ejecutar búsquedas basadas en consultas para identificar un conjunto de mensajes de correo electrónico y documentos que puedan contener datos derramados y, a continuación, recopilarlos como evidencia para revisar y analizar. Además, puede usar la herramienta de búsqueda para obtener una vista previa de los documentos de ejemplo y ver estadísticas de búsqueda que pueden ayudarle a refinar y mejorar los resultados de la búsqueda. Una vez que haya comprobado que los resultados de la búsqueda contienen todos los datos relevantes para la investigación, agregue los resultados de la búsqueda al conjunto de evidencias para una revisión más detallada, la evaluación del impacto y la realización de acciones correctivas, según sea necesario. Para obtener más información, vea [buscar datos en una investigación](search-for-data.md).

## <a name="review-and-investigate-evidence"></a>Revisión e investigación de pruebas

Use la pestaña **evidencia** para investigar los datos que ha recopilado desde el servicio activo, que en este caso es Office 365. Los datos del conjunto de evidencias son una instantánea de los resultados de búsqueda que ha recopilado. Cuando se agregan resultados de búsqueda como evidencia, se desencadena un proceso para extraer archivos, metadatos y texto. Cuando se completa este proceso, la herramienta de investigaciones de datos crea un nuevo índice de todos los datos y lo agrega a un conjunto de evidencias. Para cualquier investigación que tenga en cuenta el tiempo, esto le permite incluir rápidamente el entorno mediante la eliminación de datos ubicados en las ubicaciones de contenido originales (en el servicio activo) mientras se investiga la evidencia recopilada en un entorno en cuarentena. Una vez recopilada la evidencia, puede ejecutar consultas adicionales para restringir los datos por intervalo de tiempo, tipos de archivo, propietarios de datos y otros tipos de condiciones. Por ejemplo, mediante el uso de las condiciones de autor, remitente y destinatario, puede identificar rápidamente a los usuarios que han participado en la reescritura de datos y si alguno de los datos derramados se ha compartido con personas fuera de la organización.

También puede ejecutar análisis avanzados en la evidencia que recopila. Esto puede proporcionarle temas generales y organizar las pruebas por parte de los subprocesos de correo electrónico, los duplicados exactos y los duplicados Near para facilitar su investigación. Puede revisar documentos en la vista Texto extraído o en el formato de archivo nativo, y etiquetarlos con resultados de la investigación. Para obtener más información, vea:

  - [Revisar los datos como evidencia](review-data-in-evidence.md)

  - [Ejecutar el análisis para investigar más rápido](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>Administración de personas de interés

Use la ficha **personas de interés** para agregar y administrar las personas que ha identificado como personas de interés durante la investigación de la evidencia. Al agregar personas de interés, se identifican y asignan sus orígenes de datos, como el buzón de correo y la cuenta de OneDrive. A continuación, puede asignar el ámbito de búsquedas adicionales buscando solo las ubicaciones de contenido de esas personas. Cuando se trata de personas de interés, las búsquedas son más eficaces y precisas, ya que la herramienta vuelve a procesar los datos no indizados, como imágenes o tipos de archivo no admitidos. En la ficha **personas de interés** , también puede ver y buscar la actividad de los registros de auditoría de esas personas para ayudarle a investigar con más detalle. Puede agregar más personas de interés durante la investigación. Para obtener más información, consulte [Manage People of Interest a Investigate](manage-people-of-interest.md).

## <a name="indexing-the-data-of-people-of-interest"></a>Indización de los datos de personas de interés

Agregar una persona de interés a una investigación vuelve a indizar los elementos parcialmente indizados de los orígenes de datos de la persona. Este proceso se denomina *indización avanzada*. La indización avanzada vuelve a procesar datos como imágenes y tipos de archivo no admitidos para que estos datos se puedan detectar completamente cuando se ejecutan búsquedas para recopilar datos para una investigación. Use la ficha **procesamiento** para supervisar el estado de la indización avanzada y corregir los errores de procesamiento que puedan producirse mediante un proceso denominado *corrección de errores*. Para obtener más información, vea [corrección de errores al procesar datos para una investigación](error-remediation.md).

## <a name="exporting-data"></a>Exportar datos

Si desea exportar datos, use la pestaña **exportaciones** para administrar un trabajo de exportación y descargar datos del conjunto de evidencias. Cuando se exportan pruebas, los datos se cargan en una ubicación de almacenamiento de Azure y, a continuación, se pueden descargar en un equipo local. En la pestaña **exportaciones** , puede obtener la dirección URL de ubicación de almacenamiento de Azure y la clave de evaluación de almacenamiento, que son necesarias para descargar los datos exportados. Para obtener más información, vea [exportar datos de una investigación](export-data.md).

## <a name="managing-jobs"></a>Administración de trabajos

Use la ficha **trabajos** para supervisar los procesos de ejecución prolongada de las tareas relacionadas con la investigación. Esto incluye trabajos para la ejecución de búsquedas, agregar datos a un conjunto de evidencias, volver a indizar datos y exportar pruebas. Por ejemplo, puede crear una nueva búsqueda en la ficha **búsquedas** que incluya un gran número de orígenes de datos. El estado de este proceso de búsqueda se muestra en la pestaña **trabajos** . Para obtener más información, vea [Manage Jobs in a Data Investigation](manage-jobs.md).

## <a name="configuring-investigation-settings"></a>Configuración de las opciones de investigación

Use la pestaña **configuración** para establecer la configuración de toda la investigación. Esto incluye agregar miembros a una investigación, cerrar o eliminar una investigación y configurar el comportamiento de búsqueda y análisis. Para obtener más información, vea [Configure Settings in Data investigaciones (Preview)](configure-settings-datainvestigations.md).

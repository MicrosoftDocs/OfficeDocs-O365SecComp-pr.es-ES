---
title: Administrar un incidente de derrame de datos en Microsoft 365
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
description: En este artículo se describe el uso de la herramienta nueva investigación de datos (vista previa) en el centro de seguridad & cumplimiento para administrar un incidente de derrame de datos.
ms.openlocfilehash: 93199ad1f548e999dce9ad79ab311a57345b8772
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649935"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Administrar un incidente de derrame de datos en Microsoft 365

La derramación de datos es cuando se publica un documento que contiene información confidencial, confidencial o malintencionada en un entorno que no es de confianza. Cuando se detecta un incidente de derrame de datos, es importante que contenga rápidamente el entorno, evalúe el tamaño y las ubicaciones del derrame, examine las actividades de los usuarios que lo rodean y, a continuación, elimine los datos derramados del servicio. Mediante la herramienta de investigación de datos (versión preliminar), puede buscar datos confidenciales, malintencionados o mal colocados en Office 365, investigar para averiguar qué ha sucedido y, a continuación, tomar las medidas adecuadas.  

## <a name="scope-of-this-article"></a>Ámbito de este artículo

En este artículo se proporciona una lista de instrucciones sobre cómo eliminar elementos de forma permanente de los buzones de correo de Office 365 para que los usuarios o administradores ya no puedan obtener acceso a ellos o puedan recuperarlos. 

> [!NOTE]
> Cuando se eliminan elementos ubicados en un sitio de SharePoint o de OneDrive para la empresa, se conservan durante 93 días desde el momento en que se eliminan de su ubicación original.

## <a name="scenario"></a>Escenario

Se le informa de un incidente de derrame de datos donde un empleado ha compartido sin saberlo un documento altamente confidencial con varias personas a través del correo electrónico. Desea evaluar rápidamente quién recibió este documento, tanto dentro como fuera de la organización. Una vez que haya investigado el incidente, tiene previsto compartir sus hallazgos con otros investigadores para revisar y, a continuación, eliminar de forma permanente los datos derramados de la organización de Office 365. Una vez completada la investigación, desea quitar todas las evidencias. 

> [!IMPORTANT]
> Aunque podrá quitar de forma permanente los datos derramados de su propia organización, los datos que se hayan derramado fuera de la organización no se pueden quitar con estas capacidades.

## <a name="workflow"></a>Flujo de trabajo

Este es el flujo de trabajo para usar investigaciones de datos (versión preliminar) para administrar un incidente de derrame de datos:

1.  Cree una investigación de datos.

2.  Buscar datos confidenciales, malintencionados o mal colocados y recopilarlos como evidencia.

3.  Revise e investigue la evidencia.

4.  Eliminar de forma permanente los datos derramados.

5.  Cierre o elimine la investigación.


## <a name="before-you-begin"></a>Antes de empezar

- Para crear una investigación de datos, buscar contenido y eliminar datos derramados, debe pertenecer al grupo de funciones de investigador de datos en el centro de seguridad & cumplimiento.

- Para controlar los buzones de usuario y las cuentas de OneDrive que puede buscar un investigador, su organización puede configurar límites de cumplimiento. Para obtener más información, configure los [límites de cumplimiento para las investigaciones de eDiscovery](../set-up-compliance-boundaries.md). 

## <a name="step-1-create-a-data-investigation"></a>Paso 1: crear una investigación de datos

Para crear una investigación en la herramienta de investigación de datos (versión preliminar):

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con una cuenta que sea miembro del grupo de funciones de investigador de datos.
    
3. En el centro de seguridad y cumplimiento, haga clic en **investigaciones de datos**.
 
4. En la página **investigaciones de datos (vista previa)** , haga clic en **crear nueva investigación**.
    
5. En la página flotante **nueva investigación de datos** , dé un nombre a la investigación (obligatorio) y, a continuación, escriba una descripción y un número de investigación opcional. El nombre debe ser único en la organización.

6. En **¿desea configurar opciones adicionales después de crear esta investigación?**, siga uno de estos procedimientos:

    - Haga clic en **sí** para crear la investigación y mostrar la página de **configuración** en el nuevo caso. Esto le permite agregar miembros a la investigación.
    
    - Haga clic en **no** para crear la investigación y mostrarla en la lista de casos de la página **investigaciones de datos (vista previa)** . Si elige esta opción, se agregará como el único miembro de la investigación y se usará la configuración de búsqueda y análisis predeterminada. Puede Agregar miembros o cambiar la configuración en cualquier momento después de crear la investigación.

7. Haga clic en **Guardar** para crear la investigación.

    La nueva investigación se muestra en la lista de la página **investigaciones de datos (vista previa)** . 

8. Para abrir una investigación, haga clic en el nombre de la investigación. 

    Se muestra la pestaña **Inicio** de la investigación. 

> [!TIP]
> Considere la posibilidad de establecer una Convención de nomenclatura para las investigaciones y proporcionar toda la información que pueda en el nombre y la descripción para poder buscarla y hacer referencia a ella en el futuro si es necesario.
 
## <a name="step-2-search-for-the-spilled-data"></a>Paso 2: buscar los datos derramados 
 
Si sabe qué usuarios desean buscar datos derramados, puede agregarlos como personas de interés para asignar sus orígenes de datos a la investigación y buscar rápidamente sus buzones de correo y su cuenta de OneDrive. Para agregar personas de interés a la investigación, haga clic en **personas de interés**y, a continuación, haga clic en **Agregar personas de interés**. Para obtener más información, consulte [administrar personas de interés](manage-people-of-interest.md).

En la pestaña **búsquedas** , puede crear búsquedas para buscar los datos derramados. Para obtener más información acerca de la creación de búsquedas, consulte [Search for Data in](search-for-data.md)a Investigation.

Después de ejecutar la búsqueda, puede obtener una vista previa de los ejemplos de los resultados de búsqueda y ver las estadísticas de búsqueda para evaluar la efectividad de la consulta de búsqueda. Después de identificar los elementos que desea eliminar de Office 365, puede Agregar los resultados de la búsqueda a un conjunto de evidencias. Para ello, haga clic en la búsqueda que desea investigar. En la página de control flotante, haga clic en **Agregar resultados a evidencia** y siga las instrucciones. A continuación, en el conjunto de evidencias, puede revisar los documentos individuales, investigar quién tenía acceso a los documentos y exportar los documentos. Para eliminar los documentos (o un subconjunto de documentos) en lugar de revisarlos, vaya al [paso 4](#step-4-delete-the-spilled-data). 

> [!IMPORTANT]
> Las palabras clave que se usan en la consulta de búsqueda pueden contener los datos que se han derramado reales que se están buscando. Por ejemplo, si busca documentos que contengan un número de la seguridad social y lo usa como una palabra clave en la consulta de búsqueda, debe eliminar la consulta posteriormente para evitar más derrames. Puede eliminar la búsqueda o eliminar la investigación completa en el [paso 5](#step-5-close-or-delete-the-investigation). 

## <a name="step-3-review-and-investigate"></a>Paso 3: revisar e investigar 

En la investigación, vaya a la pestaña **evidencia** y haga clic en el conjunto de evidencias que creó en el paso anterior. Una vez completado el trabajo de procesamiento y agregados los resultados de la búsqueda a la evidencia, puede revisar los documentos individuales en su formato nativo, formato de texto o un formato casi nativo. Puede crear consultas adicionales para restringir la lista de documentos y etiquetar los documentos para indicar los resultados de la investigación. Para obtener más información, vea [Review Data in Evidence](review-data-in-evidence.md) .

Para agrupar documentos y obtener más ayuda para su revisión, haga clic en **administrar evidencias**. En el mosaico **Analytics** , haga clic en **analizar**. Esto ejecuta análisis avanzados como detección de duplicados, subprocesamiento de correo electrónico y análisis de temas. Para obtener más información, vea:

- [Ejecutar el análisis para investigar más rápido](run-analytics-to-investigate-faster.md)
- [Detección de semiduplicados](near-duplicates.md)
- [Subprocesos de correo electrónico](email-threading.md)
- [Temas](themes.md)

Para determinar qué usuarios participan en la derrame de datos, puede crear una consulta en el conjunto de evidencias y, a continuación, usar las condiciones de remitente/autor y destinatarios. Se crea una lista de todos los remitentes, destinatarios y autores de los datos recopilados que se agregaron a la evidencia. Asegúrese de examinar la lista para determinar si hay usuarios externos. Para obtener más información acerca del uso de condiciones para restringir los resultados de búsqueda, vea [condiciones de búsqueda](../keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-delete-the-spilled-data"></a>Paso 4: eliminar los datos derramados

Mediante la herramienta de investigaciones de datos, puede eliminar elementos de sus ubicaciones originales. Por ejemplo, puede eliminar elementos de los buzones de correo, los sitios de SharePoint y las cuentas de OneDrive en toda la organización. Tenga en cuenta que, debido a que recopiló los elementos como evidencia (agregando los resultados de la búsqueda al conjunto de evidencias en el paso 2), tiene copias de los elementos del conjunto de evidencias para investigarlos más o conservarlos.

Para eliminar elementos de sus ubicaciones originales:

1. En el conjunto de evidencias, seleccione los elementos que desea eliminar. Si selecciona elementos adjuntos a un mensaje de correo electrónico, también se seleccionará y se eliminará el mensaje de correo electrónico principal. 
 
2. Haga clic en **acción** y, a continuación, en **eliminar elementos desde ubicaciones originales**.

   ![Haga clic en acción y, a continuación, en eliminar elementos desde ubicaciones originales](../media/DataInvestigationsDeleteItems1.png)

3. En la página de flotante, compruebe el número de elementos y los documentos secundarios relacionados que se eliminarán y, a continuación, haga clic en **eliminar**.

En este momento, cuando se eliminan elementos de su ubicación original, los elementos se eliminan temporalmente. Esto significa que los elementos eliminados se conservarán hasta que expire el período de recuperación de elementos eliminados para el elemento. Esto también significa que los usuarios pueden recuperar estos elementos. Para obtener más información sobre lo que sucede cuando se eliminan los elementos de los buzones y los sitios, consulte [eliminar elementos de su ubicación original](delete-items-from-original-locations.md).

## <a name="step-5-close-or-delete-the-investigation"></a>Paso 5: cerrar o eliminar la investigación

Después de eliminar documentos en las ubicaciones de contenido de origen (buzones o sitios) en el servicio activo, seguirá teniendo copias de estos documentos que agregó a Evidence como parte de la investigación. Para evitar la posterior derramación de datos, considere la posibilidad de eliminar la investigación en sí.

Para eliminar una investigación:

1. En la pestaña **configuración** , haga clic en información de la **investigación**.

2. Haga clic en **eliminar investigación**. 

Si no necesita eliminar la investigación o si desea guardar la información recopilada durante la investigación, puede hacer clic en **cerrar caso**. Posteriormente, puede volver a abrir las investigaciones cerradas.

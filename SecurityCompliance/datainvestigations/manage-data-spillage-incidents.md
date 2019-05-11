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
description: En este artículo se describe el uso de la nueva herramienta de investigaciones de datos (vista previa) en el centro de seguridad & cumplimiento para administrar un incidente de derrame de datos.
ms.openlocfilehash: eef273bd1690845be61b6aec5918dcc0870ed6b2
ms.sourcegitcommit: 09fd88272187f82b6e635af83edabea08c2cc49c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884768"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Administrar un incidente de derrame de datos en Microsoft 365

La derramación de datos es cuando se publica un documento que contiene información confidencial, confidencial o malintencionada en un entorno que no es de confianza. Cuando se detecta un incidente de derrame de datos, es importante que contenga rápidamente el entorno, evalúe el tamaño y las ubicaciones del derrame, examine las actividades de los usuarios que lo rodean y, a continuación, elimine los datos derramados del servicio. Mediante la herramienta de investigación de datos (versión preliminar), puede buscar datos confidenciales, malintencionados o mal colocados en Office 365, investigar para averiguar qué sucedió y, a continuación, tomar las acciones adecuadas.  

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

- Usará la herramienta de investigación de datos (vista previa) en el centro de seguridad & cumplimiento para crear una investigación, buscar los datos derramados y revisarlos y analizarlos. A continuación, usará Security & Compliance Center PowerShell para eliminar de forma permanente los datos derramados de Office 365. 

- Para crear una investigación, debe ser miembro del grupo de roles de administrador de cumplimiento en el centro de seguridad & cumplimiento.

- Para eliminar mensajes, debe ser miembro de un grupo de roles en el centro de seguridad & cumplimiento que tiene asignada la función de búsqueda y purga. De forma predeterminada, este rol se asigna al grupo de funciones de administración de la organización. Para obtener información sobre cómo agregar usuarios a un grupo de roles, consulte Permissions [in the Security _AMP_ Compliance Center](../permissions-in-the-security-and-compliance-center.md). 

- Para controlar los buzones de usuario y las cuentas de OneDrive que puede buscar un investigador, su organización puede configurar límites de cumplimiento. Para obtener más información, configure los [límites de cumplimiento para las investigaciones de eDiscovery](../set-up-compliance-boundaries.md). 

## <a name="step-1-create-a-data-investigation"></a>Paso 1: crear una investigación de datos

Para crear una investigación en la herramienta de investigación de datos (versión preliminar):

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el centro de cumplimiento, haga clic en **investigaciones de datos**.
 
4. En la página **investigaciones de datos (vista previa)** , haga clic en **crear nueva investigación**.
    
5. En la página flotante **nueva investigación de datos** , dé un nombre a la investigación (obligatorio) y, a continuación, escriba una descripción y un número de investigación opcional. Tenga en cuenta que el nombre debe ser único en su organización.

6. En **¿desea configurar opciones adicionales después de crear esta investigación?**, siga uno de estos procedimientos:

    - Haga clic en **sí** para crear la investigación y mostrar la página de **configuración** en el nuevo caso. Esto le permite agregar miembros a la investigación.
    
    - Haga clic en **no** para crear la investigación solo y mostrarla en la lista de casos de la página **investigaciones de datos (vista previa)** . Si elige esta opción, se agregará como el único miembro de la investigación y se usará la configuración de búsqueda y análisis predeterminada. Puede Agregar miembros o cambiar la configuración en cualquier momento después de crear la investigación.

7. Haga clic en **Guardar** para crear la investigación.

    La nueva investigación se muestra en la lista de la página **investigaciones de datos (vista previa)** . 

8. Para abrir una investigación, haga clic en el nombre de la investigación. 

    Se muestra la pestaña **Inicio** de la investigación. 

> [!TIP]
> Considere la posibilidad de establecer una Convención de nomenclatura para las investigaciones y proporcionar toda la información que pueda en el nombre y la descripción para que pueda ubicar y hacer referencia a ella en el futuro si es necesario.
 
## <a name="step-2-search-for-the-spilled-data"></a>Paso 2: buscar los datos derramados 
 
Si sabe qué usuarios desean buscar datos derramados, puede agregarlos como personas de interés para asignar sus orígenes de datos a la investigación y buscar rápidamente sus buzones de correo y su cuenta de OneDrive. Para agregar personas de interés a la investigación, haga clic en **personas de interés**y, a continuación, haga clic en **Agregar personas de interés**. Para obtener más información, consulte [administrar personas de interés](manage-people-of-interest.md).

En la pestaña **búsquedas** , puede crear búsquedas para buscar los datos derramados. Usará la misma consulta de búsqueda que usó para buscar los datos derramados para eliminar los mismos mensajes en el [paso 4](#step-4-delete-the-spilled-data). Para obtener más información acerca de la creación de búsquedas, consulte [Search for Data in](search-for-data.md)a Investigation.

Después de ejecutar la búsqueda, puede obtener una vista previa de los ejemplos de los resultados de búsqueda y ver las estadísticas de búsqueda para evaluar la efectividad de la consulta de búsqueda. Una vez que identifique los elementos que desea eliminar de Office 365, puede hacer clic en la pestaña **evidencia** y, a continuación, crear un conjunto de evidencias y agregar resultados de búsqueda que contengan dichos elementos. 

Para ello, haga clic en la búsqueda que desea investigar. En la página de control flotante, haga clic en **Agregar resultados a evidencia** y siga las instrucciones. A continuación, en la evidencia, puede revisar documentos individuales, investigar quién tenía acceso a los documentos y exportar los documentos. Para eliminar los documentos en lugar de revisarlos, vaya al [paso 4](#step-4-delete-the-spilled-data). 

> [!IMPORTANT]
> Las palabras clave que se usan en la consulta de búsqueda pueden contener los datos que se han derramado reales que se están buscando. Por ejemplo, si busca documentos que contengan un número de la seguridad social y lo usa como una palabra clave en la consulta de búsqueda, debe eliminar la consulta posteriormente para evitar más derrames. Puede eliminar la búsqueda o eliminar la investigación completa en el [paso 5](#step-5-close-or-delete-the-investigation). 

## <a name="step-3-review-and-investigate"></a>Paso 3: revisar e investigar 

En la investigación, vaya a **evidence** (ficha) y haga clic en el conjunto de pruebas que creó en el paso anterior. Una vez completado el trabajo de procesamiento y agregados los resultados de la búsqueda a la evidencia, puede revisar los documentos individuales en su formato nativo, formato de texto o un formato casi nativo. Puede crear consultas adicionales para restringir la lista de documentos y etiquetar los documentos para indicar los resultados de la investigación. Para obtener más información, vea [Review Data in Evidence](review-data-in-evidence.md) .

Para agrupar documentos y obtener más ayuda para su revisión, haga clic en **administrar evidencias**. En el mosaico **Analytics** , haga clic en **analizar**. De esta forma, se ejecutarán análisis avanzados, como la detección de duplicados, el procesamiento de correo electrónico y el análisis de temas. Para obtener más información, vea:

- [Ejecutar el análisis para investigar más rápido](run-analytics-to-investigate-faster.md)
- [Detección de semiduplicados](near-duplicates.md)
- [Subprocesos de correo electrónico](email-threading.md)
- [Temas](themes.md)

Para determinar qué usuarios participan en la derrame de datos, puede crear una nueva consulta en el conjunto de evidencias y, a continuación, usar las condiciones de remitente/autor y destinatarios. Se creará una lista de todos los remitentes, destinatarios y autores de los datos recopilados que se agregaron a la evidencia. Asegúrese de examinar la lista para determinar si hay usuarios externos. Para obtener más información acerca del uso de condiciones para restringir los resultados de búsqueda, vea [condiciones de búsqueda](../keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-delete-the-spilled-data"></a>Paso 4: eliminar los datos derramados

### <a name="deleting-mailbox-items"></a>Eliminación de elementos de buzón

Después de revisar y validar que los resultados de la búsqueda contengan solo los mensajes de correo electrónico que deben eliminarse, puede eliminarlos de forma permanente ejecutando el comando **New-ComplianceSearchAction-Purge-PurgeType HardDelete** en Security & Compliance. Center PowerShell. Para obtener instrucciones, consulte [Buscar y eliminar mensajes de correo electrónico](../search-for-and-delete-messages-in-your-organization.md). 

Si la recuperación de elementos individuales está habilitada para los buzones de la organización, los elementos eliminados permanentemente se conservarán en la carpeta elementos recuperables del usuario (y los administradores podrán acceder a ellos) hasta que finalice el período de retención de elementos eliminados (el valor predeterminado es 14 días). Además, si algún buzón de correo que contiene datos sobrecargados está en suspensión legal o asignado a una directiva de retención, los mensajes purgados se conservarán en la carpeta elementos recuperables hasta que expire la duración de retención del elemento. Para eliminar los mensajes de forma inmediata, debe realizar tareas adicionales. Para obtener instrucciones, consulte [eliminar elementos de la carpeta elementos recuperables de buzones basados en la nube en retención](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).  

> [!IMPORTANT]
> Compruebe con la administración de registros o los departamentos jurídicos antes de quitar una retención o Directiva de retención. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad. 

### <a name="deleting-site-items"></a>Eliminación de elementos de sitio

Para eliminar de forma permanente un documento de un sitio de SharePoint o una cuenta de OneDrive, tiene que eliminar el documento y, a continuación, eliminarlo de la papelera de reciclaje del sitio y, a continuación, eliminarlo de la papelera de reciclaje de la colección de sitios. Para obtener más información, vea [Eliminar documentos en SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

Como alternativa, puede eliminar una colección de sitios completa que podría contener datos derramados. Para obtener instrucciones, vea [Delete a site Collection](https://docs.microsoft.com/sharepoint/delete-site-collection).

## <a name="step-5-close-or-delete-the-investigation"></a>Paso 5: cerrar o eliminar la investigación

Después de eliminar documentos en las ubicaciones de contenido de origen (buzones o sitios) en el servicio activo, seguirá teniendo copias de estos documentos que agregó a Evidence como parte de la investigación. Para evitar la posterior derramación de datos, considere la posibilidad de eliminar la investigación en sí.

Para eliminar una investigación:

1. En la pestaña **configuración** , haga clic en información de la **investigación**.

2. Haga clic en **eliminar investigación**. 

Si no necesita eliminar la investigación o si desea guardar la información recopilada durante la investigación, puede hacer clic en **cerrar caso**. A continuación, en una fecha posterior, puede volver a abrir investigaciones cerradas.

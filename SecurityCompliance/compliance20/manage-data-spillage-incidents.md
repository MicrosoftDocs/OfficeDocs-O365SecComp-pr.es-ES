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
ms.collection: M365-security-compliance M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se describe el uso de la herramienta nueva investigación de datos (vista previa) en el centro de seguridad de Office 365 Security & para administrar un incidente de derrame de datos.
ms.openlocfilehash: 33943ee4367e01f413cfa7840c796d5197323185
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862562"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Administrar un incidente de derrame de datos en Microsoft 365 

La derramación de datos es cuando se publica un documento confidencial en un entorno que no es de confianza. Cuando se detecta un incidente de derrame de datos, es importante evaluar rápidamente el tamaño y las ubicaciones del derrame, examinar las actividades de los usuarios en torno a él y, a continuación, purgar de forma permanente los datos derramados del sistema.

## <a name="scope-of-this-article"></a>Ámbito de este artículo

En este artículo se proporciona una lista de instrucciones sobre cómo quitar permanentemente los elementos de los buzones de correo de Office 365 para que los usuarios o los administradores ya no puedan obtener acceso a ellos o puedan recuperarlos. 

> [!NOTE]
> Cuando se eliminan elementos ubicados en un sitio de SharePoint o de OneDrive para la empresa, se conservan durante 93 días desde el momento en que se eliminan de su ubicación original.

## <a name="scenario"></a>Escenario

Se le informa de un incidente de derrame de datos donde un empleado ha compartido sin saberlo un documento altamente confidencial con varias personas a través del correo electrónico. Desea evaluar rápidamente quién recibió este documento, tanto dentro como fuera de la organización. Una vez que haya investigado el incidente, tiene previsto compartir sus hallazgos con otros investigadores para revisar y, a continuación, eliminar de forma permanente los datos derramados de Office 365. Una vez completada la investigación, desea quitar todas las evidencias. 

## <a name="workflow"></a>Flujo de trabajo

Este es el flujo de trabajo para usar investigaciones de datos (versión preliminar) para administrar un incidente de derrame de datos:

1.  Cree una investigación de datos.

2.  Busque los datos derramados.

3.  Revise e investigue el incidente.

4.  Eliminar de forma permanente los datos derramados.

5.  Cierre o elimine la investigación.


## <a name="before-you-begin"></a>Antes de empezar

- Debe usar la herramienta de investigación de datos (vista previa) del centro de seguridad de Office 365 & para crear una investigación, buscar los datos derramados y revisarlos y analizarlos. A continuación, usará Security & Compliance Center PowerShell para eliminar de forma permanente los datos derramados de Office 365. 

- Para crear una investigación, debe ser miembro del grupo de roles de administrador de cumplimiento en el centro de seguridad & cumplimiento.

- Para eliminar mensajes, debe ser miembro del grupo de roles de administración de la organización en el centro de seguridad & cumplimiento o tener asignado el rol de búsqueda y dePuración. Para obtener información sobre cómo agregar usuarios a un grupo de roles, consulte [proporcionar a los usuarios acceso al centro de seguridad _AMP_ cumplimiento](../grant-access-to-the-security-and-compliance-center.md). 

- Para controlar los buzones de usuario y las cuentas de OneDrive que puede buscar un investigador, su organización puede configurar límites de cumplimiento. Para obtener más información, configure los [límites de cumplimiento para las investigaciones de eDiscovery](../set-up-compliance-boundaries.md). 

## <a name="step-1-create-a-data-investigation"></a>Paso 1: crear una investigación de datos

Para crear una investigación de datos:

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el centro de seguridad & cumplimiento, haga clic en **investigaciones de datos**.
 
4. En la página **investigaciones de datos (vista previa)** , haga clic en **crear una nueva investigación**.
    
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
 
Si sabe qué usuarios desean buscar datos derramados, puede agregarlos como personas de interés para asignar sus orígenes de datos a la investigación y buscar rápidamente sus buzones de correo y su cuenta de OneDrive. Para agregar personas de interés a la investigación, haga clic en **personas de interés**y, a continuación, haga clic en **Agregar personas de interés**. 

En la pestaña **búsquedas** , puede crear búsquedas para buscar los datos derramados. Usará la misma consulta de búsqueda que usó para buscar los datos derramados para eliminar los mismos mensajes en el [paso 4](#step-4-permanently-delete-the-spilled-data). Para obtener más información acerca de la creación de búsquedas, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).

Después de ejecutar la búsqueda, puede obtener una vista previa de los ejemplos de los resultados de búsqueda y ver las estadísticas de búsqueda para evaluar la efectividad de la consulta de búsqueda. Una vez que identifique los elementos que desea eliminar de Office 365, puede hacer clic en la pestaña **incidentes** y, a continuación, crear un incidente y agregar resultados de búsqueda que contengan dichos elementos. 

Para ello, haga clic en la búsqueda que desea investigar. En la página flotante, haga clic en **Agregar resultados a incidente** y siga las instrucciones. A continuación, en la incidencia, puede revisar documentos individuales, investigar quién tenía acceso a los documentos y exportar los documentos. Para eliminar los documentos en lugar de revisarlos, vaya al [paso 4](#step-4-permanently-delete-the-spilled-data). 

> [!IMPORTANT]
> Las palabras clave que se usan en la consulta de búsqueda pueden contener los datos que se han derramado reales que se están buscando. Por ejemplo, si busca documentos que contengan un número de la seguridad social y lo usa como una palabra clave en la consulta de búsqueda, debe eliminar la consulta posteriormente para evitar más derrames. Puede eliminar la búsqueda o eliminar la investigación completa en el [paso 5](#step-5-close-or-delete-the-investigation). 

## <a name="step-3-review-and-investigate"></a>Paso 3: revisar e investigar 

En la investigación, vaya a **incidentes** y haga clic en el incidente que ha creado en el paso anterior. Una vez completado el trabajo de procesamiento y agregados los resultados de la búsqueda al incidente, puede revisar documentos individuales en su formato nativo, formato de texto o un formato casi nativo. Puede crear consultas adicionales para restringir aún más la lista de documentos y etiquetar los documentos para indicar los resultados de la investigación.

Para agrupar documentos y obtener más ayuda para su revisión, haga clic en **administrar incidente**. En el mosaico **Analytics** , haga clic en **analizar**. De esta forma, se ejecutarán análisis avanzados, como la detección de duplicados, el procesamiento de correo electrónico y el análisis de temas. Para más información, visite:

- [Detección de semiduplicados](near-duplicates.md)
- [Subprocesos de correo electrónico](email-threading.md)
- [Temas](themes.md)

Para determinar qué usuarios participan en la derrame de datos, puede crear una nueva consulta en el incidente y, a continuación, usar las condiciones de remitente/autor y destinatarios. Se creará una lista de todos los remitentes, destinatarios y autores encontrados en los datos recopilados que se agregaron al incidente. Asegúrese de examinar la lista para determinar si hay usuarios externos en la lista. Para obtener más información, vea [condiciones de búsqueda](../keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-permanently-delete-the-spilled-data"></a>Paso 4: eliminar permanentemente los datos derramados

### <a name="deleting-mailbox-items"></a>Eliminación de elementos de buzón

Después de revisar y validar que los resultados de la búsqueda contengan solo los mensajes de correo electrónico que deben eliminarse, puede eliminarlos de forma permanente ejecutando el comando **New-ComplianceSearchAction-Purge-PurgeType HardDelete** en Security & Compliance. Center PowerShell. Para obtener instrucciones, consulte [Buscar y eliminar mensajes de correo electrónico](../search-for-and-delete-messages-in-your-organization.md). 

Tenga en cuenta que si la recuperación de elementos individuales está habilitada para los buzones de la organización, los elementos eliminados permanentemente se conservarán en la carpeta elementos recuperables del usuario (y los administradores podrán acceder a ellos) hasta que finalice el período de retención de elementos eliminados (el valor predeterminado es de 14 días). Además, si alguno de los buzones de correo que contienen datos derramados están en suspensión legal o se asignan a una directiva de retención, el mensaje purgado se conservará en la carpeta elementos recuperables hasta que se quite la retención o hasta que el buzón de correo se excluya de las directivas de retención. Para eliminar los mensajes de forma inmediata, debe realizar tareas adicionales. Para obtener instrucciones, consulte [eliminar elementos de la carpeta elementos recuperables de buzones basados en la nube en retención ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).  

> [!IMPORTANT]
> Compruebe con la administración de registros o los departamentos jurídicos antes de quitar una retención o Directiva de retención. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad. 

### <a name="deleting-site-items"></a>Eliminación de elementos de sitio

Para eliminar de forma permanente un documento de un sitio de SharePoint o una cuenta de OneDrive para la empresa, debe eliminarlo y, a continuación, eliminarlo del sitio y, a continuación, eliminarlo de la papelera de reciclaje de la colección de sitios. Para obtener instrucciones, vea [Eliminar documentos en SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

Como alternativa, puede eliminar una colección de sitios completa que podría contener datos derramados. Para obtener instrucciones, vea [Delete a site Collection](https://docs.microsoft.com/sharepoint/delete-site-collection).

## <a name="step-5-close-or-delete-the-investigation"></a>Paso 5: cerrar o eliminar la investigación

Después de eliminar documentos en las ubicaciones de contenido de origen (buzones o sitios), seguirá teniendo copias de estos documentos que agregó a los incidentes como parte de la investigación. Para evitar la posterior derramación de datos, debe considerar la posibilidad de eliminar la investigación.

Para eliminar una investigación:

1. En la pestaña **configuración** , haga clic en información de la **investigación**.

2. Haga clic en **eliminar caso**. 

Si no necesita eliminar la investigación o si desea guardar la información recopilada durante la investigación, puede hacer clic en **cerrar caso**. En una fecha posterior, puede volver a abrir investigaciones cerradas.
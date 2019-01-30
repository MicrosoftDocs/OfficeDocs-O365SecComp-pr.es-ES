---
title: Administración de un incidente de pérdidas de datos en Microsoft 365
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
description: En este artículo se describe cómo utilizar la nueva herramienta de investigaciones (vista previa) de datos en el centro de cumplimiento de seguridad de Office 365 & para administrar un incidente de pérdidas de datos.
ms.openlocfilehash: d863d87cc667b9695f9bf619c35575715dfa144e
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636642"
---
# <a name="managing-a-data-spillage-incident-in-microsoft-365"></a>Administración de un incidente de pérdidas de datos en Microsoft 365 

Pérdidas de datos es cuando se libera un documento confidencial en un entorno que no se confía. Cuando se detecta un incidente de pérdidas de datos, es importante evaluar rápidamente el tamaño y las ubicaciones de las pérdidas, se examinan las actividades del usuario alrededor de él y, a continuación, permanentemente purgar los datos derramados desde el sistema.

## <a name="scope-of-this-article"></a>Ámbito de este artículo

En este artículo se proporciona una lista de instrucciones acerca de cómo quitar permanentemente los elementos de buzones de Office 365 por lo que ya no son accesibles o recuperables por los usuarios o administradores. 

> [!NOTE]
> Cuando elimina los elementos ubicados en un SharePoint o OneDrive para el sitio de negocio, sí se conservan para 93 días desde el momento en que eliminarlos de su ubicación original.

## <a name="scenario"></a>Escenario

Se está informado de un incidente de pérdidas de datos donde un empleado sin darse cuenta comparte un documento altamente confidencial con varias personas a través de correo electrónico. Desea evaluar rápidamente que recibió este documento, tanto dentro como fuera de la organización. Una vez haya investigar el incidente, planea compartir sus conclusiones con otros investigadores para revisar y, a continuación, quitar permanentemente los datos derramados de Office 365. Una vez finalizada la investigación, que desea quitar todas las pruebas. 

## <a name="workflow"></a>Flujo de trabajo

Este es el flujo de trabajo para usar datos de investigaciones (vista previa) para administrar un incidente de pérdidas de datos:

1.  Crear una investigación de datos.

2.  Buscar los datos derramados.

3.  Revise e investigar el incidente.

4.  Eliminar permanentemente los datos derramados.

5.  Cierre o elimine la investigación.


## <a name="before-you-begin"></a>Antes de empezar

- Para crear una investigación, buscar los datos derramados y revisar y analizar, debe usar la herramienta de investigaciones de datos (vista previa) en el centro de cumplimiento de seguridad de Office 365 &. A continuación, usará seguridad & PowerShell de centro de cumplimiento para eliminar permanentemente los datos derramados de Office 365. 

- Para crear una investigación, debe ser miembro del grupo de roles de administrador de cumplimiento de normas en el centro de cumplimiento de seguridad &.

- Para eliminar los mensajes, debe ser miembro del grupo de roles de administración de la organización en el centro de cumplimiento de seguridad & o tener asignada la función de búsqueda y depuración. Para obtener información sobre cómo agregar usuarios a un grupo de roles, consulte [dar acceso a los usuarios para el centro de cumplimiento de seguridad &](../grant-access-to-the-security-and-compliance-center.md). 

- Para controlar las cuentas de OneDrive para la que se puede buscar una investigación y que los buzones de usuario, su organización puede configurar los límites de cumplimiento. Para obtener más información, [establecer los límites de cumplimiento para investigaciones de exhibición de documentos electrónicos](../set-up-compliance-boundaries.md). 

## <a name="step-1-create-a-data-investigation"></a>Paso 1: Crear una investigación de datos

Para crear una investigación de datos:

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el centro de cumplimiento de seguridad &, haga clic en **Datos de investigaciones**.
 
4. En la página **Datos de investigaciones (vista previa)** , haga clic en **crear una nueva investigación**.
    
5. En la página de emergente **nueva investigación de datos** , asigne un nombre (obligatorio) a la investigación y, a continuación, escriba una descripción y un número de investigación opcional. Tenga en cuenta que el nombre debe ser único en la organización.

6. Bajo **¿desea configurar opciones adicionales después de crear esta investigación?**, siga uno de los siguientes procedimientos:

    - Haga clic en **Sí** para crear la investigación y mostrar la página de **configuración** en el caso nuevo. Esto le permite agregar miembros a la investigación.
    
    - Haga clic en **No** para acaba de crear la investigación y mostrarlos en la lista de los casos, en la página de **Datos de investigaciones (vista previa)** . Si elige esta opción, se agrega como el único miembro de la investigación y la configuración de búsqueda y análisis de predeterminada que se va a usar. Puede agregar a miembros o cambiar configuración en cualquier momento después de haber creado la investigación.

7. Haga clic en **Guardar** para crear la investigación.

    La nueva investigación se muestra en la lista en la página de **Datos de investigaciones (vista previa)** . 

8. Para abrir una investigación, haga clic en el nombre de la investigación. 

    Se muestra la ficha **Inicio** para la investigación. 

> [!TIP]
> Considere la posibilidad de establecer una convención de nomenclatura para las investigaciones y proporcione tanta información como lo haría en el nombre y la descripción para que pueda buscar y hacer referencia a en el futuro si es necesario.
 
## <a name="step-2-search-for-the-spilled-data"></a>Paso 2: Búsqueda de los datos derramados 
 
Si sabe qué usuarios desea buscar datos derramados, puede agregarlas como personas de interés para asignar sus orígenes de datos para la investigación y buscar rápidamente su buzón de correo y la cuenta de OneDrive. Para agregar personas de interés para la investigación, haga clic en **personas de interés**y, a continuación, haga clic en **agregar personas de interés**. 

En la ficha de **búsquedas** , puede crear las búsquedas para encontrar los datos derramados. Va a usar la misma consulta de búsqueda que usa para buscar los datos derramados para eliminar esos mismos mensajes en el [paso 4](##step-4:-permanently-delete-the-spilled-data). Para obtener más información sobre la creación de búsquedas, vea [crear una búsqueda para recopilar datos](create-search-to-collect-data.md).

Después de ejecutar la búsqueda, puede obtener una vista previa de ejemplos de los resultados de búsqueda y ver las estadísticas de búsqueda para evaluar la eficacia de la consulta de búsqueda. Una vez que se identifican los elementos que desea eliminar de Office 365, puede haga clic en la ficha de **incidentes** y, a continuación, crear un incidente y agregar los resultados de búsqueda que contienen esos elementos. 

Para ello, haga clic en la búsqueda que desea investigar. En la página emergente, haga clic en **Agregar resultados a incidentes** y siga las instrucciones. A continuación, en el incidente, puede revisar documentos individuales, investigar quién ha tenido acceso a documentos y exportar los documentos. Para eliminar simplemente los documentos en lugar de revisarlos, vaya al [paso 4](##step-4:-permanently-delete-the-spilled-data). 

> [!IMPORTANT]
> Las palabras clave que usar en la consulta de búsqueda pueden contener los datos derramados real que se va a buscar. Por ejemplo, si busca documentos que contienen un número de la seguridad social y usarlo como una palabra clave en la consulta de búsqueda, debe eliminar la consulta posteriormente para evitar pérdidas de otros. Puede eliminar la búsqueda o eliminar la investigación toda en el [paso 5](##step-5:-close-or-delete-investigation). 

## <a name="step-3-review-and-investigate"></a>Paso 3: Revisar e investigar 

En la investigación, vaya a la ficha de **incidentes** y haga clic en el incidente que creó en el paso anterior. Después de que se complete el trabajo de procesamiento y los resultados de búsqueda se agregan a un incidente, puede revisar los documentos individuales en su formato nativo, formato de texto o un formato casi nativo. Puede crear consultas adicionales para restringir más la lista de documentos y documentos de etiqueta para indicar los resultados de la investigación.

Para agrupar los documentos y obtener más ayuda para su revisión, haga clic en **Administrar incidente**. En el icono del **análisis** , haga clic en **analizar**. Esto ejecutará análisis avanzados, como la detección de duplicados, correo electrónico threading y análisis de tema. Para obtener más información, vea:

- [Cerca de detección de duplicados](near-duplicates.md)
- [Subprocesos de correo electrónico](email-threading.md)
- [Temas](themes.md)

Para determinar los usuarios que participan en las pérdidas de datos, puede crear una nueva consulta en el incidente y, a continuación, usar el remitente/autor y las condiciones de los destinatarios. Esto creará una lista de todos los remitentes, destinatarios y los autores que se encuentran en los datos recopilados que se ha agregado a un incidente. Asegúrese de examinar la lista para determinar si hay algún usuario externo en la lista. Para obtener más información, vea [condiciones de búsqueda](../keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-permanently-delete-the-spilled-data"></a>Paso 4: Eliminar permanentemente los datos derramados

### <a name="deleting-mailbox-items"></a>Eliminar elementos del buzón de correo

Después de revisar y validar que los resultados de búsqueda contienen solo los mensajes de correo electrónico que se deben eliminar, puede eliminar ellos permanentemente mediante la ejecución de la **New-ComplianceSearchAction-purgar - PurgeType HardDelete** command en & cumplimiento de seguridad Centro PowerShell. Para obtener instrucciones, vea [Buscar y eliminar mensajes de correo electrónico](../search-for-and-delete-messages-in-your-organization.md). 

Tenga en cuenta que si está habilitada la recuperación de elemento único para los buzones de correo en la organización, los elementos eliminados permanentemente será retenidas en la carpeta del usuario elementos recuperables (y pueden tener acceso a los administradores) hasta que finalice de período de retención de elementos eliminados (el valor predeterminado es de 14 días). Además, si cualquiera de los buzones de correo que contienen datos derramados están en una suspensión legal o asignados a una directiva de retención, los mensajes purgados se conservarán en la carpeta elementos recuperables hasta que se elimina la suspensión o el buzón de correo se excluye de las directivas de retención. Para eliminar disco duro mensajes inmediatamente, necesario para llevar a cabo tareas de incorporación. Para obtener instrucciones, vea [Eliminar elementos en la carpeta de buzones de correo basados en la nube en retención de elementos recuperables ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).  

> [!IMPORTANT]
> Compruebe con la administración de registros o departamentos legales antes de quitar una directiva de retención o suspensión. Su organización puede tener una directiva que define si un buzón de correo en espera o un incidente de pérdidas de datos tiene prioridad. 

### <a name="deleting-site-items"></a>Eliminación de elementos de sitio

Para eliminar permanentemente un documento desde un sitio de SharePoint o OneDrive para la cuenta de empresa, debe eliminarlo y, a continuación, se debe eliminar del sitio y, a continuación, elimine la Papelera de reciclaje de la colección de sitios. Para obtener instrucciones, consulte [eliminación de documentos en SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).

Como alternativa, puede eliminar una colección de sitios completa que es posible que contenía datos derramados. Para obtener instrucciones, vea [Eliminar una colección de sitios](https://docs.microsoft.com/sharepoint/delete-site-collection).

## <a name="step-5-close-or-delete-the-investigation"></a>Paso 5: Cerrar o eliminar la investigación

Después de eliminar documentos en las ubicaciones de contenido de origen (buzones de correo o sitios), aún tendrá copias de estos documentos que haya agregado al incidentes como parte de la investigación. Para evitar aún más pérdidas de datos, considere la posibilidad de eliminar la investigación.

Para eliminar una investigación:

1. En la ficha **configuración** , haga clic en **información de investigación**.
2. Haga clic en **Eliminar caso**. 

Si no es necesario eliminar la investigación o si desea guardar la información recopilada durante la investigación, puede hacer clic en **Cerrar el caso**. En una fecha posterior, puede volver a abrir investigaciones cerradas.
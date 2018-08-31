---
title: Exportar un informe de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento, sólo puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de búsqueda y un documento con información detallada acerca de cada elemento que se van a exportar.
ms.openlocfilehash: 45415f25754b4549a919e4ce56853a6ae09a9bdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535603"
---
# <a name="export-a-content-search-report"></a>Exportar un informe de búsqueda de contenido

En lugar de exportar el conjunto completo de búsqueda de resultados de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento (y de una búsqueda de contenido que está asociado con un caso de exhibición de documentos electrónicos), sólo tiene que puede exportar los mismos informes que se generan cada vez exportar los resultados de búsqueda.
  
Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly* . Por ejemplo, si la búsqueda de contenido se denomina *ContosoCase0815* , el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly* . Para obtener una lista de los documentos que se incluyen en el informe, vea [qué se incluye en el informe](#whats-included-in-the-report).

## <a name="before-you-begin"></a>Antes de empezar

- Para exportar un informe de búsqueda de contenido, tiene que tener asignado el rol de administración de búsqueda de cumplimiento de la seguridad de Office 365 &amp; centro de cumplimiento. Esta función se asigna a los grupos de roles de administrador y administración de la organización de exhibición de documentos electrónicos integrados. No se asigna de forma predeterminada al grupo de funciones de administración de la organización. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
    
- Al exportar un informe, los datos se almacenan temporalmente en un área de almacenamiento de Windows Azure único en la nube de Microsoft antes de se descarga en el equipo local. Asegúrese de que la organización puede conectarse al extremo en Azure, que es ** \*. blob.core.windows.net** (el carácter comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan desde el área de almacenamiento de Azure dos semanas después de crearla. 
    
- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:
    
  - Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
  - Microsoft .NET Framework 4.7
    
  - Un explorador compatible:
    
    - Microsoft Edge
    
      o
    
    - Microsoft Internet Explorer 10 y versiones posteriores
    
    **Nota:** Microsoft no fabrica las extensiones de terceros o complementos para las aplicaciones ClickOnce. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con las extensiones de terceros o los complementos. 
    
## <a name="generate-and-download-a-content-search-report"></a>Generar y descargar un informe de búsqueda de contenido

Los pasos necesarios para generar y descargar un informe de búsqueda de contenido son muy similares a realmente exportar los resultados de búsqueda.
  
## <a name="step-1-generate-the-report-for-export"></a>Paso 1: Generar el informe para la exportación

El primer paso consiste en preparar el informe para la descarga a su equipo de exportación. Cuando se el informe, el informe se cargan documentos en un área de almacenamiento de Azure en Microsoft en la nube.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **Búsqueda de contenido**.
    
4. En la página de **búsqueda de contenido** , seleccione una búsqueda. 
    
5. En el panel de detalles, en **exportar el informe a un equipo**, haga clic en **Generar informe**.
    
    > [!NOTE]
    > Si los resultados de una búsqueda son más de 7 días, se le pedirán para actualizar los resultados de búsqueda. Si esto sucede, cancelar la exportación, haga clic en **resultados de búsqueda de actualizaciones** en el panel de detalles para la búsqueda seleccionada y, a continuación, iniciar la exportación de informes después de que se actualizan los resultados. 
  
6. En la página **exportar un informe** , en **incluir estos elementos de la búsqueda**, elija una de las siguientes opciones:
    
    - Exportar solo los elementos indexados
    
    - Exportar los elementos indexados y sin indexar
    
    - Exportar solo los elementos sin indexar
    
    Para obtener más información acerca de los elementos sin indizar, consulte [parcialmente indizar los elementos de búsqueda de contenido](partially-indexed-items-in-content-search.md).
    
7. Elija esta opción incluir las estadísticas de búsqueda para todas las versiones de documentos de SharePoint. Esta opción aparece únicamente si los orígenes de contenido de la búsqueda incluye SharePoint o OneDrive para los sitios de negocio.
    
8. Haga clic en **Generar informe**.
    
    El informe de resultados de búsqueda está preparado para descargar el archivo, lo que significa que los documentos de informe se cargará en el área de almacenamiento de Azure en la nube de Microsoft. Cuando el informe está listo para su descarga, se muestra el vínculo **Descargar informe** en **exportar el informe a un equipo** en el panel de detalles. 
    
> [!NOTE]
> También puede exportar un informe para una búsqueda de contenido que está asociado con un caso de exhibición de documentos electrónicos. Para ello, vaya a **búsqueda &amp; investigación** \> seleccione un caso de **exhibición de documentos electrónicos**y haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). En la página de **búsquedas** , seleccione una búsqueda y, a continuación, haga clic en **Exportar** ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **exportar un informe**. 
  
## <a name="step-2-download-the-report"></a>Paso 2: Descargar el informe

El siguiente paso es descargar el informe desde el área de almacenamiento de Azure en el equipo local.
  
1. En el panel de detalles de la búsqueda que generó el informe, en **exportar el informe a un equipo**, haga clic en **Descargar informe**.
    
    La página **Descargar informe** se muestra y contiene la siguiente información sobre el informe hasta que se descargan en el equipo. 
    
    - El número de elementos que se descargarán.
    
    - El tamaño total estimado de los elementos que se descargarán.
    
    - Se exportará si indexados o no indexados. Elementos sin indizar son elementos que tienen un formato reconocido, se cifran o no estaban indizados por otras razones.
    
    - Si las versiones de los documentos de SharePoint se descargarán o no.
    
    - El estado del proceso de exportación de informe. Puede iniciar la descarga del informe, incluso si la preparación del informe no está completa.
    
2. **Exportar la clave**, haga clic en **Copiar al Portapapeles**. Para descargar el informe va a usar esta clave en el paso 5.
    
    > [!IMPORTANT]
    > Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, use esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave, al igual que protege a las contraseñas u otra información relacionada con la seguridad. 
  
3. Haga clic en **Descargar informe**.
    
4. Si le pide para instalar la **exhibición de documentos de Microsoft Office 365 herramienta para exportar**, haga clic en **instalar**.
    
5. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.
    
6. Haga clic en **Examinar** para especificar la ubicación donde desea descargar el informe. 
    
7. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **exhibición de documentos electrónicos herramienta para exportar** muestra información de estado sobre el proceso de exportación, así como una estimación del número (y tamaño) de los elementos restantes para ser descargado. Cuando se completa el proceso de exportación, puede tener acceso a los archivos en la ubicación donde se han descargado. 
    
> [!NOTE]
> Puede descargar el informe para una búsqueda de contenido que está asociado con un caso de exhibición de documentos electrónicos. Para ello, vaya a **búsqueda &amp; investigación** \> seleccione un caso de **exhibición de documentos electrónicos**y haga clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). En la página de **exportaciones** , seleccione una exportación de informe y, a continuación, haga clic en **Descargar informe** en el panel de detalles. 
  
## <a name="whats-included-in-the-report"></a>¿Qué se incluye en el informe

Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los documentos siguientes:
  
- **Exportar resumen** - documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se han buscado, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se van a exportar y el tamaño estimado y real de los elementos que se exportarán. 
    
    > [!NOTE]
    > Si al exportar el informe incluye elementos sin indizar, el número de elementos sin indizar se incluyen en el número total de resultados de búsqueda estimado y en el número total de descargado los resultados de búsqueda (si estuviera exportar los resultados de búsqueda) que se enumeran en la Exportar el informe de resumen. En otras palabras, el número total de elementos que se necesiten descargar es igual que el número total de resultados estimados y el número total de elementos sin indizar. 
  
- **Manifiesto** - un archivo de manifiesto (en formato XML) que contiene información acerca de los artículos incluidos en los resultados de búsqueda. 
    
- **Resultados** - documento de Excel que contiene una fila con información acerca de cada elemento indizado que sería exportado con los resultados de búsqueda. Para el correo electrónico, el registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
    
  - La fecha en que se envió o se recibió el mensaje.
    
  - La línea Asunto del mensaje.
    
  - El remitente y los destinatarios del mensaje.
    
    Para los documentos de SharePoint y OneDrive para los sitios comerciales, el registro de los resultados contiene información acerca de cada documento, incluidos:
    
  - La dirección URL del documento.
    
  - La dirección URL de la colección de sitio donde se ubica el documento.
    
  - La fecha en la que el documento se modificó por última vez.
    
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
    > [!NOTE]
    > El número de filas en el informe de **resultados** debe ser igual que el número total de resultados de búsqueda que se necesiten descargar menos el número total de elementos que aparecen en el informe de **Elementos no indizados** . 
  
- **Elementos sin indizar** - documento de Excel que contiene información acerca de todos los elementos sin indizar que se incluirán en los resultados de búsqueda. Si no incluye elementos sin indizar cuando se genera el informe de resultados de búsqueda, se descargará este informe, pero estará vacía.

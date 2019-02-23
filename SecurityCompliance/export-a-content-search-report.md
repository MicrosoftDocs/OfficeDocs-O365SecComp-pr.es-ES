---
title: Exportar un informe de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el centro de &amp; seguridad y cumplimiento de Office 365, puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportará.
ms.openlocfilehash: 12799474bfb099c521f72cd3902173d42b17d4dd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216240"
---
# <a name="export-a-content-search-report"></a>Exportar un informe de búsqueda de contenido

En lugar de exportar el conjunto completo de resultados de búsqueda de una búsqueda de contenido en el centro &amp; de seguridad y cumplimiento de Office 365 (y desde una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos), puede exportar los mismos informes que se generan al exportar los resultados de la búsqueda.
  
Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly* . Por ejemplo, si la búsqueda de contenido se denomina *ContosoCase0815* , el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly* . Para obtener una lista de los documentos que se incluyen en el informe, consulte [what's included in the Report](#whats-included-in-the-report).

## <a name="before-you-begin"></a>Antes de empezar

- Para exportar un informe de búsqueda de contenido, debe tener asignado el rol de administración de búsqueda de cumplimiento en el &amp; centro de seguridad y cumplimiento de Office 365. Este rol se asigna a los grupos de roles integrados administrador de eDiscovery y administración de la organización. No está asignada de forma predeterminada al grupo de funciones de administración de la organización. Para obtener más información, consulte [asignar permisos de exhibición de documentos electrónicos &amp; en el centro de seguridad y cumplimiento de Office 365](assign-ediscovery-permissions.md).
    
- Al exportar un informe, los datos se almacenan temporalmente en un área de almacenamiento única de Windows Azure en la nube de Microsoft antes de descargarlos en el equipo local. asegúrese de que su organización puede conectarse al extremo en Azure, que es ** \*. blob.core.windows.net** (el carácter comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan del área de Azure Storage dos semanas después de su creación. 
    
- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:
    
  - Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
  - Microsoft .NET Framework 4,7
    
  - Un explorador compatible:
    
    - Microsoft Edge
    
      o
    
    - Microsoft Internet Explorer 10 y versiones posteriores
    
    **Nota:** Microsoft no fabrica extensiones de terceros o complementos para aplicaciones ClickOnce. No se admite la exportación de resultados de búsqueda con un explorador no compatible con extensiones de terceros o complementos. 

- Si el tamaño total estimado de los resultados devueltos por una búsqueda de&nbsp;contenido supera los 20 TB, se producirá un error al exportar el informe. Para exportar correctamente el informe, intente restringir el ámbito y vuelva a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a&nbsp;20 TB.

- La exportación de informes de búsqueda de contenido cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario. Para obtener más información acerca de los límites de exportación, consulte [exportar resultados de búsqueda de contenido desde el centro de cumplimiento de & de seguridad de Office 365](export-search-results.md#export-limits).

## <a name="generate-and-download-a-content-search-report"></a>Generar y descargar un informe de búsqueda de contenido

Los pasos para generar y descargar un informe de búsqueda de contenido son muy similares a la exportación real de los resultados de búsqueda.
  
## <a name="step-1-generate-the-report-for-export"></a>Paso 1: generar el informe para la exportación

El primer paso consiste en preparar el informe para descargarlo en la exportación de su equipo. Cuando se trata de un informe, los documentos del informe se cargan en un área de almacenamiento de Azure en la nube de Microsoft.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **Búsqueda de contenido**.
    
4. En la página **búsqueda de contenido** , seleccione una búsqueda. 
    
5. En el panel de detalles, en **exportar informe a un equipo**, haga clic en **generar informe**.
    
    > [!NOTE]
    > Si los resultados de una búsqueda son anteriores a 7 días, se le pedirá que actualice los resultados de la búsqueda. Si esto ocurre, cancele la exportación, haga clic en **Actualizar resultados de búsqueda** en el panel de detalles de la búsqueda seleccionada y, a continuación, vuelva a iniciar la exportación del informe después de que se actualicen los resultados. 
  
6. En la página **exportar un informe** , en **incluir estos elementos de la búsqueda**, elija una de las siguientes opciones:
    
    - Exportar solo los elementos indexados
    
    - Exportar los elementos indexados y sin indexar
    
    - Exportar solo los elementos sin indexar
    
    Para obtener más información acerca de los elementos sin indexar, vea [elementos parcialmente indizados en la búsqueda de contenido](partially-indexed-items-in-content-search.md).
    
7. Elija incluir estadísticas de búsqueda para todas las versiones de los documentos de SharePoint. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios de SharePoint o de OneDrive para la empresa.
    
8. Haga clic en **generar informe**.
    
    El informe de resultados de búsqueda está preparado para la descarga, lo que significa que los documentos del informe se cargarán en el área de almacenamiento de Azure en la nube de Microsoft. Cuando el informe está listo para la descarga, el vínculo de **descarga del informe** se muestra en **exportar informe a un equipo** en el panel de detalles. 
    
> [!NOTE]
> También puede exportar un informe para una búsqueda de contenido que esté asociada a un caso de exhibición de documentos electrónicos. Para ello, vaya a la \> **exhibición**de documentos electrónicos de **investigación de &amp; búsqueda** , seleccione un caso y](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)haga clic en **Editar** ![icono de edición. En la página **búsquedas** , seleccione una búsqueda y, a continuación, haga clic en **exportar** ![los resultados](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> de la búsqueda exportar **un informe**. 
  
## <a name="step-2-download-the-report"></a>Paso 2: descargar el informe

El siguiente paso es descargar el informe desde el área de almacenamiento de Azure a su equipo local.
  
1. En el panel de detalles de la búsqueda para la que generó el informe, en **exportar informe a un equipo**, haga clic en **Descargar Informe**.
    
    Se muestra la página **Descargar Informe** , que contiene la siguiente información sobre el informe que se descargará en el equipo. 
    
    - El número de elementos que se descargarán.
    
    - El tamaño total estimado de los elementos que se descargarán.
    
    - Si se exportarán o no indexados. Los elementos sin indexar son elementos que tienen un formato reconocido, están cifrados o no se indizaron por otros motivos.
    
    - Si las versiones de los documentos de SharePoint se descargarán o no.
    
    - El estado del proceso de exportación del informe. Puede iniciar la descarga del informe incluso si no se ha completado la preparación del informe.
    
2. En **Exportar clave**, haga clic en **copiar al**portapapeles. Esta clave se utilizará en el paso 5 para descargar el informe.
    
    > [!IMPORTANT]
    > Dado que cualquiera puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave igual que lo haría con las contraseñas u otra información relacionada con la seguridad. 
  
3. Haga clic en **Descargar Informe**.
    
4. Si se le pide que instale la **herramienta de exportación MicrosoftOffice 365 eDiscovery**, haga clic en **instalar**.
    
5. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.
    
6. Haga clic en **examinar** para especificar la ubicación en la que desea descargar el informe. 
    
7. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **herramienta de exportación de exhibición** de documentos electrónicos muestra información de estado sobre el proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez finalizado el proceso de exportación, puede tener acceso a los archivos en la ubicación en la que se descargaron. 
    
> [!NOTE]
> Puede descargar el informe para una búsqueda de contenido que esté asociada con un caso de exhibición de documentos electrónicos. Para ello, vaya a la \> **exhibición**de documentos electrónicos de **investigación de &amp; búsqueda** , seleccione un caso y](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)haga clic en **Editar** ![icono de edición. En la página **exportaciones** , seleccione una exportación de informe y, a continuación, haga clic en **Descargar Informe** en el panel de detalles. 
  
## <a name="whats-included-in-the-report"></a>Contenido incluido en el informe

Cuando se genera y se exporta un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:
  
- **Resumen de exportación** : un documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se han buscado, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarán. 
    
    > [!NOTE]
    > Si incluye elementos sin indexar al exportar el informe, el número de elementos sin indexar se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de la búsqueda descargados (si se exportaron los resultados de la búsqueda) que aparecen en la lista Informe de Resumen de exportación. Es decir, el número total de elementos que se descargarán es igual al número total de resultados estimados y el número total de elementos sin indexar. 
  
- **Manifest** -un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. 
    
- **Resultados** : un documento de Excel que contiene una fila con información sobre cada elemento indizado que se exportará con los resultados de la búsqueda. Para el correo electrónico, el registro de resultados contiene información sobre cada mensaje, incluidos: 
    
  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
    
  - La fecha en que se envió o se recibió el mensaje.
    
  - La línea Asunto del mensaje.
    
  - El remitente y los destinatarios del mensaje.
    
    Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:
    
  - La dirección URL del documento.
    
  - La dirección URL de la colección de sitio donde se ubica el documento.
    
  - La fecha en la que el documento se modificó por última vez.
    
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
    > [!NOTE]
    > El número de filas en el informe de **resultados** debe ser igual al número total de resultados de búsqueda que se descargarían menos el número total de elementos que aparecen en el informe de **elementos** sin indexar. 
  
- **Elementos** sin indexar: un documento de Excel que contiene información sobre los elementos sin indexar que se incluirían en los resultados de la búsqueda. Si no incluye elementos sin indexar al generar el informe de resultados de la búsqueda, este informe se descargará, pero estará vacío.

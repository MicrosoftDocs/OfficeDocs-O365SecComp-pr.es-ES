---
title: Aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Obtenga información sobre cómo configurar el registro de Windows para aumentar el rendimiento de los datos al descargar los resultados de búsqueda y búsqueda de datos de la seguridad de Office 365 &amp; centro de cumplimiento y Office 365 avanzada de exhibición de documentos electrónicos.
ms.openlocfilehash: 3f456f5ee0312d4d4d7b95f868520e6756a90fd1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536855"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365

Cuando use la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para descargar los resultados de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento o descarga de datos de Office 365 avanzada exhibición de documentos electrónicos, la herramienta inician un cierto número de exportación simultánea operaciones para descargar los datos en el equipo local. De forma predeterminada, se establece el número de operaciones simultáneas a 8 veces el número de núcleos en el equipo que está utilizando para descargar los datos. Por ejemplo, si tiene un equipo de doble núcleo (lo que significa dos unidades centrales de procesamiento en uno chip), el número predeterminado de las operaciones de exportación de usuarios simultáneos es de 16. Para aumentar el rendimiento de transferencia de datos y el proceso de descarga de velocidad, puede aumentar el número de operaciones simultáneas mediante la configuración de una configuración del registro de Windows en el equipo que se utiliza para descargar los resultados de búsqueda. Para el proceso de descarga de la velocidad, se recomienda que comience con una configuración de 24 operaciones simultáneas.
  
Si descarga los resultados de búsqueda a través de una red de ancho de banda bajo, el aumento de esta configuración podría tener un impacto negativo. Como alternativa, es posible que pueda aumentar la configuración de más de 24 operaciones simultáneas en una red de gran ancho de banda (el número máximo de operaciones simultáneas es 512). Después de configurar este valor del registro, debe cambiar para buscar el número óptimo de las operaciones de usuarios simultáneos para su entorno.
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>Crear una configuración para cambiar el número de operaciones simultáneas al exportar datos del registro

Realice el siguiente procedimiento en el equipo que se usará para descargar los resultados de búsqueda de la seguridad &amp; centro de cumplimiento o datos de exhibición de documentos electrónicos avanzada.
  
1. Si está abierta, cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365. 
    
2. Guarde el siguiente texto en un archivo de registro de la ventana mediante el uso de un sufijo de nombre de archivo de. reg; Por ejemplo, ConcurrentOperations.reg. 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    Como anterior se explica, se recomienda que empiece por 24 operaciones simultáneas y, a continuación, cambie esta opción según corresponda.
    
3. En el Explorador de Windows, haga clic en o haga doble clic en el archivo .reg que creó en el paso anterior.
    
4. En la ventana de Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del registro de realizar el cambio. 
    
5. Cuando se le solicite para continuar, haga clic en **Sí**.
    
    El Editor del registro, se muestra un mensaje que indica que la configuración se ha agregado correctamente en el registro.
    
6. Repita los pasos del 2 al 5 para cambiar el valor para el `DownloadConcurrency` configuración del registro. 
    
    > [!IMPORTANT]
    > Después de crear o cambiar la `DownloadConcurrency` , la configuración del registro asegúrese de crear un nuevo trabajo de exportación o reiniciar un trabajo de exportación existente para los resultados de búsqueda o los datos que desea descargar. Vea la sección [obtener más información](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) para obtener más detalles. 
  
## <a name="more-information"></a>Más información

- Una nueva clave de registro se crea la primera vez que ejecute el archivo .reg que creó en este procedimiento. Entonces el `DownloadConcurrency` configuración del registro se edita cada vez que cambie y vuelva a ejecuta el archivo de edición. reg. 
    
- La herramienta de exportación de exhibición de documentos electrónicos de Office 365 usa la [utilidad AzCopy de Azure](https://go.microsoft.com/fwlink/?linkid=849949) para descargar los datos de búsqueda de la seguridad &amp; centro de cumplimiento de normas o de exhibición de documentos electrónicos avanzada. Configuración de la `DownloadConcurrency` configuración del registro es similar a utilizar el **parámetro/NC** cuando ejecute la utilidad AzCopy. Por lo que la configuración del registro de `"DownloadConcurrency=24"` tendría el mismo efecto que utilizar el valor del parámetro de `/NC:24` con la utilidad AzCopy. 
    
- Si detiene una descarga de exportación que está actualmente en curso y, a continuación, reinícielo (al tratar de volver a descargar los resultados de búsqueda), la herramienta de exportación de exhibición de documentos electrónicos de Office 365 intentará reanudar la descarga del misma. Por lo tanto, si inicia una descarga, deténgalo y, a continuación, cambie la `DownloadConcurrency` registro de configuración, la descarga se probablemente producirá un error si reinicia (haciendo clic en **descarga exporta resultados**). Esto es debido a que la herramienta de exportación intentará reanudar la descarga anterior con la configuración que no es válida debido a que ha cambiado la configuración del registro.
    
    Por lo tanto, después de cambiar la `DownloadConcurrency` no olvide reiniciar el trabajo de exportación (haciendo clic en **reiniciar exportación**) de la seguridad, la configuración del registro &amp; centro de cumplimiento. A continuación, puede descargar los resultados exportados. Para obtener más información acerca de cómo exportar los resultados de búsqueda y datos, vea:
    
  - [Exportar los resultados de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md)
    
  - [Exportar resultados en eDiscovery avanzado de Office 365](export-results-in-advanced-ediscovery.md)
    

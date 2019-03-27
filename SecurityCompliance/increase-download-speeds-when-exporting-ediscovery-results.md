---
title: Aumentar la velocidad de descarga al exportar resultados de búsqueda de exhibición de documentos electrónicos de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Aprenda a configurar el registro de Windows para aumentar el rendimiento de los datos al descargar los resultados de búsqueda y los datos de &amp; búsqueda del centro de seguridad y cumplimiento de Office 365 y eDiscovery avanzado.
ms.openlocfilehash: ddeb247be6981dbfdb874e270a123e4465914d86
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899929"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Aumentar la velocidad de descarga al exportar resultados de búsqueda de exhibición de documentos electrónicos de Office 365

Cuando usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para descargar los resultados de una búsqueda de &amp; contenido en el centro de seguridad de cumplimiento de Office 365 o descargar datos desde Office 365 Advanced eDiscovery, la herramienta inicia un determinado número de exportaciones simultáneas. operaciones para descargar los datos en el equipo local. De forma predeterminada, el número de operaciones simultáneas se establece en 8 veces el número de núcleos en el equipo que está usando para descargar los datos. Por ejemplo, si tiene un equipo con dos núcleos (es decir, dos unidades de procesamiento central en un chip), el número predeterminado de operaciones de exportación simultáneas es 16. Para aumentar el rendimiento de la transferencia de datos y acelerar el proceso de descarga, puede aumentar el número de operaciones simultáneas configurando una configuración del registro de Windows en el equipo que use para descargar los resultados de la búsqueda. Para acelerar el proceso de descarga, se recomienda comenzar con una configuración de 24 operaciones simultáneas.
  
Si descarga los resultados de la búsqueda en una red de ancho de banda bajo, aumentar esta configuración puede tener un impacto negativo. Como alternativa, es posible que pueda aumentar la configuración a más de 24 operaciones simultáneas en una red de ancho de banda alto (el número máximo de operaciones simultáneas es 512). Después de configurar este valor del registro, es posible que tenga que cambiarlo para encontrar el número óptimo de operaciones simultáneas para su entorno.
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>Crear una configuración del registro para cambiar el número de operaciones simultáneas al exportar datos

Lleve a cabo el siguiente procedimiento en el equipo que va a usar para descargar los resultados de &amp; la búsqueda del centro de seguridad y cumplimiento o de los datos de la exhibición avanzada de documentos electrónicos.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta. 
    
2. Guarde el siguiente texto en un archivo de registro de la ventana mediante un sufijo de nombre de archivo. reg; por ejemplo, ConcurrentOperations. reg. 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    Como se ha explicado anteriormente, se recomienda comenzar con 24 operaciones simultáneas y, a continuación, cambiar esta configuración según corresponda.
    
3. En el explorador de Windows, haga clic o doble clic en el archivo. reg que creó en el paso anterior.
    
4. En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios. 
    
5. Cuando se le pregunte si desea continuar, haga clic en **sí**.
    
    El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.
    
6. Puede repetir los pasos 2-5 para cambiar el valor de la `DownloadConcurrency` configuración del registro. 
    
    > [!IMPORTANT]
    > Una vez que haya creado o `DownloadConcurrency` cambiado la configuración del registro, asegúrese de crear un nuevo trabajo de exportación o reiniciar un trabajo de exportación existente para los resultados de búsqueda o los datos que desea descargar. Consulte la sección [More Information](#more-information) para obtener más información. 
  
## <a name="more-information"></a>Más información

- La primera vez que ejecute el archivo. reg que creó en este procedimiento, se creará una nueva clave del registro. A continuación `DownloadConcurrency` , la configuración del registro se edita cada vez que cambia y vuelve a ejecutar el archivo de edición. reg. 
    
- La herramienta de exportación de exhibición de documentos electrónicos de Office 365 usa la [utilidad de Azure AzCopy](https://go.microsoft.com/fwlink/?linkid=849949) para descargar los datos de búsqueda del centro de seguridad &amp; y cumplimiento o de la exhibición avanzada de documentos electrónicos. La configuración `DownloadConcurrency` del registro es similar a usar el parámetro **/NC** al ejecutar la utilidad AzCopy. Por lo tanto, la `"DownloadConcurrency=24"` configuración del registro de tendría el mismo efecto que usar el `/NC:24` valor del parámetro de con la utilidad AzCopy. 
    
- Si detiene una descarga de exportación que está actualmente en curso y la reinicia (intentando descargar los resultados de la búsqueda de nuevo), la herramienta de exportación de exhibición de documentos electrónicos de Office 365 intentará reanudar la misma descarga. Por lo tanto, si inicia una descarga, la detiene y, a continuación `DownloadConcurrency` , cambia la configuración del registro, es probable que se produzca un error en la descarga si la reinicia (al hacer clic en **Descargar resultados**exportados). Esto se debe a que la herramienta de exportación intentará reanudar la descarga anterior con una configuración que no es válida porque ha cambiado la configuración del registro.
    
    Por lo tanto, después de `DownloadConcurrency` cambiar la configuración del registro, asegúrese de reiniciar el trabajo de exportación (haciendo clic en **reiniciar exportación**) en el centro de seguridad &amp; y cumplimiento. A continuación, puede descargar los resultados exportados. Para obtener más información sobre la exportación de resultados de búsqueda y datos, vea:
    
  - [Exportar resultados de búsqueda de contenido desde el centro &amp; de seguridad y cumplimiento de Office 365](export-search-results.md)
    
  - [Exportar resultados en Office 365 Advanced eDiscovery](export-results-in-advanced-ediscovery.md)
    

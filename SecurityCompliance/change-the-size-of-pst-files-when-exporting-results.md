---
title: Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Puede cambiar el tamaño predeterminado de los archivos PST que se descargó a su equipo al exportar los resultados de búsqueda de exhibición de documentos electrónicos.
ms.openlocfilehash: d38189c437154dbe27a084230d4d3fd4de418ece
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535662"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

Cuando se usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para exportar los resultados de correo electrónico de una búsqueda de exhibición de documentos electrónicos de las distintas herramientas de exhibición de documentos electrónicos de Microsoft, el tamaño predeterminado de un archivo PST que se puede exportar es 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Una razón para hacer esto es para que un archivo PST puede quepan en medios extraíbles, como un DVD, un CD o una unidad USB. 
  
> [!NOTE]
>  La herramienta de exportación de exhibición de documentos electrónicos de Office 365 se usa para exportar los resultados de búsqueda cuando se usa la búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento, en lugar de exhibición de documentos electrónicos en Exchange Online y el centro de exhibición de documentos electrónicos en SharePoint Online. 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Crear una configuración del registro para cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

Realice el procedimiento siguiente en el equipo que se usará para exportar los resultados de una búsqueda de exhibición de documentos electrónicos.
  
1. Si está abierta, cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365. 
    
2. Guarde el siguiente texto en un archivo de registro de la ventana mediante el uso de un sufijo de nombre de archivo de. reg; Por ejemplo, PstExportSize.reg. 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    En el ejemplo anterior, el `PstSizeLimitInBytes` valor está establecido en 1.073.741.824 bytes o aproximadamente 1 GB. A continuación presentamos algunos otros valores de ejemplo para la `PstSizeLimitInBytes` configuración. 
    
    |**Cambio de tamaño en GB (aproximadamente)**|**Tamaño en bytes**|
    |:-----|:-----|
    |.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Cambiar el `PstSizeLimitInBytes` valor para el tamaño máximo que desee de un archivo PST al exportar los resultados de búsqueda y, a continuación, guarde el archivo. 
    
4. En el Explorador de Windows, haga clic en o haga doble clic en el archivo .reg que creó en los pasos anteriores.
    
5. En la ventana de Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del registro de realizar el cambio. 
    
6. Cuando se le solicite para continuar, haga clic en **Sí**.
    
    El Editor del registro, se muestra un mensaje que indica que la configuración se ha agregado correctamente en el registro.
    
7. Repita los pasos del 3 al 6 para cambiar el valor para el `PstSizeLimitInBytes` configuración del registro. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Preguntas más frecuentes acerca de cómo cambiar el tamaño predeterminado de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

 **¿Por qué es el valor predeterminado de tamaño 10 GB?**
  
El tamaño predeterminado de 10 GB se ha basado en los comentarios del cliente; 10 GB es un buen equilibrio entre la cantidad óptima de contenido en un archivo PST único y con un mínimo de posibilidades de daños en el archivo.
  
 **¿Debo aumentar o disminuir el tamaño predeterminado de los archivos PST?**
  
Los clientes tienden a reducir el límite de tamaño para que quepan los resultados de búsqueda en medios extraíbles que puede enviar físicamente otras ubicaciones en su organización. No se recomienda aumentar el tamaño predeterminado porque PST archivos mayor que 10 GB podría tener problemas de daños.
  
 **¿Qué equipo es necesario hacer esto en?**
  
Debe cambiar la configuración del registro en cualquier equipo local que ejecute la herramienta de exportación de exhibición de documentos electrónicos de Office 365 en.
  
 **¿Después de cambiar esta configuración, tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Pero, si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos de Office 365, tendrá que cerrarlo y el reinicio después de cambiar esta configuración.
  
 **¿Obtener editada una clave del registro existente o se crea una nueva clave?**
  
Una nueva clave de registro se crea la primera vez que ejecute el archivo .reg que creó en este procedimiento. A continuación, la configuración se edita cada vez que cambie y vuelva a ejecuta el archivo de edición. reg.

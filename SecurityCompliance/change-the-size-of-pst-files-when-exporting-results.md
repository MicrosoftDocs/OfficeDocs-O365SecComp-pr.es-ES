---
title: Cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Puede cambiar el tamaño predeterminado de los archivos PST que se descargan en el equipo cuando exporta resultados de la búsqueda de exhibición de documentos electrónicos.
ms.openlocfilehash: 8a956091f29ec1b564d3194c7e3ca2680fdeb564
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214630"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de eDiscovery

Cuando usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para exportar los resultados de correo electrónico de una búsqueda de exhibición de documentos electrónicos de las diferentes herramientas de eDiscovery de Microsoft, el tamaño predeterminado de un archivo PST que se puede exportar es 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Un motivo para hacerlo es que un archivo PST puede encajar en un medio extraíble, un DVD, un disco compacto o una unidad USB. 
  
> [!NOTE]
>  La herramienta de exportación de exhibición de documentos electrónicos de Office 365 se usa para exportar los resultados de la búsqueda al &amp; usar la búsqueda de contenido en el centro de seguridad y cumplimiento de Office 365, en la exhibición de documentos electrónicos local en Exchange Online y en el centro de eDiscovery en SharePoint Online. 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Crear una configuración del registro para cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de exhibición de documentos electrónicos

Realice el procedimiento siguiente en el equipo que va a usar para exportar los resultados de una búsqueda de exhibición de documentos electrónicos.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta. 
    
2. Guarde el siguiente texto en un archivo de registro de la ventana mediante un sufijo de nombre de archivo. reg; por ejemplo, PstExportSize. reg. 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    En el ejemplo anterior, el `PstSizeLimitInBytes` valor se establece en 1.073.741.824 bytes o aproximadamente 1 GB. Estos son algunos de los otros valores de `PstSizeLimitInBytes` ejemplo para la configuración. 
    
    |**Tamaño en GB (aprox.)**|**Tamaño en bytes**|
    |:-----|:-----|
    |.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Cambie el `PstSizeLimitInBytes` valor al tamaño máximo deseado de un archivo pst cuando exporte los resultados de la búsqueda y, a continuación, guarde el archivo. 
    
4. En el explorador de Windows, haga clic o doble clic en el archivo. reg que creó en los pasos anteriores.
    
5. En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios. 
    
6. Cuando se le pregunte si desea continuar, haga clic en **sí**.
    
    El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.
    
7. Puede repetir los pasos 3-6 para cambiar el valor de la `PstSizeLimitInBytes` configuración del registro. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Preguntas más frecuentes sobre cómo cambiar el tamaño predeterminado de los archivos PST al exportar los resultados de la búsqueda de eDiscovery

 **¿Por qué el tamaño predeterminado es 10 GB?**
  
El tamaño predeterminado de 10 GB se basaba en los comentarios de los clientes; 10 GB es un buen equilibrio entre la cantidad óptima de contenido en un PST único y con una mínima probabilidad de daños en el archivo.
  
 **¿Debo aumentar o disminuir el tamaño predeterminado de los archivos PST?**
  
Los clientes tienden a reducir el límite de tamaño para que los resultados de la búsqueda quepan en medios extraíbles que pueden enviar físicamente otras ubicaciones de la organización. No se recomienda aumentar el tamaño predeterminado, ya que los archivos PST con más de 10 GB podrían tener problemas de daños.
  
 **¿En qué equipo tengo que hacerlo?**
  
Debe cambiar la configuración del registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos de Office 365.
  
 **Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Pero, si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos de Office 365, tendrá que cerrarla y reiniciarla después de cambiar esta configuración.
  
 **¿Se modifica una clave del registro existente o se crea una nueva clave?**
  
La primera vez que ejecute el archivo. reg que creó en este procedimiento, se creará una nueva clave del registro. A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición. reg.

---
title: DesHabilitar los informes al exportar los resultados de la búsqueda de contenido &amp; en el centro de seguridad y cumplimiento de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Edite el registro de Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido desde &amp; el centro de confianza de seguridad de Office 365. La desHabilitación de estos informes puede acelerar el tiempo de descarga y ahorrar espacio en disco.
ms.openlocfilehash: f08f5e7143022591d38bda787301e71ae80fb3d3
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936720"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>DesHabilitar los informes al exportar los resultados de la búsqueda de contenido &amp; en el centro de seguridad y cumplimiento de Office 365

Cuando usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para exportar los resultados de una &amp; búsqueda de contenido en el centro de seguridad y cumplimiento, la herramienta crea y exporta automáticamente dos informes que contienen información adicional acerca del contenido exportado. Estos informes son el archivo Results. csv y el archivo manifest. XML (consulte la sección [preguntas más frecuentes sobre cómo deshabilitar los informes de exportación](#frequently-asked-questions-about-disabling-export-reports) de este tema para obtener descripciones detalladas de estos informes). Como estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco al impedir que se exporten estos archivos. Para ello, puede cambiar el registro de Windows en el equipo que usa para exportar los resultados de la búsqueda. Si desea incluir los informes más adelante, puede editar la configuración del registro. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Crear una configuración del registro para deshabilitar los informes de exportación

Lleve a cabo el siguiente procedimiento en el equipo que va a usar para exportar los resultados de una búsqueda de contenido.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta.
    
2. Realice uno o ambos de los pasos siguientes, según el informe de exportación que quiera deshabilitar.
    
    - **Results. csv**
    
      Guarde el siguiente texto en un archivo de registro de Windows mediante un sufijo de nombre de archivo. reg; por ejemplo, DisableResultsCsv. reg.
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest. XML**
    
      Guarde el siguiente texto en un archivo de registro de Windows mediante un sufijo de nombre de archivo. reg; por ejemplo, DisableManifestXml. reg.
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. En el explorador de Windows, haga clic o doble clic en el archivo. reg que creó en los pasos anteriores.
    
4. En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios. 
    
5. Cuando se le pregunte si desea continuar, haga clic en **sí**.
    
    El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Editar la configuración del registro para volver a habilitar los informes de exportación

Si ha deshabilitado los informes Results. csv y manifest. XML creando los archivos. reg en el procedimiento anterior, puede editar esos archivos para volver a habilitar un informe de manera que se exporte con los resultados de la búsqueda. De nuevo, realice el siguiente procedimiento en el equipo que va a usar para exportar los resultados de una búsqueda de contenido.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta.
    
2. Edite uno o ambos de los archivos. reg Edit que creó en el procedimiento anterior.
    
    - **Results. csv**
    
        Abra el archivo DisableResultsCsv. reg en el Bloc de notas, `False` cambie `True`el valor a y, a continuación, guarde el archivo. Por ejemplo, después de editar el archivo, tiene el siguiente aspecto:
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest. XML**
    
        Abra el archivo DisableManifestXml. reg en el Bloc de notas, `False` cambie `True`el valor a y, a continuación, guarde el archivo. Por ejemplo, después de editar el archivo, tiene el siguiente aspecto:
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. En el explorador de Windows, haga clic o doble clic en un archivo. reg que modificó en el paso anterior.
    
4. En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios. 
    
5. Cuando se le pregunte si desea continuar, haga clic en **sí**.
    
    El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Preguntas más frecuentes sobre la deshabilitación de informes de exportación
<a name="faqs"> </a>

 **¿Cuáles son los informes Results. csv y manifest. XML?**
  
Los archivos Results. csv y manifest. XML contienen información adicional acerca del contenido que se exportó.
  
- **Results. csv** un documento de Excel que contiene información acerca de cada elemento que se descarga como resultado de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
    
  - La fecha en que se envió o se recibió el mensaje.
    
  - La línea Asunto del mensaje.
    
  - El remitente y los destinatarios del mensaje.
    
  - Si el mensaje es un mensaje duplicado si ha habilitado la desduplicación al exportar los resultados de la búsqueda. Los mensajes duplicados tendrán un valor en la columna **principal de Itemid** que identifica el mensaje como duplicado. El valor de la columna **principal de Itemid** es el mismo que el valor de la columna DocumentId del **elemento** del mensaje que se exportó. 
    
    Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:
    
  - La dirección URL del documento.
    
  - La dirección URL de la colección de sitio donde se ubica el documento.
    
  - La fecha en la que el documento se modificó por última vez.
    
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
- **Manifest. XML** un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. La información de este informe es la misma que la del informe Results. csv, pero está en el formato especificado por el modelo de referencia de detección electrónica (EDRM). Para obtener más información acerca de EDRM, [https://www.edrm.net](https://www.edrm.net)vaya a.
    
 **¿Cuándo debo deshabilitar la exportación de estos informes?**
  
Depende de sus necesidades específicas. Muchas organizaciones no necesitan más información sobre los resultados de la búsqueda y no necesitan estos informes.
  
 **¿En qué equipo tengo que hacerlo?**
  
 Tiene que cambiar la configuración del registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos de Office 365. 
  
 **Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Pero si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos de Office 365, debe cerrarla y reiniciarla después de cambiar la configuración del registro.
  
 **¿Se modifica una clave del registro existente o se crea una nueva clave?**
  
La primera vez que ejecute el archivo. reg que creó en el procedimiento de este tema, se creará una nueva clave del registro. A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición. reg.

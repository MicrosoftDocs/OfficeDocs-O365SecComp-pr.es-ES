---
title: Deshabilitar informes al exportar los resultados de la búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Edite el registro de Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido de la seguridad de Office 365 &amp; centro de Comliance. Deshabilitar estos informes puede acelerar el tiempo de descarga y ahorrar espacio en disco.
ms.openlocfilehash: 3c09e0563ddd4469f21950dc3a698ce08b0014df
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536722"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>Deshabilitar informes al exportar los resultados de la búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento

Cuando use la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para exportar los resultados de una búsqueda de contenido en la seguridad &amp; centro de cumplimiento, la herramienta automáticamente crea y se exporta dos informes que contienen información adicional sobre el contenido exportado. Estos informes son el archivo Results.csv y el archivo Manifest.xml (consulte la sección [preguntas acerca de cómo deshabilitar los informes de exportación más frecuentes](#frequently-asked-questions-about-disabling-export-reports) de este tema para obtener descripciones detalladas de estos informes). Debido a que estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco al impedir que estos archivos se va a exportar. Para ello, puede cambiar el registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Si desea incluir los informes en un momento posterior, puede editar la configuración del registro. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Crear una configuración del registro para deshabilitar los informes de exportación

Realice el procedimiento siguiente en el equipo que se usará para exportar los resultados de una búsqueda de contenido.
  
1. Si está abierta, cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365.
    
2. Lleve a cabo uno de los pasos siguientes, dependiendo de qué informe de exportación que desee deshabilitar o ambos.
    
    - **Results.csv**
    
      Guarde el siguiente texto en un archivo de registro de Windows mediante el uso de un sufijo de nombre de archivo de. reg; Por ejemplo, DisableResultsCsv.reg.
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.Xml**
    
      Guarde el siguiente texto en un archivo de registro de Windows mediante el uso de un sufijo de nombre de archivo de. reg; Por ejemplo, DisableManifestXml.reg.
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. En el Explorador de Windows, haga clic en o haga doble clic en el archivo .reg que creó en los pasos anteriores.
    
4. En la ventana de Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del registro de realizar el cambio. 
    
5. Cuando se le solicite para continuar, haga clic en **Sí**.
    
    El Editor del registro, se muestra un mensaje que indica que la configuración se ha agregado correctamente en el registro.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Editar la configuración del registro para volver a habilitar los informes de exportación

Si deshabilita los informes de Results.csv y Manifest.xml mediante la creación de los archivos .reg en el procedimiento anterior, puede editar los archivos para volver a habilitar un informe para que se exporta con los resultados de búsqueda. Una vez más, realice el siguiente procedimiento en el equipo que se usará para exportar los resultados de una búsqueda de contenido.
  
1. Si está abierta, cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365.
    
2. Edite uno o ambos de los archivos de editar .reg que creó en el procedimiento anterior.
    
    - **Results.csv**
    
        Abra el archivo DisableResultsCsv.reg en el Bloc de notas, cambie el valor de `False` a `True`y, a continuación, guarde el archivo. Por ejemplo, después de editar el archivo, lo tiene este aspecto:
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.Xml**
    
        Abra el archivo DisableManifestXml.reg en el Bloc de notas, cambie el valor de `False` a `True`y, a continuación, guarde el archivo. Por ejemplo, después de editar el archivo, lo tiene este aspecto:
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. En el Explorador de Windows, haga clic en o haga doble clic en un archivo .reg que modificó en el paso anterior.
    
4. En la ventana de Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del registro de realizar el cambio. 
    
5. Cuando se le solicite para continuar, haga clic en **Sí**.
    
    El Editor del registro, se muestra un mensaje que indica que la configuración se ha agregado correctamente en el registro.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Preguntas más frecuentes acerca de cómo deshabilitar los informes de exportación
<a name="faqs"> </a>

 **¿Qué son los informes Results.csv y Manifest.xml?**
  
Los archivos Results.csv y Manifest.xml contienen información adicional sobre el contenido que se ha exportado.
  
- **Results.csv** documento de Excel que contiene información acerca de cada elemento que se descarga como un resultado de búsqueda. Para el correo electrónico, el registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
    
  - La fecha en que se envió o se recibió el mensaje.
    
  - La línea Asunto del mensaje.
    
  - El remitente y los destinatarios del mensaje.
    
  - Si el mensaje es un mensaje duplicado si se habilita la desduplicación al exportar los resultados de búsqueda. Mensajes duplicados tendrá un valor en la columna **Primaria ItemId** que identifica el mensaje como un duplicado. El valor de la columna **ItemId primario** es el mismo que el valor de la columna **Elemento DocumentId** del mensaje que se ha exportado. 
    
    Para los documentos de SharePoint y OneDrive para sitios de profesionales, el registro de resultados contiene información acerca de cada documento, incluidos:
    
  - La dirección URL del documento.
    
  - La dirección URL de la colección de sitio donde se ubica el documento.
    
  - La fecha en la que el documento se modificó por última vez.
    
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
- **Manifest.XML** un archivo de manifiesto (en formato XML) que contiene información acerca de los artículos incluidos en los resultados de búsqueda. La información de este informe es el mismo que el informe de Results.csv, pero en el formato especificado por el modelo de referencia de detección electrónica (EDRM). Para obtener más información acerca de EDRM, vaya a [https://www.edrm.net](https://www.edrm.net).
    
 **¿Cuándo debo Deshabilitar exportación de estos informes?**
  
Depende de sus necesidades concretas. Muchas organizaciones no requieren información adicional acerca de los resultados de búsqueda y no es necesario estos informes.
  
 **¿Qué equipo es necesario hacer esto en?**
  
 Se debe cambiar la configuración del registro en cualquier equipo local que ejecute la herramienta de exportación de exhibición de documentos electrónicos de Office 365 en. 
  
 **¿Después de cambiar esta configuración, tengo que reiniciar el equipo?**
  
No, no es necesario que reinicie el equipo. Pero si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos de Office 365, debe cerrarlo y, a continuación, reinícielo después de cambiar la configuración del registro.
  
 **¿Obtener editada una clave del registro existente o se crea una nueva clave?**
  
Una nueva clave de registro se crea la primera vez que ejecute el archivo .reg que creó en el procedimiento descrito en este tema. A continuación, la configuración se edita cada vez que cambie y vuelva a ejecuta el archivo de edición. reg.

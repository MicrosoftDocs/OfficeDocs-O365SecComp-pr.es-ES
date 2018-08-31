---
title: Exportar resultados en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'Obtenga información sobre cómo definir las opciones de exportación de resultados desde Office 365 avanzada exhibición de documentos electrónicos, incluido el procedimiento para especificar los parámetros de una sección de exportación. '
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536788"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a>Exportar resultados en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En este tema se describe las opciones de configuración de exportación de exhibición de documentos electrónicos avanzada.
  
 **En este tema:**
  
- [Definición de exportación de lotes y sesiones](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [Exporta incremental y adicional](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [Configurar los parámetros de exportación por lotes](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [Exportar archivos de salida de informe](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a>Definición de exportación de lotes y sesiones
<a name="BK_Define"> </a>

Una sección de exportación permite el proceso de exportación con un conjunto de parámetros definidos. Exhibición de documentos electrónicos avanzada le permite definir lotes para personalizar cada exportación.
  
Los parámetros se definen por lotes de exportación. Se crea una sección denominada "Exportar por lotes 01" de forma predeterminada para el primer lote de un caso. También puede editar el nombre de la sección y la descripción.
  
Una sesión de exportación es una ejecución de exportación de eDiscovery avanzada dentro de una sección de exportación.
  
## <a name="incremental-and-additional-exports"></a>Exporta incremental y adicional
<a name="BK_IncrementalReports"> </a>

Puede ejecutar varias sesiones de exportación dentro de una sección de exportación, para garantizar un resultado homogéneo en función de la misma plantilla de exportación y los parámetros. Para cada sesión dentro de un lote, puede exportar el análisis para recién procesan los datos de casos y procesar cada uno "incrementalmente".
  
Con el fin de exportar con un conjunto diferente de parámetros, primero debe crear un nuevo lote. La primera sesión en el nuevo lote generarán los resultados de los archivos procesados en el caso de hasta el momento, si estos archivos se han importado y procesan a través de una o varias de las importaciones. Vuelve a calcular cada lote de tablas dinámicas, similitud, inclusives, etcetera. Las sesiones de usar los parámetros definidos para el lote y no volver a calcular tablas dinámicas, similitud, inclusives, etc. para cada ejecución de la sesión.
  
Por ejemplo, supongamos que se ha importado un caso y analizan sus datos. Con el fin de recuperar los resultados de subprocesos de correo electrónico para los datos incrementales y cerca de duplicados, haga clic en **crear exportación de sesión** en el mismo lote que se usó anteriormente para exportar datos. 
  
## <a name="set-up-batch-export-parameters"></a>Configurar los parámetros de exportación por lotes
<a name="BK_SetUpExport"> </a>

La herramienta de exportación de exhibición de documentos se usa para exportar los resultados de búsqueda de exhibición de documentos electrónicos avanzada a su equipo local. Para aumentar el rendimiento de transferencia de datos y el proceso de exportación de velocidad, puede configurar una configuración del registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Si desea aumentar la velocidad de descarga, configurar la configuración del registro antes de configurar los parámetros de exportación. Para obtener más información, vea [aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. En la exhibición de documentos electrónicos avanzada, seleccione un caso y haga clic en **Exportar** \> **el programa de instalación**.
    
  - En la lista **Exportar por lotes** , seleccione el nombre del lote o exportar los resultados a la sección de exportación 01, (el lote de forma predeterminada). 
    
  - Para exportar los resultados de los archivos nuevos que ha agregado a un caso existente, continúe con el lote actual. Para crear una sesión en el lote, seleccione el mismo número de lote y haga clic en **crear exportación sesión** puede usar esta opción para exportar los mismos parámetros como el lote anterior, de manera incremental. 
    
  - Para exportar a un nuevo lote, haga clic en **Agregar**![agregar icono](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)y especifique un nuevo nombre en **nombre de lote** (o acepte el valor predeterminado) y una descripción en la **Descripción de lote**. Haga clic en **Aceptar**.
    
  - Para editar un nombre de proceso por lotes o una descripción, seleccione el nombre de **exportación por lotes**, haga clic en **Editar** ![icono Editar](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)y, a continuación, modifique los campos.
    
    > [!NOTE]
    > Una vez ejecutado el sesiones de una sección de exportación, no se puede eliminar. Además, se pueden editar sólo algunos parámetros una vez que se ejecuta la primera sesión. 
  
  - Para crear un lote de exportación duplicados, elija **por lotes de exportación de duplicado**![crear un icono de proceso por lotes de exportación duplicados](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) y escriba un nombre y una descripción para el lote de duplicados en el panel. 
    
  - Para eliminar una sección de exportación, elija **Eliminar**![eliminar un icono de exportación de lote](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).
    
  - Para ver el historial de un lote, elija **Historial por lotes**![icono de vista de historial](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).
    
2. En la **población**, seleccione **incluir sólo los archivos por encima de la puntuación de relevancia corte** o **por lotes de exportación de refinar** si desea ajustar la configuración de la sección de exportación. 
    
3. Si selecciona **incluir sólo archivos por encima de la puntuación de relevancia corte**, está habilitado el **problema** . Si la puntuación de relevancia del archivo es mayor que la puntuación de límite para el problema seleccionado, el archivo se exportará a menos que se excluye el filtro 'para revisión'. 
  
Si selecciona **por lotes de exportación de refinar**, la **desduplicación** y filtro 'Para revisión' se habilitan los botones de opción de campo. Si elige **la desduplicación**, a continuación, los archivos duplicados se filtrarán según la directiva definida [Case nivel (valor predeterminado): en cada conjunto de archivos duplicados en el caso todo, será desaprovisionamiento duped todos menos un archivo. Nivel de custodia: de cada conjunto de archivos duplicados de la misma custodia, será desaprovisionamiento duped todos menos un archivo.] El resultado de exportación contiene un registro de todos los archivos duplicados. Si elige **filtrar por 'para revisión'** campo, seleccione **modificar en metadatos** para escribir la configuración de campo **'para revisión'** . Seleccione **incluir los archivos de entrada** para incluir los archivos de origen en el contenido del paquete. Puede desactivar esta opción para acelerar el proceso de exportación. Tenga en cuenta que se exportará los archivos nativos en cualquier caso. 
    
4. En **metadatos**, seleccione una de las siguientes opciones en la lista **plantilla de exportación** (una vez por sesión). 
    
  - **Estándar**: conjunto básico de propiedades, metadatos y elementos de datos. Use esta opción cuando importar datos ya se procesan en la exhibición de documentos electrónicos avanzada y exportar datos se carguen a un sistema que ya contiene los archivos. De forma predeterminada, se crean las columnas de plantilla de exportación y se rellena.
    
  - **Todos los**: conjunto completo de metadatos estándar, incluidos todos los datos de procesamiento, así como las puntuaciones de análisis y la relevancia. Esta plantilla se requiere cuando exhibición de documentos electrónicos avanzada realiza el procesamiento y datos de archivo se carguen a un sistema externo por primera vez.
    
  - **Problemas**: seleccione **Todos los problemas** o seleccione un problema determinado que haya creado. 
    
5. En el área **destino**:
    
  - **Descargar en el equipo local**
    
  - **Exportar a definidas por el usuario Azure blob**: si se activa esta característica, puede especificar un token de dirección URL y SAS de contenedor.
    
    > [!NOTE]
    > Una vez que se almacena un paquete de exportación para el usuario definido Azure blob, los datos ya no se administran mediante avanzada exhibición de documentos electrónicos; se administra mediante el blob de Azure. Esto significa que si se elimina el caso, los archivos exportados seguirá estando en el blob de Azure. 
  
  - **Guardar SAS símbolo (token) de sesión de exportación futuras**: si está activado, el token de SAS se cifrarán en la base de datos interna de la exhibición de documentos avanzadas para un uso futuro.
    
    > [!NOTE]
    > Actualmente, el token de SAS expira después de un mes. Si se intenta descargar después de más de un mes que tenga que deshacer la última sesión, a continuación, exportar de nuevo. 
  
6. Haga clic en **Modificar** para establecer el "para su revisión ' configuración de campo. 
    
> ![Configurar para la configuración de campo de revisión de un lote de exportación](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> En los **mensajes de correo electrónico** , seleccione los mensajes de correo electrónico que desee exportar: 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> En los **documentos** , seleccione los documentos que desea exportar: 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> En **los datos adjuntos** , seleccione los datos adjuntos que desea exportar 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> En **Micellaneous** puede elegir para **tratar los datos adjuntos como documentos**, **tratar los correos electrónicos como documentos**o **Expandir para incluir los archivos de la familia**. Cuando elija **Expandir para incluir los archivos de la familia**, para cada archivo que se marca para su revisión, también se marcará todos los archivos de la misma familia.
    
    Choose **Save** to save the settings. 
    
7. Después de especificar los parámetros de exportación, para iniciar el proceso de exportación, haga clic en **Crear sesión de exportación**.
    
    Durante la exportación, el estado se muestra en el **estado de la tarea**. Los resultados se muestran en el **Resumen de exportación**.
    
8. En la ventana **descarga de archivos** , haga clic en **Copiar al Portapapeles** para copiar la clave de exportación. 
    
    ![Descargar archivos](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. Haga clic en **Cerrar**. 
    
    Se inicia la herramienta de exportación de exhibición de documentos electrónicos.
    
    ![Herramienta de exportación de exhibición de documentos electrónicos](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. En la **exhibición de documentos electrónicos herramienta para exportar**:
    
1. En **Pegar que se usará para conectarse al origen de la firma de acceso compartidos**, pegue la clave de exportación que youcopied en el Portapapeles en el paso 7.
    
2. Haga clic en **Examinar** para seleccionar la ubicación de destino para almacenar los archivos de exportación descargado en el equipo local. 
    
11. Haga clic en **Iniciar**. Los archivos de exportación se descargan en el equipo local. Si opta por **Exportar a blob Azure definidas por el usuario** en el paso 4, la sesión se exporta a un destino de dirección URL de almacenamiento de blobs de su elección. 
    
Para obtener una descripción completa de los campos en el informe de exportación, consulte [los campos del informe de exportación](export-report-fields-in-advanced-ediscovery.md).
  
## <a name="export-report-output-files"></a>Exportar archivos de salida de informe
<a name="BK_ExportOutputFIles"> </a>

En la siguiente tabla se enumera los archivos de resultados que se generan cuando se ejecuta una sección de exportación.
  
|**Nombre de archivo**|**Tipo de archivo**|**Descripción**|
|:-----|:-----|:-----|
|Resumen de exportación  <br/> |CSV  <br/> |Un archivo de registro generado por la herramienta de exportación de exhibición de documentos electrónicos.  <br/> |
|Seguimiento  <br/> |txt  <br/> |Un archivo de registro generado por la herramienta de exportación de exhibición de documentos electrónicos.  <br/> |
|Archivos de texto extraídos  <br/> |Carpeta de archivos  <br/> |Carpeta que contiene los archivos extraídos de texto de los archivos exportados.  <br/> |
|Archivos nativos o datos proporcionados por  <br/> |Carpeta de archivos  <br/> |Carpeta que contiene los archivos de entrada y nativos de los archivos exportados.  <br/> |
|Lista de exportación  <br/> |xlsx  <br/> |Metadatos de los archivos exportados en formato xlsx. Se realicen los campos en los archivos de plantilla usuario selecciona para exportar. Si es necesario, se crean varios archivos, cada uno de ellos contiene filas de 100-150K. Si un determinado valor contiene más caracteres que puede contener una celda de Excel (actualmente el límite de caracteres es 32.767), a continuación, se recortará el valor para la longitud máxima permitida. Si un valor se recorta, color de fondo de la celda es rojo para indicar esto al usuario." Los participantes de correo electrónico"es un ejemplo de un campo que puede superar el límite de longitud, si el correo electrónico se envió a una distribución de gran tamaño. Para obtener información detallada acerca de los campos de resultados, vea [exportar campos de informe](export-report-fields-in-advanced-ediscovery.md) .<br/> |
|Archivo de carga  <br/> |CSV  <br/> |Metadatos de los archivos exportados en formato csv para cargarse en otra aplicación. Se realicen los campos en los archivos de plantilla usuario selecciona para exportar.  <br/> |
|Indicador de éxito  <br/> |txt  <br/> |Sólo se crean al exportar para un 3 º Azure blob. Si la exportación se realiza correctamente completamente, se creará el archivo. En caso de fallo, parcial o no se creará el archivo correcto. Se creará el archivo en la carpeta raíz, lo que permite el seguimiento automatizado en diferentes Estados de lotes o sesiones de exportación. Esto es un archivo vacío. Su nombre es: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.  <br/> |
   
## <a name="see-also"></a>Vea también
<a name="BK_ExportOutputFIles"> </a>

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Visualización del historial de proceso por lotes y exportar más allá de los resultados](view-batch-history-and-export-past-results.md)
  
[Configuración rápida de eDiscovery avanzado de Office 365](quick-setup-for-advanced-ediscovery.md)

[Campos de exportación de informe](export-report-fields-in-advanced-ediscovery.md)
  
[Aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365](increase-download-speeds-when-exporting-ediscovery-results.md)


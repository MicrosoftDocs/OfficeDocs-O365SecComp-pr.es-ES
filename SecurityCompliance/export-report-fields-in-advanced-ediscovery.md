---
title: Exportar campos de resultados en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: Describe todos los campos que se incluyen en los informes de exportación de exhibición de documentos electrónicos avanzada.
ms.openlocfilehash: a578523098248bcfa16ea8ba97d756d97ba060fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535883"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>Exportar campos de resultados en eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En este tema se describe los campos del informe de exportación de exhibición de documentos electrónicos avanzadas para el estándar y todas las plantillas de.
  
## <a name="export-report-fields"></a>Campos de exportación de informe

En la siguiente tabla se enumera los campos de cada plantilla de exportación.
  
|**Nombre de campo de exportación**|**Grupo**|**Descripción**|**Disponible en la plantilla estándar**|**Disponible en todas las plantillas**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |General  <br/> |Número de fila.  <br/> |Sí  <br/> |Sí  <br/> |
|File_ID  <br/> |General  <br/> |Identificador de archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|File_class  <br/> |Proceso  <br/> |Archivo de clase.  <br/> |Sí  <br/> |Sí  <br/> |
|Family_ID  <br/> |Proceso  <br/> |Identificador numérico que se usa para agrupar archivos (normalmente, la instancia de correo electrónico y sus datos adjuntos).  <br/> |Sí  <br/> |Sí  <br/> |
|For_review  <br/> |Proceso  <br/> |Marca para indicar que el campo se incluirá en la exportación para su revisión.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_file_name  <br/> |Proceso  <br/> |Nombre de archivo nativo, sin hacer referencia a la carpeta y la extensión.  <br/> |Sí  <br/> |Sí  <br/> |
|Custodia  <br/> |General  <br/> |Custodia del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Set_ID  <br/> |Analizar  <br/> |"Establece ND" o "Conjunto de correo electrónico" identificador.  <br/> |Sí  <br/> |Sí  <br/> |
|Inclusive_type  <br/> |Correo electrónico  <br/> |Indica si el archivo es inclusive, según los siguientes valores: 0 - no inclusive, 1 - 2 Inclusive, - Inclusive menos 3 - copia Inclusive.  <br/> |Sí  <br/> |Sí  <br/> |
|Marked_as_pivot  <br/> |NEAR duplicados  <br/> |Indica si el archivo es una tabla dinámica.  <br/> |Sí  <br/> |Sí  <br/> |
|Similarity_percent  <br/> |NEAR duplicados  <br/> |Porcentaje de similitud con relación a la tabla dinámica.  <br/> |Sí  <br/> |Sí  <br/> |
|Duplicate_subset  <br/> |NEAR duplicados  <br/> |Identificador único del subconjunto duplicado. Indica si el archivo tiene duplicados de texto exacto.  <br/> |Sí  <br/> |Sí  <br/> |
|Fecha  <br/> |General  <br/> |Fecha de archivo (depende de tipo de archivo - correo electrónico: fecha de envío; documento: fecha de modificación).  <br/> |Sí  <br/> |Sí  <br/> |
|Dominant_theme  <br/> |Analizar  <br/> |Tema principal del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Themes_list  <br/> |Temas  <br/> |Lista de nombres de temas.  <br/> |Sí  <br/> |Sí  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Identificador numérico único de un conjunto de Nearduplicate.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_set  <br/> |Correo electrónico  <br/> |Identificador numérico único de un conjunto de correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_thread  <br/> |Correo electrónico  <br/> |Describe la posición del correo electrónico dentro del correo electrónico establece consiste en todos los identificadores de nodo desde la raíz en el correo electrónico actual, separado por puntos.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_subject  <br/> |Correo electrónico  <br/> |Asunto del mensaje de correo.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_date_sent  <br/> |Correo electrónico  <br/> |Fecha en que se envió el correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_participants  <br/> |Correo electrónico  <br/> |Direcciones de correo electrónico de todos los participantes en un subproceso de correo electrónico, incluidos para faltan vínculos.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_participant_domains  <br/> |Correo electrónico  <br/> |Dominios de todos los participantes en un subproceso de correo electrónico, incluidos para el enlace que falta.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_sender  <br/> |Correo electrónico  <br/> |Nombre del remitente de correo electrónico o dirección.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_sender_domain  <br/> |Correo electrónico  <br/> |Dominio del remitente de correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_to  <br/> |Correo electrónico  <br/> |A los destinatarios del correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_cc  <br/> |Correo electrónico  <br/> |Destinatario CC del mensaje de correo.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_bcc  <br/> |Correo electrónico  <br/> |Destinatario CCO del mensaje de correo.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_recipient_domains  <br/> |Correo electrónico  <br/> |Correo electrónico a destinatarios de dominios (para, CC y CCO).  <br/> |Sí  <br/> |Sí  <br/> |
|Email_date_received  <br/> |Correo electrónico  <br/> |Fecha en que se recibió el correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_action  <br/> |Correo electrónico  <br/> |Valores: Según el asunto de correo electrónico: "Hacia adelante" (para "Rv:"), "Reply" (para "RE:") o "Other" (otro texto del asunto).  <br/> |Sí  <br/> |Sí  <br/> |
|Meeting_Start_Date y hora  <br/> ||La fecha y la hora en que se inició un elemento de reunión.  <br/> |Sí  <br/> |Sí  <br/> |
|Meeting_End_Date y hora  <br/> ||La fecha y hora en que finalizó un elemento de reunión.  <br/> |Sí  <br/> |Sí  <br/> |
|File_relevance_score  <br/> |Relevancia  <br/> |La relevancia de puntuación (0-100). Por cada problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Family_relevance_score  <br/> |Relevancia  <br/> |Familia de Max la relevancia de puntuación (0-100). Por cada problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Relevance_tag  <br/> |Relevancia  <br/> |Etiquetado del archivo, si el archivo se ha etiquetado manualmente en la relevancia. Por cada problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Relevance_load_group  <br/> |Relevancia  <br/> |Grupo de carga de la relevancia del archivo especificado, con un campo por el problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Normalized_relevance_score  <br/> |Relevancia  <br/> |La relevancia normalizada puntuación (0-100), que es comparable entre problemas y cargas.  <br/> |Sí  <br/> |Sí  <br/> |
|Marked_as_seed  <br/> |Relevancia  <br/> |Etiquetado del archivo, si se ha definido como un archivo de inicialización de la relevancia por/categoría del problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Etiquetado de Marked_as_pre  <br/> |Relevancia  <br/> |Etiquetado del archivo, si era establecer como con previa a la etiqueta en la relevancia por/categoría del problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Relevance_status_description  <br/> |Relevancia  <br/> |Descripción del estado de la relevancia.  <br/> |Sí  <br/> |Sí  <br/> |
|Comentario  <br/> |General  <br/> |Comentario escrito por el usuario.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_input_path  <br/> |Proceso  <br/> |Ruta de exportación de entrada.  <br/> |Sí  <br/> |Sí  <br/> |
|Pivot_ID  <br/> |NEAR duplicados  <br/> |Identificador de tabla dinámica del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Family_size  <br/> |Proceso  <br/> |Número de archivos en una familia.  <br/> |Sí  <br/> |Sí  <br/> |
|Tipo_nativo  <br/> |Proceso  <br/> |Tipo de archivo nativo. Por ejemplo, hoja de cálculo o una presentación.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_MD5  <br/> |Proceso  <br/> |Valor de hash MD5 del archivo nativo.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_size  <br/> |Proceso  <br/> |Tamaño de archivo nativo.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_extension  <br/> |Proceso  <br/> |Extensión de archivo nativo.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_date_modified  <br/> |Propiedades de documento  <br/> |Fecha de archivo nativo se ha modificado, tomado de los metadatos del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_date_created  <br/> |Propiedades de documento  <br/> |Se creó el archivo nativo de fecha, efectuado desde los metadatos del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_modified_by  <br/> |Propiedades de documento  <br/> |Usuario que modificó el archivo nativo, tomado de los metadatos del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|O365_date_modified  <br/> |Propiedades de documento  <br/> |Se modificó el archivo nativo de fecha, tomado de los campos de SharePoint o Exchange.  <br/> |Sí  <br/> |Sí  <br/> |
|O365_date_created  <br/> |Propiedades de documento  <br/> |Se creó el archivo nativo de fecha, tomado de los campos de SharePoint o Exchange.  <br/> |Sí  <br/> |Sí  <br/> |
|O365_modified_by  <br/> |Propiedades de documento  <br/> |Último usuario que modificó el archivo nativo, tomado de los campos de SharePoint o Exchange.  <br/> |Sí  <br/> |Sí  <br/> |
|Compound_path  <br/> |Proceso  <br/> |Ruta de acceso de archivo nativo, incluido su origen compuesto.  <br/> |Sí  <br/> |Sí  <br/> |
|Input_path  <br/> |Proceso  <br/> |Ruta de acceso del archivo de entrada.  <br/> |Sí  <br/> |Sí  <br/> |
|Input_date_modified  <br/> |Proceso  <br/> |Archivo de entrada de fecha se modificó por última vez.  <br/> |Sí  <br/> |Sí  <br/> |
|ND_ET_sort_excl_attach  <br/> |Analizar  <br/> |Establezca la concatenación de correo electrónico y ND para su revisión. Tenía ' se agrega como prefijo a conjuntos de ND y 'E' se agrega a ssets de correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|ND_ET_sort_incl_attach  <br/> |Analizar  <br/> |Establece concatenación de correo electrónico y ND establecer para su revisión sería ' se agrega como prefijo a conjuntos de ND y 'E' se agrega a los conjuntos de correo electrónico. Además, cada correo electrónico dentro de un Email_set va seguido de sus datos adjuntos adecuados.  <br/> |Sí  <br/> |Sí  <br/> |
|Deduped_custodians  <br/> |General  <br/> |Custodia de archivos desaprovisionamiento duped  <br/> |Sí  <br/> |Sí  <br/> |
|Deduped_file_IDs  <br/> |General  <br/> |Identificadores de archivos desaprovisionamiento duped  <br/> |Sí  <br/> |Sí  <br/> |
|Deduped_paths  <br/> |General  <br/> |Rutas de acceso de archivos desaprovisionamiento duped  <br/> |Sí  <br/> |Sí  <br/> |
|File_key  <br/> |General  <br/> |Identificador interno para un uso futuro.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_native_path  <br/> |Proceso  <br/> |Ruta de acceso del archivo nativo en el paquete de exportación.  <br/> |Sí  <br/> |Sí  <br/> |
|Extracted_text_path  <br/> |Proceso  <br/> |Ruta de acceso de los archivos extraídos.  <br/> |Sí  <br/> |Sí  <br/> |
|Process_batch  <br/> |Proceso  <br/> |Identificador de lote para el lote de importación.  <br/> |Sí  <br/> |Sí  <br/> |
|Process_status_ID  <br/> |Proceso  <br/> |Identificador que representa el estado de fase de proceso.  <br/> |Sí  <br/> |Sí  <br/> |
|Process_status_description  <br/> |Proceso  <br/> |Descripción del estado de etapa del proceso: correcta o la descripción del error.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_status_ID  <br/> |Proceso  <br/> |Identificador del estado de exportación.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_status_description  <br/> |Proceso  <br/> |Descripción del estado de exportación; correcta o la descripción del error.  <br/> |Sí  <br/> |Sí  <br/> |
|Read_percent  <br/> |Relevancia  <br/> |% De lectura (0-100). Por cada problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_author  <br/> |Propiedades de documento  <br/> |Propiedades del documento: autor.  <br/> |No  <br/> |Sí  <br/> |
|Doc_comments  <br/> |Propiedades de documento  <br/> |Propiedades del documento: comentarios.  <br/> |No  <br/> |Sí  <br/> |
|Doc_keywords  <br/> |Propiedades de documento  <br/> |Propiedades del documento: palabras clave.  <br/> |No  <br/> |Sí  <br/> |
|Doc_last_saved_by  <br/> |Propiedades de documento  <br/> |Propiedades del documento: guardado por.  <br/> |No  <br/> |Sí  <br/> |
|Doc_revision  <br/> |Propiedades de documento  <br/> |Propiedades del documento: número de revisión.  <br/> |No  <br/> |Sí  <br/> |
|Doc_subject  <br/> |Propiedades de documento  <br/> |Propiedades del documento: asunto.  <br/> |No  <br/> |Sí  <br/> |
|Doc_template  <br/> |Propiedades de documento  <br/> |Propiedades del documento: plantilla.  <br/> |No  <br/> |Sí  <br/> |
|Doc_title  <br/> |Propiedades de documento  <br/> |Propiedades del documento: título.  <br/> |No  <br/> |Sí  <br/> |
|Email_has_attachment  <br/> |Correo electrónico  <br/> |Indica si el correo electrónico tiene uno o más datos adjuntos.  <br/> |No  <br/> |Sí  <br/> |
|Email_importance  <br/> |Correo electrónico  <br/> |Propiedad de importancia de correo electrónico.  <br/> |No  <br/> |Sí  <br/> |
|Email_level  <br/> |Correo electrónico  <br/> |Indica el nivel del correo electrónico dentro del subproceso de correo electrónico. Los datos adjuntos, el valor del correo electrónico adjunto.  <br/> |No  <br/> |Sí  <br/> |
|Email_recipients  <br/> |Correo electrónico  <br/> |Los destinatarios de correo electrónico nombre o direcciones (para, CC y CCO).  <br/> |No  <br/> |Sí  <br/> |
|Email_security  <br/> |Correo electrónico  <br/> |Propiedad de seguridad de correo electrónico.  <br/> |No  <br/> |Sí  <br/> |
|Email_sensitivity  <br/> |Correo electrónico  <br/> |Propiedad sensitivity de correo electrónico.  <br/> |No  <br/> |Sí  <br/> |
|Export_batch  <br/> |Proceso  <br/> |Nombre de lote de exportación última del archivo.  <br/> |No  <br/> |Sí  <br/> |
|Export_session  <br/> |Proceso  <br/> |Última sesión de exportación del archivo incluido el identificador de fecha.  <br/> |No  <br/> |Sí  <br/> |
|Extracted_text_length  <br/> |Proceso  <br/> |Longitud de caracteres del archivo de texto Extracted.  <br/> |No  <br/> |Sí  <br/> |
|Family_duplicate_set  <br/> |Proceso  <br/> |Identificador numérico para familias que son duplicados de texto exacta de cada uno de los otros (respectivamente - todos los miembros de las familias sean duplicados exactos).  <br/> |No  <br/> |Sí  <br/> |
|Has_Text  <br/> |Proceso  <br/> |Indica si hay un texto en el archivo: 0 - ninguna; 1 - sí.  <br/> |No  <br/> |Sí  <br/> |
|Input_file_ID  <br/> |Proceso  <br/> |Identificador del archivo de entrada desde la que se extrajeron los archivos de.  <br/> |No  <br/> |Sí  <br/> |
|Native_SHA_256  <br/> |Proceso  <br/> |Valor hash SHA-256 del archivo nativo.  <br/> |No  <br/> |Sí  <br/> |
|O365_authors  <br/> |Propiedades de documento  <br/> |Usuarios que modificó el archivo nativo, tomado de los campos de SharePoint o Exchange.  <br/> |No  <br/> |Sí  <br/> |
|O365_created_by  <br/> |Propiedades de documento  <br/> |Usuario que creó el archivo nativo, tomado de los campos de SharePoint o Exchange.  <br/> |No  <br/> |Sí  <br/> |
|Parent_node  <br/> |Correo electrónico  <br/> |Relaciona un nodo en un subproceso de correo electrónico para el nodo primario más cercano que no es un enlace que falta.  <br/> |No  <br/> |Sí  <br/> |
|Set_order_inclusives_first  <br/> |Correo electrónico  <br/> |Mensajes de correo electrónico y los datos adjuntos: orden cronológico de contador (Inclusives primera). Documentos: gira primero y el resto por la puntuación de similitud, descendente.  <br/> |No  <br/> |Sí  <br/> |
|Tagged_By  <br/> |Relevancia  <br/> |Usuario que con etiqueta el archivo en la relevancia para el problema específico.  <br/> |No  <br/> |Sí  <br/> |
|Word_count  <br/> |Analizar  <br/> |Número de palabras del documento.  <br/> |No  <br/> |Sí  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>Temas relacionados

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Exportar datos de mayúsculas y minúsculas con avanzadas exhibición de documentos electrónicos](export-case-data-in-advanced-ediscovery.md)
  
[Exportar resultados](export-results-in-advanced-ediscovery.md)
  
[Visualización del historial de proceso por lotes y exportar más allá de los resultados](view-batch-history-and-export-past-results.md)
  


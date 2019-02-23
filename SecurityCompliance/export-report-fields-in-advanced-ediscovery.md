---
title: Exportar campos de resultados en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: Describe todos los campos que se incluyen en la exportación de informes para eDiscovery avanzada.
ms.openlocfilehash: a910fa94a1361e48099ef5792ce93d5934fdccc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216660"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>Exportar campos de resultados en eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
En este tema se describen los campos de informe de importación de exhibición de documentos electrónicos avanzado para las plantillas estándar y todas.
  
## <a name="export-report-fields"></a>Exportar campos de informes

En la tabla siguiente se enumeran los campos de cada plantilla de exportación.
  
|**Exportar nombre de campo**|**Grupo**|**Descripción**|**Disponible en plantilla estándar**|**Disponible en todas las plantillas**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |General  <br/> |Número de fila.  <br/> |Sí  <br/> |Sí  <br/> |
|File_ID  <br/> |General  <br/> |IDENTIFICADOR de archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|File_class  <br/> |Proceso  <br/> |Clase File.  <br/> |Sí  <br/> |Sí  <br/> |
|Family_ID  <br/> |Proceso  <br/> |Identificador numérico que se usa para agrupar archivos (por lo general, instancia de correo electrónico y sus datos adjuntos).  <br/> |Sí  <br/> |Sí  <br/> |
|For_review  <br/> |Proceso  <br/> |Marca para indicar que el campo se incluirá en la exportación para revisión.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_file_name  <br/> |Proceso  <br/> |Nombre de archivo nativo, sin referencia a la carpeta y la extensión.  <br/> |Sí  <br/> |Sí  <br/> |
|Administradores  <br/> |General  <br/> |Custodio del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Set_ID  <br/> |Analizar  <br/> |Identificador "ND set" o "email set".  <br/> |Sí  <br/> |Sí  <br/> |
|Inclusive_type  <br/> |Correo electrónico  <br/> |Indica si el archivo es inclusivo, de acuerdo con los siguientes valores: 0-no inclusive, 1-inclusivo, 2-inclusivo menos, 3-copia inclusiva.  <br/> |Sí  <br/> |Sí  <br/> |
|Marked_as_pivot  <br/> |Duplicados Near  <br/> |Indica si el archivo es un pivote.  <br/> |Sí  <br/> |Sí  <br/> |
|Similarity_percent  <br/> |Duplicados Near  <br/> |Porcentaje de similitud con respecto al pivote.  <br/> |Sí  <br/> |Sí  <br/> |
|Duplicate_subset  <br/> |Duplicados Near  <br/> |Identificador único del subconjunto duplicado. Indica si el archivo tiene duplicados de texto exactos.  <br/> |Sí  <br/> |Sí  <br/> |
|Fecha  <br/> |General  <br/> |Fecha del archivo (según el tipo de archivo-correo electrónico: fecha de envío; documento: fecha de modificación).  <br/> |Sí  <br/> |Sí  <br/> |
|Dominant_theme  <br/> |Analizar  <br/> |Tema principal del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Themes_list  <br/> |Temas  <br/> |Lista de nombres de temas.  <br/> |Sí  <br/> |Sí  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Identificador numérico único de un conjunto de Nearduplicate.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_set  <br/> |Correo electrónico  <br/> |Identificador numérico único de un conjunto de correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_thread  <br/> |Correo electrónico  <br/> |Describe la posición del correo electrónico dentro del conjunto de correo electrónico consta de todos los identificadores de nodo de la raíz al correo electrónico actual, separados por puntos.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_subject  <br/> |Correo electrónico  <br/> |Asunto del correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_date_sent  <br/> |Correo electrónico  <br/> |Fecha en la que se envió el correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_participants  <br/> |Correo electrónico  <br/> |Direcciones de correo electrónico de todos los participantes en una conversación de correo electrónico, incluidos los vínculos que faltan.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_participant_domains  <br/> |Correo electrónico  <br/> |Dominios de todos los participantes en una conversación de correo electrónico, incluido el vínculo que falta.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_sender  <br/> |Correo electrónico  <br/> |Nombre o dirección del remitente de correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_sender_domain  <br/> |Correo electrónico  <br/> |Dominio del remitente de correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_to  <br/> |Correo electrónico  <br/> |Para destinatarios del correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_cc  <br/> |Correo electrónico  <br/> |Destinatario CC del correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_bcc  <br/> |Correo electrónico  <br/> |Destinatario CCO del correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_recipient_domains  <br/> |Correo electrónico  <br/> |Dominios de destinatarios de correo electrónico (para, CC y CCO).  <br/> |Sí  <br/> |Sí  <br/> |
|Email_date_received  <br/> |Correo electrónico  <br/> |Fecha en la que se recibió el correo electrónico.  <br/> |Sí  <br/> |Sí  <br/> |
|Email_action  <br/> |Correo electrónico  <br/> |Values: según el asunto del correo electrónico: "forward" (para "FW:"), "Reply" (para "RE:") u "Other" (otro texto de asunto).  <br/> |Sí  <br/> |Sí  <br/> |
|Meeting_Start_Date/hora  <br/> ||Fecha y hora en que se inició un elemento de reunión.  <br/> |Sí  <br/> |Sí  <br/> |
|Meeting_End_Date/hora  <br/> ||Fecha y hora de finalización de un elemento de reunión.  <br/> |Sí  <br/> |Sí  <br/> |
|File_relevance_score  <br/> |Coordinación  <br/> |Puntuación de relevancia (0-100). Por problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Family_relevance_score  <br/> |Coordinación  <br/> |Puntuación de relevancia de familia máxima (0-100). Por problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Relevance_tag  <br/> |Coordinación  <br/> |Etiquetado del archivo, si el archivo se ha etiquetado manualmente en relevancia. Por problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Relevance_load_group  <br/> |Coordinación  <br/> |Grupo de carga de relevancia, del archivo especificado, con un campo por problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Normalized_relevance_score  <br/> |Coordinación  <br/> |Puntuación de relevancia normalizada (0-100), que es comparable entre problemas y cargas.  <br/> |Sí  <br/> |Sí  <br/> |
|Marked_as_seed  <br/> |Coordinación  <br/> |Etiquetado del archivo, si se estableció como un archivo de inicialización en relevancia por problema o categoría.  <br/> |Sí  <br/> |Sí  <br/> |
|Marked_as_pre-etiquetada  <br/> |Coordinación  <br/> |Etiquetado del archivo, si se estableció con una etiqueta predefinida en la relevancia por problema/categoría.  <br/> |Sí  <br/> |Sí  <br/> |
|Relevance_status_description  <br/> |Coordinación  <br/> |Descripción del estado de relevancia.  <br/> |Sí  <br/> |Sí  <br/> |
|Comentario  <br/> |General  <br/> |Comentario escrito por el usuario.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_input_path  <br/> |Proceso  <br/> |Exportar ruta de acceso de entrada.  <br/> |Sí  <br/> |Sí  <br/> |
|Pivot_ID  <br/> |Duplicados Near  <br/> |IDENTIFICADOR de tabla dinámica del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Family_size  <br/> |Proceso  <br/> |Número de archivos en una familia.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_type  <br/> |Proceso  <br/> |Tipo de archivo nativo. Por ejemplo, hoja de cálculo o presentación.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_MD5  <br/> |Proceso  <br/> |Valor hash MD5 del archivo nativo.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_size  <br/> |Proceso  <br/> |Tamaño de archivo nativo.  <br/> |Sí  <br/> |Sí  <br/> |
|Native_extension  <br/> |Proceso  <br/> |Extensión de archivo nativa.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_date_modified  <br/> |Propiedades del documento  <br/> |Fecha en que se modificó el archivo nativo, tomado de los metadatos del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_date_created  <br/> |Propiedades del documento  <br/> |Fecha en que se creó el archivo nativo, tomado de los metadatos del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_modified_by  <br/> |Propiedades del documento  <br/> |Usuario que modificó el archivo nativo, tomado de los metadatos del archivo.  <br/> |Sí  <br/> |Sí  <br/> |
|O365_date_modified  <br/> |Propiedades del documento  <br/> |Fecha en que se modificó el archivo nativo, tomado de los campos de SharePoint o Exchange.  <br/> |Sí  <br/> |Sí  <br/> |
|O365_date_created  <br/> |Propiedades del documento  <br/> |Fecha en que se creó el archivo nativo, tomado de los campos de SharePoint o de Exchange.  <br/> |Sí  <br/> |Sí  <br/> |
|O365_modified_by  <br/> |Propiedades del documento  <br/> |Usuario que modificó por última vez el archivo nativo, tomado de los campos de SharePoint o Exchange.  <br/> |Sí  <br/> |Sí  <br/> |
|Compound_path  <br/> |Proceso  <br/> |Ruta de acceso al archivo nativo, incluido su origen compuesto.  <br/> |Sí  <br/> |Sí  <br/> |
|Input_path  <br/> |Proceso  <br/> |Ruta de acceso del archivo de entrada.  <br/> |Sí  <br/> |Sí  <br/> |
|Input_date_modified  <br/> |Proceso  <br/> |Fecha en que se modificó el archivo de entrada por última vez.  <br/> |Sí  <br/> |Sí  <br/> |
|ND_ET_sort_excl_attach  <br/> |Analizar  <br/> |Concatenación de los conjuntos de correo electrónico y ND configurados para revisión. "D" se agrega como prefijo a los conjuntos de ND y "E" se agrega a email ssets.  <br/> |Sí  <br/> |Sí  <br/> |
|ND_ET_sort_incl_attach  <br/> |Analizar  <br/> |La concatenación de un conjunto de correo electrónico y el de ND para revisión se agregan como prefijo a los conjuntos de ND y se agrega ' E ' a los conjuntos de correo electrónico. Además, cada correo electrónico de un Email_set va seguido de los datos adjuntos correspondientes.  <br/> |Sí  <br/> |Sí  <br/> |
|Deduped_custodians  <br/> |General  <br/> |Custodios de archivos de desduplicación  <br/> |Sí  <br/> |Sí  <br/> |
|Deduped_file_IDs  <br/> |General  <br/> |Identificadores de archivos de desduplicación  <br/> |Sí  <br/> |Sí  <br/> |
|Deduped_paths  <br/> |General  <br/> |Rutas de archivos de desduplicación  <br/> |Sí  <br/> |Sí  <br/> |
|File_key  <br/> |General  <br/> |Identificador interno para uso futuro.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_native_path  <br/> |Proceso  <br/> |Ruta de acceso al archivo nativo en el paquete de exportación.  <br/> |Sí  <br/> |Sí  <br/> |
|Extracted_text_path  <br/> |Proceso  <br/> |Ruta de acceso del archivo extraído.  <br/> |Sí  <br/> |Sí  <br/> |
|Process_batch  <br/> |Proceso  <br/> |Identificador de lote del lote de importación.  <br/> |Sí  <br/> |Sí  <br/> |
|Process_status_ID  <br/> |Proceso  <br/> |Identificador que representa el estado de fase de proceso.  <br/> |Sí  <br/> |Sí  <br/> |
|Process_status_description  <br/> |Proceso  <br/> |Descripción del estado de fase de proceso: descripción correcta o error.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_status_ID  <br/> |Proceso  <br/> |IDENTIFICADOR del estado de exportación.  <br/> |Sí  <br/> |Sí  <br/> |
|Export_status_description  <br/> |Proceso  <br/> |Descripción del estado de exportación; Descripción de éxito o error.  <br/> |Sí  <br/> |Sí  <br/> |
|Read_percent  <br/> |Coordinación  <br/> |% De lectura (0-100). Por problema.  <br/> |Sí  <br/> |Sí  <br/> |
|Doc_author  <br/> |Propiedades del documento  <br/> |Propiedades del documento: autor.  <br/> |No  <br/> |Sí  <br/> |
|Doc_comments  <br/> |Propiedades del documento  <br/> |Propiedades del documento: Comentarios.  <br/> |No  <br/> |Sí  <br/> |
|Doc_keywords  <br/> |Propiedades del documento  <br/> |Propiedades del documento: Palabras clave.  <br/> |No  <br/> |Sí  <br/> |
|Doc_last_saved_by  <br/> |Propiedades del documento  <br/> |Propiedades del documento: última guardado por.  <br/> |No  <br/> |Sí  <br/> |
|Doc_revision  <br/> |Propiedades del documento  <br/> |Propiedades del documento: número de revisión.  <br/> |No  <br/> |Sí  <br/> |
|Doc_subject  <br/> |Propiedades del documento  <br/> |Propiedades del documento: asunto.  <br/> |No  <br/> |Sí  <br/> |
|Doc_template  <br/> |Propiedades del documento  <br/> |Propiedades del documento: plantilla.  <br/> |No  <br/> |Sí  <br/> |
|Doc_title  <br/> |Propiedades del documento  <br/> |Propiedades del documento: título.  <br/> |No  <br/> |Sí  <br/> |
|Email_has_attachment  <br/> |Correo electrónico  <br/> |Indica si el correo electrónico tiene uno o más datos adjuntos.  <br/> |No  <br/> |Sí  <br/> |
|Email_importance  <br/> |Correo electrónico  <br/> |Propiedad importance de correo electrónico.  <br/> |No  <br/> |Sí  <br/> |
|Email_level  <br/> |Correo electrónico  <br/> |Indica el nivel de correo electrónico dentro del hilo de correo electrónico. Para datos adjuntos, el valor del correo electrónico adjunto.  <br/> |No  <br/> |Sí  <br/> |
|Email_recipients  <br/> |Correo electrónico  <br/> |Nombre y/o direcciones de los destinatarios de correo electrónico (para, CC y CCO).  <br/> |No  <br/> |Sí  <br/> |
|Email_security  <br/> |Correo electrónico  <br/> |Propiedad de seguridad del correo electrónico.  <br/> |No  <br/> |Sí  <br/> |
|Email_sensitivity  <br/> |Correo electrónico  <br/> |Propiedad Sensitivity email.  <br/> |No  <br/> |Sí  <br/> |
|Export_batch  <br/> |Proceso  <br/> |Último nombre del lote de exportación del archivo.  <br/> |No  <br/> |Sí  <br/> |
|Export_session  <br/> |Proceso  <br/> |Último identificador de sesión de exportación del archivo, incluida la fecha.  <br/> |No  <br/> |Sí  <br/> |
|Extracted_text_length  <br/> |Proceso  <br/> |Longitud de caracteres del archivo de texto exTraído.  <br/> |No  <br/> |Sí  <br/> |
|Family_duplicate_set  <br/> |Proceso  <br/> |Identificador numérico de las familias que son duplicados de texto exactos (respectivamente, todos los miembros de las familias son duplicados exactos).  <br/> |No  <br/> |Sí  <br/> |
|Has_Text  <br/> |Proceso  <br/> |Indica si hay un texto en el archivo: 0-no; 1: sí.  <br/> |No  <br/> |Sí  <br/> |
|Input_file_ID  <br/> |Proceso  <br/> |IDENTIFICADOR del archivo de entrada desde el que se ha extraído el archivo.  <br/> |No  <br/> |Sí  <br/> |
|Native_SHA_256  <br/> |Proceso  <br/> |El valor hash de SHA-256 del archivo nativo.  <br/> |No  <br/> |Sí  <br/> |
|O365_authors  <br/> |Propiedades del documento  <br/> |Usuarios que modificaron el archivo nativo, tomando como parte de los campos de SharePoint o Exchange.  <br/> |No  <br/> |Sí  <br/> |
|O365_created_by  <br/> |Propiedades del documento  <br/> |Usuario que ha creado un archivo nativo, tomado de los campos de SharePoint o de Exchange.  <br/> |No  <br/> |Sí  <br/> |
|Parent_node  <br/> |Correo electrónico  <br/> |Relaciona un nodo de un subproceso de correo electrónico con el nodo primario más cercano que no es un vínculo que falta.  <br/> |No  <br/> |Sí  <br/> |
|Set_order_inclusives_first  <br/> |Correo electrónico  <br/> |Mensajes de correo electrónico y datos adjuntos: contador orden cronológico (inclusive en primer lugar). Documentos: pivotes primero y resto por puntuación de similitud, descendente.  <br/> |No  <br/> |Sí  <br/> |
|Tagged_By  <br/> |Coordinación  <br/> |Usuario que etiquetó el archivo en relevancia para el problema específico.  <br/> |No  <br/> |Sí  <br/> |
|Word_count  <br/> |Analizar  <br/> |Número de palabras del documento.  <br/> |No  <br/> |Sí  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>Temas relacionados

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Exportación de datos de casos con eDiscovery avanzado](export-case-data-in-advanced-ediscovery.md)
  
[Exportar resultados](export-results-in-advanced-ediscovery.md)
  
[Ver el historial del lote y exportar los resultados anteriores](view-batch-history-and-export-past-results.md)
  


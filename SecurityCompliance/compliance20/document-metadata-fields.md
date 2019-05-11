---
title: Campos de metadatos del documento en eDiscovery avanzado
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e45400726537a3b1ebadcc3d828d9cb8110e2100
ms.sourcegitcommit: 09fd88272187f82b6e635af83edabea08c2cc49c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884758"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadatos del documento en eDiscovery avanzado

En la siguiente tabla se enumeran los campos de metadatos de los documentos en un conjunto de revisión en un caso en eDiscovery avanzado. La tabla indica el nombre del campo de metadatos, si el campo se puede buscar al ejecutar una consulta en un conjunto de revisiones, si el campo está presente cuando se ven los metadatos de un documento seleccionado en un conjunto de revisiones y si el campo se incluye cuando documentos a re exportó.

| Nombre del campo | Nombre de campo de búsqueda | Nombre del campo exportado | Mostrar nombre de campo | Descripción |
| :- |  :- |  :- |  :- |  :- |
| Identificador de contenido de datos adjuntos | AttachmentContentId |  | Identificador de contenido de datos adjuntos | Identificador de contenido de datos adjuntos del elemento. |
| Nombres de datos adjuntos | AttachmentNames | Attachment_Names | Nombres de datos adjuntos | Lista de nombres de datos adjuntos. |
| Puntuación de privilegios de cliente abogado | AttorneyClientPrivilegeScore |  | Puntuación de privilegios de cliente abogado | Abogado-puntuación del contenido del modelo de privilegio de cliente. |
| Autor | Autor | Doc_authors | Autor | Autor de los metadatos del documento. |
| BCC | Bcc | Email_bcc | BCC | Campo Cco para para tipos de mensaje.  Format es **displayName \<SMTPAddress>**. |
| CC | Cc | Email_cc | CC | Campo CC para para tipos de mensaje.  Format es **displayName \<SMTPAddress>**. |
| Etiquetas de cumplimiento | ComplianceLabels | Compliance_labels | Etiquetas de cumplimiento | Etiquetas de cumplimiento aplicadas en Office 365. |
| Ruta de acceso compuesta | CompoundPath | Compound_path | Ruta de acceso compuesta | Ruta de acceso legible que describe el origen del elemento. |
| Contenido | Contenido |  |  | Texto extraído del elemento. |
| Cuerpo de la conversación | Cuerpo de la conversación |  | Cuerpo de la conversación | Cuerpo de la conversación del elemento. |
| Tema de conversación | Tema de conversación |  | Tema de conversación | Tema de conversación del elemento. |
| IDENTIFICADOR de conversación | ConversationId | Conversation_ID | IDENTIFICADOR de conversación | Identificador de la conversación del mensaje. |
| Índice de conversaciones |  | Conversation_index | Índice de conversaciones | Índice de la conversación del mensaje. |
| Tiempo de PDF de conversación | ConversationPdfTime |  | Tiempo de PDF de conversación | Fecha en que se creó la versión PDF de la conversación. |
| Tiempo de grabación de redacción de conversación | ConversationRedactionBurnTime |  | Tiempo de grabación de redacción de conversación | Fecha en que se creó la versión PDF de la conversación para el chat. |
| Fecha de documento creada | CreatedTime | Doc_date_created | Fecha de documento creada | Crear fecha a partir de los metadatos del documento. |
| Custodian | Custodian | Custodian | Custodian | Nombre del custodio al que estaba asociado el elemento. |
| Fecha | Fecha | Fecha | Fecha | Fecha es un campo calculado que depende del tipo de archivo.<br />**Correo electrónico**: fecha de envío<br />**Datos adjuntos de correo electrónico**: fecha de la última modificación del documento, si no está disponible, fecha de envío del elemento primario<br />**Documentos incrustados**: fecha de la última modificación del documento, si no está disponible, de la fecha de la última modificación del elemento principal.<br />**Documentos de SpO (incluye datos adjuntos modernos)**: fecha de última modificación de SharePoint, si no está disponible, la fecha de última modificación de los documentos<br />**Documentos que no son de Office**: fecha de la última modificación<br />**Reuniones**: fecha de inicio de la reunión<br />**Correo de voz**: fecha de envío<br />**Mi**: fecha de envío. |
| Otras rutas de | Dedupedcompoundpath | Deduped_compound_path | Otras rutas de | Lista de rutas de datos compuestas de documentos que son duplicados exactos (correo electrónico: basado en contenido, documentos: basado en hash). |
| Otros custodios | DedupedCustodians | Deduped_custodians | Otros custodios | Lista de custodios de documentos que son duplicados exactos (para correo electrónico: basado en el contenido; para documentos: basado en hash). |
| Otros identificadores de archivo | DedupedFileIds | Deduped_file_IDs | Otros identificadores de archivo | Lista de identificadores de archivo de los documentos que son duplicados exactos (para correo electrónico: basado en el contenido; para documentos: basado en hash). |
| Comentarios del documento | DocComments | Doc_comments | Comentarios del documento | Comentarios de los metadatos del documento. |
| Empresa de documentos |  | Doc_company | Empresa de documentos | Compañía de los metadatos del documento. |
| DocIndex |  |  |  | Índice de la familia. -1 o 0 significa que es la raíz. |
| Palabras clave de documento |  | Doc_keywords | Palabras clave de documento | Palabras clave de los metadatos del documento. |
| Documento modificado por |  | Doc_modified_by | Documento modificado por | Fecha de la última modificación de los metadatos del documento. |
| Revisión del documento |  | Doc_revision | Revisión del documento | Revisión a partir de los metadatos del documento. |
| Asunto del documento |  | Doc_subject | Asunto del documento | Asunto de los metadatos del documento. |
| Plantilla de documento |  | Doc_template | Plantilla de documento | Plantilla de los metadatos del documento. |
| Tema dominante | DominantTheme | Dominant_theme | Tema dominante | Tema dominante como se calcula para el análisis. |
| Subconjunto duplicado |  | Duplicate_subset | Subconjunto duplicado | IDENTIFICADOR de grupo para los duplicados exactos. |
| EmailAction |  | Email_action |  | Ninguno, responder, reenviar en función de la línea de asunto de un mensaje. |
| Confirmación de entrega de correo electrónico |  | Email_delivery_receipt | Confirmación de entrega de correo electrónico | Dirección de correo electrónico suministrada en encabezados de Internet para la confirmación de entrega. |
| Importancia | EmailImportance | Email_importance | Importancia | Importancia del mensaje: **0**: bajo; **1**: normal; **2**: alta |
| EmailLevel |  | Email_level |  | Indica el nivel de un mensaje dentro del subproceso de correo al que pertenece; los datos adjuntos heredan el valor del mensaje principal. |
| Identificador del mensaje de correo electrónico |  | Email_message_ID | Identificador del mensaje de correo electrónico | Identificador del mensaje de Internet del mensaje. |
| EmailReadReceipt |  | Email_read_receipt |  | Dirección de correo electrónico suministrada en encabezados de Internet para la confirmación de lectura. |
| Seguridad del correo electrónico | EmailSecurity | Email_security | Seguridad del correo electrónico | Configuración de seguridad del mensaje: **0**: ninguno; **1**: firmado; **2**: cifrado; **3**: cifrado y firmado. |
| Confidencialidad del correo electrónico | EmailSensitivity | email_sensitivity | Confidencialidad del correo electrónico | Configuración de sensibilidad del mensaje: **0**: ninguno; **1**: personal; **2**: privado; **3**: CompanyConfidential. |
| Conjunto de correo electrónico | EmailSet | Email_set | Conjunto de correo electrónico | IDENTIFICADOR de grupo para todos los mensajes en el mismo conjunto de correo electrónico. |
| EmailThread |  | Email_thread |  | Posición del mensaje dentro del conjunto de correo electrónico; consta de todos los identificadores de nodo de la raíz al mensaje actual, separados por puntos. |
| Tipo de contenido extraído |  | Extracted_content_type | Tipo de contenido extraído | Tipo de contenido extraído, en forma de tipo MIME; por ejemplo, image/JPEG. |
| ExtractedTextLength |  | Extracted_text_length |  | Número de caracteres en el texto extraído. |
| Puntuación de la relevancia de familia problema de caso 1 |  | Family_relevance_score_case_issue_1 |  | Puntuación de relevancia de familia el problema 1 de la relevancia. |
| FamilyDuplicateSet |  | Family_duplicate_set |  | Identificador numérico de las familias que son duplicados exactos entre sí (el mismo contenido y todos los mismos datos adjuntos). |
| IDENTIFICADOR de familia | FamilyId | Family_ID | IDENTIFICADOR de familia | ID de familia agrupa todos los elementos; para el correo electrónico, incluye el mensaje y todos los datos adjuntos; en el caso de los documentos, incluye el documento y los elementos incrustados. |
| Tamaño de la familia |  | Family_size | Tamaño de la familia | Número de documentos de la familia. |
| Número de caso 1 de puntuación de relevancia de archivo |  | File_relevance_score_case_issue_1 |  | Puntuación de relevancia de archivo caso del problema 1 de la relevancia. |
| Clase File | FileClass | File_class | Clase File | Para contenido de SharePoint y OneDrive: **documento**; para contenido de Exchange: **correo electrónico**o **datos**adjuntos. |
| IDENTIFICADOR de archivo | FileId | File_ID | IDENTIFICADOR de archivo | Identificador del documento único en el caso.|
| Fecha de creación del sistema de archivos |  | File_system_date_created | Fecha de creación del sistema de archivos | Fecha de creación desde el sistema de archivos (solo se aplica a los datos que no son de Office 365). |
| Fecha del sistema de archivos modificada |  | File_system_date_modified | Fecha del sistema de archivos modificada | Fecha de modificación del sistema de archivos (solo se aplica a los datos que no son de Office 365). |
| Tipo de archivo | FileType |  | Tipo de archivo | Tipo de archivo del elemento, en función de la extensión del archivo. |
| Tiene datos adjuntos | HasAttachment | Email_has_attachment | Tiene datos adjuntos | Indica si el mensaje tiene o no datos adjuntos. |
| Tiene abogado | HasAttorney |  | Tiene abogado | True cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es false. |
| HasText |  | Has_text |  | Indica si el elemento tiene texto, los valores posibles son true y false. |
| IDENTIFICADOR inmutable | ImmutableId | Immutable_ID | IDENTIFICADOR inmutable | Identificador inmutable tal y como se almacena en Office 365. |
| Tipo inclusivo | InclusiveType | Inclusive_type | Tipo inclusivo | Tipo inclusivo calculado para análisis: **0** -no inclusivo; **1** -ambos inclusive; **2** -inclusive menos; **3** -copia inclusiva. |
| En responder a ID. |  | In_reply_to_ID | En responder a ID. | En responder al identificador del mensaje. |
| Es representativo | IsRepresentative | Is_representative | Es representativo | Un documento de cada conjunto de duplicados exactos se marca como representativo. |
| Clase Item | ItemClass | Item_class | Clase Item | Clase de elemento proporcionada por Exchange Server; por ejemplo, **IPM. Nota:** |
| Última modificación | LastModifiedDate | Doc_date_modified | Última modificación | Fecha de última modificación de los metadatos del documento. |
| IDENTIFICADOR de carga | LoadId | Load_ID | IDENTIFICADOR de carga | Identificador de carga, en el que el elemento se cargó en un conjunto de revisión. |
| Ubicación | Ubicación | Ubicación | Ubicación | Cadena que indica el tipo de ubicación de origen de los documentos;<br />Datos importados que no son de O365 ><br />Teams: > Teams<br />EXO-> Exchange<br />SPO-> SharePoint<br />OneDrive para la empresa: > OneDrive |
| Nombre de la ubicación | LocationName | Location_name | Nombre de la ubicación | Cadena que identifica el origen del elemento.  Para Exchange, será la dirección SMTP del buzón.  Para SharePoint y OneDrive, la dirección URL de la colección de sitios. |
| Marcado como representativo | MarkAsRepresentative |  | Marcado como representativo | Un documento de cada conjunto de duplicados exactos está marcado como representantes. |
| Marcado como tipo de caso con etiqueta previa 1 |  | Marked_as_pre_tagged_Case_issue_1 |  | Marcado como un problema de caso predefinido 1 de la relevancia. |
| Marcado como caso de inicialización, problema 1 |  | Marked_as_seed_Case_issue_1 |  | Marcado como el problema del caso de inicialización 1 de la relevancia. |
| Fecha de finalización de la reunión | MeetingEndDate | Meeting_end_date | Fecha de finalización de la reunión | Fecha de finalización de la reunión para las reuniones. |
| Fecha de inicio de la reunión | MeetingStartDate | Meeting_start_date | Fecha de inicio de la reunión | Fecha de inicio de la reunión para las reuniones. |
| Tipo de mensaje | MessageKind | Message_kind | Tipo de mensaje | El tipo de mensaje que se va a buscar.<br />Valores posibles: <br />contactos <br />documentos <br />correo electrónico <br />externaldata <br />faxes <br />mensajería instantánea <br />diarios <br />reuniones <br />Microsoft Teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams) <br />notas <br />entradas <br />fuentes rss <br />tareas <br />correo de voz |
| Extensión nativa | NativeExtension | Native_extension | Extensión nativa | Extensión nativa del elemento. |
| Nombre de archivo nativo | NativeFileName | Native_file_name | Nombre de archivo nativo | Nombre de archivo nativo del elemento. |
| NativeMD5 |  | Native_MD5 |  | Hash MD5 de la secuencia de archivo. |
| Ordenación de ND: excluir datos adjuntos | NdEtSortExclAttach | ND_ET_sort_excl_attach | Ordenación de ND: excluir datos adjuntos | Concatenación de un conjunto de correo electrónico y un conjunto de ND para una ordenación eficaz en el momento de la revisión; D se agrega como prefijo a los conjuntos de ND y E se agrega a los conjuntos de correo electrónico. |
| Ordenación de ND: incluidos datos adjuntos | NdEtSortInclAttach | ND_ET_sort_incl_attach | Ordenación de ND: incluidos datos adjuntos | Concatenación de un conjunto de correo electrónico y un conjunto de ND para una ordenación eficaz en el momento de la revisión; D se agrega como prefijo a los conjuntos de ND y E se agrega a los conjuntos de correo electrónico. Cada correo electrónico de un conjunto de correo electrónico va seguido de los datos adjuntos correspondientes. |
| Número de caso 1 de puntuación de relevancia normalizada |  | Normalized_relevance_score_case_issue_1 |  | Problema de la puntuación del caso 1 de relevancia normalizada respecto a la relevancia. |
| Autores de O365 |  | O365_authors | Autores de O365 | Autor de SharePoint. |
| O365 creado por |  | O365_created_by | O365 creado por | Creado por desde SharePoint. |
| Fecha de creación de O365 |  | O365_date_created | Fecha de creación de O365 | Fecha de creación de SharePoint. |
| Fecha de modificación de O365 |  | O365_date_modified | Fecha de modificación de O365 | Fecha de última modificación de SharePoint. |
| O365 modificada por |  | O365_modified_by | O365 modificada por | Modificado por desde SharePoint. |
| IDENTIFICADOR primario | ParentId | Parent_ID | IDENTIFICADOR primario | Identificador del elemento primario del elemento. |
| ParentNode |  | Parent_node |  | El mensaje de correo electrónico anterior más cercano en el hilo de correo electrónico. |
| Ruta de acceso primaria | ParentPath | Parent_path | Ruta de acceso primaria | Ruta de acceso compuesta del elemento primario directo del elemento. |
| Dominios de participantes | ParticipantDomains | Email_participant_domains | Dominios de participantes | Lista de todos los dominios de participantes de un mensaje. |
| Participantes | Participantes | Email_participants | Participantes | Lista de todos los participantes de un mensaje; por ejemplo, Sender, to, CC o BCC. |
| IDENTIFICADOR dinámico | PivotId | Pivot_ID | IDENTIFICADOR dinámico | IDENTIFICADOR de una tabla dinámica. |
| Potencialmente privilegiado | PotentiallyPrivileged | Potentially_privileged | Potencialmente privilegiado | True si el modelo de detección de privilegios de cliente de abogado considera el documento potencialmente privilegiado |
| Estado de procesamiento | ProcessingStatus | Error_code | Estado de procesamiento | Estado de procesamiento después de que el elemento se haya agregado a un conjunto de revisión. |
| Número 1 del caso de lectura porcentual |  | Read_percent_Case_issue_1 |  | El caso de porcentaje de lectura del problema 1 de la relevancia. |
| Percentil de lectura | ReadPercentile |  | Percentil de lectura | El percentil de lectura del documento en función de la relevancia. |
| Número de destinatarios |  | Recipient_count | Número de destinatarios | Número de destinatarios del mensaje. |
| Dominios de destinatarios | RecipientDomains | Email_recipient_domains | Dominios de destinatarios | Lista de todos los dominios de los destinatarios de un mensaje. |
| Destinatarios | Destinatarios | Email_recipients | Destinatarios | Lista de todos los destinatarios de un mensaje (para, CC, CCO). |
| Problema del caso del grupo de carga de relevancia 1 |  | Relevance_load_group_case_issue_1 |  | Problema del caso de grupo de carga de relevancia 1 de la relevancia. |
| Problema de Descripción del caso de estado de relevancia 1 |  | Relevance_status_description_Case_issue_1 |  | Descripción del estado de relevancia caso del problema 1 de la relevancia. |
| Problema de caso de etiqueta de relevancia 1 |  | Relevance_tag_case_issue_1 |  | Caso de la etiqueta de relevancia el problema 1 de la relevancia. |
| Comentario de relevancia |  | Relevance_comment | Comentario de relevancia | Campo Comentario de la relevancia. |
| Puntuación de relevancia | RelevanceScore |  | Puntuación de relevancia | Puntuación de relevancia de un documento en función de su relevancia. |
| Etiqueta de relevancia | RelevanceTag |  | Etiqueta de relevancia | Puntuación de relevancia de un documento en función de su relevancia. |
| IDENTIFICADOR representativo | RepresentativeId |  | IDENTIFICADOR representativo | Identificador numérico de cada conjunto de duplicados exactos. |
| Remitente | Remitente | Email_sender | Remitente | Campo de remitente (de) para los tipos de mensaje.  Format es **displayName \<SmtpAddress>**. |
| Remitente/autor | SenderAuthor |  | Remitente/autor | Campo calculado formado por el remitente o el autor del elemento. |
| Dominio del remitente | SenderDomain | Email_sender_domain | Dominio del remitente | Dominio del remitente. |
| Sent | Sent | Email_date_sent | Sent | Fecha de envío del mensaje. |
| Establecer orden: primero inclusive | SetOrderInclusivesFirst | Set_order_inclusives_first | Set Order: inclusive en primer lugar. | Campo de ordenación-correo electrónico y datos adjuntos: contador-cronológico, documentos: Pivot primero luego por puntuación de similitud, descendente. |
| SimilarityPercent |  | Similarity_percent |  | Indica la similitud de un documento con el pivote del conjunto de duplicados near. |
| Tamaño de archivo nativo | Size | Native_size | Tamaño de archivo nativo | Número de bytes del elemento nativo. |
| Subject | Subject | Email_subject | Subject | Asunto del mensaje. |
| Asunto/título | SubjectTitle |  | Asunto/título | Campo calculado compuesto por el asunto o el título del elemento. |
| Se etiquetan por el número de caso 1 |  | Tagged_by_Case_issue_1 |  | Usuario que etiquetó este documento por el problema de caso 1 en relevancia. |
| Tags | Tags | Tags | Tags | Etiquetas aplicadas en un conjunto de revisión. |
| Lista de temas | ThemesList | Themes_list | Lista de temas | Lista de temas tal y como se calcula para el análisis. |
| Título | Título | Doc_title | El título | Título de los metadatos del documento. |
| To | To | Email_to | To | Campo para para para tipos de mensaje.  El formato **es\<DisplayName SmtpAddress>** |
| Único en el conjunto de correo electrónico | UniqueInEmailSet |  | Único en el conjunto de correo electrónico | False si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico. |
| Se corrigió | WasRemediated | Was_Remediated | Se corrigió | True si el elemento se ha corregido; en caso contrario, false. |
| Word count | WordCount | Word_count | Word count | Número de palabras del elemento. |
||||||

  > [!NOTE]
  > Para obtener más información acerca de los campos que permiten búsquedas al buscar directamente en Office 365, consulte [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](https://docs.microsoft.com/en-us/office365/securitycompliance/keyword-queries-and-search-conditions)
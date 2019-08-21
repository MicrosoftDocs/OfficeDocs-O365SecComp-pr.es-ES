---
title: Información general sobre la prevención de pérdida de datos
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Con una directiva de prevención de pérdida de datos (DLP) del Centro de seguridad y cumplimiento, puede identificar, supervisar y proteger automáticamente información confidencial en todo Office 365.
ms.openlocfilehash: 3b108e292e7c7942e471d345b11124beac52f369
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478249"
---
# <a name="overview-of-data-loss-prevention"></a>Información general sobre la prevención de pérdida de datos
<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
> [!NOTE]
> Las funciones de prevención de pérdida de datos se han agregado recientemente a los mensajes de conversaciones y canales de Microsoft Teams para usuarios con licencia de Cumplimiento avanzado de Office 365, que está disponible como opción independiente y se incluye en Cumplimiento de Microsoft 365 E5 y Office 365 E5. Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 de el nivel de espacio empresarial](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

Para cumplir con los estándares de la empresa y las normativas del sector, las organizaciones deben proteger información confidencial e impedir su divulgación involuntaria. La información confidencial puede incluir datos financieros o información de identificación personal (PII), tales como números de tarjeta de crédito, números de seguridad social o registros médicos. Con una directiva de prevención de pérdida de datos (DLP) del Centro de seguridad y cumplimiento de Office 365, puede identificar, supervisar y proteger automáticamente información confidencial en todo Office 365.
  
Con una directiva DLP, puede:
  
- **Identificar información confidencial en varias ubicaciones, como Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.**
    
    Por ejemplo, puede identificar cualquier documento que contenga un número de tarjeta de crédito y que esté almacenado en un sitio de OneDrive para la Empresa, o puede supervisar solo los sitios de OneDrive de determinadas personas.
    
- **Evitar el uso compartido accidental de información confidencial**. 
    
    Por ejemplo, puede identificar cualquier documento o correo electrónico que contenga un registro médico compartido con personas de fuera de su organización y, a continuación, bloquear automáticamente el acceso a dicho documento o el envío del correo electrónico.
    
- **Supervisar y proteger información confidencial en las versiones de escritorio de Excel, PowerPoint y Word.**
    
    Al igual que en Exchange Online, SharePoint Online y OneDrive para la Empresa, estos programas de escritorio de Office incluyen las mismas capacidades para identificar información confidencial y aplicar directivas DLP. DLP proporciona supervisión continua cuando las personas comparten contenido en estos programas de Office.
    
- **Ayudar a los usuarios a aprender a cumplir las directivas sin interrumpir el flujo de trabajo.**
    
    Puede educar a sus usuarios acerca de las directivas DLP y ayudar a que sigan manteniendo el cumplimiento normativo sin bloquear su trabajo. Por ejemplo, si un usuario intenta compartir un documento que contiene información confidencial, una directiva DLP puede enviarle una notificación por correo electrónico y mostrarle una sugerencia de directiva en el contexto de la biblioteca de documentos que le permite invalidar la directiva si tiene una justificación comercial. Las mismas sugerencias de directiva también aparecen en Outlook en la Web, Outlook, Excel, PowerPoint y Word.
    
- **Ver informes de DLP con contenido que coincida con las directivas DLP de su organización.**
    
    Para evaluar si la organización está cumpliendo con una directiva DLP, puede ver cuántas coincidencias tiene la directiva y la regla a lo largo del tiempo. Si una directiva DLP permite a los usuarios invalidar una sugerencia de directiva y notificar un falso positivo, también puede ver sobre qué han informado los usuarios.
    
Para crear y administrar las directivas DLP, vaya a la página sobre la prevención de pérdida de datos del Centro de seguridad y cumplimiento de Office 365.
  
![Página de prevención de pérdida de datos en el Centro de seguridad y cumplimiento de Office 365](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>Qué contiene una directiva DLP

Una directiva DLP contiene unas pocas cosas básicas:
  
- Dónde proteger el contenido: **ubicaciones** como Exchange Online, SharePoint Online y sitios de OneDrive para la Empresa, así como mensajes de chat y canales de Microsoft Teams. 
    
- Cuándo y cómo proteger el contenido aplicando **reglas** compuestas de: 
    
  - **Condiciones** que el contenido debe cumplir antes de que se aplique la regla. Por ejemplo, una regla se puede configurar para que busque solo contenido que incluya números de seguridad social y que se haya compartido con personas de fuera de su organización. 
    
  - **Acciones** que quiere que la regla realice automáticamente cuando se encuentra contenido que coincide con las condiciones. Por ejemplo, una regla se puede configurar para bloquear el acceso a un documento y enviar una notificación por correo electrónico al usuario y al responsable de cumplimiento. 
    
Puede usar una regla para satisfacer un requisito de protección específico y después usar una directiva DLP para agrupar los requisitos de protección comunes, como todas las reglas necesarias para cumplir una normativa específica.
  
Por ejemplo, podría tener una directiva DLP que ayude a detectar la presencia de información sujeta a la Ley de transferencia y responsabilidad de seguros de salud (HIPAA). Esta directiva DLP podría ayudar a proteger los datos HIPAA (el qué) en todos los sitios de SharePoint Online y OneDrive para la Empresa (el dónde) al buscar cualquier documento que contenga información confidencial y que se comparte con personas de fuera de la organización (las condiciones) y, a continuación, bloquear el acceso al documento y enviar una notificación (las acciones). Estos requisitos se almacenan como reglas individuales y se agrupan de forma conjunta como directiva DLP para simplificar la administración y la creación de informes.
  
![El diagrama muestra que la directiva DLP contiene ubicaciones y reglas](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>Ubicaciones

Una directiva DLP puede buscar y proteger información confidencial en todo Office 365, independientemente de si esa información se encuentra en Exchange Online, SharePoint Online, OneDrive para la Empresa o Microsoft Teams. Puede elegir proteger el contenido en el correo electrónico de Exchange, y los mensajes de canales y chats de Microsoft Teams, y todas las bibliotecas de SharePoint o OneDrive, o bien seleccionar ubicaciones específicas para una directiva.
  
![Opciones de ubicaciones donde se puede aplicar una directiva DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
Si elige incluir o excluir sitios de SharePoint o cuentas de OneDrive específicos, una directiva DLP no puede contener más de 100 inclusiones y exclusiones. Aunque este límite exista, puede superar este límite aplicando una directiva para toda la organización o una directiva que se aplique ubicaciones completas.
  
### <a name="rules"></a>Reglas

Las reglas son las que aplican los requisitos empresariales en el contenido de su organización. Una directiva contiene una o más reglas, y cada regla consta de las condiciones y acciones. Para cada regla, cuando se cumplen las condiciones, las acciones se realizan automáticamente. Las reglas se ejecutan secuencialmente, comenzando por la regla de mayor prioridad de cada directiva.
  
Una regla también proporciona opciones para notificar a los usuarios (con sugerencias de directiva y notificaciones por correo electrónico) y los administradores (con informes de incidentes por correo electrónico) de que el contenido ha coincidido con la regla.
  
Estos son los componentes de una regla, explicados detalladamente a continuación.
  
![Secciones del editor de reglas DLP](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condiciones

Las condiciones son importantes porque determinan los tipos de información que está buscando y cuándo se debe realizar una acción. Por ejemplo, puede optar por omitir el contenido que contiene números de pasaporte a menos que el contenido contenga más de 10 de esos números y se comparta con personas fuera de la organización.
  
Las condiciones se centran en el **contenido**, como el tipo de información confidencial que está buscando, y también en el **contexto**, como con quién se comparte el documento. Puede usar condiciones para asignar acciones diferentes a distintos niveles de riesgo. Por ejemplo, el contenido confidencial compartido internamente podría ser de menor riesgo y necesitar menos acciones que el contenido confidencial compartido con personas de fuera de la organización. 
  
![Lista que muestra las condiciones de DLP disponibles](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
Las condiciones disponibles ahora pueden determinar si:
  
- El contenido incluye un tipo de información confidencial.
    
- El contenido incluye una etiqueta. Para obtener más información, consulte la sección [Usar una etiqueta como una condición en una directiva DLP](#using-a-label-as-a-condition-in-a-dlp-policy), que encontrará a continuación.
    
- El contenido se comparte con personas de fuera o dentro de la organización.
    
#### <a name="types-of-sensitive-information"></a>Tipos de información confidencial

Una directiva DLP puede ayudar a proteger información confidencial, lo que se define como un **tipo de información confidencial**. Office 365 incluye definiciones para muchos tipos comunes de información confidencial en muchas regiones diferentes que están listas para su uso, como números de tarjeta de crédito, números de cuentas bancarias, números de identificación nacionales y números de pasaporte. 
  
![Lista de tipos de información confidencial disponibles](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Cuando una directiva DLP busca un tipo de información confidencial, como un número de tarjeta de crédito, no solamente busca un número de 16 dígitos. Cada tipo de información confidencial se define y se detecta mediante una combinación de:
  
- Palabras clave
    
- Funciones internas para validar las sumas de comprobación o composición
    
- Evaluación de expresiones regulares para buscar coincidencias de patrón
    
- Otros exámenes de contenido
    
Esto ayuda a que la detección de DLP alcance un alto grado de precisión reduciendo el número de falsos positivos que pueden interrumpir el trabajo de las personas.
  
#### <a name="actions"></a>Acciones

Cuando el contenido coincide con una condición en una regla, puede aplicar acciones para proteger automáticamente el contenido.
  
![Lista de acciones de DLP disponibles](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Con las acciones ahora disponibles, podrá:
  
- **Restringir el acceso al contenido**. Para el contenido del sitio, esto significa que los permisos del documento están restringidos para todos los usuarios excepto el administrador de la colección de sitios, el propietario del documento y la persona que lo modificó por última vez. Estas personas pueden eliminar la información confidencial del documento o realizar otras acciones correctivas. Cuando el documento cumple la normativa, los permisos originales se restauran automáticamente. Cuando se bloquea el acceso a un documento, este aparece con un icono de sugerencia de directiva especial en la biblioteca del sitio. 
    
    ![Sugerencia de directiva que muestra que el acceso al documento está bloqueado](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    Para el contenido del correo electrónico, esta acción evita que se envíe el mensaje. Según la configuración de la regla DLP, el remitente ve un NDR o, si la regla usa una notificación, una notificación por correo electrónico y la sugerencia de directiva.
    
    ![Advertencia para quitar del mensaje a los destinatarios no autorizados](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notificaciones de usuario e invalidaciones de usuario

Puede utilizar notificaciones de usuario e invalidaciones de usuario para concienciarles sobre las directivas DLP y ayudarles a que sigan manteniendo el cumplimiento normativo sin bloquear su trabajo. Por ejemplo, si un usuario intenta compartir un documento que contiene información confidencial, una directiva DLP puede enviarle una notificación por correo electrónico y mostrarle una sugerencia de directiva en el contexto de la biblioteca de documentos que le permite invalidar la directiva si tiene una justificación comercial.
  
![Secciones Notificaciones de usuario e Invalidaciones de usuario del editor de reglas DLP](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
El correo electrónico puede notificar a la persona que envió, compartió o modificó el contenido por última vez y, para el contenido del sitio, al administrador de la colección de sitios primaria y al propietario del documento. Además, puede agregar a cualquier persona a la notificación por correo electrónico o quitarla de ella.
  
Además de enviar una notificación por correo electrónico, la notificación de usuario muestra una sugerencia de directiva:
  
- En Outlook y Outlook en la Web
    
- Para el documento en un sitio de SharePoint Online o OneDrive para la Empresa.
    
- En Excel, PowerPoint y Word, cuando el documento está almacenado en un sitio que se incluye en una directiva DLP.
    
La notificación por correo electrónico y la sugerencia de directiva explican por qué el contenido entra en conflicto con una directiva DLP. Si lo elige, la sugerencia de directiva y la notificación por correo electrónico pueden permitir que los usuarios invaliden una regla al informar de un falso positivo o proporcionar una justificación comercial. Esto puede ayudar a educar a los usuarios sobre las directivas DLP y aplicarlas sin impedir que los usuarios realicen su trabajo. La información sobre invalidaciones y falsos positivos también se registra para los informes (consulte a continuación sobre los informes de DLP) y se incluye en los informes de incidentes (sección siguiente), a fin de que el responsable de cumplimiento normativo pueda revisar periódicamente esta información.
  
Así es como se muestra una sugerencia de directiva en una cuenta de OneDrive para la Empresa.
  
![Sugerencia de directiva para un documento de una cuenta de OneDrive](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>Informes de incidentes

Cuando una regla coincide, puede enviar un informe de incidentes a su responsable de cumplimento normativo (o a la persona que elija) con los detalles del evento. Este informe incluye información sobre el elemento que ha coincidido, el contenido que ha coincidido con la regla y el nombre de la persona que ha modificado el contenido por última vez. Para los mensajes de correo electrónico, el informe también incluye el mensaje original que coincide con una directiva DLP como datos adjuntos.
  
![Página para configurar informes de incidentes](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>Operadores lógicos y de agrupación

A menudo, la directiva DLP tiene un requisito sencillo, como, por ejemplo, identificar todo el contenido que incluya un número de la seguridad social de Estados Unidos. Sin embargo, en otros escenarios, la directiva DLP podría necesitar identificar datos definidos de forma más flexible.
  
Por ejemplo, para identificar el contenido sujeto a la Ley de seguros de salud (HIPAA) de Estados Unidos, debe buscar:
  
- Contenido que incluye tipos concretos de información confidencial, como un Número de la Seguridad social o un Número de la Agencia antidroga (DEA) de Estados Unidos.
    
    Y
    
- Contenido que es más difícil identificar, como las comunicaciones sobre la atención a un paciente o las descripciones de los servicios médicos proporcionados. La identificación de este tipo de contenido requiere que coincida con las palabras clave de una lista muy grande, como la Clasificación internacional de enfermedades (ICD-9-CM o ICD-10-CM).
    
Puede identificar fácilmente estos datos definidos de manera imprecisa mediante el uso de operadores lógicos y de agrupación (Y, O). Al crear una directiva DLP, se puede:
  
- Agrupar tipos de información confidencial
    
- Elegir el operador lógico entre los tipos de información confidencial dentro de un grupo y entre los propios grupos
    
### <a name="choosing-the-operator-within-a-group"></a>Elegir el operador dentro de un grupo

Dentro de un grupo, puede elegir si se deben cumplir algunas o todas las condiciones de ese grupo para que el contenido coincida con la regla.
  
![Grupos que muestran el operador dentro del grupo](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Adición de un grupo

Puede agregar rápidamente un grupo, que puede tener sus propias condiciones y operador dentro de ese grupo.
  
![Botón Agregar grupo](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Elección del operador entre grupos

Entre los grupos, puede elegir si se deben cumplir las condiciones de un solo grupo o de todos los grupos para que el contenido coincida con la regla.
  
Por ejemplo, la directiva **HIPAA de Estados Unidos** tiene una regla que usa un operador **Y** entre los grupos para identificar el contenido que incluya lo siguiente: 
  
- del grupo **Identificadores PII** (por lo menos un número de SSN **O** número DEA) 
    
    **Y**
    
- del grupo **Términos médicos** (por lo menos una palabra clave ICD-9-CM **O** ICD-10-CM) 
    
![Grupos que muestran el operador entre grupos](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>Prioridad por la que se procesan las reglas

Al crear reglas en una directiva, a cada regla se le asigna una prioridad en el orden en que se crea (es decir, la regla creada en primer lugar tiene la máxima prioridad, la regla creada en segundo lugar tiene una prioridad secundaria, etc.). 
  
![Reglas en orden de prioridad](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
Una vez que haya configurado más de una directiva DLP, puede cambiar la prioridad de una o más directivas. Para hacerlo, seleccione una directiva, elija **Editar directiva** y use la lista de **Prioridad** para especificar la prioridad.

![Establecer la prioridad de una directiva](media/dlp-set-policy-priority.png)

Cuando se evalúa el contenido frente a reglas, estas se procesan en orden de prioridad. Si el contenido coincide con varias reglas, estas se procesan en orden de prioridad y se aplica la acción más restrictiva. Por ejemplo, si el contenido coincide con todas las reglas siguientes, se aplica la Regla 3 porque es la regla más restrictiva y con mayor prioridad:
  
- Regla 1: solo notifica a los usuarios
    
- Regla 2: notifica a los usuarios, restringe el acceso y permite invalidaciones de usuario
    
- Regla 3: notifica a los usuarios, restringe el acceso y no permite invalidaciones de usuario
    
- Regla 4: solo notifica a los usuarios
    
- Regla 5: restringe el acceso
    
- Regla 6: notifica a los usuarios, restringe el acceso y no permite invalidaciones de usuario
    
En este ejemplo, tenga en cuenta que las coincidencias de todas las reglas se graban en los registros de auditoría y se muestran en los informes DLP, aunque se aplique solo la regla más restrictiva.
  
En relación con las sugerencias de directiva, tenga en cuenta lo siguiente:
  
- Solo se mostrará la sugerencia de directiva de la regla más restrictiva y con mayor prioridad. Por ejemplo, una sugerencia de directiva de una regla que bloquea el acceso al contenido se mostrará por encima de una sugerencia de directiva de una regla que simplemente envía una notificación. Esto impide que las personas vean una cascada de sugerencias de directiva.
    
- Si las sugerencias de directiva en la regla más restrictiva permite que los usuarios invaliden la regla, la invalidación de esta regla invalida también otras reglas que coinciden con el contenido.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Ajustar reglas para que sea más fácil o más difícil que coincidan

Después de crear y activar sus directivas DLP, a veces los usuarios se encuentran con estos problemas:
  
- Demasiado contenido que **no es** información confidencial coincide con las reglas (es decir, demasiados falsos positivos). 
    
- Muy poco contenido que **es** información confidencial coincide con las reglas. Es decir, las acciones de protección no se están aplicando en la información confidencial. 
    
Para solucionar estos problemas, puede ajustar las reglas al modificar el recuento de instancias y la precisión de coincidencia para que sea más fácil o más difícil que el contenido coincida con las reglas. Todos los tipos de información confidencial que se usan en una regla tienen un recuento de instancias y precisión de coincidencia.
  
### <a name="instance-count"></a>Recuento de instancias

El recuento de instancias significa simplemente qué número de apariciones de un determinado tipo de información confidencial debe estar presente en el contenido para que coincida con la regla. Por ejemplo, el contenido coincide con la regla que se muestra a continuación si se identifican entre 1 y 9 números únicos de pasaporte de los Estados Unidos o Reino Unido.
  
Tenga en cuenta que el número de instancias incluye solo coincidencias **únicas** con palabras clave y tipos de información confidenciales. Por ejemplo, si un correo electrónico contiene diez veces el mismo número de tarjeta de crédito, esas diez cuentan como una única instancia de un número de tarjeta de crédito. 
  
Las instrucciones para usar el recuento de instancias para ajustar las reglas son sencillas:
  
- Para facilitar que la regla coincida, disminuya el recuento **mín** o aumente el recuento **máx**. También puede establecer **máx** en **cualquiera** si elimina el valor numérico. 
    
- Para que sea más difícil que la regla coincida, aumente el recuento **mín**. 
    
Normalmente, se usan acciones menos restrictivas, como el envío de notificaciones de usuario, en una regla con un recuento de instancias inferior (por ejemplo, 1-9). Y se usan acciones más restrictivas, como restringir el acceso al contenido sin permitir invalidaciones de usuario, en una regla con un recuento de instancias superior (por ejemplo, de 10 a cualquiera).
  
![Recuentos de instancias en el editor de reglas](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Precisión de coincidencia

Como se describió anteriormente, un tipo de información confidencial se define y detecta mediante una combinación de distintos tipos de evidencia. Frecuentemente, un tipo de información confidencial se define mediante esas combinaciones, denominadas patrones. Un patrón que requiere menos evidencia tiene una precisión de coincidencia (o nivel de confianza) inferior, mientras que un patrón que requiere más evidencia tiene una precisión de coincidencia (o nivel de confianza) mayor. Para obtener más información sobre los patrones y niveles de confianza reales que usa cada tipo de información confidencial, consulte [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
Por ejemplo, el tipo de información confidencial denominado Número de tarjeta de crédito se define mediante dos patrones:
  
- Un patrón con un 65 % de confianza que requiere:
    
  - Un número en el formato de un número de tarjeta de crédito.
    
  - Un número que pasa la suma de comprobación.
    
- Un patrón con un 85 % de confianza que requiere:
    
  - Un número en el formato de un número de tarjeta de crédito.
    
  - Un número que pasa la suma de comprobación.
    
  - Una palabra clave o una fecha de expiración en el formato correcto.
    
Puede usar estos niveles de confianza (o precisión de coincidencia) en sus reglas. Normalmente, se usan acciones menos restrictivas, como el envío de notificaciones de usuario, en una regla con una precisión de coincidencia inferior. Y se usan acciones más restrictivas, como restringir el acceso al contenido sin permitir invalidaciones de usuario, en una regla con una precisión de coincidencia superior.
  
Es importante comprender que, cuando se identifica en el contenido un tipo específico de información confidencial (como un número de tarjeta de crédito), se devuelve solo un único nivel de confianza:
  
- Si todas las coincidencias son para un único patrón, se devuelve el nivel de confianza de ese patrón.
    
- Si hay coincidencias para más de un patrón (es decir, hay coincidencias con dos niveles de confianza diferentes), se devuelve un nivel de confianza superior a cualquiera de los patrones únicos independientes. Esta es la parte complicada. Por ejemplo, para una tarjeta de crédito, si se cumplen los patrones del 65 % y del 85 %, el nivel de confianza que devuelve ese tipo de información confidencial es mayor al 90 % porque más evidencia implica más confianza.
    
Por lo tanto, si quiere crear dos reglas que se excluyan mutuamente para tarjetas de crédito, una para la precisión de coincidencia del 65 % y otra para la precisión de coincidencia del 85 %, los intervalos de la precisión de coincidencia tendrían el siguiente aspecto. La primera regla selecciona solo coincidencias del patrón del 65 %. La segunda regla selecciona coincidencias con **al menos una** coincidencia del 85 % y **puede tener** otras coincidencias con un nivel menor de confianza. 
  
![Dos reglas con rangos diferentes para la precisión de coincidencia](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Por estas razones, las instrucciones para crear reglas con diferentes precisiones de coincidencia son:
  
- Normalmente, el nivel inferior de confianza usa el mismo valor para **mín** y **máx** (no un rango). 
    
- El nivel superior de confianza suele ser un rango desde el nivel de confianza inferior hasta 100.
    
- Por lo general, los niveles de confianza intermedios oscilan entre justo después del nivel de confianza inferior y justo antes del nivel de confianza superior.
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>Usar una etiqueta como condición en una directiva DLP

Puede crear una etiqueta y después:
<!-- what kind of label? -->
  
- **Publicarla** , para que los usuarios finales puedan ver y aplicar manualmente la etiqueta al contenido. 
    
- **Aplicarla automáticamente** al contenido que coincida con las condiciones que elija. 
    
Para obtener más información sobre las etiquetas, vea [Información general sobre etiquetas de retención](labels.md).
  
Después de crear una etiqueta, podrá usarla como una condición en sus directivas DLP. Por ejemplo, es posible que desee hacer esto porque:
  
- Publicó una etiqueta denominada **Confidencial**, de modo que los usuarios de su organización pueden aplicar manualmente la etiqueta a documentos y correo electrónico confidencial. Si usa esta etiqueta como una condición en la directiva DLP, puede restringir el uso compartido del contenido con la etiqueta **Confidencial** con personas fuera de su organización. 
    
- Ha creado una etiqueta denominada **Casa alpina** para un proyecto de ese nombre y luego aplica ese etiqueta automáticamente al contenido que contiene las palabras clave "Casa alpina". Al usar esta etiqueta como una condición en la directiva DLP, puede mostrar una sugerencia de directiva a los usuarios finales cuando estén a punto de compartir este contenido con personas ajenas a su organización. 
    
- Ha publicado una etiqueta denominada **Registro de impuestos**, de modo que el administrador de registros puede aplicar manualmente la etiqueta al contenido que deba clasificarse como un registro. Al usar esta etiqueta como una condición en la directiva DLP, puede buscar contenido con esta etiqueta junto con otros tipos de información confidencial, como Números de Identificación del contribuyente individual o números de la seguridad social, aplicar acciones de protección al contenido con la etiqueta **Registro de impuestos**, y obtener informes de actividades detallados sobre la directiva DLP a partir de los informes DLP y los datos de registro de auditoría. 
    
- Ha publicado una etiqueta denominada **Equipo ejecutivo de liderazgo: confidencial** a las cuentas de OneDrive y los buzones de Exchange de un grupo de ejecutivos. Al usar esta etiqueta como una condición en la directiva DLP, puede aplicar acciones de retención y protección en el mismo subconjunto de contenido y usuarios. 
    
Al usar etiquetas como condiciones en las reglas DLP, puede también aplicar acciones de protección de forma selectiva en un conjunto específico de contenido, ubicaciones o usuarios.
  
![Etiquetas como una condición](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a>La compatibilidad con las etiquetas de confidencialidad estará disponible próximamente

Actualmente, solo puede usar una etiqueta de retención como condición, pero no una [etiqueta de confidencialidad](sensitivity-labels.md). Actualmente, estamos trabajando en la compatibilidad para usar una etiqueta de confidencialidad en esta condición.
  
### <a name="how-this-feature-relates-to-other-features"></a>Cómo esta característica se relaciona con otras características

Varias características pueden aplicarse al contenido que incluye información confidencial:
  
- Una [etiqueta de retención](labels.md#applying-a-retention-label-automatically-based-on-conditions) y una [directiva de retención](retention-policies.md) pueden aplicar acciones de **retención** en este contenido. 
    
- Una directiva DLP puede aplicar acciones de **protección** en este contenido. Y antes de aplicar estas acciones, una directiva DLP puede requerir que se cumplan otras condiciones además del contenido que contiene una etiqueta. 
    
![Diagrama de características que pueden aplicarse a la información confidencial](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Tenga en cuenta que una directiva DLP tiene una capacidad de detección más profunda que una directiva de retención o etiqueta aplicada a la información confidencial. Una directiva DLP puede aplicar acciones de protección al contenido que incluye información confidencial y si se elimina la información confidencial del contenido, esas acciones de protección se desharán la próxima vez que se examine el contenido. Sin embargo, si una directiva de retención o etiqueta se aplica al contenido que incluye información confidencial, esta será una acción única que no se puede deshacer, incluso aunque se quite de la información confidencial.
  
Al usar una etiqueta como una condición en una directiva DLP, puede aplicar acciones de retención y protección en el contenido con esa etiqueta. Puede considerar el contenido que incluya una etiqueta exactamente igual al que incluye información confidencial: una etiqueta y un tipo de información confidencial son propiedades que se usan para clasificar contenido, por lo que se pueden aplicar acciones a ese contenido.
  
![Diagrama de la directiva DLP usando la etiqueta como una condición](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Configuraciones simples y configuraciones avanzadas

Cuando cree una directiva DLP, tendrá que seleccionar entre configuración simple o avanzada:
  
- La **configuración simple** facilita la creación del tipo más común de directiva DLP sin usar el editor de reglas para crearlas o modificarlas. 
    
- La **configuración avanzada** usa el editor de reglas para darle un control completo sobre cada configuración de la directiva DLP. 
    
No se preocupe, en realidad, las opciones simples y las avanzadas funcionan exactamente igual, ejecutando reglas compuestas de condiciones y acciones. La única diferencia es que con la configuración simple, no verá el editor de reglas. Es una forma rápida de crear una directiva DLP.
  
### <a name="simple-settings"></a>Configuración simple

De lejos, el escenario DLP más común es crear una directiva para ayudar a proteger el contenido con información confidencial para que no se comparta con personas de fuera de su organización y realizar una acción correctiva automática, como restringir quién puede tener acceso al contenido, enviar notificaciones de administrador o de usuario final y auditar el evento para una futura investigación. Los usuarios usan DLP para evitar la divulgación involuntaria de información confidencial.
  
Para facilitar el cumplimiento de este objetivo, cuando cree una directiva DLP, puede elegir **usar la configuración simple**. Esta configuración proporciona todo lo que necesita para implementar la directiva DLP más común, sin tener que utilizar el editor de reglas.
  
![Opciones de DLP para configuraciones simples y avanzadas](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Configuración avanzada

Si necesita crear directivas DLP más personalizadas, puede elegir **usar la configuración avanzada**.
  
La configuración avanzada le muestra el editor de reglas, con el que tiene pleno control sobre cada opción posible, incluido el recuento de instancias y la precisión de coincidencia (nivel de confianza) para cada regla.
  
Para saltar a una sección rápidamente, haga clic en un elemento de la navegación superior del editor de reglas para ir a esa sección.
  
![Menú de navegación superior del editor de reglas DLP](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Plantillas de directiva de DLP

El primer paso para crear una directiva DLP consiste en elegir la información que se protegerá. Al partir de una plantilla DLP, se ahorra el trabajo de crear un nuevo conjunto de reglas desde cero y de averiguar qué tipos de información deben incluirse de forma predeterminada. A continuación, puede agregar estos requisitos o modificarlos para ajustar la regla de modo que satisfaga los requisitos específicos de su organización.
  
Una plantilla de directiva DLP preconfigurada le ayuda a detectar tipos concretos de información confidencial, como datos HIPAA, datos PCI-DSS, datos de la ley Gramm-Leach-Bliley o incluso información de identificación personal (P.I.) específica de una ubicación. Para facilitar la búsqueda y la protección de tipos comunes de información confidencial, las plantillas de directiva que se incluyen en Office 365 ya contienen los tipos más comunes de información confidencial necesarios para comenzar.
  
![Lista de plantillas para las directivas de prevención de pérdida de datos centrada en la plantilla de Patriot Act de EE. UU.](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
Su organización también puede tener requisitos específicos propios, en cuyo caso puede crear una directiva DLP desde cero eligiendo la opción **Directiva personalizada**. Una directiva personalizada está vacía y no contiene reglas predefinidas. 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>Implementar las directivas DLP gradualmente con el modo de prueba

Cuando crea directivas DLP, considere la posibilidad de implementarlas gradualmente para evaluar su impacto y probar su eficacia antes de aplicarlas completamente. Por ejemplo, no es deseable que una nueva directiva DLP bloquee accidentalmente el acceso a miles de documentos a los que las personas necesitan acceso para realizar su trabajo.
  
Si está creando directivas DLP con un gran impacto potencial, se recomienda seguir esta secuencia:
  
1. **Inicie en modo de prueba sin sugerencias de directiva** y, a continuación, use los informes DLP para evaluar el impacto. Los informes DLP le sirven para ver el número, la ubicación, el tipo y la gravedad de las coincidencias de directivas. En función de los resultados, puede ajustar las reglas según sea necesario. En el modo de prueba, las directivas DLP no afectarán a la productividad de las personas que trabajan en su organización. 
    
2. **Cambie a modo de prueba con notificaciones y sugerencias de directivas** para que pueda comenzar a enseñar a los usuarios las directivas de cumplimiento y prepararlos para las reglas que se van a aplicar. En esta fase, también puede solicitar a los usuarios que informen de falsos positivos para que pueda perfeccionar las reglas de los usuarios. 
    
3. **Comience el cumplimiento completo de las directivas** para que se apliquen las acciones en las reglas y se proteja el contenido. Continúe supervisando los informes DLP y los informes de incidentes o las notificaciones para asegurarse de que los resultados sean los deseados. 
    
![Opciones para usar el modo de prueba y activar la directiva](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
Puede desactivar una directiva DLP en cualquier momento, lo que afecta a todas las reglas de la directiva. No obstante, también es posible desactivar reglas individuales mediante el botón de alternancia de estado del editor de reglas.
  
![Opciones para desactivar una regla de una directiva](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

También puede cambiar la prioridad de varias reglas en una directiva. Para hacerlo, abra una directiva para editarla. En una fila de una regla, elija el signo de puntos suspensivos (**...**) y elija una opción, como **Bajar** o **Llevar al final**. 

![Establecer la prioridad de la regla](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a>Informes de DLP

Después de crear y activar las directivas DLP, deberá comprobar que su funcionamiento es el deseado y que le ayudan a cumplir las normativas. Con los informes de DLP, puede ver rápidamente el número de directivas DLP y coincidencias de regla a lo largo del tiempo, así como el número de falsos positivos e invalidaciones. En cada informe, las coincidencias se pueden filtrar por ubicación, período de tiempo e incluso se puede especificar una directiva, una regla o una acción concretas.
  
Con los informes de DLP, puede obtener información de la empresa y:
  
- Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
- Descubrir los procesos de negocio que infringen las directivas de cumplimiento de su organización.
    
- Comprender cualquier impacto de negocio de las directivas DLP.
    
Además, puede usar los informes de DLP para ajustar sus directivas DLP mientras las ejecuta.
  
![Panel de informes en el Centro de seguridad y cumplimiento](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Cómo funcionan las directivas DLP

DLP detecta información confidencial mediante un análisis profundo del contenido (no solo un análisis de texto simple). Este análisis profundo del contenido usa coincidencias de palabras clave, coincidencias de diccionario, la evaluación de expresiones regulares, funciones internas y otros métodos para detectar el contenido que coincide con las directivas DLP. Posiblemente solo un pequeño porcentaje de los datos se considera confidencial. Una directiva DLP puede identificar, supervisar y proteger automáticamente solo esos datos, sin obstaculizar o afectar a las personas que trabajan con el resto del contenido.
  
### <a name="policies-are-synced"></a>Las directivas se sincronizan

Después de crear una directiva DLP en el Centro de seguridad y cumplimiento, esta se almacena en un almacén central de directivas y después se sincroniza con los distintos orígenes de contenido, entre ellos:
  
- Exchange Online y de ahí a Outlook en la Web y Outlook
    
- Sitios de OneDrive para la Empresa
    
- Sitios de SharePoint Online
    
- Programas de escritorio de Office (Excel, PowerPoint y Word)

- Mensajes de conversaciones y canales de Microsoft Teams
    
Después de que la directiva se sincroniza en las ubicaciones adecuadas, empieza a evaluar el contenido y a aplicar las acciones.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Evaluación de la directiva en sitios de OneDrive para la Empresa y SharePoint Online

En los sitios de SharePoint Online y OneDrive para la Empresa, los documentos cambian todo el tiempo: se crean, se modifican y se comparten continuamente. Esto significa que los documentos pueden entrar en conflicto o pasar a ser conformes con una directiva DLP en cualquier momento. Por ejemplo, una persona puede cargar un documento que no contenga información confidencial a su sitio de grupo, pero más adelante, puede editar el mismo documento y agregar información confidencial.
  
Por este motivo, las directivas DLP buscan frecuentemente y en segundo plano coincidencias de directivas en los documentos. Puede considerarlo como una evaluación asincrónica de directiva.
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>Cómo funciona
 
A medida que los usuarios agregan o cambian documentos en sus sitios, el motor de búsqueda analiza el contenido, para que pueda buscarlo más adelante. Cuando esto ocurre, también se busca información confidencial en el contenido y se comprueba si se ha compartido. La información confidencial encontrada se almacena de forma segura en el índice de búsqueda para que solo el equipo de cumplimiento pueda tener acceso a ella, pero no los usuarios normales. Cada directiva DLP activada se ejecuta en segundo plano (asincrónicamente), comprobando la búsqueda con frecuencia de cualquier contenido que coincida con una directiva y aplicando acciones para protegerla de pérdidas accidentales.
  
![Diagrama que muestra cómo la directiva DLP evalúa el contenido asincrónicamente](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> Por último, los documentos pueden entrar en conflicto con una directiva DLP, pero también pueden cumplir con una directiva DLP. Por ejemplo, si una persona agrega números de tarjeta de crédito a un documento, podría hacer que una directiva DLP bloquee el acceso al documento de forma automática. Pero si la persona elimina más adelante la información confidencial, la acción (en este caso, el bloqueo) se deshace automáticamente la próxima vez que se evalúa el documento con la directiva.
  
DLP evalúa el contenido que se puede indexar. Para obtener más información sobre los tipos de archivo que se rastrean de forma predeterminada, consulte [Extensiones de nombre de archivo y tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Evaluación de la directiva en Exchange Online, Outlook y Outlook en la Web

Cuando se crea una directiva DLP que incluye Exchange Online como ubicación, la directiva se sincroniza desde el Centro de seguridad y cumplimiento de Office 365 con Exchange Online y, después, desde Exchange Online con Outlook en la Web y Outlook.
  
Cuando se redacta un mensaje en Outlook, el usuario puede ver sugerencias de directiva mientras el contenido creado se evalúa según las directivas DLP. Y cuando se envía un mensaje, este se evalúa según las directivas DLP como una parte normal del flujo de correo, junto con las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) y las directivas DLP creadas en el centro de administración de Exchange. Las directivas DLP escanean tanto el mensaje como los archivos adjuntos.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Evaluación de la directiva en los programas de escritorio de Office

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint y Word incluyen la misma capacidad para identificar información confidencial y aplicar directivas DLP que SharePoint Online y OneDrive para la Empresa. Estos programas de Office sincronizan sus directivas DLP directamente desde el almacén central de directivas y evalúan continuamente el contenido con las directivas DLP cuando los usuarios trabajan con documentos abiertos desde un sitio que se incluye en una directiva DLP.
  
La evaluación de directivas DLP en Office está diseñada para no afectar al rendimiento de los programas ni a la productividad de las personas que trabajan en el contenido. Si están trabajando en un documento de gran tamaño o el equipo del usuario está ocupado, tardará unos segundos en aparecer una sugerencia de directiva.

### <a name="policy-evaluation-in-microsoft-teams"></a>Evaluación de directivas en Microsoft Teams
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Cuando crea una directiva DLP que incluye Microsoft Teams como ubicación, la directiva se sincroniza desde el Centro de seguridad y cumplimiento de Office 365 con las cuentas de usuario y mensajes de chat y de canales de Microsoft Teams. En función de cómo estén configuradas las directivas DLP, cuando un usuario intenta compartir información confidencial en un mensaje de chat o canal de Microsoft Teams, el mensaje se puede bloquear o revocar. Y los documentos que contienen información confidencial y que se comparten con invitados (usuarios externos) no se abrirán para estos usuarios. Para obtener más información, vea [Prevención de pérdida de datos y Microsoft Teams](dlp-microsoft-teams.md).
 
## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento que vayan a crear directivas DLP necesitan permisos para el Centro de seguridad y cumplimiento. De forma predeterminada, el administrador de espacios empresariales tendrá acceso a esta ubicación y puede conceder a los responsables de cumplimiento y a otros usuarios acceso al Centro de seguridad y cumplimiento, sin darles todos los permisos de un administrador de espacios empresariales. Para hacerlo, le recomendamos:
  
1. Crear un grupo en Office 365 y agregarle responsables de cumplimiento.
    
2. Crear un grupo de roles en la página **Permisos** del Centro de seguridad y cumplimiento. 
    
3. Agregar el grupo de Office 365 al grupo de roles.
    
Para más información, vea [Conceder acceso a los usuarios al Centro de cumplimiento de Office 365](grant-access-to-the-security-and-compliance-center.md).
  
Estos permisos son necesarios solo para crear y aplicar una directiva de DLP. La aplicación de directivas no requiere acceso al contenido.
  
## <a name="find-the-dlp-cmdlets"></a>Encontrar los cmdlets DLP

Para usar la mayoría de los cmdlets para el Centro de seguridad y cumplimiento, necesita:
  
1. [Conectarse al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. Usar cualquiera de estos [cmdlets policy-and-compliance-dlp](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)
    
Sin embargo, los informes de DLP necesitan extraer datos de todo Office 365, incluido Exchange Online. Por este motivo, **los cmdlets para los informes de DLP están disponibles en el PowerShell de Exchange Online. no en el PowerShell del Centro de seguridad y cumplimiento**. Por lo tanto, para usar los cmdlets para los informes de DLP, debe:
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. Use cualquiera de estos cmdlets para los informes de DLP:
    
  - [Get-DlpDetectionsReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [Get-DlpDetailReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a>Más información

- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificaciones y mostrar sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md)
    
- [Crear una directiva DLP para proteger documentos con FCI u otras propiedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
    
- [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md)
    
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
    


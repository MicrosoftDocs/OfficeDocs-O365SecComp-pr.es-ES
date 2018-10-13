---
title: Información general sobre directivas de prevención de pérdida de datos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 1966b2a7-d1e2-4d92-ab61-42efbb137f5e
description: Con una directiva de (DLP) de prevención de pérdida de datos en la seguridad de Office 365 &amp; centro de cumplimiento, puede identificar, supervisar y proteger información confidencial de forma automática a través de Office 365.
ms.openlocfilehash: c33fe53797f86208e7cd033029949737a5c84d2f
ms.sourcegitcommit: 397a5fe594e4cf4bb64c0c6f233d310ef3cbd922
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25540426"
---
# <a name="overview-of-data-loss-prevention-policies"></a>Información general sobre directivas de prevención de pérdida de datos

Para cumplir con los estándares de negocio y reglamentaciones de la industria, las organizaciones necesitan proteger información confidencial y evitar que su divulgación involuntaria. Datos financieros o información de identificación personal (PII), como números de tarjeta de crédito, números de la seguridad social o registros de mantenimiento son ejemplos de información confidencial que es posible que desee evitar que se pierdan fuera de su organización. Con una directiva de (DLP) de prevención de pérdida de datos en la seguridad de Office 365 &amp; centro de cumplimiento, puede identificar, supervisar y proteger información confidencial de forma automática a través de Office 365.
  
Con una directiva DLP, puede:
  
- **Identificar la información confidencial a través de varias ubicaciones, como Exchange Online, SharePoint Online y OneDrive para la empresa.**
    
    Por ejemplo, puede identificar cualquier documento que contiene un número de tarjeta de crédito que se almacena en cualquier OneDrive para el sitio de negocio, o puede supervisar los sitios de OneDrive de personas específicas.
    
- **Evitar el uso compartido accidental de información confidencial**. 
    
    Por ejemplo, puede identificar cualquier documento o el correo electrónico que contiene un registro de mantenimiento que se comparte con personas fuera de la organización, y, a continuación, bloquear automáticamente el acceso a ese documento o bloquear el correo electrónico no se envía.
    
- **Supervisar y proteger información confidencial en las versiones de escritorio de Excel 2016, PowerPoint 2016 y Word 2016.**
    
    Al igual que en Exchange Online, SharePoint Online y OneDrive para la empresa, estos programas de escritorio de Office 2016 incluyen las mismas funciones para identificar la información confidencial y aplicar directivas de DLP. DLP proporciona supervisión continua cuando las personas compartan el contenido de estos programas de Office 2016.
    
- **Ayudar a los usuarios a aprender a cumplir sin interrumpir el flujo de trabajo.**
    
    Puede enseñar a los usuarios acerca de las directivas DLP y que puedan permanecer compatible con sin bloquear su trabajo. Por ejemplo, si un usuario intenta compartir un documento que contiene información confidencial, una directiva de DLP puede enviarles una notificación de correo electrónico y mostrar una sugerencia de directiva en el contexto de la biblioteca de documentos que les permite invalidar la directiva si disponen de una empresa justificación. Las mismas sugerencias de directiva también aparecen en Outlook en el web, Outlook 2013 y posterior, Excel 2016, 2016 de PowerPoint y Word 2016.
    
- **Ver DLP informes que muestra contenido que coincide con las directivas DLP de su organización.**
    
    Para evaluar cómo la organización es que se ajusten a una directiva de DLP, puede ver cuántos coincide con cada directiva y regla tiene a través del tiempo. Si una directiva de DLP permite a los usuarios reemplazar una sugerencia de directiva y notificar un falso positivo, también puede ver qué han informado sobre los usuarios.
    
Puede crear y administrar las directivas de DLP en la página de prevención de pérdida de datos en la seguridad de Office 365 &amp; centro de cumplimiento.
  
![Página de prevención de pérdida de datos en la seguridad de Office 365 &amp; centro de cumplimiento](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>Qué contiene una directiva DLP

Una directiva DLP contiene unas pocas cosas básicas:
  
- WHERE proteger el contenido - **ubicaciones** , como Exchange Online, SharePoint Online y OneDrive para sitios de negocio. 
    
- Cuándo y cómo proteger el contenido aplicando **reglas** compuestas de: 
    
  - Por ejemplo, busque **condiciones** debe coincidir el contenido antes de que se aplica la regla--sólo para el contenido que contiene los números de la seguridad Social que se ha compartido con personas fuera de la organización. 
    
  - **Acciones** que desea que la regla realice automáticamente cuando se encuentra contenido que coincide con las condiciones. Por ejemplo, bloquear el acceso al documento y enviar una notificación por correo electrónico al usuario y al responsable de cumplimiento normativo. 
    
Puede usar una regla para satisfacer un requisito específico de protección y, a continuación, utilizar una directiva DLP para agrupar los requisitos comunes de protección, por ejemplo, todas las reglas necesarias para cumplir con un Reglamento específico.
  
Por ejemplo, puede tener una directiva de DLP que le ayuda a detectar la presencia de información está sujeta a la portabilidad de seguros médicos y responsabilidad (HIPAA). Esta directiva DLP podría ayudar a proteger los datos HIPAA (¿qué) a través de todos los sitios de SharePoint Online y todos los OneDrive para sitios de negocio (where) mediante la búsqueda de cualquier documento que contiene esta información confidencial que se comparte con personas fuera de la organización (la condiciones) y, a continuación, bloquear el acceso al documento y enviar una notificación (las acciones). Estos requisitos se almacenan como reglas individuales y se agrupan juntos como una directiva de DLP para simplificar la administración y creación de informes.
  
![El diagrama muestra que la directiva DLP contiene ubicaciones y reglas](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>Ubicaciones

Una directiva de DLP puede buscar y proteger información confidencial a través de Office 365, si se encuentra dicha información en Exchange Online, SharePoint Online o OneDrive para la empresa. Puede elegir fácilmente proteger todos los sitios de SharePoint o OneDrive cuentas, sólo determinados sitios o cuentas o todos los buzones. Tenga en cuenta que no es aún posible seleccionar los buzones de correo de usuarios específicos.
  
![Opciones de ubicaciones donde se puede aplicar una directiva DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
Tenga en cuenta que si decide incluir o excluir determinados sitios de SharePoint o cuentas de OneDrive, una directiva de DLP puede contener no más de 100 dichas inclusiones y exclusiones. Aunque este límite existe, comprender que puede superar este límite mediante la aplicación de una directiva de toda la organización o una directiva que se aplica a las ubicaciones de toda.
  
### <a name="rules"></a>Reglas

Las reglas están qué exigir la aplicación de los requisitos empresariales en el contenido de su organización. Una directiva contiene una o varias reglas y cada regla consta de las condiciones y acciones. Para cada regla, cuando se cumplen las condiciones, las acciones se toman automáticamente. Las reglas se ejecutan secuencialmente, comenzando por la regla de prioridad más alta en cada directiva.
  
Una regla también proporciona opciones para notificar a los usuarios (con sugerencias de directivas y las notificaciones de correo electrónico) y administradores (con informes de incidentes de correo electrónico) que el contenido coincide con la regla.
  
Estos son los componentes de una regla, cada uno se explica a continuación.
  
![En las secciones del editor de reglas DLP](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condiciones

Las condiciones son importantes, porque determinan qué tipos de información que está buscando y cuándo se debe realizar una acción. Por ejemplo, es posible que elija Omitir el contenido que contengan números de passport a menos que el contenido contiene más de diez esos números y se comparte con personas fuera de la organización.
  
Condiciones de centran en el **contenido**, por ejemplo, ¿qué tipos de información confidencial que está buscando y también en el **contexto**, por ejemplo, que el documento se comparte con. Puede utilizar las condiciones para asignar distintas acciones a distintos niveles de riesgo: por ejemplo, contenido confidencial shared internamente puede disminuir el riesgo y requieren menos acciones que el contenido confidencial compartido con personas fuera de la organización. 
  
![Lista que muestra las condiciones de DLP disponibles](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
Las condiciones disponibles ahora pueden determinar si:
  
- Contenido contiene un tipo de información confidencial.
    
- Contenido contiene una etiqueta. Para obtener más información, vea la sección a continuación [mediante una etiqueta como una condición en una directiva de DLP](data-loss-prevention-policies.md#label).
    
- El contenido se comparte con personas de fuera o dentro de la organización.
    
#### <a name="types-of-sensitive-information"></a>Tipos de información confidencial

Una directiva de DLP puede ayudar a proteger información confidencial, que se define como un **tipo de información confidencial**. Office 365 incluye definiciones para muchos tipos comunes de información confidencial en varias zonas diferentes que están listas para usar, como un número de tarjeta de crédito, números de cuenta bancaria, nacionales números de identificación y números de cuenta de passport. 
  
![Lista de tipos de información confidencial disponibles](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Cuando una directiva de DLP busca un tipo de información confidencial, como un número de tarjeta de crédito, simplemente no busca un número de 16 dígitos. Cada tipo de información confidencial se define y se detecta mediante el uso de una combinación de:
  
- Palabras clave
    
- Funciones internas para validar las sumas de comprobación o composición
    
- Evaluación de expresiones regulares para buscar coincidencias de patrón
    
- Otros exámenes de contenido
    
Esto ayuda a la detección de DLP a lograr un alto grado de precisión al tiempo que reduce el número de falsos positivos que puede interrumpir el trabajo de personas.
  
#### <a name="actions"></a>Acciones

Cuando una condición de una regla coincide con el contenido, puede aplicar acciones para proteger el contenido de forma automática.
  
![Lista de acciones de DLP disponibles](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Con las acciones que ahora está disponibles, se puede:
  
- **Restringir el acceso al contenido** Para contenido del sitio, esto significa que los permisos para el documento están restringidos para todos los usuarios, excepto el Administrador de la colección de sitios primaria, el propietario del documento y la persona que modificó por última vez el documento. Estas personas pueden quitar la información confidencial del documento o tomar otras medidas correctivas. Cuando el documento está en cumplimiento, se restaurará automáticamente los permisos originales. Cuando se bloquea el acceso a un documento, el documento se muestra con un icono de sugerencia de directiva especial en la biblioteca en el sitio. 
    
    ![Sugerencia de directiva que muestra que el acceso al documento está bloqueado](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    Contenido de correo electrónico, esta acción bloquea el mensaje no se envía. Dependiendo de cómo se configura la regla DLP, el remitente verán un NDR o (si la regla usa una notificación) una notificación de sugerencia o correo electrónico de la directiva.
    
    ![Advertencia de que los destinatarios no autorizados deben quitarse del mensaje](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notificaciones de usuario e invalidaciones de usuario

Puede usar las notificaciones y se reemplaza para enseñar a los usuarios acerca de las directivas DLP y que puedan permanecer compatible con sin bloquear su trabajo. Por ejemplo, si un usuario intenta compartir un documento que contiene información confidencial, una directiva de DLP puede enviarles una notificación de correo electrónico y mostrar una sugerencia de directiva en el contexto de la biblioteca de documentos que les permite invalidar la directiva si disponen de una empresa justificación.
  
![Usuario y notificaciones de usuario anula secciones del editor de la regla DLP](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
El correo electrónico puede notificar a la persona que envía, compartidos o modificó por última vez el contenido y, para el contenido del sitio, el Administrador de la colección de sitios primaria y el propietario del documento. Además, puede agregar o quitar todos los usuarios elija en la notificación de correo electrónico.
  
Además de enviar una notificación de correo electrónico, una notificación de usuario muestra una sugerencia de directiva:
  
- En Outlook 2013 y versiones posteriores y Outlook en el web.
    
- Para el documento en SharePoint Online o OneDrive para el sitio de negocio.
    
- En Excel 2016, 2016 de PowerPoint y Word 2016, cuando el documento está almacenado en un sitio incluyen en una directiva de DLP.
    
La notificación de correo electrónico y la sugerencia de directiva explican por qué contenido entra en conflicto con una directiva de DLP. Si elige, la sugerencia de notificación y la directiva de correo electrónico puede permitir que los usuarios puedan invalidar una regla, un falso positivo de generación de informes o proporcionar una justificación comercial. Esto puede ayudar a enseñar a los usuarios sobre las directivas DLP y aplicarlas sin impedir que los usuarios puedan realizar su trabajo. Información acerca de invalidaciones y falsos positivos también es registrada para la creación de informes (vea más adelante acerca de los informes DLP) y se incluyen en el incidente informes (sección siguiente), para que el agente de cumplimiento con regularidad puede revisar esta información.
  
Aquí es una sugerencia de directiva aspecto en un OneDrive para la cuenta de empresa.
  
![Sugerencia de directiva para un documento de una cuenta de OneDrive](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>Informes de incidentes

Cuando se cumple una regla, puede enviar un informe del incidente a su delegado de conformidad (o todas las personas que elija) con detalles del evento. Este informe incluye información sobre el elemento coincidente, el contenido real que coincide con la regla y el nombre de la persona que modificó por última vez el contenido. Para los mensajes de correo electrónico, el informe también incluye como datos adjuntos del mensaje original que coincide con una directiva de DLP.
  
![Página para configurar informes de incidentes](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>Operadores de agrupación y lógicos

A menudo su directiva DLP tiene un requisito sencillo, por ejemplo, para identificar todo el contenido que contiene un número de seguridad Social de Estados Unidos. Sin embargo, en otros escenarios, es posible que necesite su directiva DLP identificar los datos definidos de forma más flexible.
  
Por ejemplo, para identificar contenido sujetos a Estados Unidos seguro de salud Act (HIPAA), debe tener un aspecto:
  
- Contenido que contiene tipos específicos de información confidencial, como un número de seguridad Social de Estados Unidos o agencia de cumplimiento de drogas (DEA).
    
    AND
    
- El contenido es más difícil identificar, como las comunicaciones acerca de un paciente atención o descripciones de servicios médicos proporcionados. Identificación de este contenido requiere la coincidencia de palabras clave de listas muy grandes de palabra clave, como las internacional de clasificación de enfermedades (ICD-9-CM o ICD-10-CM).
    
Puede identificar fácilmente este tipo de datos definido de forma flexible mediante el uso de operadores de agrupación y lógicos (AND, OR). Cuando se crea una directiva de DLP, se puede:
  
- Tipos de información confidencial del grupo.
    
- Elija el operador lógico entre los tipos de información confidencial dentro de un grupo y entre los propios grupos.
    
### <a name="choosing-the-operator-within-a-group"></a>Elige el operador dentro de un grupo

Dentro de un grupo, puede elegir si se deben satisfacer cualquiera o todas las condiciones de ese grupo para que el contenido para que coincida con la regla.
  
![Grupo que muestra los operadores dentro del grupo](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Adición de un grupo

Puede agregar rápidamente un grupo, que puede tener su propio condiciones y el operador dentro de ese grupo.
  
![Agregar botón de grupo](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Elige el operador entre grupos

Entre los grupos, puede elegir si se deben satisfacer las condiciones en un solo grupo o todos los grupos para que el contenido para que coincida con la regla.
  
Por ejemplo, la directiva de **Estados Unidos HIPAA** integrada tiene una regla que usa un operador **AND** entre los grupos de modo que identifica el contenido que contiene: 
  
- desde el grupo de **Identificadores de PII** (número de SSN al menos un número DEA **o** ) 
    
    **AND**
    
- desde el grupo de **Términos médicos** (al menos un ICD-9-CM **o** ICD-10-CM palabra clave) 
    
![Grupos que muestra el operador entre grupos](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>La prioridad que se procesan las reglas

Al crear reglas en una directiva, cada regla se le asigna una prioridad en el orden en el que se crea - es decir, la regla creada en primer lugar tiene prioridad, la regla creada en segundo lugar tiene prioridad segundo y así sucesivamente. Después de crear una regla, no se puede cambiar su prioridad, excepto si eliminar y volver a crearlo.
  
![Reglas en orden de prioridad](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
Cuando el contenido se evalúa con las reglas, las reglas se procesan en el orden de prioridad. Si el contenido coincide con varias reglas, las reglas se procesan en el orden de prioridad y se aplica la acción más restrictiva. Por ejemplo, si el contenido coincide con todas las reglas siguientes, se aplica la regla 3 porque es la prioridad más alta, la regla más restrictiva:
  
- Regla 1: sólo notifica a los usuarios
    
- Regla 2: notifica a los usuarios, restringe el acceso a y permite invalidaciones de usuario
    
- Regla 3: notifica a los usuarios, restringe el acceso a y no permitir invalidaciones de usuario
    
- Regla 4: sólo notifica a los usuarios
    
- Regla 5: restringe el acceso a
    
- Regla 6: notifica a los usuarios, restringe el acceso a y no permitir invalidaciones de usuario
    
En este ejemplo, tenga en cuenta que coincidencias para todas las reglas se registran en los registros de auditoría y se muestra en los informes DLP, aunque se aplica sólo a la regla más restrictiva.
  
Con respecto a sugerencias de directivas, tenga en cuenta:
  
- Sólo la sugerencia de directiva desde la prioridad más alta, se mostrará la regla más restrictiva. Por ejemplo, una sugerencia de directiva de una regla que bloquea el acceso al contenido que se mostrarán a través de una sugerencia de directiva de una regla que simplemente envía una notificación. Esto evita que las personas vean una cascada de sugerencias de directiva.
    
- Si las sugerencias de directiva en la regla más restrictiva permite que los usuarios invaliden la regla, la invalidación de esta regla invalida también otras reglas que coinciden con el contenido.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Las reglas para que sean más fácil o más difícil para que coincida con la optimización

Después de que las personas creación y activar sus directivas de DLP, en ocasiones, ejecute estos problemas:
  
- Demasiado contenido que **no es** información confidencial coincide con las reglas - en otras palabras, hay demasiados falsos positivos. 
    
- Demasiado poco contenido que **es** información confidencial coincide con las reglas, en otras palabras, que se no se aplican las acciones de protección de la información confidencial. 
    
Para solucionar estos problemas, puede ajustar las reglas mediante el ajuste de la cuenta de instancias y coinciden con precisión para que sea más fácil para el contenido para que coincida con las reglas o más difícil. Cada tipo de información confidencial usado en una regla tiene una instancia de ambos contar y coinciden con precisión.
  
### <a name="instance-count"></a>Recuento de instancias

Recuento de instancias de significa simplemente cuántos repeticiones de un tipo específico de información confidencial deben estar presentes para el contenido para que coincida con la regla. Por ejemplo, contenido coincidirán con la regla que se muestra a continuación si se identifican los números de cuenta de passport entre 1 y 9 únicos Estados Unidos o Reino Unido.
  
Tenga en cuenta que el recuento de instancia incluye sólo **único** coincidencias de palabras clave y tipos de información confidencial. Por ejemplo, si un correo electrónico contiene 10 veces el mismo número de tarjeta de crédito, esas 10 repeticiones consideran como una sola instancia de un número de tarjeta de crédito. 
  
Para usar el recuento de instancias de las reglas de ajuste, las instrucciones son bastante sencilla:
  
- Para que sea más fácil para que coincida con la regla, disminuir el recuento de **min** o aumente el recuento **máximo** . También puede establecer **max** a **cualquier** mediante la eliminación del valor numérico. 
    
- Para que sea más difícil para que coincida con la regla, aumente el número de **min** . 
    
Normalmente, se utilizan menos restrictivas acciones, como el envío de notificaciones de usuario, en una regla con un recuento de instancia inferior (por ejemplo, 1-9). Y usar acciones más restrictivas, como la restricción del acceso al contenido sin permitir invalidaciones de usuario, en una regla con un recuento de instancia superior (por ejemplo, 10-any).
  
![Los recuentos de instancia en el editor de reglas](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Precisión de coincidencia

Tal y como se describió anteriormente, un tipo de información confidencial es definido y se detectan mediante una combinación de diferentes tipos de evidencia. Con frecuencia, se define un tipo de información confidencial por varios dichas combinaciones, denominados patrones. Un patrón que requiere menos pruebas tiene una precisión de coincidencia inferior (o nivel de confianza), mientras un patrón que requiere que más evidencia tiene una mayor precisión de coincidencia (o nivel de confianza). Para obtener más información acerca de las tramas real y los niveles de confianza utilizados por cada tipo de información confidencial, vea [Buscar qué los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
  
Por ejemplo, se define el tipo de información confidencial denominado número de tarjeta de crédito mediante dos modelos:
  
- Un patrón con confianza el 65% que requiere:
    
  - Un número en el formato de un número de tarjeta de crédito.
    
  - Un número que pasa la suma de comprobación.
    
- Un patrón con confianza 85% que requiere:
    
  - Un número en el formato de un número de tarjeta de crédito.
    
  - Un número que pasa la suma de comprobación.
    
  - Una palabra clave o una fecha de caducidad en el formato correcto.
    
Puede utilizar estos niveles de confianza (o precisión de coincidencia) en las reglas. Normalmente, se utilizan menos restrictivas acciones, como el envío de notificaciones de usuario, en una regla con una precisión de coincidencia inferior. Y usar acciones más restrictivas, como la restricción del acceso al contenido sin permitir invalidaciones de usuario, en una regla con una mayor precisión de coincidencia.
  
Es importante comprender que cuando se identifica un tipo específico de información confidencial, como un número de tarjeta de crédito, en el contenido, se devuelve sólo un nivel de confianza único:
  
- Si todas las coincidencias de un patrón único, se devuelve el nivel de confianza para ese patrón.
    
- Si no hay coincidencias para más de un patrón (es decir, no hay coincidencias con dos niveles diferentes de confianza), se devuelve un nivel de confianza superior a cualquiera de los patrones de único por sí solo. Esto es la parte complicada. Por ejemplo, para una tarjeta de crédito, si se cumplen el 65% y el 85% de patrones, el nivel de confianza para que el tipo de información confidencial se devuelve más del 90% porque evidencia más significa más confianza.
    
Por lo que si desea crear dos reglas mutuamente excluyentes para tarjetas de crédito, uno para la precisión de coincidencia del 65% y otro para la precisión de coincidencia del 85%, los intervalos de precisión de coincidencia tendrá este aspecto. La primera regla descuelga sólo las coincidencias de la trama de 65%. La segunda regla recoge coincide con **al menos una** coincidencia de 85% y **puede tener** otras coincidencias de confianza de inferior. 
  
![Dos reglas con diferentes rangos de precisión de coincidencia](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Por estos motivos, las instrucciones para la creación de reglas con diferente coincidencia precisión son:
  
- El nivel de confianza más bajo normalmente usa el mismo valor para **min** y **max** (no un intervalo). 
    
- El mayor nivel de confianza suele ser un intervalo de justo sobre el nivel de confianza inferior a 100.
    
- Normalmente, los niveles de confianza intermedias oscilar entre justo sobre el nivel de confianza inferior a la posición inmediatamente por debajo del nivel de confianza superior.
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>Usar una etiqueta como condición en una directiva DLP

Puede crear una etiqueta y, a continuación:
  
- **Publicar** , para que los usuarios finales puede ver y aplicar manualmente la etiqueta para el contenido. 
    
- **Aplicar automáticamente** al contenido que coincida con las condiciones que elija. 
    
Para obtener más información sobre las etiquetas, vea [Información general sobre etiquetas](labels.md).
  
Después de crear una etiqueta, a continuación, puede usar esa etiqueta como una condición en las directivas de DLP. Por ejemplo, es posible que desee hacerlo porque:
  
- Publicar una etiqueta denominada **confidencial**, por lo que las personas de su organización pueden aplicar manualmente la etiqueta a documentos y correo electrónico confidencial. Mediante el uso de esta etiqueta como una condición en la directiva de DLP, puede restringir el contenido con la etiqueta **confidencial** desde que se está compartiendo con personas fuera de la organización. 
    
- Crea una etiqueta denominada **Casa alpino** para un proyecto con ese nombre y, a continuación, aplica esa etiqueta automáticamente al contenido que contenga las palabras clave "Alpino corchos". Mediante el uso de esta etiqueta como una condición en la directiva de DLP, puede mostrar una sugerencia de directiva a los usuarios finales cuando va a compartir este contenido con alguien de fuera de la organización. 
    
- Publicar una etiqueta denominada **registro de impuesto**, por lo que el Administrador de registros puede aplicar manualmente la etiqueta para el contenido que debe clasificarse como un registro. Mediante el uso de esta etiqueta como una condición en la directiva de DLP, que puede buscar contenido con esta etiqueta junto con otros tipos de información confidencial, como ITINs o números de seguridad social; aplicar acciones de protección al contenido etiquetado como **registro de impuesto**; y obtener informes de actividad detallada acerca de la directiva DLP desde los informes DLP y datos de registro de auditoría. 
    
- Publicar una etiqueta con el nombre de **Equipo de liderazgo ejecutivo - confidenciales** a las cuentas de OneDrive de un grupo de los ejecutivos y los buzones de Exchange. Mediante el uso de esta etiqueta como una condición en la directiva de DLP, puede aplicar acciones de retención y protección en el mismo subconjunto de contenido y los usuarios. 
    
Mediante el uso de las etiquetas como una condición en las reglas DLP, pueden se selectivamente exigir la aplicación de acciones de protección en un conjunto específico de contenido, ubicaciones o usuarios.
  
![Etiquetas como una condición](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)
  
### <a name="how-this-feature-relates-to-other-features"></a>¿Cómo se relaciona esta característica con otras características

Varias características se pueden aplicar a contenido que contiene información confidencial:
  
- Una [etiqueta de retención](labels.md#applying-a-retention-label-automatically-based-on-conditions)[aplicar una etiqueta automáticamente según las condiciones] y una [Directiva de retención](retention-policies.md) pueden aplicar acciones de **retención** en este contenido. 
    
- Una directiva de DLP puede aplicar acciones de **protección** en este contenido. Y antes de aplicar estas acciones, una directiva de DLP puede requerir otras condiciones que deben cumplirse además del contenido que contiene una etiqueta. 
    
![Diagrama de las características que se pueden aplicar a la información confidencial](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Tenga en cuenta que una directiva de DLP tiene una capacidad de detección más rica una etiqueta o directiva de retención aplicada a la información confidencial. Una directiva de DLP puede exigir la aplicación de medidas de protección en el contenido que contiene información confidencial, y si el contenido se quita la información confidencial, esas acciones protección se deshacen la próxima vez que examina el contenido. Pero si se aplica una directiva de retención o una etiqueta para el contenido que contiene información confidencial, que es una única acción que no se puede deshacer, incluso si se quita la información confidencial.
  
Mediante el uso de una etiqueta como una condición en una directiva de DLP, puede aplicar acciones de retención y protección en contenido con esa etiqueta. Puede considerar contenido que contenga una etiqueta exactamente igual que contenido que contiene información confidencial: una etiqueta y un tipo de información confidencial son propiedades que se usan para clasificar el contenido, por lo que puede aplicar acciones en dicho contenido.
  
![Diagrama de uso de etiqueta como una condición de directiva DLP](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Configuración simple frente a la configuración avanzada

Cuando se crea una directiva de DLP, decide entre configuración simple o avanzada:
  
- **Configuración simple** que sea fácil crear el tipo más común de directiva de DLP sin utilizar el editor de reglas para crear o modificar reglas. 
    
- **Configuración avanzada** , use el editor de reglas para dar a un control completo sobre todos los valores para la directiva de DLP. 
    
No se preocupe, en realidad, opciones simples y opciones avanzadas funcionan exactamente el mismo, al aplicar reglas consta de las condiciones y acciones--sólo con la configuración simple, no ve el editor de reglas. Es una manera rápida de crear una directiva de DLP.
  
### <a name="simple-settings"></a>Configuración simple

Sin lugar a dudas, el escenario más común de DLP es crear una directiva para ayudar a proteger el contenido que contiene información confidencial de la que se está compartiendo con personas fuera de la organización y tomar una acción correctiva automática como la restricción que se pueden obtener acceso al contenido, enviar notificaciones de administración o para el usuario final y el evento de investigación posterior de auditoría. Personas usan DLP para ayudar a evitar la divulgación accidental de información confidencial.
  
Para simplificar el proceso para conseguir este objetivo, cuando se crea una directiva de DLP, puede elegir la **configuración de uso simple**. Estas opciones proporcionan todo lo que necesita para implementar la directiva DLP más comunes, sin tener que ir en el editor de reglas.
  
![Opciones de DLP para la configuración simple y avanzada](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Configuración avanzada

Si necesita crear más directivas DLP personalizadas, puede elegir **Usar configuración avanzada**.
  
La configuración avanzada que incluyen con el editor de reglas, donde tiene control total sobre todas las opciones posibles, incluidos el recuento de la instancia y coinciden con exactitud (nivel de confianza) para cada regla.
  
Para saltar rápidamente a una sección, haga clic en un elemento en el panel de navegación superior del editor de reglas para ir a esa sección que aparece a continuación.
  
![Menú de exploración superior del editor de la regla DLP](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Plantillas de directiva de DLP

El primer paso en la creación de una directiva de DLP es elegir qué información va a proteger. A partir de una plantilla de DLP, guarde el trabajo de creación de un nuevo conjunto de reglas desde el principio y averiguar qué tipos de información se deberían incluir de forma predeterminada. A continuación, puede agregar a o modificar estos requisitos para ajustar la regla para satisfacer los requisitos específicos de su organización.
  
Una plantilla de directiva DLP preconfigurada puede ayudar a detectar tipos específicos de información confidencial, como datos HIPAA, datos PCI-DSS, datos de la Ley Gramm-Leach-Bliley o información personal identificable incluso específicas de configuración regional (P.I.). Para que sea fácil de encontrar y proteger tipos comunes de información confidencial, las plantillas de directiva incluidas en Office 365 ya contienen los tipos más comunes de información confidencial necesarios empezar a trabajar.
  
![Lista de plantillas para las directivas de prevención de pérdida de datos centrada en la plantilla de Patriot Act de EE. UU.](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
Su organización también puede tener sus propios requisitos específicos, en cuyo caso puede crear una directiva de DLP desde el principio, elija la opción de **directiva personalizada** . Una directiva personalizada está vacía y no contiene predefinidos reglas. 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>Implementar las directivas DLP gradualmente con el modo de prueba

Al crear las directivas de DLP, considere la posibilidad de implantar ellos gradualmente para evaluar su impacto y probar su eficacia antes de aplicarlas plenamente. Por ejemplo, no desea una nueva directiva de DLP por equivocación bloquear el acceso a miles de documentos que personas necesitan tener acceso a fin de realizar su trabajo.
  
Si está creando directivas de DLP con un gran impacto potencial, se recomienda seguir esta secuencia:
  
1. Informes de **Inicio en modo de prueba sin sugerencias de directiva** y, a continuación, usar el DLP e informa de cualquier incidente para evaluar el impacto. Puede usar informes de DLP para ver el número, la ubicación, el tipo y la gravedad de coincidencias de directivas. En función de los resultados, puede ajustar las reglas según sea necesario. En el modo de prueba, las directivas de DLP no afectará a la productividad de las personas que trabajan en su organización. 
    
2. **Mover a modo de prueba con las notificaciones y sugerencias de directivas** para que pueda comenzar a enseñar a los usuarios sobre las directivas de cumplimiento y prepararlos para las reglas que se van a aplicar. En esta fase, también puede pedir a los usuarios de informes falsos positivos para que puede restringir aún más las reglas. 
    
3. **Iniciar la aplicación completa de las directivas de** modo que se aplican las acciones en las reglas y el contenido protegido. Continuar supervisar los informes DLP y los informes de incidentes o notificaciones para asegurarse de que los resultados son lo que piensa. 
    
![Opciones para usar el modo de prueba y activar la directiva](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
Puede desactivar una directiva de DLP en cualquier momento, lo que afecta a todas las reglas en la directiva. Sin embargo, cada regla también se puede desactivar individualmente alternar su estado en el editor de reglas.
  
![Opciones para desactivar una regla de una directiva](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a>Informes de DLP

Después de crear y activar las directivas de DLP, desea asegurarse de que está funcionan según se destinados y ayudarle a que permanezca compatible. Con informes de DLP, puede ver rápidamente el número de directivas de DLP y regla coincide con el tiempo y el número de falsos positivos y reemplaza. Para cada informe, puede filtrar a las coincidencias por ubicación, plazo de tiempo e incluso se estrechan hacia abajo a una directiva específica, la regla o la acción.
  
Con los informes de DLP, puede obtener información de la empresa y:
  
- Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
- Descubra los procesos de negocio que infringen las directivas de cumplimiento de normas de la organización.
    
- Comprender cualquier impacto de negocio de las directivas DLP.
    
Además, puede usar los informes de DLP para ajustar sus directivas DLP mientras las ejecuta.
  
![Panel de informes en el centro de cumplimiento y seguridad](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Cómo funcionan las directivas DLP

DLP detecta información confidencial mediante un análisis profundo del contenido (no solo un análisis de texto simple). Este análisis profundo del contenido usa coincidencias de palabras clave, coincidencias de diccionario, la evaluación de expresiones regulares, funciones internas y otros métodos para detectar el contenido que coincide con las directivas DLP. Posiblemente solo un pequeño porcentaje de los datos se considera confidencial. Una directiva DLP puede identificar, supervisar y proteger automáticamente solo esos datos, sin obstaculizar o afectar a las personas que trabajan con el resto del contenido.
  
### <a name="policies-are-synced"></a>Las directivas se sincronizan

Después de crear una directiva de DLP en la seguridad &amp; centro de cumplimiento, tiene almacenados en un almacén central de directiva y, a continuación, se sincronizan con los diversos orígenes de contenido, incluidos:
  
- Exchange Online y desde allí a Outlook en la web y Outlook 2013 y versiones posteriores
    
- Sitios de OneDrive para la Empresa
    
- Sitios de SharePoint Online
    
- Programas de escritorio de Office 2016 (Excel 2016, PowerPoint 2016 y Word 2016)
    
Después de la directiva de sincronizado en las ubicaciones adecuadas, se inicia evaluar el contenido y aplicar acciones.
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Evaluación de la directiva en sitios de OneDrive para la Empresa y SharePoint Online

A través de todos los sitios de SharePoint Online y OneDrive para sitios de profesionales, están cambiando constantemente documentos — se continuamente que se crean, editado, compartida y así sucesivamente. Esto significa que los documentos pueden entrar en conflicto o ser compatibles con una directiva de DLP en cualquier momento. Por ejemplo, una persona puede cargar un documento que no contenga información confidencial a su sitio de grupo, pero más adelante, puede editar el mismo documento y agregarle información confidencial a otra persona.
  
Por este motivo, las directivas DLP buscan frecuentemente y en segundo plano coincidencias de directivas en los documentos. Puede considerarlo como una evaluación asincrónica de directiva.
  
Así es cómo funciona. Como las personas agregar o cambiar los documentos en sus sitios, el motor de búsqueda analiza el contenido, para que puedan buscar para él más adelante. Mientras que esto sucede, el contenido también se examina para información confidencial así como para comprobar si se comparte. Cualquier información confidencial que se encuentra se almacena de forma segura en el índice de búsqueda, para que sólo el equipo de cumplimiento puede tener acceso a, pero los usuarios no típicos. Cada directiva DLP que ha activado se ejecuta en segundo plano (asincrónicamente), aplicar acciones para proteger de pérdidas accidentales y comprobación de la búsqueda con frecuencia para cualquier contenido que coincide con una directiva.
  
![Diagrama que muestra cómo Directiva de DLP se evalúa como contenido de forma asincrónica](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
Por último, los documentos pueden entrar en conflicto con una directiva DLP, pero también pueden cumplir con una directiva DLP. Por ejemplo, si una persona agrega números de tarjeta de crédito a un documento, podría hacer que una directiva DLP bloquee el acceso al documento de forma automática. Pero si la persona elimina más adelante la información confidencial, la acción (en este caso, el bloqueo) se deshace automáticamente la próxima vez que se evalúa el documento con la directiva.
  
DLP se evalúa como cualquier contenido que se puede indizar. Para obtener más información sobre qué tipos de archivo se rastrean de forma predeterminada, vea [extensiones de nombre de archivo y tipos de archivo en SharePoint Server 2013 analizados predeterminados](https://go.microsoft.com/fwlink/p/?LinkID=627430).
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a>Evaluación de las directivas en Exchange Online, Outlook 2013 y versiones posteriores y Outlook en la web

Cuando se crea una directiva de DLP que incluye Exchange Online como una ubicación, la directiva de sincronizado desde la seguridad de Office 365 &amp; centro de cumplimiento a Exchange Online y, a continuación, desde Exchange Online a Outlook en la web y Outlook 2013 y versiones posteriores.
  
Cuando se va a redacta un mensaje en Outlook, el usuario puede ver sugerencias de directiva como el contenido que se está creando se evalúa con las directivas de DLP. Y después de que se envía un mensaje, se evalúa con las directivas de DLP como una parte normal de flujo de correo, junto con las reglas de transporte de Exchange y las directivas DLP creadas en el centro de administración de Exchange (vea la siguiente sección para obtener más información). Las directivas de DLP examen el mensaje y los datos adjuntos.
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a>Evaluación de la directiva en los programas de escritorio de Office 2016

Excel 2016, 2016 de PowerPoint y Word 2016 incluyen la misma capacidad para identificar la información confidencial y aplicar directivas de DLP como SharePoint Online y OneDrive para la empresa. Estos programas de Office 2016 sincronización sus directivas de DLP directamente desde el almacén de directivas central y, a continuación, evaluación el contenido con las directivas DLP de forma continua cuando los usuarios trabajan con los documentos abiertos desde un sitio que se incluye en una directiva de DLP.
  
Evaluación de directivas DLP en 2016 de Office está diseñado para afectar el rendimiento de los programas o la productividad de las personas que trabajan en contenido. Si está trabajando en un documento de gran tamaño, o el equipo del usuario está ocupado, puede tardar unos segundos en aparecer una sugerencia de directiva.
  
## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento de normas que va a crear directivas de DLP necesitan permisos a la seguridad &amp; centro de cumplimiento. De forma predeterminada, el Administrador de inquilinos tendrán acceso a esta ubicación y puede proporcionar responsables del cumplimiento normativo y otras personas el acceso a la seguridad &amp; centro de cumplimiento, sin conceder todos los permisos de un administrador de inquilinos. Para ello, se recomienda:
  
1. Crear un grupo en Office 365 y agregarle responsables de cumplimiento.
    
2. Crear un grupo de roles en la página **permisos** de la seguridad &amp; centro de cumplimiento. 
    
3. Agregar el grupo de Office 365 al grupo de roles.
    
Para obtener más información, consulte [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).
  
Estos permisos son necesarios solo para crear y aplicar una directiva de DLP. La aplicación de directivas no requiere acceso al contenido.
  
## <a name="find-the-dlp-cmdlets"></a>Busque los cmdlets DLP

Para utilizar la mayoría de los cmdlets para la seguridad &amp; centro de cumplimiento, necesita:
  
1. [Conectarse al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Use cualquiera de estas [Office 365 seguridad &amp; centro de cumplimiento cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Sin embargo, los informes de DLP necesitan extraer datos de a través de Office 365, como Exchange Online. Por este motivo, los cmdlets de para los informes DLP están disponibles en Exchange Online Powershell--no en seguridad &amp; Powershell de centro de cumplimiento. Por lo tanto, para usar los cmdlets de para los informes DLP, necesitará:
  
1. [Conectarse a Exchange Online con el PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Use cualquiera de estos cmdlets para los informes DLP:
    
  - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a>Más información

- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificaciones y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
    
- [Crear una directiva DLP para proteger documentos con FCI u otras propiedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
    
- [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md)
    
- [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md)
    


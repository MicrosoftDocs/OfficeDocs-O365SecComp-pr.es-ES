---
title: Directivas de supervisión de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Descripción de las directivas de supervisión en Office 365
ms.openlocfilehash: 0c76ba5b17277d8bd441810415e7e9acd1adbf36
ms.sourcegitcommit: 3cb775e60b3806b66568ed2f9664c17ef96ca8de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2019
ms.locfileid: "29603530"
---
# <a name="supervision-policies-in-office-365"></a>Directivas de supervisión de Office 365

Las directivas de supervisión de Office 365 le permiten capturar las comunicaciones de los empleados para un examen revisores designados. Puede definir directivas específicas que capturen el correo electrónico interno y externo, Microsoft Teams o 3rd fabricante communications en su organización. Los revisores, a continuación, pueden examinar los mensajes para asegurarse de que son compatibles con los estándares de mensajes de su organización y resolverlos con el tipo de clasificación. Estas directivas también pueden ayudar a superar los desafíos de cumplimiento moderno muchos, incluida la supervisión crecientes tipos de canales de comunicación, aumentar el volumen de datos de mensajes y cumplimiento normativas & el riesgo de multas.

En algunas organizaciones, puede haber una separación de tareas entre el grupo de administración de cumplimiento de normas y soporte técnico de TI. Office 365 admite la separación entre la configuración del inquilino con características de soporte técnico de directiva de supervisión y la configuración de directivas y que actúa en las comunicaciones capturadas. Por ejemplo, el grupo de TI para una organización puede ser responsable de la configuración de permisos de la función y grupos para admitir las directivas de supervisión que se configuran y administradas por el equipo de cumplimiento de normas de la organización.

## <a name="scenarios-for-supervision-policies"></a>Escenarios de directivas de supervisión

Las directivas de supervisión pueden prestar asistencia a la supervisión de las comunicaciones en su organización en varias áreas:

- **Directivas corporativas**

    Los empleados deben cumplir con uso aceptable, los estándares de protección de datos confidenciales y otras directivas corporativas en sus comunicaciones relacionadas con la empresa. Las directivas de supervisión pueden detectar infracciones de directivas y le ayudarán a tomar medidas correctivas para ayudar a mitigar estos tipos de incidentes. Por ejemplo, puede supervisar la organización de posibles infracciones de recursos humanos como acoso o el uso de lenguaje inadecuado u ofensivo en comunicaciones de los empleados.

- **Administración de riesgos**

    Las organizaciones son responsables de todas las comunicaciones distribuidas en toda la infraestructura y los sistemas de la red corporativa. Uso de directivas de supervisión para ayudar a identificar y administrar los riesgos y la exposición legal potencial puede ayudar a reducir los riesgos antes de que pueden dañar las operaciones corporativas. Por ejemplo, puede supervisar la organización para las comunicaciones no autorizadas de proyectos confidenciales como próximas adquisiciones, fusiones, información a revelar de utilidades, reorganizaciones o cambios de equipo de liderazgo.

- **Cumplimiento de normativas**

    La mayoría de las organizaciones deben cumplir con algún tipo de estándares de cumplimiento de normativas como parte de sus procedimientos de funcionamiento normales. A menudo estas normativas exigen a las organizaciones a implementar algún tipo de supervisión o proceso de supervisión para la mensajería es apropiado para su sector. La regla financieros del sector normativas autoridad (FINRA) 3110 es un buen ejemplo de un requisito para las organizaciones a disponer de procedimientos de supervisión para supervisar las actividades de sus empleados y los tipos de empresas en el que se activa. Otro ejemplo puede ser una necesidad de supervisar corredores / agentes en la organización para protegerse frente a posible blanqueo, privilegiada, colusión o actividades soborno. Las directivas de supervisión pueden ayudar a su organización a cumplir estos requisitos, ya que proporciona un proceso para supervisar e informe en las comunicaciones corporativas.

## <a name="feature-components"></a>Componentes de las características

### <a name="supervision-policy"></a>Directiva de supervisión

Va a crear directivas de supervisión en el centro de cumplimiento de seguridad &. Estas directivas definen las comunicaciones y los usuarios están sujetos a la revisión de la organización, definir condiciones personalizadas que deben cumplir las comunicaciones y especifica que debe llevar a cabo las revisiones. Los usuarios incluidos en la revisión de supervisión puede establecer grupo de roles de seguridad de las directivas y cualquier persona que tiene este rol asignado pueden tener acceso a la página de supervisión en el gobierno de datos en el centro de cumplimiento de seguridad de Office 365 &.

### <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar la supervisión, debe determinar quién tendrá sus comunicaciones revisado. En la directiva, para identificar los individuos o grupos de personas para supervisar, debe usar direcciones de correo electrónico del usuario. Algunos ejemplos de estos grupos son grupos de Office 365, listas de distribución basada en Exchange y canales de Microsoft Teams. También puede excluir usuarios o grupos específicos de supervisión que se incluyen dentro de un grupo de supervisión o una lista de grupos.

> [!IMPORTANT]
> Todos los usuarios supervisados por las directivas de supervisión deben tener una licencia de acceso E3 Enterprise de Office 365 con el complemento de cumplimiento avanzadas o estar incluidos en una suscripción a Office 365 Enterprise E5. Si no tiene un plan de empresa E5 existente y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Revisores

Cuando se crea una directiva de supervisión, también podrá determinar quién llevará a cabo las revisiones de los mensajes de los usuarios supervisados. En la directiva, usará las direcciones de correo electrónico del usuario para identificar los individuos o grupos de personas para revisar las comunicaciones.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuarios supervisados y revisores

Para simplificar el programa de instalación, crear grupos para las personas que tendrán su comunicación revisado y grupos para las personas que va a revisar las comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos distintos de personas, o si desea especificar un grupo que no se va a ser supervisados.

### <a name="supported-communication-types"></a>Tipos de comunicación compatibles

Con las directivas de supervisión, puede elegir para supervisar los mensajes en una o varias de las plataformas de comunicación siguientes:

- **Correo electrónico de exchange:** Buzones de correo que se hospedan en Exchange Online como parte de su suscripción de Office 365 son todos los aptos para la supervisión de mensaje. Mensajes de correo electrónico y datos adjuntos que coincidan con las condiciones de la directiva de supervisión están disponibles al instante para la supervisión y en los informes de supervisión. Tipos de datos adjuntos compatibles son:

    - Microsoft Word (.docx)
    - Microsoft Excel (.xlsx)
    - Microsoft PowerPoint (.pptx)

- **Equipos de Microsoft:** Comunicaciones de chat y los datos adjuntos asociados en los canales de Microsoft Teams públicos y privados y chats individuales pueden ser supervisados. Chats de los equipos que coincidan con las condiciones de la directiva de supervisión se procesan una vez cada 24 horas y, a continuación, están disponibles para la supervisión y en los informes de supervisión.
- **Orígenes de terceros:** Puede supervisar las comunicaciones de orígenes de terceros (como desde la lista desplegable o de Facebook) si se han importado estos datos a los buzones de correo de Office 365 en su organización. [Obtenga información sobre cómo importar datos de 3rd terceros a Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data).

### <a name="policy-settings"></a>Configuración de directivas

#### <a name="direction"></a>Dirección

De forma predeterminada, la condición **es la dirección** se muestra y no se puede quitar. Configuración de la dirección de comunicación en una directiva se puede elegir individualmente o juntos:

- **Entrante** : puede elegir **entrante** para revisar las comunicaciones que se envían **a** las personas que eligió para supervisar **de** personas no se incluyen en la directiva.
- **Salida** : **salida** puede elegir si desea revisar las comunicaciones que se envían **desde** las personas que eligió para supervisar **a** personas no se incluyen en la directiva.
- **Internal** - puede elegir **interno** para revisar comunicaciones enviadas **entre** las personas que ha identificado en la directiva.

#### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la directiva de supervisión. Tipos de información confidencial son ambos tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger los números de tarjeta de crédito, números de cuenta bancaria, los números de cuenta de passport y mucho más. Como parte de Office 365 [prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md), la configuración de información confidencial puede sacar provecho de patrones, proximidad de carácter, niveles de confianza y tipos de datos incluso personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial de forma predeterminada son:

- Financieros
- Salud y médicas
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los modelos incluidos en los tipos predeterminados, vea [Buscar qué tipos de información confidencial](what-the-sensitive-information-types-look-for.md).

#### <a name="custom-keyword-dictionaries"></a>Diccionarios personalizados de palabra clave

Configuración de diccionarios personalizados de palabra clave (o políticas) puede proporcionar una administración simple de palabras clave específicas de su organización o del sector y puede admitir hasta 100.000 términos por diccionario. Si es necesario, puede aplicar varios diccionarios personalizados de palabra clave a una sola directiva o tiene un diccionario de palabra clave única por directiva. Estos diccionarios se asignan en una directiva de supervisión y se pueden originar desde un archivo (por ejemplo, una lista .csv o .txt), o desde una lista, se puede [escribir directamente en un cmdlet de PowerShell](create-a-keyword-dictionary.md).

#### <a name="conditional-settings"></a>Configuración condicional

Las condiciones que elija para la directiva se aplicarán a las comunicaciones de correo electrónico y 3rd terceros orígenes en su organización (como desde la lista desplegable o de Facebook).

En la siguiente tabla se explica más acerca de cada condición.
  
|**Condición**|**Cómo usar esta condición**|
|:-----|:-----|
|Se recibe el mensaje de cualquiera de estos dominios  <br><br> No se recibe el mensaje de cualquiera de estos dominios | Para aplicar la directiva cuando determinados dominios se incluyen o excluyen en un mensaje recibido, escriba cada dominio y separe varios dominios con una coma. Cada dominio que especifique se aplicará por separado (se debe aplicar sólo uno de estos dominios para que la directiva que se debe aplicar al mensaje). |
|Mensaje se envía a cualquiera de estos dominios  <br><br> Mensaje no se envía a cualquiera de estos dominios | Para aplicar la directiva cuando determinados dominios se incluyen o excluyen en un mensaje enviado, escriba cada dominio y separe varios dominios con una coma. Cada dominio que especifique se aplicará por separado (se debe aplicar sólo uno de estos dominios para que la directiva que se debe aplicar al mensaje). |
|Los mensajes se clasifican con cualquiera de estas etiquetas repetidas  <br><br> Los mensajes no se clasifican con cualquiera de estas etiquetas repetidas | Para aplicar la directiva cuando ciertas etiquetas de retención se incluyen o excluyen en un mensaje. Etiquetas de retención se deben configurar por separado y se pueden elegir las etiquetas configuradas como parte de esta condición. Cada etiqueta que elija se aplicará por separado (sólo una de estas etiquetas se debe aplicar para que la directiva que se debe aplicar al mensaje). Para obtener más información acerca de cómo configurar las etiquetas de retención, consulte [información general de las etiquetas de retención](https://docs.microsoft.com/office365/securitycompliance/labels).|
|El mensaje contiene cualquiera de estas palabras  <br><br> El mensaje contiene ninguna de estas palabras | Para aplicar la directiva cuando ciertas palabras o frases se incluyen o excluyen en un mensaje, escriba cada palabra o frase en una línea independiente. Cada línea de las palabras que especifique se aplicará por separado (sólo una de estas líneas debe aplicar para que la directiva que se debe aplicar al mensaje). Para obtener más información sobre cómo especificar palabras o frases, vea la sección siguiente [coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos](supervision-policies.md#Matchwords).|
|Datos adjuntos contienen cualquiera de estas palabras  <br><br> Datos adjuntos no contienen ninguna de estas palabras | Para aplicar la directiva cuando ciertas palabras o frases se incluyen o excluyen en un datos adjuntos del mensaje (por ejemplo, un documento de Word), escriba cada palabra o frase en una línea independiente. Cada línea de las palabras que especifique se aplicará por separado (se debe aplicar sólo una línea para que la directiva que se debe aplicar a los datos adjuntos). Para obtener más información sobre cómo especificar palabras o frases, vea la sección siguiente [coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos](supervision-policies.md#Matchwords).|
|Datos adjuntos están cualquiera de estos tipos de archivo  <br><br> Datos adjuntos no son ninguno de estos tipos de archivo | Para supervisar las comunicaciones que incluyen o excluyan tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba estos en líneas separadas. Extensión de un único archivo adjunto debe coincidir para que aplicar la directiva.|
|El tamaño del mensaje es mayor que  <br><br> No es mayor que el tamaño de mensaje | Para revisar los mensajes según un determinado tamaño, use estas condiciones para especificar el tamaño máximo o mínimo que puede ser un mensaje antes de que esté sujeto a revisión. Por ejemplo, si especifica el **tamaño del mensaje es mayor que** \> **MB 1.0**, todos los mensajes que son 1.01 MB y será mayor estar sujeto a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
|Datos adjuntos son mayor que  <br><br> Datos adjuntos no son mayor que | Para revisar los mensajes según el tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo adjuntos puede ser antes de que el mensaje y sus datos adjuntos están sujetos a revisión. Por ejemplo, si especifica **los datos adjuntos son mayor que** \> **2,0 MB**, todos los mensajes con datos adjuntos MB 2.01 y realizarán más estar sujeto a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada línea de las palabras que especifique se aplicará por separado (se debe aplicar sólo una línea para que la condición de directiva que se debe aplicar al correo electrónico o datos adjuntos). Por ejemplo, vamos a usar la condición, **que mensaje contiene cualquiera de estas palabras**, con el bancario"palabras clave" y "privilegiada" en líneas separadas. La directiva se aplicará a todos los mensajes que incluye el bancario"word" o la frase "interno comerciales". Se debe producir solo una de estas palabras o frases para que esta condición de directiva que se debe aplicar. Las palabras en el mensaje o adjunto deben coincidir exactamente con lo que escribe.
  
##### <a name="entering-multiple-conditions"></a>Especificar varias condiciones

Si escribe varias condiciones, Office 365 usa todas las condiciones conjuntamente para determinar cuándo se debe aplicar la directiva a los elementos de comunicación. Cuando configura varias condiciones, todos se deben cumplir para que la directiva que se debe aplicar, a menos que especifique una excepción. Por ejemplo, supongamos que necesita para crear una directiva que se debe aplicar si un mensaje contiene la palabra "comercio" y es mayor que 2MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financiero", no debe aplicar la directiva. Por lo tanto, en este caso, las tres condiciones sería como sigue:
  
- **El mensaje contiene cualquiera de estas palabras**, con las palabras clave "comercial"

- **Tamaño del mensaje es mayor que**, con el valor 2 MB

- **El mensaje contiene ninguna de estas palabras**, con las palabras clave "Aprobado por el equipo financiero de Contoso".

#### <a name="review-percentage"></a>Porcentaje de revisión

Puede especificar un porcentaje de todas las comunicaciones que se rijan por una directiva de supervisión, si desea reducir la cantidad de contenido para revisar. Se seleccionará al azar esa cantidad de contenido en el porcentaje del total que cumple las condiciones que ha elegido. Si desea que los revisores para revisar todos los elementos, puede escribir **100%** en una directiva de supervisión.

## <a name="monitoring--managing"></a>Supervisión de administración de &

Supervisión de los resultados de las directivas de supervisión y aplicar una etiqueta de resolución es fácil y cómodo. Puede ver rápidamente el estado de los elementos revisados, los usuarios y grupos bajo supervisión y los usuarios y grupos designados como revisores.

### <a name="supervision-policy-dashboard"></a>Panel de la directiva de supervisión

La forma más sencilla para administrar los resultados de directivas de supervisión y resolver los elementos pendientes es usar el panel de la directiva de supervisión. Este panel permite a los revisores ver rápidamente los elementos que se deben revisarse, realizar acciones en un elemento y revise los resultados de anteriormente revisan y solucionado elementos para cada directiva de supervisión. Puede obtener acceso el panel de la directiva de supervisión en el centro de cumplimiento en la **supervisión**de seguridad de Office 365 & > *De su directiva personalizada* > **Open**.

#### <a name="dashboard-home"></a>Panel principal

La página **principal** del panel tiene varias secciones que le ayudarán a tomar medidas rápidamente sus directivas de supervisión. Aquí se puede:

- Revisar rápidamente los aspectos pendientes y resueltos para la semana
- Ver una lista de los usuarios supervisados y controlados grupos para la directiva seleccionada
- Ver una lista de los revisores y revisión de los equipos para la directiva seleccionada
- Vea qué plataformas de comunicación tienen contenido bajo supervisión para la directiva.

#### <a name="supervise-tab"></a>Supervisar la ficha

Donde los revisores pueden tomar medidas y resolver los elementos de la ficha **Supervise** se identifica por la directiva seleccionada. Aquí se puede:

- Filtrar por, compatible con, no es compatible y dudosos elementos pendientes
- Marcar un elemento único como compatible, no compatibles o dudosos. También puede registrar un comentario con el elemento para ayudar a aclarar el etiquetado acción realizada.
- Masiva marcar varios elementos como compatibles con, no compatibles o dudosos. También puede registrar un comentario con varios elementos para ayudar a aclarar el etiquetado acción realizada.
- Ver el historial de las etiquetas para un solo elemento, incluidos que resuelve el elemento, la fecha y hora de la acción, la etiqueta de la resolución y cualquier incluye comentarios.
- Volver a clasificar los elementos revisados anteriormente como dudosos, compatible con o que no son compatibles con. También puede registrar un comentario con uno o varios elementos para ayudar a aclarar la acción reclasificación realizada.

#### <a name="resolved-items-tab"></a>Resuelve la ficha elementos

La ficha **Elementos resuelto** es donde los revisores pueden ver todos los elementos anteriormente resueltos para la directiva seleccionada. Aquí se puede:

- Ver y ordenar el asunto, remitente y fecha de elementos resueltos rápidamente.
- Ver el historial de comentario y clasificación de cualquier elemento seleccionado

### <a name="other-ways-to-review-items"></a>Otros métodos para revisar los elementos

Si los revisores prefiere no usar el panel de supervisión en Office 365, también tienen otras opciones para revisar y administrar elementos recopilados por las directivas de supervisión.

#### <a name="outlook-on-the-web"></a>Outlook en la Web

Los usuarios designados como revisores en una directiva de supervisión pueden usar Outlook en la web para revisar y resuelven los elementos de supervisión. El complemento de supervisión se instala automáticamente en Outlook en el web para todos los revisores especificados en la directiva. No es necesario realizar ninguna configuración adicional por la organización para las carpetas de directiva shared de supervisión para que esté disponible para los revisores configurados.

Utilizando Outlook en el web, los revisores pueden:

- Ver los elementos filtrados por estado compatible, que no son compatibles con, dudoso y resuelto
- Marcar un solo elemento como compatible, que no son compatibles con, dudoso o resuelto. También puede registrar un comentario con el elemento para ayudar a aclarar el etiquetado acción realizada.
- Ver el historial de las etiquetas para un solo elemento, incluidos que resuelve el elemento, la fecha y hora de la acción, la etiqueta de la resolución y cualquier incluye comentarios.
- Volver a clasificar los elementos revisados anteriormente como dudosos, compatible con o que no son compatibles con. También puede registrar un comentario con elementos individuales para ayudar a aclarar la acción reclasificación realizada.

#### <a name="microsoft-outlook"></a>Microsoft Outlook

Para revisar communications identificado por una directiva de supervisión, los revisores también pueden utilizar el complemento de supervisión para Microsoft Outlook. Sin embargo, deben ejecutar los revisores a través de algunos pasos para instalar en la versión de escritorio de Outlook. Para obtener instrucciones detalladas acerca de cómo instalar el complemento de supervisión para Outlook, vea [Configurar directivas de supervisión](configure-supervision-policies.md).

Con Outlook, los revisores pueden:

- Ver los elementos filtrados por estado compatible, que no son compatibles con, dudoso y resuelto
- Marcar un solo elemento como compatible, que no son compatibles con, dudoso o resuelto. También puede registrar un comentario con el elemento para ayudar a aclarar el etiquetado acción realizada.
- Ver el historial de las etiquetas para un solo elemento, incluidos que resuelve el elemento, la fecha y hora de la acción, la etiqueta de la resolución y cualquier incluye comentarios.
- Volver a clasificar los elementos revisados anteriormente como dudosos, compatible con o que no son compatibles con. También puede registrar un comentario con elementos individuales para ayudar a aclarar la acción reclasificación realizada.

## <a name="reporting"></a>Informes

Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada directiva, también puede ver las estadísticas de live en el estado actual de la actividad de revisión. Puede usar los informes de supervisión para:
  
- Compruebe que las directivas se funcionan según lo previsto.
- Descubra cómo muchas comunicaciones se que se identifican para su revisión.
- Descubra cómo muchas comunicaciones no son compatibles y cuáles están pasando la revisión. Esta información puede ayudarle a decidir si se debe ajustar con precisión las directivas o cambiar el número de revisores.

### <a name="view-the-supervision-report"></a>Ver el informe de supervisión

1. Inicie sesión en la [seguridad & centro de cumplimiento](https://protection.office.com/) con las credenciales para una cuenta de administrador de la organización de Office 365 que tiene permisos para ver informes de supervisión.
2. Vaya a cualquiera de **los informes** \> **panel** o **supervisión**. Verá un widget con un resumen de la actividad actual de directiva de supervisión de informes de supervisión.
3. Seleccione el widget de **supervisión** para abrir la página de informe detallado.

> [!NOTE]
> Si no puede tener acceso a la página de **informes** , compruebe que se encuentra un miembro del grupo de roles de revisión de supervisión, tal como se describe en [realizar supervisión disponible en su organización](configure-supervision-policies.md). Que se incluye en este rol grupo le permite crea y administrar supervisión directivas y ejecuta el informe.
  
### <a name="how-to-use-the-report"></a>Cómo usar el informe

Cuando una directiva de supervisión identifica un mensaje de comunicación para su revisión, el correo electrónico se entrega en la carpeta de supervisión del revisor en Outlook y Outlook web app. Este informe muestra el nombre de la directiva y el número de comunicaciones en cada etapa del proceso de revisión.
  
Utilice el informe para:
  
- Ver los datos para todas o directivas específicas.
- Ver los datos agrupados por tipo de etiqueta (como compatible, Questionable, etc.), el revisor o el tipo de mensaje.
- Exportar datos a un archivo CSV en función de la fecha de la actividad, directiva y por actividad de revisor.
- Filtrar los datos según la fecha de actividad, tipo de etiqueta, revisor y tipo de mensaje.

Éste es un desglose de los valores que aparecen en la columna **tipo de etiqueta** .
  
|**Tipo de etiqueta**|**¿Qué significa**|
|:-----|:-----|
| No se ha revisado | El número de mensajes de correo electrónico que no se han revisado todavía. Estos mensajes de correo electrónico están en espera de revisión en el panel de supervisión de Office 365 o en la carpeta de supervisión del revisor en Outlook y Outlook Web App.|
| Compatible con | El número de mensajes de correo electrónico revisado y marcado como compatible. Estos mensajes aún es necesario resolver. |
| Dudosos | El número de mensajes de correo electrónico revisado y marca dudoso. Esto actúa como un indicador; otros revisores pueden ayudar a comprobar si un correo electrónico necesita investigación para cumplimiento de normas. Estos mensajes aún es necesario resolver. |
| No compatible (activo) | El número de mensajes de correo electrónico que no son compatibles con que actualmente están investigar los revisores. |
| No compatible (resuelto) | El número de mensajes de correo electrónico que no son compatibles con que investigar y resuelven los revisores. |
| Directiva de aciertos | El número total (diariamente) de los mensajes de Exchange, los equipos y los orígenes de datos de terceros que coincidieron con uno o más de las condiciones definidas en una directiva de supervisión |
| En Purview | El número total (diariamente) de los mensajes de Exchange, los equipos y orígenes de datos de terceros examinados por una directiva de supervisión |
| Resolver | El número total de mensajes de Exchange, los equipos y orígenes de datos de terceros que se han clasificado como **resuelto**|

> [!NOTE]
> En primer lugar se deben aprovisionar las directivas de supervisión antes de que aparecen en este informe. Además, si se eliminan las directivas, aún se muestran datos históricos. Sin embargo, están indicados como "directiva inexistente" y no está disponible la función **de exportación** .

## <a name="auditing"></a>Auditoría

En algunos casos, debe proporcionar información a las normativas o auditores de cumplimiento de normas para probar la supervisión de las actividades de los empleados y las comunicaciones. Esto puede resultar un resumen de todas las actividades de supervisión asociadas a una directiva definida o cada vez que se ha cambiado o se actualizó una directiva de supervisión. Las directivas de supervisión tienen registros de auditoría integradas para preparación completado para auditorías internas o externas. Prueba de procedimientos de supervisión pueda demostrar con un historial de auditoría detallada de cada acción supervisada por las directivas de supervisión.

Las siguientes actividades de directiva de supervisión se auditan y se pueden ver con los registros de auditoría de Office 365 unificados:

|**Actividad**|**Comandos asociados**|
|:-----|:-----|
| Creación de una directiva | Nueva SupervisoryReviewPolicy <br> Nueva SupervisoryReviewRule |
| Edición de una directiva | Set-SupervisoryReviewPolicy <br> Set-SupervisoryReviewRule |
| Eliminación de una directiva| Remove-SupervisoryReviewPolicy |

Las auditorías se pueden recuperar mediante la función de búsqueda de registro de auditoría unificadas o mediante el cmdlet de PowerShell de [Búsqueda UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) .

Por ejemplo, el siguiente ejemplo devuelve las actividades para el todas las revisiones de supervisión actividades (las directivas y reglas) y muestra información detallada para cada uno:

```
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"} | fl CreationDate,Operations,UserIds,AuditData 
```

Además de la información proporcionada en los informes de supervisión y los registros, también puede usar el cmdlet de PowerShell [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewactivity?view=exchange-ps) para devolver una lista detallada completa de la supervisión de todas las actividades de la directiva.

## <a name="ready-to-get-started"></a>¿Listo para empezar?

Para iniciar la configuración de directivas de supervisión para su organización, vea [Configurar directivas de supervisión](configure-supervision-policies.md).
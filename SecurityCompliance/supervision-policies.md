---
title: Directivas de supervisión en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Descripción de las directivas de supervisión en Office 365
ms.openlocfilehash: db0dedbbb41eef334165a4bde65c45a52d14299a
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900099"
---
# <a name="supervision-policies-in-office-365"></a>Directivas de supervisión en Office 365

Las directivas de supervisión en Office 365 permiten capturar comunicaciones de los empleados para que las examinen los revisores designados. Puede definir directivas específicas que capturen el correo electrónico interno y externo, Microsoft Teams o las comunicaciones de terceros de la organización. A continuación, los revisores pueden examinar los mensajes para asegurarse de que cumplen con los estándares de mensajes de la organización y los resuelven con el tipo de clasificación. Estas directivas también pueden ayudarle a superar muchos de los retos de cumplimiento modernos, incluidos la supervisión de tipos crecientes de canales de comunicación, el aumento del volumen de datos de mensajes y el cumplimiento de la reglamentación & el riesgo de las multas.

En algunas organizaciones, puede haber una separación de tareas entre el soporte de ti y el grupo de administración de cumplimiento. Office 365 admite la separación entre la configuración del espacio empresarial y las características de compatibilidad de la Directiva de supervisión, así como la configuración de directivas y la actuación en las comunicaciones capturadas. Por ejemplo, el grupo de TI de una organización puede ser responsable de configurar permisos de funciones y grupos para admitir directivas de supervisión configuradas y administradas por el equipo de cumplimiento de la organización.

## <a name="scenarios-for-supervision-policies"></a>Escenarios para directivas de supervisión

Las directivas de supervisión pueden ayudar a supervisar las comunicaciones en la organización en varias áreas:

- **Directivas corporativas**

    Los empleados deben cumplir con el uso aceptable, los estándares éticos y otras directivas corporativas en todas sus comunicaciones relacionadas con la empresa. Las directivas de supervisión pueden detectar infracciones de directivas y ayudarle a tomar medidas correctivas para ayudar a mitigar estos tipos de incidentes. Por ejemplo, puede supervisar a su organización las infracciones potenciales de recursos humanos, como acoso o el uso de lenguaje inadecuado o ofensivo en las comunicaciones de los empleados.

- **Administración de riesgos**

    Las organizaciones son responsables de todas las comunicaciones distribuidas en su infraestructura y en los sistemas de la red corporativa. El uso de directivas de supervisión para ayudar a identificar y administrar posibles exposiciones y riesgos legales puede ayudar a minimizar los riesgos antes de que puedan dañar las operaciones corporativas. Por ejemplo, puede supervisar la organización en busca de comunicaciones no autorizadas para proyectos confidenciales, como próximas adquisiciones, fusiones, divulgaciones de ingresos, reorganizaciones o cambios de equipo de liderazgo.

- **Cumplimiento normativo**

    La mayoría de las organizaciones deben cumplir con algún tipo de estándares de cumplimiento normativo como parte de los procedimientos de funcionamiento normales. Estas normativas a menudo requieren que las organizaciones implementen algún tipo de supervisión o proceso de supervisión para la mensajería que sea adecuada para su sector. La regla 3110 de la autoridad reguladora del sector financiero (FINRA) es un buen ejemplo de un requisito para que las organizaciones dispongan de procedimientos de supervisión para supervisar las actividades de sus empleados y los tipos de empresas en las que participa. Otro ejemplo podría ser una necesidad de supervisar a los corredores de bolsa de su organización para protegerse contra el blanqueo de dinero, la colusión o las actividades de soborno. Las directivas de supervisión pueden ayudar a su organización a cumplir estos requisitos proporcionando un proceso para supervisar y notificar en las comunicaciones corporativas.

## <a name="feature-components"></a>Componentes de características

### <a name="supervision-policy"></a>Directiva de supervisión

Creará directivas de supervisión en el centro de seguridad & cumplimiento. Estas directivas definen qué comunicaciones y usuarios están sujetos a revisión en su organización, define las condiciones personalizadas que deben cumplir las comunicaciones y especifica quién debe realizar revisiones. Los usuarios incluidos en el grupo de roles revisión de supervisión pueden configurar directivas y cualquier persona con este rol asignado puede tener acceso a la página supervisión en Gobierno de datos en el centro de seguridad & cumplimiento de Office 365.

### <a name="supervised-users"></a>Usuarios superVisados

Antes de empezar a usar la supervisión, deberá determinar quién tendrá las comunicaciones revisadas. En la Directiva, usará direcciones de correo electrónico de usuario para identificar personas o grupos de personas para supervisar. Algunos ejemplos de estos grupos son los grupos de Office 365, las listas de distribución basadas en Exchange y los canales de Microsoft Teams. También puede excluir de la supervisión a determinados usuarios o grupos que están incluidos en un grupo supervisado o en una lista de grupos.

> [!IMPORTANT]
> Los usuarios supervisados por directivas de supervisión deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción a Office 365 Enterprise E5.
Si no tiene un plan existente de Enterprise E5 y desea intentar la supervisión, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Reviewers

Cuando se crea una directiva de supervisión, también se determina quién realizará las revisiones de los mensajes de los usuarios supervisados. En la Directiva, usará direcciones de correo electrónico de usuario para identificar personas o grupos de personas para revisar las comunicaciones supervisadas.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuarios supervisados y revisores

Para simplificar la configuración, cree grupos para las personas que tendrán su comunicación revisada y grupos para las personas que revisarán esas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos de personas distintos, o si desea especificar un grupo que no va a supervisarse.

### <a name="supported-communication-types"></a>Tipos de comunicación admitidos

Con las directivas de supervisión, puede elegir supervisar los mensajes en una o varias de las plataformas de comunicación siguientes:

- **Correo electrónico de Exchange:** Los buzones que se hospedan en Exchange online como parte de su suscripción a Office 365 son aptos para la supervisión de mensajes. Los correos electrónicos y datos adjuntos que coinciden con las condiciones de la supervisión están disponibles instantáneamente para la supervisión y en los informes de supervisión. Los tipos de datos adjuntos compatibles para la supervisión son los mismos que los [tipos de archivo admitidos para las inspecciones de contenido de reglas de flujo de correo de Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).
- **Microsoft Teams:** Se pueden supervisar las comunicaciones de chat y los datos adjuntos asociados tanto en canales públicos y privados de Microsoft Teams como en chats individuales. Chats de Microsoft teams que cumplen las condiciones de directiva de supervisión se procesan una vez cada 24 horas y, a continuación, están disponibles para la supervisión y en los informes de supervisión. Use las siguientes configuraciones de administración de grupos para supervisar de forma eficaz los chats de usuarios individuales y las comunicaciones de canal en Microsoft Teams:

    - **Para la supervisión de chat de Microsoft Teams:** tendrá que asignar usuarios individuales o asignar un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de supervisión. Esto es para relaciones de usuario y chat entre 1 y 1 o entre 1 y muchos.
    - **Para las comunicaciones de canal de Teams:** tendrá que asignar cada canal de equipo de Microsoft o grupo de Office 365 que quiera supervisar y que contenga un usuario específico para la Directiva de supervisión. Si agrega el mismo usuario a otros canales de Microsoft Teams o a otros grupos de Office 365, asegúrese de agregar estos nuevos canales y grupos a la Directiva de supervisión.

- **Orígenes de terceros:** Puede supervisar las comunicaciones de orígenes de terceros (como en Facebook o DropBox) si ha importado estos datos en los buzones de Office 365 de la organización. [Obtenga información sobre cómo importar datos de terceros a Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data).

### <a name="policy-settings"></a>Configuración de directivas

#### <a name="direction"></a>Dirección

De forma predeterminada, la condición **es la dirección** se muestra y no se puede quitar. La configuración de la dirección de la comunicación en una Directiva puede elegirse de forma individual o conjunta:

- **Entrante** : puede elegir **entrante** para revisar las comunicaciones que se envían **a** las personas que ha elegido supervisar **de** las personas no incluidas en la Directiva.
- **Saliente** : puede elegir **saliente** si desea revisar las comunicaciones que se envían **de** las personas que ha elegido supervisar **a** las personas que no están incluidas en la Directiva.
- **Interna** : puede elegir **interna** para revisar las comunicaciones enviadas **entre** las personas que identificó en la Directiva.

#### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la Directiva de supervisión. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte, etc. Como parte de la prevención de [pérdida de datos (DLP)](data-loss-prevention-policies.md)de Office 365, la configuración de información confidencial puede aprovechar los patrones, la proximidad de caracteres, los niveles de confianza e incluso los tipos de datos personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial predeterminados son:

- Financieras
- Médico y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).

#### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizados

La configuración de diccionarios de palabras clave personalizados (o léxicos) puede proporcionar una administración sencilla de palabras clave específicas de la organización o del sector y puede admitir hasta 100.000 términos por Diccionario. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizados a una sola directiva o tener un diccionario de palabras clave único por directiva. Estos diccionarios se asignan en una directiva de supervisión y pueden ser origen de un archivo (por ejemplo, una lista. csv o. txt) o de una lista que se puede [importar en el centro de cumplimiento](create-a-keyword-dictionary.md).

#### <a name="conditional-settings"></a>Configuración condicional

Las condiciones que elija para la Directiva se aplicarán a las comunicaciones de los orígenes de correo electrónico y de terceros de la organización (como en Facebook o DropBox).

La siguiente tabla explica más sobre cada condición.
  
|**Condition**|**Cómo usar esta condición**|
|:-----|:-----|
|Se recibe el mensaje desde cualquiera de estos dominios  <br><br> No se recibe el mensaje desde ninguno de estos dominios | Para aplicar la Directiva cuando se incluyan o excluyan determinados dominios en un mensaje recibido, escriba cada dominio y separe varios dominios con una coma. Cada dominio que escriba se aplicará por separado (solo uno de estos dominios debe aplicarse para que la Directiva se aplique al mensaje). |
|El mensaje se envía a cualquiera de estos dominios  <br><br> El mensaje no se envía a ninguno de estos dominios | Para aplicar la Directiva cuando se incluyan o excluyan determinados dominios en un mensaje enviado, escriba cada dominio y separe varios dominios con una coma. Cada dominio que escriba se aplicará por separado (solo uno de estos dominios debe aplicarse para que la Directiva se aplique al mensaje). |
|El mensaje se clasifica con cualquiera de estas etiquetas  <br><br> El mensaje no está clasificado con ninguna de estas etiquetas | Para aplicar la Directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención se deben configurar por separado y las etiquetas configuradas se pueden elegir como parte de esta condición. Cada etiqueta que elija se aplicará por separado (solo una de estas etiquetas se debe aplicar para que la Directiva se aplique al mensaje). Para obtener más información acerca de la configuración de etiquetas de retención, consulte [Overview of Retention Labels](https://docs.microsoft.com/office365/securitycompliance/labels).|
|El mensaje contiene alguna de estas palabras  <br><br> El mensaje no contiene ninguna de estas palabras | Para aplicar la Directiva cuando se incluyan o excluyan ciertas palabras o frases en un mensaje, escriba cada palabra o frase en una línea independiente. Cada línea de palabras que escriba se aplicará por separado (solo se debe aplicar una de estas líneas para que la Directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
|Los datos adJuntos contienen alguna de estas palabras  <br><br> Los datos adJuntos no contienen ninguna de estas palabras | Para aplicar la Directiva cuando ciertas palabras o frases se incluyen o excluyen en datos adjuntos de un mensaje (como un documento de Word), escriba cada palabra o frase en una línea independiente. Cada línea de palabras que escriba se aplicará por separado (solo se debe usar una línea para que la directiva se aplique al dato adjunto). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
|Los datos adJuntos son cualquiera de estos tipos de archivo  <br><br> Datos adJuntos no es ninguno de estos tipos de archivo | Para supervisar las comunicaciones que incluyan o excluyan tipos de datos adjuntos específicos, escriba las extensiones de archivo (por ejemplo,. exe o. pdf). Si desea incluir o excluir varias extensiones de archivo, indíquela en líneas separadas. Solo una extensión de dato adjunto debe coincidir para aplicar la directiva.|
|El tamaño del mensaje es mayor que  <br><br> El tamaño del mensaje no es mayor que | Para revisar los mensajes según un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. por ejemplo, si especifica que **el tamaño del mensaje es superior a** \> **1,0 mb**, todos los mensajes que tengan 1,01 MB o más, estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
|El dato adjunto es mayor que  <br><br> Los datos adJuntos no tienen un tamaño superior a | Para revisar los mensajes en función del tamaño de los datos adjuntos, especifique el tamaño máximo o mínimo que pueden tener los datos adjuntos antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. por ejemplo, si especifica que el **dato adjunto es superior** \> a **2,0 mb**, todos los mensajes con datos adjuntos 2,01 MB o superior estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada línea de palabras que escriba se aplicará por separado (solo se debe usar una línea para que la condición de la directiva se aplique al correo electrónico o al dato adjunto). Por ejemplo, vamos a usar la condición, **Message contiene cualquiera de estas palabras**, con las palabras clave "Banker" y "Insider comercia" en líneas separadas. La Directiva se aplicará a todos los mensajes que incluyan la palabra "Banker" o la frase "comercio Insider". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o del archivo adjunto deben coincidir exactamente con lo que se especifique.
  
##### <a name="entering-multiple-conditions"></a>Especificar varias condiciones

Si especifica varias condiciones, Office 365 usa todas las condiciones para determinar cuándo debe aplicarse la Directiva a los elementos de comunicación. Al configurar varias condiciones, deben cumplirse todas para que la directiva se aplique, a menos que introduzca una excepción. Por ejemplo, supongamos que necesita crear una directiva que se debe aplicar si un mensaje contiene la palabra "Trade" y su tamaño es superior a 2 MB. Sin embargo, si el mensaje también contiene las palabras "aprobado por contoso Financial", la Directiva no debe aplicarse. Por lo tanto, en este caso, las tres condiciones serían las siguientes:
  
- El **mensaje contiene cualquiera de estas palabras**, con las palabras clave "Trade"

- El **tamaño del mensaje es mayor que**, con el valor de 2 MB

- El **mensaje no contiene ninguna de estas palabras**, con las palabras clave "aprobado por contoso Financial Team".

#### <a name="review-percentage"></a>Porcentaje de revisión

Puede especificar un porcentaje de todas las comunicaciones regidas por una directiva de supervisión si desea reducir la cantidad de contenido que se va a revisar. Seleccione de forma aleatoria la cantidad de contenido del porcentaje total que coincide con las condiciones que ha elegido. Si desea que los revisores revisen todos los elementos, puede escribir **100%** en una directiva de supervisión.

## <a name="monitoring--managing"></a>Supervisión & administración

Supervisar los resultados de las directivas de supervisión y aplicar una etiqueta de resolución es fácil y práctico. Puede ver rápidamente el estado de los elementos revisados, los usuarios y los grupos que están bajo la supervisión, así como los usuarios y grupos designados como revisores.

### <a name="supervision-policy-dashboard"></a>Panel de directivas de supervisión

La forma más sencilla de administrar los resultados de la Directiva de supervisión y resolver los elementos pendientes es usar el panel de directivas de supervisión. Este panel permite a los revisores ver rápidamente los elementos que se deben revisar, realizar acciones en un elemento y revisar los resultados de los elementos revisados y reparados anteriormente para cada directiva de supervisión. puede obtener acceso al panel directiva de supervisión en el centro de seguridad de Office 365 & en **supervisión** > *de la directiva* > personalizada**abierta**.

#### <a name="dashboard-home"></a>Página principal del panel

La página de **Inicio** del panel incluye varias secciones para ayudarle a tomar medidas rápidamente en sus directivas de supervisión. Aquí puede:

- Revisar rápidamente los resaltados pendientes y resueltos durante la semana
- Ver una lista de los usuarios supervisados y los grupos supervisados para la Directiva seleccionada
- Ver una lista de los revisores y revisar los equipos para la Directiva seleccionada
- Consulte Qué plataformas de comunicación tienen contenido bajo supervisión para la Directiva.

#### <a name="review-tab"></a>Pestaña revisión

La pestaña **revisar** es donde los revisores pueden realizar acciones y resolver los elementos identificados por la Directiva seleccionada. Aquí puede:

- Filtrar por elementos pendientes, compatibles, no compatibles y cuestionables
- Etiquete un solo elemento como compatible, no compatible o cuestionable. También puede grabar un comentario con el elemento para ayudar a aclarar la acción de etiquetado tomada.
- Etiquetas en masa varios elementos como compatibles, no compatibles o cuestionables. También puede grabar un comentario con varios elementos para ayudar a aclarar la acción de etiquetado que se realiza.
- Permite ver el historial de etiquetado de un elemento único, como, por ejemplo, quién resolvió el elemento, la fecha y la hora de la acción, la etiqueta de resolución y los comentarios incluidos.
- Reclasifique los elementos revisados anteriormente como compatibles, no compatibles o cuestionables. También puede grabar un comentario con uno o varios elementos para ayudar a aclarar la acción de reclasificación emprendida.

#### <a name="resolved-items-tab"></a>Ficha elementos resueltos

La ficha **elementos resueltos** es donde los revisores pueden ver todos los elementos resueltos previamente para la Directiva seleccionada. Aquí puede:

- Ver y ordenar rápidamente el asunto, el remitente y la fecha de los elementos resueltos.
- Ver el historial de comentarios y clasificación de cualquier elemento seleccionado

### <a name="other-ways-to-review-items"></a>Otras formas de revisar elementos

Si los revisores prefieren no usar el panel de supervisión en Office 365, también tienen otras opciones para revisar y administrar los elementos recopilados por las directivas de supervisión.

#### <a name="outlook-on-the-web"></a>Outlook en la Web

Los usuarios designados como revisores en una directiva de supervisión pueden usar Outlook en la web para revisar los elementos de supervisión y resolverlos. El complemento de supervisión se instala automáticamente en Outlook en la web para todos los revisores que ha especificado en la Directiva. La organización no necesita realizar ninguna configuración adicional para que las carpetas compartidas de directivas estén disponibles para los revisores configurados.

Con Outlook en la web, los revisores pueden:

- Ver elementos filtrados por estado conforme, no conforme, dudoso y resuelto
- Etiquete un solo elemento como compatible, no compatible, cuestionable o resuelto. También puede grabar un comentario con el elemento para ayudar a aclarar la acción de etiquetado tomada.
- Permite ver el historial de etiquetado de un elemento único, como, por ejemplo, quién resolvió el elemento, la fecha y la hora de la acción, la etiqueta de resolución y los comentarios incluidos.
- Reclasifique los elementos revisados anteriormente como compatibles, no compatibles o cuestionables. También puede grabar un comentario con elementos únicos para ayudar a aclarar la acción de reclasificación realizada.

#### <a name="microsoft-outlook"></a>Microsoft Outlook

Para revisar las comunicaciones identificadas por una directiva de supervisión, los revisores también pueden usar el complemento de supervisión para Microsoft Outlook. Sin embargo, los revisores deben ejecutarse a través de algunos pasos para instalarlo en la versión de escritorio de Outlook. Para obtener instrucciones detalladas acerca de la instalación del complemento de supervisión para Outlook, vea configure la [supervisión Policies](configure-supervision-policies.md).

Con Outlook, los revisores pueden:

- Ver elementos filtrados por estado conforme, no conforme, dudoso y resuelto
- Etiquete un solo elemento como compatible, no compatible, cuestionable o resuelto. También puede grabar un comentario con el elemento para ayudar a aclarar la acción de etiquetado tomada.
- Permite ver el historial de etiquetado de un elemento único, como, por ejemplo, quién resolvió el elemento, la fecha y la hora de la acción, la etiqueta de resolución y los comentarios incluidos.
- Reclasifique los elementos revisados anteriormente como compatibles, no compatibles o cuestionables. También puede grabar un comentario con elementos únicos para ayudar a aclarar la acción de reclasificación realizada.

## <a name="reporting"></a>Reporting

Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada Directiva, también puede ver estadísticas activas en el estado actual de la actividad de revisión. Puede usar los informes de supervisión para:
  
- Compruebe que las directivas funcionan según lo previsto.
- Averigüe cuántas comunicaciones se están identificando para su revisión.
- Averigüe cuántas comunicaciones no son compatibles y cuáles son las que pasan una revisión. Esta información puede ayudarle a decidir si debe ajustar las directivas o cambiar el número de revisores.

### <a name="view-the-supervision-report"></a>Ver el informe de supervisión

1. Inicie sesión en el [centro de seguridad _AMP_ cumplimiento](https://protection.office.com/) con las credenciales de una cuenta de administrador en la organización de Office 365 que tenga permisos para ver informes de supervisión.
2. Vaya a la **** \> **consola** de informes o a la **supervisión**. Verá un widget de informes de supervisión con un resumen de la actividad de la Directiva de supervisión actual.
3. Seleccione el widget de **supervisión** para abrir la página informe detallado.

> [!NOTE]
> Si no puede obtener acceso a la página de **informes** , compruebe que es miembro del grupo de roles revisión de supervisión, tal y como se describe en [hacer que la supervisión esté disponible en su organización](configure-supervision-policies.md). Si se incluye en este grupo de roles, podrá crear y administrar directivas de supervisión y ejecutar el informe.
  
### <a name="how-to-use-the-report"></a>Uso del informe

Cuando una directiva de supervisión identifica un mensaje de comunicación para revisión, el correo electrónico se entrega a la carpeta de supervisión del revisor en Outlook y en Outlook en la web (anteriormente conocido como Outlook Web App). Este informe muestra el nombre de cada directiva y el número de comunicaciones en cada fase del proceso de revisión.
  
Use el informe para:
  
- Ver los datos de todas las directivas o específicas.
- Ver datos agrupados por tipo de etiqueta (como conformes, dudosos, etc.), revisor o tipo de mensaje.
- Exportar datos a un archivo CSV en función de la fecha de actividad, la Directiva y la actividad de revisor.
- Filtrar datos según la fecha de la actividad, el tipo de etiqueta, el revisor y el tipo de mensaje.

Este es un desglose de los valores que puede ver en la columna **tipo de etiqueta** .
  
|**Tipo de etiqueta**|**Qué significa**|
|:-----|:-----|
| No revisado | El número de correos electrónicos que todavía no se han revisado. Estos mensajes de correo electrónico están pendientes de revisión en el panel de supervisión de Office 365 o en la carpeta supervisión del revisor en Outlook/Outlook en la web
| Compliant | Número de mensajes de correo electrónico revisados y marcados como compatibles. Estos mensajes todavía deben resolverse. |
| Questionable | Número de correos electrónicos revisados y marcados como cuestionables. Esto actúa como una marca; otros revisores pueden ayudarle a comprobar si un correo electrónico necesita investigar el cumplimiento. Estos mensajes todavía deben resolverse. |
| No compatible (activo) | El número de correos electrónicos no compatibles que los revisores están investigando en este momento. |
| No compatible (resuelto) | El número de correos electrónicos no compatibles que los revisores han investigado y resuelto. |
| Directiva de visitas | Número total (diario) de mensajes de Exchange, Teams y orígenes de datos de terceros que coinciden con una o varias condiciones definidas en una directiva de supervisión |
| En ámbito | Número total (diario) de mensajes de Exchange, Teams y orígenes de datos de terceros examinados mediante una directiva de supervisión |
| Resuelto | El número total de mensajes de Exchange, Teams y orígenes de datos de terceros que se han clasificado como **resueltos**|

> [!NOTE]
> Las directivas de supervisión deben aprovisionarse primero antes de que aparezcan en este informe. Además, si se eliminan directivas, aún se muestran los datos históricos. Sin embargo, se indican como una "Directiva no existente" y la función de **exportación** no está disponible.

## <a name="auditing"></a>Auditoría

En algunos casos, deberá proporcionar información a auditores de cumplimiento normativos o de cumplimiento para probar la supervisión de las comunicaciones y las actividades de los empleados. Esto puede ser un resumen de todas las actividades de supervisión asociadas con una directiva definida o cada vez que se cambia o se actualiza una directiva de supervisión. Las directivas de supervisión tienen pistas de auditoría integradas para disponer de una preparación completa de las auditorías internas o externas. Se puede demostrar la prueba de los procedimientos de supervisión con un historial de auditoría detallado de cada acción supervisada por las directivas de supervisión.

Las siguientes actividades de directiva de supervisión se auditan y se pueden ver con los registros de auditoría de Office 365 unificados:

|**Actividad**|**Comandos asociados**|
|:-----|:-----|
| Creación de una directiva | [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| Edición de una directiva | [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| Eliminación de una directiva| [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |
| Ver una directiva | [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2) |

Las auditorías se pueden recuperar con la función de búsqueda de registros de auditoría unificada o mediante el cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell.

Por ejemplo, en el siguiente ejemplo se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas) y se enumera la información detallada de cada uno de los elementos siguientes:

```
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

Además de la información proporcionada en los informes y registros de supervisión, también puede usar el cmdlet de PowerShell [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) para obtener una lista detallada completa de todas las actividades de la Directiva de supervisión.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para empezar a configurar las directivas de supervisión para su organización, consulte [Configure tutela Policies](configure-supervision-policies.md).
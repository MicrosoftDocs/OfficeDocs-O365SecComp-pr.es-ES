---
title: Directivas de supervisión en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
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
description: Obtenga información sobre las directivas de supervisión en Office 365
ms.openlocfilehash: 3259620e16b626c81c9c0f71f7be1f627e9c6bc9
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490767"
---
# <a name="supervision-policies-in-office-365"></a>Directivas de supervisión en Office 365

Las directivas de supervisión en Office 365 permiten capturar comunicaciones de los empleados para que las examinen los revisores designados. Puede definir directivas específicas que capturen el correo electrónico interno y externo, Microsoft Teams o las comunicaciones de terceros de la organización. A continuación, los revisores pueden examinar los mensajes para asegurarse de que cumplen con los estándares de mensajes de la organización y los resuelven con el tipo de clasificación. 

Estas directivas también pueden ayudarle a superar muchos de los retos de cumplimiento modernos, entre los que se incluyen:

- Supervisión de tipos cada vez mayores de canales de comunicación
- El volumen creciente de los datos de los mensajes
- Cumplimiento normativo & el riesgo de las multas

En algunas organizaciones, puede haber una separación de tareas entre el soporte de ti y el grupo de administración de cumplimiento. Office 365 admite la separación entre la configuración de características de la Directiva de supervisión y la configuración de directivas para las comunicaciones capturadas. Por ejemplo, el grupo de TI de una organización puede ser responsable de configurar permisos de funciones y grupos para admitir directivas de supervisión configuradas y administradas por el equipo de cumplimiento de la organización.

Para obtener una introducción rápida a las directivas de supervisión, vea el vídeo sobre la [Directiva de supervisión](https://youtu.be/C3Y8WZ7o_dI) en el canal de [mecánica de Microsoft](https://www.youtube.com/user/OfficeGarageSeries).

Para obtener más información acerca de las mejoras y la disponibilidad de las próximas características de supervisión, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="scenarios-for-supervision-policies"></a>Escenarios para directivas de supervisión

Las directivas de supervisión pueden ayudar a supervisar las comunicaciones en la organización en varias áreas:

- **Directivas corporativas**

    Los empleados deben cumplir con el uso aceptable, los estándares éticos y otras directivas corporativas en todas sus comunicaciones relacionadas con la empresa. Las directivas de supervisión pueden detectar infracciones de directivas y ayudarle a tomar medidas correctivas para ayudar a mitigar estos tipos de incidentes. Por ejemplo, puede supervisar a su organización las infracciones potenciales de recursos humanos, como acoso o el uso de lenguaje inadecuado o ofensivo en las comunicaciones de los empleados.

- **Administración de riesgos**

    Las organizaciones son responsables de todas las comunicaciones distribuidas en su infraestructura y en los sistemas de la red corporativa. El uso de directivas de supervisión para ayudar a identificar y administrar posibles exposiciones y riesgos legales puede ayudar a minimizar los riesgos antes de que puedan dañar las operaciones corporativas. Por ejemplo, puede supervisar la organización en busca de comunicaciones no autorizadas para proyectos confidenciales, como próximas adquisiciones, fusiones, divulgaciones de ingresos, reorganizaciones o cambios de equipo de liderazgo.

- **Cumplimiento normativo**

    La mayoría de las organizaciones deben cumplir con algún tipo de estándares de cumplimiento normativo como parte de los procedimientos de funcionamiento normales. Estas normativas a menudo requieren que las organizaciones implementen algún tipo de supervisión o proceso de supervisión para la mensajería que sea adecuada para su sector. La regla 3110 de la autoridad reguladora del sector financiero (FINRA) es un buen ejemplo de un requisito para que las organizaciones dispongan de procedimientos de supervisión para supervisar las actividades de sus empleados y los tipos de empresas en las que participa. Otro ejemplo podría ser una necesidad de supervisar a los corredores de bolsa de su organización para protegerse contra el blanqueo de dinero, la colusión o las actividades de soborno. Las directivas de supervisión pueden ayudar a su organización a cumplir estos requisitos proporcionando un proceso para supervisar y notificar en las comunicaciones corporativas.

## <a name="components"></a>Componentes

### <a name="supervision-policy"></a>Directiva de supervisión

Las directivas de supervisión se crean en el centro de cumplimiento. Estas directivas definen qué comunicaciones y usuarios están sujetos a revisión en su organización, define las condiciones personalizadas que deben cumplir las comunicaciones y especifica quién debe realizar revisiones. Los usuarios incluidos en el grupo de roles revisión de supervisión pueden configurar directivas y cualquier persona con este rol asignado puede tener acceso a la página supervisión en el centro de cumplimiento.

### <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar la supervisión, debe determinar quién necesita que se revisen sus comunicaciones. En la Directiva, las direcciones de correo electrónico de usuario identifican a los individuos o grupos de personas que deben supervisarse. Algunos ejemplos de estos grupos son los grupos de Office 365, las listas de distribución basadas en Exchange y los canales de Microsoft Teams. También puede excluir determinados usuarios o grupos de la supervisión con un grupo supervisado o una lista de grupos.

> [!IMPORTANT]
> Los usuarios supervisados por directivas de supervisión deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción a Office 365 Enterprise E5. Si no tiene un plan existente de Enterprise E5 y desea intentar la supervisión, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Reviewers

Al crear una directiva de supervisión, debe determinar quién realizará las revisiones de los mensajes de los usuarios supervisados. En la Directiva, las direcciones de correo electrónico de usuario identifican personas o grupos de personas para revisar las comunicaciones supervisadas. Todos los revisores deben tener buzones hospedados en Exchange Online.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuarios supervisados y revisores

Para simplificar la configuración, cree grupos para los usuarios que necesitan sus comunicaciones revisadas y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos de personas distintos, o si desea especificar un grupo que no está supervisado.

Cuando se selecciona un grupo de Office 365 para los usuarios supervisados, la Directiva supervisa el contenido del buzón de correo de Office 365 compartido y los canales de Microsoft Teams asociados con el grupo. Al seleccionar una lista de distribución, la Directiva supervisa los buzones de usuario individuales.

### <a name="supported-communication-types"></a>Tipos de comunicación admitidos

Con las directivas de supervisión, puede elegir supervisar los mensajes en una o varias de las plataformas de comunicación siguientes:

- **Correo electrónico de Exchange:** Los buzones hospedados en Exchange online como parte de su suscripción a Office 365 son válidos para la supervisión de mensajes. Los correos electrónicos y datos adjuntos que coinciden con las condiciones de la supervisión están disponibles instantáneamente para la supervisión y en los informes de supervisión. Los tipos de datos adjuntos compatibles para la supervisión son los mismos que los [tipos de archivo admitidos para las inspecciones de contenido de reglas de flujo de correo de Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Microsoft Teams:** Se pueden supervisar las comunicaciones de chat y los datos adjuntos asociados tanto en canales públicos y privados de Microsoft Teams como en chats individuales. Chats de Microsoft teams que cumplen las condiciones de directiva de supervisión se procesan una vez cada 24 horas y, a continuación, están disponibles para la supervisión y en los informes de supervisión. Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Microsoft Teams:

    - **Para supervisar los chats de Microsoft Teams:** Asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de supervisión. Esto es para relaciones de usuario y chat de 1 a 1 o de uno a varios.
    - **Para las comunicaciones de canal de Teams:** Asigne cada canal de Microsoft Teams o grupo de Office 365 que desee supervisar que contenga un usuario específico a la Directiva de supervisión. Si agrega el mismo usuario a otros canales de Microsoft Teams o a otros grupos de Office 365, asegúrese de agregar estos nuevos canales y grupos a la Directiva de supervisión.

- **Skype empresarial online:** Las comunicaciones de chat y los datos adjuntos asociados en Skype empresarial online pueden supervisarse. Chats de Skype empresarial online las condiciones de la Directiva de supervisión se procesan una vez cada 24 horas y, a continuación, están disponibles para la supervisión y en los informes de supervisión. Las conversaciones de chat supervisadas se han originado a partir de [conversaciones anteriores guardadas en Skype empresarial online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de los usuarios en Skype empresarial online:

    - **Para la supervisión de chats de Skype empresarial online:** Asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de supervisión. Esto es para relaciones de usuario y chat de 1 a 1 o de uno a varios.

- **Orígenes de terceros:** Puede supervisar las comunicaciones de orígenes de terceros (como en Facebook o DropBox) para los datos que se importan a los buzones de correo de Office 365 de la organización. [Obtenga información sobre cómo importar datos de terceros a Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data).

Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios dejan su organización y se elimina su buzón de correo.

### <a name="policy-settings"></a>Configuración de directivas

#### <a name="direction"></a>Dirección

De forma predeterminada, la condición **es la dirección** se muestra y no se puede quitar. La configuración de la dirección de la comunicación en una directiva se eligen de forma individual o conjunta:

- **Entrante**: puede elegir **entrante** para revisar las comunicaciones enviadas **a** las personas que haya elegido supervisar **de** las personas que no estén incluidas en la Directiva.
- **Saliente**: puede elegir **salida** si desea revisar las comunicaciones enviadas **por** las personas que ha elegido para supervisar **a** personas no incluidas en la Directiva.
- **Interno**: puede elegir **interna** para revisar las comunicaciones enviadas **entre** las personas que identificó en la Directiva.

#### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la Directiva de supervisión. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte, etc. Como parte de la prevención de [pérdida de datos (DLP)](data-loss-prevention-policies.md)de Office 365, la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar contenido que pueda ser confidencial. Los tipos de información confidencial predeterminados son:

- Financieras
- Médico y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).

#### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizados

Configure diccionarios de palabras clave personalizados (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de la organización o del sector. Los diccionarios de palabras clave admiten hasta 100.000 términos por Diccionario. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizados a una sola directiva o tener un diccionario de palabras clave único por directiva. Estos diccionarios se asignan en una directiva de supervisión y pueden ser origen de un archivo (por ejemplo, una lista. csv o. txt) o de una lista que se puede [importar en el centro de cumplimiento](create-a-keyword-dictionary.md).

#### <a name="offensive-language"></a>Lenguaje ofensivo

Supervisar los mensajes de correo electrónico enviados o recibidos de la organización en busca de lenguaje ofensivo. El modelo usa una combinación de aprendizaje automático, inteligencia artificial y palabras clave para identificar el idioma en los mensajes de correo electrónico que puedan infringir las directivas de Antiacoso y acosos. El modelo de lenguaje ofensivo admite en este momento palabras clave en inglés y supervisa el cuerpo de los mensajes de correo electrónico.

> [!NOTE]
> Cree una [Directiva de prevención de pérdida de datos](create-test-tune-dlp-policy.md) con un [Diccionario de palabras clave personalizado](create-a-keyword-dictionary.md) de términos bloqueados si necesita:
>
> - supervisar las comunicaciones de Microsoft Teams en su organización en busca de lenguaje ofensivo
> - impedir o bloquear el idioma ofensivo en las comunicaciones de la organización

Tenga en cuenta que el modelo no proporciona una lista exhaustiva de lenguaje ofensivo. Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho a actualizar el modelo según su criterio. Aunque el modelo puede ayudar a su organización a supervisar el lenguaje ofensivo, el modelo no está destinado a proporcionar a los únicos medios de la organización la supervisión o el direccionamiento de ese idioma. La organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con la supervisión y el bloqueo del lenguaje ofensivo.

El modelo de lenguaje ofensivo supervisa el correo electrónico en busca de la opinión asociada a los siguientes tipos de lenguaje:

|**Tipo**|**Descripción**|
|:-----|:-----|
| **Palabras soeces** | Expresiones que avergonzan a la mayoría de los usuarios. |
| **Slurs** | Expresiones que expresan el obstáculo contra determinados grupos (por ejemplo, raza, étnicos, orientación sexual, discapacidad). |
| **Taunts** | Las expresiones que taunt, condemn, Ridicule o podrían causar potencialmente el enojo o la violencia. |
| **Expresiones disfrazadas** | Expresiones cuyo significado o pronunciación es el mismo que otro término ofensivo. |

#### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la Directiva se aplican a las comunicaciones de los orígenes de correo electrónico y de terceros de la organización (como en Facebook o DropBox).

La siguiente tabla explica más sobre cada condición.
  
|**Condición**|**Cómo usar esta condición**|
|:-----|:-----|
| **Se recibe el mensaje desde cualquiera de estos dominios**  <br><br> **No se recibe el mensaje desde ninguno de estos dominios** | Aplicar la Directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe los distintos dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico que se escriba se aplica por separado, solo se debe solicitar un dominio o una dirección de correo electrónico para que la Directiva se aplique al mensaje. <br><br> Si desea supervisar todo el correo electrónico de un dominio específico pero desea excluir los mensajes que no necesitan revisión (boletines, anuncios, etc.), debe configurar la condición **en que no se recibe un mensaje desde ninguna de estas** condiciones de dominio que excluye el Dirección de correo electrónico (ejemplo "newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplicar la Directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe los distintos dominios o direcciones de correo electrónico con una coma. Cada dirección de correo electrónico o dominio se aplica por separado, solo se debe solicitar un dominio o una dirección de correo electrónico para que la Directiva se aplique al mensaje. <br><br> Si desea supervisar todo el correo electrónico enviado a un dominio específico pero desea excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - **Se envía un mensaje a cualquiera de estas condiciones de los dominios** que define el dominio ("contoso.com") y <br> -Un **mensaje no se envía a ninguna condición de dominio** que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no está clasificado con ninguna de estas etiquetas** | Para aplicar la Directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención se deben configurar por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo una de estas etiquetas se debe aplicar para que la Directiva se aplique al mensaje). Para obtener más información acerca de la configuración de etiquetas de retención, consulte [Overview of Retention Labels](https://docs.microsoft.com/office365/securitycompliance/labels).|
| **El mensaje contiene alguna de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la Directiva cuando se incluyan o excluyan ciertas palabras o frases en un mensaje, escriba cada palabra o frase en una línea independiente. Cada línea de palabras que escriba se aplica por separado (solo se debe aplicar una de estas líneas para que la Directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Los datos adjuntos contienen alguna de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la Directiva cuando ciertas palabras o frases se incluyen o excluyen en datos adjuntos de un mensaje (como un documento de Word), escriba cada palabra o frase en una línea independiente. Cada línea de palabras que escriba se aplica por separado (solo se debe aplicar una línea para que la Directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo**  <br><br> **Datos adjuntos no es ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyan o excluyan tipos de datos adjuntos específicos, escriba las extensiones de archivo (por ejemplo,. exe o. pdf). Si desea incluir o excluir varias extensiones de archivo, indíquela en líneas separadas. Para que se aplique la Directiva, solo debe coincidir una extensión de datos adjuntos.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes según un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. Por ejemplo, si especifica que **el tamaño del mensaje es superior a** \> **1,0 MB**, todos los mensajes que tengan 1,01 MB o más, estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **El dato adjunto es mayor que**  <br><br> **Los datos adjuntos no tienen un tamaño superior a** | Para revisar los mensajes en función del tamaño de los datos adjuntos, especifique el tamaño máximo o mínimo que pueden tener los datos adjuntos antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si especifica que el **dato adjunto es superior** \> a **2,0 MB**, todos los mensajes con datos adjuntos 2,01 MB y sobre estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"></a> Cada línea de palabras que escriba se aplica por separado (solo se debe aplicar una línea para que la condición de la Directiva se aplique al correo electrónico o datos adjuntos). Por ejemplo, vamos a usar la condición, **Message contiene cualquiera de estas palabras**, con las palabras clave "Banker" y "Insider comercia" en líneas separadas. La Directiva se aplica a todos los mensajes que incluyan la palabra "Banker" o la frase "comercio Insider". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o del archivo adjunto deben coincidir exactamente con lo que se especifique.

Para analizar los mensajes de correo electrónico y los datos adjuntos de las mismas palabras clave, cree una [Directiva de prevención de pérdida de datos](create-test-tune-dlp-policy.md) con un diccionario de [palabras clave personalizado](create-a-keyword-dictionary.md) para los términos que desea supervisar. Esta configuración de directiva identifica las palabras clave definidas que aparecen en el mensaje de correo electrónico **o** en los datos adjuntos del correo electrónico. El uso de la configuración de directivas condicionales estándar (el*mensaje contiene alguna de estas palabras* y el *archivo adjunto contiene alguna de estas palabras*) para identificar los términos de los mensajes y **** en los datos adjuntos requiere que los términos estén presentes en el mensaje y en el datos adjuntos.
  
##### <a name="enter-multiple-conditions"></a>Escribir varias condiciones

Si especifica varias condiciones, Office 365 usa todas las condiciones para determinar cuándo debe aplicarse la Directiva a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la Directiva, a menos que se especifique una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "Trade" y su tamaño es superior a 2 MB. Sin embargo, si el mensaje también contiene las palabras "aprobado por contoso Financial", la Directiva no debe aplicarse. Por lo tanto, en este caso, las tres condiciones serían las siguientes:
  
- El **mensaje contiene cualquiera de estas palabras**, con las palabras clave "Trade"

- El **tamaño del mensaje es mayor que**, con el valor de 2 MB

- El **mensaje no contiene ninguna de estas palabras**, con las palabras clave "aprobado por el equipo financiero de Contoso"

#### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regidas por una directiva de supervisión. Se selecciona un ejemplo aleatorio en tiempo real del contenido del porcentaje total de contenido que coincide con las condiciones de la directiva elegida. Si desea que los revisores revisen todos los elementos, puede escribir **100%** en una directiva de supervisión.

## <a name="monitor--manage"></a>Supervisar & administrar

Es fácil supervisar los resultados de las directivas de supervisión y aplicar una etiqueta de resolución. Puede ver rápidamente:

- El estado de los elementos revisados
- Usuarios y grupos bajo supervisión
- Usuarios y grupos designados como revisores

### <a name="supervision-policy-dashboard"></a>Panel de directivas de supervisión

Use el panel de directivas de supervisión para administrar los resultados de la Directiva de supervisión y para resolver los elementos pendientes. Este panel permite a los revisores ver los elementos que se deben revisar, actuar en un elemento y revisar los resultados de los elementos revisados y resueltos anteriormente para cada directiva de supervisión. Puede tener acceso al panel Directiva de supervisión en el centro de cumplimiento al **supervisar** > *la Directiva* > personalizada**abierta**.

#### <a name="dashboard-home"></a>Página principal del panel

La página de **Inicio** del panel tiene varias secciones para ayudarle a actuar rápidamente en sus directivas de supervisión. Aquí puede:

- Revisar rápidamente los resaltados pendientes y resueltos durante la semana
- Ver una lista de los usuarios supervisados y los grupos supervisados para la Directiva seleccionada
- Ver una lista de los revisores y revisar los equipos para la Directiva seleccionada
- Ver qué plataformas de comunicación tienen contenido bajo supervisión para la Directiva

#### <a name="review-tab"></a>Pestaña revisión

La pestaña **revisar** es donde los revisores clasifican y resuelven los elementos identificados por la Directiva seleccionada. Aquí puede:

- Filtrar por elementos pendientes, compatibles, no compatibles y dudosos.
- Etiquete un solo elemento como compatible, no compatible o cuestionable. También puede grabar un comentario con el elemento para ayudar a aclarar la acción de etiquetado tomada.
- Etiquetas en masa varios elementos como compatibles, no compatibles o cuestionables. También puede grabar un comentario con varios elementos para ayudar a aclarar la acción de etiquetado que se realiza.
- Permite ver el historial de la etiqueta de un solo elemento. Incluye quién resolvió el elemento, la fecha y la hora de la acción, la etiqueta de resolución y los comentarios incluidos.
- Reclasifique los elementos revisados anteriormente como compatibles, no compatibles o cuestionables. También puede grabar un comentario con uno o varios elementos para ayudar a aclarar la acción de reclasificación emprendida.

#### <a name="resolved-items-tab"></a>Ficha elementos resueltos

La ficha **elementos resueltos** es donde los revisores pueden ver todos los elementos resueltos previamente para la Directiva seleccionada. Aquí puede:

- Ver y ordenar rápidamente el asunto, el remitente y la fecha de los elementos resueltos
- Ver el historial de comentarios y clasificación de cualquier elemento seleccionado

## <a name="reports"></a>Informes

Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada Directiva, también puede ver estadísticas activas en el estado actual de la actividad de revisión. Puede usar los informes de supervisión para:
  
- Compruebe que las directivas funcionan según lo previsto.
- Averigüe cuántas comunicaciones necesitan revisarse.
- Averigüe cuántas comunicaciones no son compatibles y cuáles son las que pasan una revisión. Esta información puede ayudarle a decidir si debe ajustar las directivas o cambiar el número de revisores.

### <a name="view-the-supervision-report"></a>Ver el informe de supervisión

1. Inicie sesión en el [centro de cumplimiento](https://compliance.microsoft.com) con credenciales para una cuenta de administrador con permisos para ver informes de supervisión.
2. Vaya a la **** \> **consola** de informes o a la **supervisión** para ver el widget supervisión de informes para ver un resumen de la actividad de la Directiva de supervisión actual.
3. Seleccione el widget de **supervisión** para abrir la página informe detallado.

> [!NOTE]
> Si no puede obtener acceso a la página de **informes** , compruebe que es miembro del grupo de roles revisión de supervisión, tal y como se describe en [hacer que la supervisión esté disponible en su organización](configure-supervision-policies.md). La inclusión en este grupo de roles permite crear y administrar directivas de supervisión y ejecutar el informe.
  
### <a name="how-to-use-the-report"></a>Uso del informe

Este informe enumera cada directiva y el número de comunicaciones en cada fase del proceso de revisión. Use el informe para:
  
- Ver los datos de todas las directivas o específicas.
- Ver datos agrupados por tipo de etiqueta, revisor o tipo de mensaje.
- Exportar datos a un archivo CSV en función de la fecha de actividad, la Directiva y la actividad de revisor.
- Filtrar datos según la fecha de la actividad, el tipo de etiqueta, el revisor y el tipo de mensaje.

A continuación, se muestra un desglose de los valores mostrados en la columna **tipo de etiqueta** .
  
|**Tipo de etiqueta**|**Qué significa**|
|:-----|:-----|
| **No revisado** | Número de correos electrónicos no revisados todavía. Estos mensajes de correo electrónico están pendientes de revisión en el panel de supervisión de Office 365.
| **Compliant** | Número de mensajes de correo electrónico revisados y marcados como compatibles. Estos mensajes aún necesitan resolución. |
| **Questionable** | Número de correos electrónicos revisados y marcados como cuestionables. Sirve como marca para otros revisores para ayudar a comprobar si un correo electrónico necesita investigar el cumplimiento. Estos mensajes aún necesitan resolución. |
| **No compatible (activo)** | El número de correos electrónicos no compatibles que los revisores están investigando en este momento. |
| **No compatible (resuelto)** | El número de correos electrónicos no compatibles que los revisores han investigado y resuelto. |
| **Directiva de visitas** | Número total (diario) de mensajes de Exchange, Teams y orígenes de datos de terceros que coinciden con una o varias condiciones definidas en una directiva de supervisión |
| **En ámbito** | Número total (diario) de mensajes de Exchange, Teams y orígenes de datos de terceros examinados mediante una directiva de supervisión |
| **Resuelto** | El número total de mensajes de Exchange, Teams y orígenes de datos de terceros clasificados **** como resueltos|

> [!NOTE]
> Las directivas de supervisión deben aprovisionarse antes de que aparezcan en los informes. Si se eliminan las directivas, aún se muestran los datos históricos. Sin embargo, se indican como una "Directiva no existente" y la función de **exportación** no está disponible.

## <a name="audit"></a>Las

En algunos casos, debe proporcionar información a los auditores reglamentarios o de cumplimiento para probar la supervisión de las comunicaciones y las actividades de los empleados. Esto puede ser un resumen de todas las actividades de supervisión asociadas con una directiva definida o cada vez que cambia una directiva de supervisión. Las directivas de supervisión tienen pistas de auditoría integradas para disponer de una preparación completa de las auditorías internas o externas. Los historiales de auditoría detallados de cada acción supervisada por las directivas de supervisión proporcionan una prueba de los procedimientos de supervisión.

Las siguientes actividades de directiva de supervisión se auditan y están disponibles en los registros de auditoría de Office 365 unificados:

|**Actividad**|**Comandos asociados**|
|:-----|:-----|
| **Crear una directiva** | [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| **Editar una directiva** | [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| **Eliminar una directiva** | [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |

Vea actividades de auditoría en el registro de auditoría unificado o con el cmdlet de PowerShell [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) .

Por ejemplo, en el siguiente ejemplo se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas) y se enumera la información detallada de cada uno de los elementos siguientes:

```
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

Además de la información proporcionada en los informes y registros de supervisión, también puede usar el cmdlet de PowerShell [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) para obtener una lista detallada completa de todas las actividades de la Directiva de supervisión.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar directivas de supervisión para su organización, consulte [Configure tutela Policies](configure-supervision-policies.md).
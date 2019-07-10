---
title: Investigación y respuesta automatizadas (AIR) con Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información sobre las capacidades de investigación y respuesta automatizadas en Office 365 Advanced Threat Protection.
ms.openlocfilehash: 3e74fd7a12727880164797f076d254416325713a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598526"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a>Investigación y respuesta automatizadas (AIR) con Office 365

La investigación y la respuesta automatizadas (que actualmente se encuentran en la versión preliminar pública como una de las muchas [capacidades de investigación y respuesta de amenazas de Office 365](office-365-ti.md)) le permiten ejecutar la investigación y la corrección automáticas para las amenazas bien conocidas que existen actualmente. Lea este artículo para obtener información general sobre AIR y cómo puede ayudar a su organización y a los equipos de operaciones de seguridad a mitigar las amenazas de forma más eficaz y eficiente. 

Para obtener más información acerca de Cuándo estarán disponibles las características de AIR, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="alerts"></a>Alertas

Las [alertas](alert-policies.md#viewing-alerts) representan desencadenadores de flujos de trabajo del equipo de operaciones de seguridad para respuesta ante incidentes. Establecer prioridades en el conjunto de alertas adecuadas para la investigación, a la vez que asegurarse de que no hay amenazas sin direcciones, supone un reto. Cuando las investigaciones en las alertas se realizan manualmente, los equipos de operaciones de seguridad deben buscar y correlacionar las entidades (por ejemplo, el contenido, los dispositivos y los usuarios) en riesgo de amenazas. Estas tareas y flujos de trabajo son muy lentos y implican el uso de varias herramientas y sistemas. Con AIR, la investigación y la respuesta se automatizan en alertas clave de seguridad y administración de amenazas que activan automáticamente las guías de respuesta de seguridad. 

En la versión inicial de AIR en abril de 2019, las alertas generadas desde las siguientes directivas de alerta de eventos únicos se investigarán de forma automática. 

1. Se ha detectado un clic en una dirección URL potencialmente malintencionada
2. Correo electrónico notificado por el usuario como phish *
3. Mensajes de correo electrónico que contienen malware quitados después de la entrega *
4. Mensajes de correo electrónico que contienen direcciones URL de phish quitadas después de la entrega *

> [!NOTE]
> A estas alertas se les ha asignado una gravedad de "información" en las directivas de alertas respectivas en el centro de seguridad & cumplimiento con las notificaciones de correo electrónico desactivadas. Se pueden activar a través de la configuración de la Directiva de alerta.

Para ver las alertas, en el centro de seguridad & cumplimiento, elija **alertas** > **Ver alertas**. Seleccione una alerta para ver sus detalles y, desde allí, use el vínculo **Ver investigación** para ir a la [investigación](#investigation-graph)correspondiente. Tenga en cuenta que las alertas informativas están ocultas en la vista de alertas de forma predeterminada. Para verlos, debe cambiar el filtrado de alertas para incluir alertas informativas.

Si su organización administra sus alertas de seguridad a través de un sistema de administración de alertas, un sistema de administración de servicios o un sistema de administración de eventos e información de seguridad (SIEM), puede enviar alertas de Office 365 a ese sistema mediante una notificación por correo electrónico o mediante el [ API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Las notificaciones de alerta de investigación a través del correo electrónico o la API incluirán vínculos para acceder a las alertas en el centro de seguridad & cumplimiento, lo que permite que el administrador de seguridad asignado navegue rápidamente a la investigación.

![Alertas que vinculan a investigaciones](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a>Guías de seguridad

Las guías de seguridad son directivas de back-end que están en el corazón de la automatización de la protección contra amenazas de Microsoft. Las guías de seguridad que se proporcionan en AIR se basan en escenarios comunes de seguridad del mundo real. Una guía de seguridad se inicia automáticamente cuando se desencadena una alerta dentro de la organización. Una vez que se activa la alerta, la guía asociada se ejecuta automáticamente. En la guía se ejecuta una investigación en todos los metadatos asociados (incluidos los mensajes de correo electrónico, usuarios, asuntos, remitentes, etc.). Basándose en las conclusiones de la guía, AIR recomienda un conjunto de acciones que el equipo de seguridad de la organización puede llevar a cabo para controlar y mitigar la amenaza. 

Las guías de seguridad que recibirá con AIR están diseñadas para enfrentarse a las amenazas más frecuentes a las que se enfrentan las organizaciones en la actualidad. Se basan en la información de las operaciones de seguridad y los equipos de respuesta ante incidentes, incluidos los que ayudan a defender los activos de Microsoft y nuestros clientes.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Las guías de seguridad se implementan en fases

Como parte del aire, las guías de seguridad se implementan en fases

- **Fase 1 (abril de 2019)**: las guías incluyen recomendaciones para acciones que los administradores de seguridad revisan y aprueban. La fase 1 incluirá las guías siguientes:
    - Mensaje de phish notificado por el usuario
    - Dirección URL haga clic en cambiar veredicto 
    - Malware detectado después de la entrega (ZAP de malware)
    - Phish detectado tras entrega tras entrega (ZAP de Phish)
    - Investigaciones manuales de correo electrónico (mediante el explorador de amenazas)

- **Fase 2 (segunda mitad de 2019)**: varias nuevas guías y mejoras en la guía, además de la opción de los administradores de seguridad para configurar las guías de seguridad para que realicen algunas acciones automáticamente sin interacción administrativa. 

### <a name="playbooks-include-investigation-and-recommendations"></a>Las guías incluyen investigación y recomendaciones

Cada guía incluye: 
- una investigación raíz, 
- pasos que hay que seguir para identificar y correlacionar otras posibles amenazas y 
- acciones recomendadas de corrección de amenazas.

Cada paso de alto nivel incluye varios pasos secundarios que se ejecutan para proporcionar una respuesta profunda, detallada y exhaustiva a las amenazas.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Ejemplo: un mensaje de phish notificado por el usuario inicia una guía de investigación

Cuando un usuario de la organización envía un mensaje de correo electrónico y lo notifica a Microsoft mediante el [complemento de mensajes de informe para Outlook o Outlook Web Access](enable-the-report-message-add-in.md), el informe también se envía al sistema y es visible en el explorador en la vista notificada por el usuario. Este mensaje de usuario ha informado ahora de una alerta informativa basada en el sistema, que inicia automáticamente la guía de la investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Entre ellos se incluyen:
- Una determinación del tipo de amenaza que podría ser;
- Quién lo envió;
- Dónde se envió el correo electrónico desde (infraestructura de envío);
- Si se han entregado o bloqueado otras instancias del correo electrónico;
- Una evaluación de nuestros analistas;
- Si el correo electrónico está asociado con alguna de las campañas conocidas;
- etc.

Una vez completada la investigación raíz, la guía proporciona una lista de las acciones recomendadas que se deben realizar en el correo electrónico original y las entidades asociadas con ella.
  
A continuación, se ejecutan varios pasos de investigación y de búsqueda de amenazas:

- Se buscan mensajes de correo electrónico similares en otros clústeres de correo electrónico.
- La señal se comparte con otras plataformas, como [ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Se determina si algún usuario ha hecho clic en cualquier vínculo malintencionado en mensajes de correo electrónico sospechosos.
- Una comprobación se realiza a través de Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) y de la protección contra amenazas avanzada ([ATP](office-365-atp.md)) de Office 365 para ver si hay otros mensajes similares detectados por los usuarios.
- Se realiza una comprobación para ver si un usuario se ha puesto en peligro. Esta comprobación aprovecha las señales en [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando las anomalías de actividad de usuario relacionadas. 

Durante la fase de caza, los riesgos y las amenazas se asignan a varios pasos de caza. 

La corrección es la fase final de la guía. Durante esta fase, se realizan pasos de corrección que se basan en las fases de investigación y de caza. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Ejemplo: un administrador de seguridad desencadena una investigación desde el explorador de amenazas

Además de las investigaciones automáticas desencadenadas por una alerta, el equipo de operaciones de seguridad de la organización puede desencadenar una investigación automática desde una vista del [Explorador de amenazas](use-explorer-in-security-and-compliance.md).

Por ejemplo, supongamos que está viendo datos en el explorador acerca de los mensajes detectados por el usuario. Puede seleccionar un elemento de la lista de resultados y, a continuación, hacer clic en **investigar**.

![Mensajes detectados por el usuario en el explorador con el botón investigar](media/Explorer-UserReported-Investigate.png)

Como otro ejemplo, supongamos que está viendo datos sobre los mensajes de correo electrónico que se detectan como que contienen malware y que se detectan varios mensajes de correo electrónico que contienen malware. Puede seleccionar la pestaña **correo electrónico** , seleccionar uno o más mensajes de correo electrónico y, a continuación, en el menú **acciones** , seleccione **investigar**. 

![Iniciar una investigación de malware en el explorador](media/Explorer-Malware-Email-ActionsInvestigate.png)

De forma similar a las guías activadas por una alerta, las investigaciones automáticas que se desencadenan desde una vista del explorador incluyen una investigación raíz, pasos para identificar y correlacionar amenazas y las acciones recomendadas para mitigar esas amenazas.

## <a name="get-started"></a>Introducción

Para acceder a sus investigaciones, como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya al centro de seguridad &[https://protection.office.com](https://protection.office.com)cumplimiento () e inicie sesión. A continuación, siga uno de los procedimientos siguientes:

- En el panel de navegación izquierdo, vaya a **alertas** > **Ver alertas**, abra una de las alertas relacionadas con la investigación y, a continuación, haga clic en el vínculo **Ver investigación** en la parte inferior del control flotante de alerta. 

    o

- En el panel de navegación de la izquierda, vaya a**investigaciones**de **Administración** > de amenazas.

    o

- Visite el panel de administración de amenazas (en el centro de seguridad & cumplimiento, vaya a **Threat Management** > **Dashboard**).

![Widgets de aire](media/air-widgets.png)

Los widgets de AIR aparecerán en la parte superior del [Panel de seguridad](security-dashboard.md). Seleccione un widget para empezar.

También puede obtener acceso a una investigación directamente desde las alertas relacionadas.

### <a name="automated-investigations"></a>Investigaciones automatizadas

La página investigaciones automatizadas muestra las investigaciones de su organización y sus Estados actuales.

![Página principal de investigación para AIR](media/air-maininvestigationpage.png) 
  
Puede:
- Vaya directamente a una investigación (seleccione un **identificador de investigación**).
- Aplicar filtros. Elija entre el **tipo de investigación**, **el intervalo de tiempo**, el **Estado**o una combinación de estos.
- Exporte los datos a un archivo CSV.

El estado de la investigación indica el progreso del análisis y las acciones. A medida que se ejecuta la investigación, el estado cambiará para indicar si se han encontrado amenazas, así como indicar si se han aprobado las acciones. 
- **Iniciando**: la investigación se pone en cola para comenzar pronto
- En **ejecución**: la investigación se ha iniciado y está llevando a cabo el análisis
- **No se han encontrado amenazas**: la investigación ha completado el análisis y no se han encontrado amenazas
- **Finalizado por el sistema**: la investigación no se cerró y caducó después de 7 días
- **Acción pendiente**: la investigación detectó amenazas con acciones recomendadas
- **Amenazas encontradas**: la investigación detectó amenazas, pero las amenazas no tienen acciones disponibles en el aire
- **Corregido**: el investgation ha finalizado y se ha corregido completamente (todas las acciones se han aprobado)
- **Corregido parcialmente**: la investigación ha finalizado y algunas de las acciones recomendadas se han aprobado
- **Finalizado por el usuario**: un administrador terminó la investigación
- **Error**: se ha producido un error durante la investigación que ha evitado que se alcance una conclusión en amenazas
- **Puesta en cola por límite**: la investigación está esperando el análisis debido a las limitaciones del procesamiento del sistema (para proteger el rendimiento del servicio)
- **Finalizada por limitación**: la investigación no se pudo completar en el tiempo suficiente debido a las limitaciones de procesamiento del sistema y el volumen de investigación. Puede volver a desencadenar la investigación seleccionando el correo electrónico en el explorador y seleccionando la acción investigar.

### <a name="investigation-graph"></a>Gráfico de investigación

Al abrir una investigación específica, verá la página gráfico de investigación. En esta página se muestran todas las entidades distintas: mensajes de correo electrónico, usuarios (y sus actividades) y dispositivos que se investigaron automáticamente como parte de la alerta que se activó.

![Página de gráfico de investigación de aire](media/air-investigationgraphpage.png)

Puede:
- Obtenga información general visual de la investigación actual.
- Ver un resumen de la duración de la investigación.
- Seleccione un nodo de la visualización para ver los detalles de ese nodo.
- Seleccione una pestaña en la parte superior para ver los detalles de esa pestaña.

### <a name="alert-investigation"></a>Investigación de alertas

En la pestaña **alertas** de una investigación, puede ver las alertas relevantes para la investigación. Los detalles incluyen la alerta que desencadenó la investigación y otras alertas, como el inicio de sesión peligroso, la descarga masiva, etc., que están correlacionados con la investigación. En esta página, un analista de seguridad también puede ver detalles adicionales de alertas individuales.

![Página de alertas de AIR](media/air-investigationalertspage.png)

Puede:
- Obtenga información general visual de la alerta desencadenadora actual y de cualquier alerta asociada.
- Seleccione una alerta de la lista para abrir una página emergente que muestre los detalles de la alerta completa.

### <a name="email-investigation"></a>Investigación de correo electrónico

En la pestaña **correo electrónico** de una investigación, puede ver todos los clústeres de correo electrónico identificados como parte de la investigación. 

Dado el volumen total de correo electrónico que los usuarios de una organización envían y reciben, el proceso de 
- agrupación de mensajes de correo electrónico en función de atributos similares de un encabezado, cuerpo, dirección URL y datos adjuntos del mensaje; 
- separar el correo electrónico malintencionado del correo electrónico bueno; y 
- realizar acciones en mensajes de correo electrónico malintencionados 

puede tardar varias horas. AIR ahora automatiza este proceso, lo que ahorra tiempo y esfuerzo del equipo de seguridad de su organización. 

Se pueden identificar dos tipos diferentes de clústeres de correo electrónico durante el paso de análisis de correo electrónico: clústeres de similitud y clústeres de indicadores. 
- Los clústeres de similitud son mensajes de correo electrónico que contienen atributos de remitente y contenido similares. Estos clústeres se evalúan para contenido malintencionado en función de las comprobaciones de detección originales. Los clústeres de correo electrónico que contienen suficientes detecciones malintencionadas se consideran malintencionados.
- Los clústeres de indicadores son mensajes de correo electrónico que contienen la misma entidad del indicador (hash de archivo o dirección URL) del correo electrónico original. Cuando la entidad de archivo/URL original se identifica como malintencionada, AIR aplicará el veredicto del indicador a todo el clúster de mensajes de correo electrónico que contengan esa entidad. Como un archivo identificado como malware, el clúster de mensajes de correo electrónico que contiene ese archivo se tratará como mensajes de correo electrónico de malware.

El objetivo de la agrupación en clústeres es encontrar otros mensajes de correo electrónico relacionados que envía el mismo remitente como parte de un ataque o una campaña.

La ficha **correo** electrónico también mostrará los elementos de correo electrónico relacionados con la investigación, como los detalles de correo electrónico notificados por el usuario, el correo electrónico original que se ha notificado, los mensajes de correo electrónico que se han zapped debido a malware/phish, etc.

El recuento de correo electrónico identificado en la ficha correo electrónico representa actualmente la suma total de todos los mensajes de correo electrónico que se muestran en la ficha **correo electrónico** . Como los mensajes de correo electrónico estarán presentes en varios clústeres, el número total real de mensajes de correo electrónico identificados (y afectados por acciones de corrección) será el número de mensajes de correo electrónico únicos presentes en todos los clústeres y el correo electrónico de los destinatarios originales. mensaje. 

Tanto Explorer como AIR cuentan los mensajes de correo electrónico según cada destinatario, ya que los veredictos, las acciones y las ubicaciones de entrega variarán según cada destinatario. Por lo tanto, un correo electrónico original enviado a tres usuarios contará como un total de tres mensajes de correo electrónico en lugar de un correo electrónico. Nota puede haber casos en los que un mensaje de correo se cuente dos o más veces, ya que el correo electrónico puede tener varias acciones en él y puede haber varias copias del correo electrónico una vez que se produzcan todas las acciones. Por ejemplo, un correo electrónico de malware que se detecta al entregar puede dar como resultado un correo electrónico bloqueado (en cuarentena) y un correo electrónico reemplazado (el archivo de amenaza se reemplaza con un archivo de advertencia y, a continuación, se entrega en el buzón del usuario). Dado que hay literalmente dos copias del correo electrónico en el sistema, ambas pueden contarse en el recuento de clústeres. 

Los recuentos de correo electrónico se calculan en el momento de la investigación y algunos recuentos se vuelven a calcular al abrir controles flotantes de investigación (según una consulta subyacente). Los recuentos de correo electrónico que se muestran para los clústeres de correo electrónico en la ficha correo y el valor de cantidad de correo electrónico que se muestra en el control flotante de clúster se calculan en el momento de la investigación El recuento de correo electrónico que se muestra en la parte inferior de la ficha correo electrónico del control flotante de clúster, así como el número de mensajes de correo electrónico que se muestran en el explorador, reflejará los mensajes de correo electrónico recibidos después del análisis inicial de la investigación. Por lo tanto, un clúster de correo electrónico que muestra una cantidad original de 10 mensajes de correo electrónico mostraría una lista de correo electrónico con un total de 15 cuando 5 mensajes de correo electrónico entre la fase de análisis de la investigación y cuando el administrador Revise la investigación. La presentación de ambos recuentos en vistas diferentes se realiza para indicar el impacto del correo electrónico en el momento de la investigación y el impacto actual hasta el momento en que se ejecuta la corrección.

Como ejemplo, considere el siguiente escenario. El primer clúster de tres mensajes de correo electrónico se consideró phish. Se ha encontrado otro clúster de mensajes similares con la misma dirección IP y asunto, y se ha considerado malintencionado, ya que algunos de ellos se identificaron como phish durante la detección inicial. 

![Página de investigación de correo electrónico de AIR](media/air-investigationemailpage.png)

Puede:
- Obtenga información general visual de los resultados y amenazas de clúster actuales encontrados.
- Haga clic en una entidad de clúster o en una lista de amenazas para abrir una página emergente que muestre los detalles de alerta completos.
- Para investigar más detalladamente el clúster de correo electrónico, haga clic en el vínculo "abrir en el explorador" que se encuentra en la parte superior de la pestaña "detalles del clúster de correo electrónico"

![Correo electrónico de investigación de aire con detalles de control flotante](media/air-investigationemailpageflyoutdetails.png)

* Nota: en el contexto del correo electrónico, es posible que vea una superficie de amenaza con anomalías de volumen como parte de la investigación. Una anomalía de volumen indica un pico en mensajes de correo electrónico similares en torno a la hora del evento de investigación en comparación con los plazos anteriores. Este pico en el tráfico de correo electrónico con características similares (por ejemplo, el asunto y el dominio del remitente, la similitud de cuerpo y la IP del remitente) es el principio del inicio de las campañas de correo electrónico o de los ataques. Sin embargo, las campañas de correo electrónico masivos, de correo no deseado y legítimas suelen compartir estas características. Las anomalías de volumen representan una amenaza potencial y, en consecuencia, podrían ser menos graves en comparación con amenazas de malware o phish identificadas mediante motores antivirus, detonación o reputación malintencionada.

### <a name="user-investigation"></a>Investigación del usuario

En la pestaña **usuarios** , puede ver todos los usuarios identificados como parte de la investigación. Los usuarios aparecerán en la investigación cuando haya un evento o indicación de que el usuario puede verse afectado o en peligro.

Por ejemplo, en la siguiente imagen, AIR ha identificado indicadores de peligro y anomalías en función de una nueva regla de bandeja de entrada creada. Hay disponibles detalles adicionales (evidencia) de la investigación en vistas detalladas de esta ficha. los indicadores de exposición y anomalías también pueden incluir detecciones de anomalías de [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).

![Página de usuarios de investigación de aire](media/air-investigationuserspage.png)

Puede:
- Obtenga una introducción visual de los resultados de usuario identificados y los riesgos encontrados.
- Seleccione un usuario para abrir una página emergente que muestre todos los detalles de la alerta.

### <a name="machine-investigation"></a>Investigación de máquina

En la pestaña **máquinas** , puede ver todos los equipos identificados como parte de la investigación. 

![Página de la máquina de investigación de aire](media/air-investigationmachinepage.png)

Como parte de la investigación, AIR correlaciona las amenazas de correo electrónico en los dispositivos. Por ejemplo, una investigación pasa un hash de archivo malintencionado entre en [Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) para investigar. Esto permite la investigación automatizada de las máquinas pertinentes para los usuarios, para ayudar a garantizar que las amenazas se dirijan en la nube y en los extremos. 

Puede:
- Obtenga información general visual de las amenazas y los equipos actuales encontrados.
- Seleccione un equipo para abrir una vista en la investigación de [ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) relacionada en el centro de seguridad de Microsoft defender.

### <a name="entity-investigation"></a>Investigación de entidades

En la pestaña **entidades** , puede ver todas las entidades identificadas como parte de la investigación. 

Aquí, puede ver las entidades investigadas y los detalles de los tipos de entidades, como los mensajes de correo electrónico, los clústeres, las direcciones IP, los usuarios, etc. También puede ver cuántas entidades se han analizado y las amenazas que se han asociado a cada una de ellas. 

![Página de entidades de investigación de aire](media/air-investigationentitiespage.png)

Puede:
- Obtenga información general visual de las entidades de investigación y las amenazas encontradas.
- Seleccione una entidad para abrir una página emergente que muestre los detalles de la entidad relacionada.

![Detalles de entidades de investigación de aire](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Registro de la guía

En la pestaña **registro** , puede ver todos los pasos de la guía que se han producido durante la investigación. El registro captura un inventario completo de todas las acciones completadas por las capacidades de investigación automática de Office 365 como parte del aire. Proporciona una vista clara de todos los pasos realizados, incluida la propia acción, una descripción y la duración de la real desde el principio hasta el final. 

![Página de registro de investigación de aire](media/air-investigationlogpage.png)

Puede:
- Vea una descripción general visual de los pasos de la guía realizados.
- Exporte los resultados a un archivo CSV.
- Filtrar la vista.

### <a name="recommended-actions"></a>Acciones recomendadas

En la ficha **acciones** , puede ver todas las acciones de la guía que se recomiendan para la corrección después de que la investigación haya finalizado. 

Acciones Capture los pasos que Microsoft recomienda realizar al final de una investigación. Puede realizar acciones de corrección aquí si selecciona una o varias acciones. Al hacer clic en **aprobar** se permitirá que se inicie la corrección. (Es necesario disponer de los permisos adecuados: el rol "buscar y purgar" es necesario para ejecutar acciones desde el explorador y el aire). Por ejemplo, un lector de seguridad puede ver las acciones pero no aprobarlas. Nota: no es necesario aprobar todas las acciones. Si no está de acuerdo con la acción recomendada o su organización no elige determinados tipos de acciones, puede optar por **rechazar** las acciones o simplemente omitirlas y no realizar ninguna acción. La aprobación o el rechazo de todas las acciones permitirán que la investigación se cierre completamente, mientras que al dejar algunas acciones como incompletas, el estado de la investigación cambiará a un estado parcialmente corregido.

![Página de acción de investigaciones de aire](media/air-investigationactionspage.png)

Puede:
- Obtenga información general visual de las acciones recomendadas de la guía.
- Seleccione una sola acción o varias acciones.
- Aprobar o rechazar acciones recomendadas con comentarios.
- Exporte los resultados a un archivo CSV.
- Filtrar la vista.

## <a name="how-to-get-air"></a>Cómo obtener aire

Actualmente, las características de Office 365 AIR se encuentran en versión preliminar. Cuando esté disponible por lo general, las características de Office 365 AIR se incluirán en las siguientes suscripciones:

- Microsoft 365 Enterprise E5
- Office 365 Enterprise E5
- Protección contra amenazas de Microsoft
- Plan 2 de protección contra amenazas avanzada de Office 365

Para obtener más información acerca de la disponibilidad de características, visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

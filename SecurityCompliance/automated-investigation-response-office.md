---
title: Investigación y respuesta automatizadas (AIR) con Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información sobre las capacidades de investigación y respuesta automatizadas en Office 365 Advanced Threat Protection.
ms.openlocfilehash: c6cfc03588e580382f673b2e9be8543bfcaf9ac1
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747566"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a>Investigación y respuesta automatizadas (AIR) con Office 365

La investigación y respuesta automatizada (AIR) (próximamente en las [capacidades de investigación y respuesta de amenazas de Office 365](office-365-ti.md)) le permite ejecutar la investigación y la corrección automáticas para las amenazas bien conocidas que ya existen en el mercado. Lea este artículo para obtener información general sobre AIR y cómo puede ayudar a su organización y a los equipos de operaciones de seguridad a mitigar las amenazas de forma más eficaz y eficiente. Para obtener más información acerca de Cuándo estarán disponibles otras características en AIR, consulte el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="alerts"></a>Alertas

Las [alertas](alert-policies.md#viewing-alerts) representan desencadenadores de flujos de trabajo del equipo de operaciones de seguridad para respuesta ante incidentes. Establecer prioridades en el conjunto de alertas adecuadas para la investigación mientras se asegura de que no hay amenazas sin direcciones es un reto. Cuando las investigaciones en las alertas se realizan manualmente, los equipos de operaciones de seguridad deben buscar y correlacionar las entidades (por ejemplo, el contenido, los dispositivos y los usuarios) en riesgo de amenazas. Estas tareas y flujos de trabajo son muy lentos y implican el uso de varias herramientas y sistemas. Con AIR, la investigación y la respuesta se automatizan en alertas clave de seguridad y administración de amenazas que activan automáticamente las guías de respuesta de seguridad. 

En la versión inicial de AIR en abril de 2019, las alertas generadas desde las siguientes directivas de alerta de eventos de única se investigarán de forma automática. 

1. Se ha detectado un clic en una dirección URL potencialmente malintencionada
2. Correo electrónico notificado por el usuario como phish *
3. Mensajes de correo electrónico que contienen malware quitados después de la entrega *
4. Mensajes de correo electrónico que contienen direcciones URL de phish quitadas después de la entrega *

* Nota: a estas alertas se les ha asignado una gravedad de "información" en las directivas de alertas respectivas en el centro de seguridad y cumplimiento con las notificaciones de correo electrónico desactivadas. Se pueden activar a través de la configuración de la Directiva de alerta.

para ver las alertas, en el centro de cumplimiento de & de seguridad de Office 365, elija **alertas** > **ver alertas**. Seleccione una alerta para ver sus detalles y, desde allí, use el vínculo **Ver investigación** para ir a la [investigación](#investigation-graph)correspondiente.

![Alertas que vinculan a investigaciones](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a>Guías de seguridad

Las guías de seguridad son directivas de back-end que están en el corazón de la automatización de la protección contra amenazas de Microsoft. Las guías de seguridad que se proporcionan en AIR se basan en escenarios comunes de seguridad del mundo real. Una guía de seguridad se inicia automáticamente cuando se desencadena una alerta dentro de la organización. Una vez que se activa la alerta, la guía asociada se ejecuta automáticamente. La guía ejecuta una investigación en la que se examinan todos los metadatos asociados (incluidos los mensajes de correo electrónico, usuarios, asuntos, remitentes, etc.) y, según sus conclusiones, se recomienda un conjunto de acciones que el equipo de seguridad de su organización puede llevar a controlar y mitigar la amenaza. 

Las guías de seguridad que recibirá con AIR están diseñadas para enfrentarse a las amenazas más frecuentes a las que se enfrentan las organizaciones en la actualidad. Se basan en la información de las operaciones de seguridad y los equipos de respuesta ante incidentes, incluidos los que ayudan a defender los activos de Microsoft y nuestros clientes.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Las guías de seguridad se implementan en fases

Como parte del aire, las guías de seguridad se implementan en fases

- **Fase 1 (abril de 2019)**: las guías incluyen recomendaciones para acciones que los administradores de seguridad revisan y aprueban. 

- **Fase 2 (junio de 2019)**: los administradores de seguridad tendrán la opción de configurar guías de seguridad para emprender acciones automáticas, sin interacción administrativa.

La fase 1 incluirá las guías siguientes:
- Mensaje de phish notificado por el usuario
- Dirección URL haga clic en cambiar veredicto 
- Malware detectado después de la entrega (ZAP de malware)
- Phish detectado tras entrega tras entrega (ZAP de Phish)
- Investigaciones manuales de correo electrónico (mediante el explorador de amenazas)

Hay varias guías planeadas para la fase 2.

### <a name="playbooks-include-investigation-and-recommendations"></a>Las guías incluyen investigación y recomendaciones

Cada guía incluye: 
- una investigación raíz, 
- pasos que hay que seguir para identificar y correlacionar otras posibles amenazas y 
- acciones recomendadas de corrección de amenazas.

Cada paso de alto nivel incluye varios pasos secundarios que se ejecutan para proporcionar una respuesta profunda, detallada y exhaustiva a las amenazas.

## <a name="example-user-reported-phish-message"></a>Ejemplo: mensaje de phish notificado por el usuario

Cuando un usuario de la organización envía un mensaje de correo electrónico y lo notifica a Microsoft mediante el [complemento de mensajes de informe para Outlook o Outlook Web Access](enable-the-report-message-add-in.md). Esto desencadena una alerta informativa basada en el sistema que inicia automáticamente la guía de la investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Entre estos, incluyen los siguientes:
- Una determinación del tipo de amenaza que podría ser;
- Quién lo envió;
- Dónde se envió el correo electrónico desde (infraestructura de envío);
- Si se han entregado o bloqueado otras instancias del correo electrónico;
- Una evaluación de nuestros analistas;
- Si el correo electrónico está asociado con alguna de las campañas conocidas;
- etc.

Una vez completada la investigación raíz, la guía proporciona una lista de acciones recomendadas para llevar a cabo.
  
A continuación, se ejecutan varios pasos de investigación y de búsqueda de amenazas:

- Se buscan mensajes de correo electrónico similares en otros clústeres de correo electrónico.
- La señal se comparte con otras plataformas, como [ATP de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).
- Se determina si algún usuario ha hecho clic en los vínculos de mensajes de correo electrónico sospechosos.
- Se realiza una comprobación en Office 365 Exchange Online Protection ([EOP]) (eop/Exchange-Online-Protection-EOP. MD) y Office 365 Advanced Therat Protection ([ATP]) (Office-365-atp.md) para ver si hay otros mensajes similares que hayan notificado los usuarios.
- Se realiza una comprobación para ver si un usuario se ha puesto en peligro. Esta comprobación aprovecha las señales en [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando las anomalías de actividad de usuario relacionadas. 

Durante la fase de caza, los riesgos y las amenazas se asignan a varios pasos de caza.  

La corrección es la fase final de la guía. Durante esta fase, se realizan pasos de corrección, basados en las fases de investigación y de caza.  

## <a name="getting-started"></a>Introducción

Para acceder a sus investigaciones, como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya al centro de seguridad de Office 365[https://protection.office.com](https://protection.office.com)_AMP_ Compliance Center () e inicie sesión. A continuación, siga uno de los procedimientos siguientes:

- En el panel de navegación de la izquierda, vaya a**investigaciones**de **Administración** > de amenazas.

    o

- Visite el panel de administración de amenazas (en el centro de seguridad & cumplimiento, vaya a **Threat Management** > **Dashboard**).

![Widgets de aire](media/air-widgets.png)

Los widgets de AIR aparecerán en la parte superior del [Panel de seguridad](security-dashboard.md). Seleccione un widget para empezar.

También puede acceder a un invesitgation directamente desde las alertas relacionadas.

### <a name="automated-investigations"></a>Investigaciones automatizadas

La página investigaciones automatizadas muestra las investigaciones de su organización y sus Estados actuales.

![Página principal de investigación para AIR](media/air-maininvestigationpage.png) 
  
Puede:
- Vaya directamente a una investigación (seleccione un **identificador de investigación**).
- Aplicar filtros. Elija entre el **tipo de investigación**, **el intervalo de tiempo**, el **Estado**o una combinación de estos.
- ExPorte los datos a un archivo CSV.

### <a name="investigation-graph"></a>Gráfico de investigación

Al abrir una investigación específica, verá la página gráfico de investigación. En esta página se muestran todas las entidades distintas: mensajes de correo electrónico, usuarios (y sus actividades) y dispositivos que se investigaron automáticamente como parte de la alerta que se activó.

![Página de gráfico de investigación de aire](media/air-investigationgraphpage.png)

Puede:
- Obtenga información general visual de la investigación actual.
- Ver un resumen de los intervalos de investigación.
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

Como ejemplo, considere el siguiente escenario. El primer clúster de tres mensajes de correo electrónico se consideró phish. Se ha encontrado otro clúster de mensajes similares con la misma dirección IP y asunto, y se ha considerado malintencionado, ya que algunos de ellos se identificaron como phish durante la detección inicial. 

![Página de investigación de correo electrónico de AIR](media/air-investigationemailpage.png)

Puede:
- Obtenga información general visual de los resultados y amenazas de clúster actuales encontrados.
- Haga clic en una entidad de clúster o en una lista de amenazas para abrir una página emergente que muestre los detalles de alerta completos.

![Correo electrónico de investigación de aire con detalles de control flotante](media/air-investigationemailpageflyoutdetails.png)

* Nota: en el contexto del correo electrónico, es posible que vea una superficie de amenaza con anomalías de volumen como parte de la investigación. Una anomalía de volumen indica un pico en correos electrónicos similares en torno al tiempo de evento de investigación en comparación con los plazos anteriores. Este pico en el tráfico de correo electrónico con características similares (por ejemplo, el asunto y el dominio del remitente, la similitud de cuerpo y la IP del remitente) es el principio del inicio de las campañas de correo electrónico o de los ataques. Sin embargo, las campañas de correo electrónico masivo y SPOM en ocasiones también comparten estas características. Las anomalías de volumen representan una amenaza potencial y, en consecuencia, podrían ser menos graves en comparación con amenazas de malware o phish identificadas mediante motores antivirus, detonación o reputación malintencionada.

### <a name="user-investigation"></a>Investigación del usuario

En la pestaña **usuarios** , puede ver todos los usuarios identificados como parte de la investigación. 

Por ejemplo, en la siguiente imagen, AIR ha identificado indicadores de peligro y anomalías en función de una nueva regla de bandeja de entrada creada. Hay disponibles detalles adicionales (evidencia) de la investigación en vistas detalladas de esta ficha. los indicadores de exposición y anomalías también pueden incluir detecciones de anomalías de [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).

![Página de usuarios de investigación de aire](media/air-investigationuserspage.png)

Puede:
- Obtenga una introducción visual de los resultados de usuario identificados y los riesgos encontrados.
- Seleccione un usuario para abrir una página emergente que muestre todos los detalles de la alerta.

### <a name="machine-investigation"></a>Investigación de máquina

En la pestaña **máquinas** , puede ver todos los equipos identificados como parte de la investigación. 

![Página de la máquina de investigación de aire](media/air-investigationmachinepage.png)

Como parte de la investigación, AIR correlaciona las amenazas de correo electrónico en los dispositivos. Por ejemplo, una investigación pasa un hash de archivo en [ATP de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) para investigar. Esto permite la investigación automatizada de las máquinas relevantes para los usuarios y ayuda a garantizar que las amenazas se dirijan en la nube y en los dispositivos. 

Puede:
- Obtenga información general visual de las amenazas y los equipos actuales encontrados.
- Seleccione un equipo para abrir una vista en la investigación de [ATP de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) relacionada en el centro de seguridad ATP de Windows Defender.

### <a name="entity-investigation"></a>Investigación de entidades

En la pestaña **entidades** , puede ver todos los equipos identificados como parte de la investigación. 

Aquí puede ver las entidades investigadas. Puede ver los detalles de los tipos de entidades, como los mensajes de correo electrónico, los clústeres, las direcciones IP, los usuarios, etc. También puede ver cuántas entidades se han analizado y las amenazas que se han asociado a cada una de ellas. 

![Página de entidades de investigación de aire](media/air-investigationentitiespage.png)

Puede:
- Obtenga información general visual de las entidades de investigación y las amenazas encontradas.
- Seleccione una entidad para abrir una página emergente que muestre el detalle de la entidad relacionada.

![Detalles de entidades de investigación de aire](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Registro de la guía

En la pestaña **registro** , puede ver todos los pasos de la guía que se han producido durante la investigación. El registro captura un inventario completo de todas las acciones completadas por las capacidades de investigación automática de Office 365 como parte del aire. Proporciona una vista clara de todos los pasos realizados, incluida la propia acción, una descripción y la duración del real desde el principio hasta el final. 

![Página de registro de investigación de aire](media/air-investigationlogpage.png)

Puede:
- Vea una descripción general visual de los pasos de la guía realizados.
- ExPorte los resultados a un archivo CSV.
- Filtrar la vista.

### <a name="recommended-actions"></a>Acciones recomendadas

En la ficha **acciones** , puede ver todas las acciones de la guía que se recomiendan para la corrección después de que la investigación haya finalizado. 

Acciones Capture los pasos que Microsoft recomienda realizar al final de una investigación. Puede realizar acciones de corrección aquí si selecciona una o varias acciones. Al hacer clic en **aprobar** se permitirá que se inicie la corrección. (Será necesario disponer de los permisos adecuados. Por ejemplo, un lector de seguridad puede ver las acciones pero no aprobarlas.)  

![Página de acción de investigaciones de aire](media/air-investigationactionspage.png)

Puede:
- Obtenga información general visual de las acciones recomendadas de la guía.
- Seleccione una sola acción o varias acciones.
- Aprobar o rechazar acciones recomendadas con comentarios.
- ExPorte los resultados a un archivo CSV.
- Filtrar la vista.

## <a name="how-to-get-air"></a>Cómo obtener aire

Actualmente, Office 365 AIR está en versión preliminar. Office 365 AIR se incluirá en las siguientes suscripciones:

- Microsoft 365 Enterprise E5
- Office 365 Enterprise E5
- Protección contra amenazas de Microsoft
- Plan 2 de protección contra amenazas avanzada de Office 365

Para obtener más información acerca de la disponibilidad de características, visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

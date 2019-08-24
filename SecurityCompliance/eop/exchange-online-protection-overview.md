---
title: Información general de Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/31/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Protección de Exchange Online (EOP) es un servicio de filtro de correo electrónico basado en nube que ayuda a proteger su organización contra correo no deseado y malware, e incluye características para proteger a su organización contra incumplimiento de directivas de mensajería.
ms.openlocfilehash: a59839c212f365e9602c3b329c3c30953dbbf1ac
ms.sourcegitcommit: 01a9f8073eb911709be893e41414e94ec01906af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "36622035"
---
# <a name="exchange-online-protection-overview"></a>Información general de Exchange Online Protection

Microsoft Protección de Exchange Online (EOP) es un servicio de filtro de correo electrónico basado en nube que ayuda a proteger su organización contra correo no deseado y malware, e incluye características para proteger a su organización contra incumplimiento de directivas de mensajería. EOP simplifica la administración de un entorno de mensajes y puede aliviar muchas de las cargas asociadas al mantenimiento del hardware y del software local.
  
Estas son las principales formas en las que se puede usar EOP para la protección de mensajes:
  
- **En un escenario independiente** EOP proporciona protección de correo electrónico basada en la nube para su entorno local de Microsoft Exchange Server 2013, versiones heredadas de Exchange Server o para cualquier otra solución de correo SMTP local. 
    
- **Como parte de Microsoft Exchange Online**: de manera predeterminada, EOP protege los buzones de Microsoft Exchange Online hospedados en la nube. Consulte [proteger contra amenazas](../protect-against-threats.md) para ayudarle a configurar estas capacidades de Exchange Online. 
    
- **En una implementación híbrida**: EOP se puede configurar para que proteja el entorno de mensajería y controle el enrutamiento del correo cuando se tiene una mezcla de buzones locales y en la nube. 

Estos artículos de Exchange Online Protection se aplican a entornos híbridos y locales. 
    
## <a name="how-eop-works"></a>Cómo funciona EOP

Para comprender el funcionamiento de EOP, es muy útil ver cómo se procesa el correo entrante:

![Diagrama de proceso de correo electrónico.](../media/GitHubBugs/emailprocessingineop1.png)
  
Un mensaje entrante pasa inicialmente por el filtrado de conexiones, que comprueba la reputación del remitente e inspecciona el mensaje en busca de malware. En este punto, la mayoría de los correos no deseados se interrumpen y se eliminan mediante EOP. Los mensajes continúan a través del filtrado de directivas, donde los mensajes se evalúan con reglas de flujo de correo personalizado (también conocidas como reglas de transporte) que se crean o aplican a partir de una plantilla. Por ejemplo, puede tener una regla que envíe una notificación a un administrador cuando llegue el correo de un remitente específico. (Las comprobaciones de prevención de pérdida de datos también se producen en este momento, si tiene esa característica; para obtener información sobre la disponibilidad de características, consulte la [Descripción del servicio de protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=320619)). A continuación, los mensajes pasan por el filtrado de contenido, donde se comprueba la terminología o las propiedades comunes del correo no deseado en el contenido. Un mensaje determinado como correo no deseado por el filtro de contenido se puede enviar a la carpeta de correo no deseado o a la cuarentena de un usuario, entre otras opciones (incluida la bandeja de entrada o la carpeta personalizada), en función de la configuración. Una vez que un mensaje pasa todas estas capas de protección correctamente, se entrega al destinatario.
  
### <a name="eop-datacenters"></a>Centros de datos de EOP

EOP se ejecuta en una red mundial de centros de datos que están diseñados para proporcionar la mejor disponibilidad. Por ejemplo, si un centro de datos no está disponible, los mensajes de correo electrónico se enrutan automáticamente a otro centro de datos sin interrupciones del servicio. Los servidores de los centros de datos aceptan mensajes en nombre del usuario y disponen una capa de separación entre la organización e Internet, lo que permite reducir la carga en los servidores. Gracias a esta red de alta disponibilidad, Microsoft se asegura que el correo llegue a la organización de manera puntual. 
  
EOP realiza el equilibrio de carga entre los centros de datos, pero solo dentro de una región. Si está aprovisionado en una región, todos sus mensajes se procesarán usando el enrutamiento de correo de esa región. La siguiente lista muestra cómo funciona el enrutamiento regional de correo para los centros de datos de EOP:
  
    
- En Europa, Oriente Medio y África (EMEA), todos los buzones de Exchange Online están ubicados en centros de datos de EMEA, y todos los mensajes se enrutan a través de EMEA para el filtrado de EOP.
    
- En Asia-Pacífico (APAC), todos los buzones de correo de Exchange Online se encuentran en centros de recursos de APACciones y los mensajes se enrutan actualmente a través de centros de recursos de APAC para el filtrado de EOP.

- En América, todos los buzones de correo de Exchange Online se encuentran en centros de seguridad de Estados Unidos, con la excepción de Sudamérica, donde se usan centros de recursos de Brasil y Chile y en Canadá, en los que se usan centros de conexión de Canadá. Todos los mensajes de correo electrónico, incluidos los mensajes para clientes de Sudamérica y Canadá, se enrutan a través de centros de recursos locales para el filtrado de EOP; el correo electrónico de quaratined se almacena en el centro de recursos en el que se encuentra el inquilino.
    
- Para la nube de la comunidad de organismos oficiales (GCC), todos los buzones de Exchange Online están ubicados en centros de datos de Estados Unidos y los mensajes se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP.
    
## <a name="eop-plans-and-features"></a>Planes y características de EOP

A continuación se detallan los planes de suscripción de EOP disponibles:
  
- **EOP independiente**: EOP protege los buzones locales. 
    
- **Características de EOP en Exchange Online**: EOP protege los buzones de Exchange Online hospedados en la nube. 
    
- **Exchange Enterprise CAL con servicios** Donde EOP protege los buzones locales, tal como EOP independiente, e incluye prevención de pérdida de datos (DLP) e informes que usan servicios web. 
    
Para más información sobre los requisitos, límites importantes y disponibilidad de características en todos los planes de suscripción de EOP, vea la [Descripción de servicio Protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=320619).
  
## <a name="setting-up-eop"></a>Configurar EOP

Configurar EOP puede ser fácil, especialmente en las compañías pequeñas con pocas reglas de cumplimiento. Sin embargo, si tiene una organización grande con muchos dominios, reglas de cumplimiento personalizadas o flujo de correo híbrido, la configuración puede llevar más tiempo e implicar más planeación.
  
Si ya ha comprado EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md) para asegurarse de completar todos los pasos necesarios para configurar EOP de modo que proteja el entorno de mensajería. 
  
## <a name="for-more-information"></a>Más información

[Características de EOP](eop-features.md)
  
[Preguntas más frecuentes sobre EOP](eop-general-faq.md)
  
[Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP](eop-queued-deferred-and-bounced-messages-faq.md)
  
[Preguntas más frecuentes sobre administración delegada](delegated-administration-faq.md)
  
[Mover dominios y opciones de configuración de una organización de EOP a otra organización de EOP](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  


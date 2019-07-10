---
title: Informes y seguimiento de mensajes en Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/18/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) ofrece muchos informes distintos que le permitirán averiguar el estado general y el mantenimiento de la organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento normativo. La tabla siguiente describe los informes y las herramientas de solución de problemas disponibles para los administradores de EOP.
ms.openlocfilehash: d882319762fc963fd66cabdaf858d88cc1c8956a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599486"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Informes y seguimiento de mensajes en Exchange Online Protection

Microsoft Exchange Online Protection (EOP) ofrece muchos informes distintos que le permitirán averiguar el estado general y el mantenimiento de la organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento normativo. 

## <a name="usage-reports"></a>Informes de uso

**Actividad de grupos de Office 365** Permite ver información sobre el número de grupos de Office 365 que se crean y usan.  

**Actividad de correo electrónico** Permite ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.  

**Uso de aplicaciones de correo electrónico** Vea información sobre las aplicaciones de correo electrónico que se usan. Esto incluye el número total de conexiones de cada aplicación y las versiones de Outlook que se conectan.  

**Uso de buzón** Ver información sobre el almacenamiento usado, el consumo de cuotas, el recuento de elementos y la última actividad (actividad de envío o lectura) para los buzones.

Consulte los recursos siguientes para obtener más información:

- [Office 365 Reports en el centro de administración: Office 365 grupos](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [Office 365 Reports en el centro de administración: actividad de correo electrónico](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [Office 365 Reports en el centro de administración: uso de aplicaciones de correo electrónico](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [Office 365 Reports en el centro de administración: uso de buzones](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-microsoft-365-admin-center"></a>Informes &amp; de cumplimiento de seguridad en el centro de administración de Microsoft 365

Estos informes mejorados proporcionan una experiencia de creación de informes interactiva para los administradores de EOP, que incluye información de Resumen y la capacidad de profundizar para obtener más detalles.  

**Protección contra amenazas avanzada (ATP)** Ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de ATP.  

**EOP** Vea información sobre las detecciones de malware, el correo falsificado, las detecciones de correo no deseado y el flujo de correo hacia y desde la organización.  

[Ver informes para la protección contra amenazas avanzada y la protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>Informes personalizados con Microsoft Graph

Crear mediante programación informes que están disponibles en el centro de administración de Microsoft 365 mediante Microsoft Graph, vea los temas secundarios de [trabajo con informes de uso de Office 365 en Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135) 

##<a name="custom-reports-using-reporting-web-services"></a>Informes personalizados mediante servicios Web de informes

Cree informes mediante programación a partir de los cmdlets de informes de PowerShell de Exchange Online Protection disponibles mediante el filtrado de consultas REST/ODATA2.

Consulte [servicios Web de informes de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=279926) 

##<a name="message-trace"></a>Seguimiento de mensajes

Sigue los mensajes de correo electrónico mientras viajan a través de EOP. Puede determinar si un mensaje de correo electrónico se ha recibido, rechazado, aplazado o entregado por el servicio. También muestra las acciones que se tomaron en el mensaje antes de que alcanzara su estado final.  

Puede usar esta información para responder de forma eficaz a las preguntas del usuario, solucionar problemas del flujo de correo, validar los cambios en la Directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.  

Consulte [seguimiento de un mensaje de correo electrónico](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) 

## <a name="audit-logging"></a>Registro de auditoría

Realiza un seguimiento de los cambios específicos realizados por los administradores en la organización. Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con el cumplimiento o la seguridad.  vea [Auditing Reports in EOP](auditing-reports-in-eop.md) 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Informes, disponibilidad y latencia de los datos de seguimiento de mensajes

En la tabla siguiente se describe cuándo están disponibles los informes y los datos de seguimiento de mensajes de EOP y durante cuánto tiempo.
  
||||
|:-----|:-----|:-----|
|**Tipo de informe** <br/> |**Datos disponibles (período retrospectivo)** <br/> |**Latencia** <br/> |
|Informes de Resumen de protección de correo  <br/> |90 días  <br/> |La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.  <br/> |
|Informes de detalles de protección de correo  <br/> |90 días  <br/> |Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.  <br/> Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.  <br/> |
|Datos de seguimiento de mensajes  <br/> |90 días  <br/> |Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.  <br/> Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.  <br/> |
   
> [!NOTE]
> La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del centro de administración de Microsoft 365 o de PowerShell remoto. 
  


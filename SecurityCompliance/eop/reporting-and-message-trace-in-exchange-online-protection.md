---
title: Informes y seguimiento de mensajes en Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) ofrece muchos informes distintos que le permitirán averiguar el estado general y el mantenimiento de la organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento normativo. La tabla siguiente describe los informes y las herramientas de solución de problemas disponibles para los administradores de EOP.
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027147"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Informes y seguimiento de mensajes en Exchange Online Protection

Microsoft Exchange Online Protection (EOP) ofrece muchos informes diferentes que le ayudarán a determinan el estado general y el mantenimiento de la organización. También existen herramientas que le ayudarán a solucionar problemas de eventos específicos (por ejemplo, un mensaje no llegan a los destinatarios previstos) y de informes de auditoría para ayudar con los requisitos de cumplimiento. 

## <a name="usage-reports"></a>Informes de uso

**Actividad de grupos de Office 365** Ver información sobre el número de grupos de Office 365 que se crea y usa.  

**Actividad de correo electrónico** Ver información sobre el número de mensajes enviados, recibidos y leer en toda la organización y por usuarios específicos.  

**Uso de la aplicación de correo electrónico** Ver información sobre las aplicaciones de correo electrónico que se usan. Esto incluye el número total de conexiones para cada aplicación y las versiones de Outlook que se conectan.  

**Uso de buzón de correo** Ver información acerca del almacenamiento usado, consumo de cuota, recuento de elementos y la última actividad (enviar o la actividad de lectura) para los buzones de correo.

Vea los siguientes recursos para obtener más información:

- [Informes de Office 365 en el centro de administración - grupos de Office 365](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [Informes de Office 365 en el centro de administración - actividad de correo electrónico](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [Informes de Office 365 en el centro de administración - uso de aplicaciones de correo electrónico](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [Informes de Office 365 en el centro de administración - uso de buzón de correo](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a>Seguridad &amp; informes de cumplimiento de normas en el centro de administración de Office 365

Estos informes mejorados proporcionan una experiencia de creación de informes interactiva para los administradores EOP, que incluye la información de resumen y la capacidad de explorar en profundidad para obtener más detalles.  

**Protección de amenaza (ATP) avanzada** Ver información sobre vínculos seguros y los datos adjuntos seguros que forman parte de ATP.  

**Elevación de privilegios** Ver información sobre las detecciones de malware, correo falsificado, detecciones de spam y el flujo de correo a y desde la organización.  

[Visualización de informes de protección contra amenazas de avanzada y Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>Informes personalizados con Microsoft Graph

Crear mediante programación informes que están disponibles en el centro de administración de Office 365 mediante el uso de Microsoft Graph vea los temas secundarios de [trabajar con informes de uso de Office 365 en Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135) 

##<a name="custom-reports-using-reporting-web-services"></a>Informes personalizados mediante servicios Web de informes

Crear mediante programación informes desde el PowerShell de protección en línea de Exchange disponibles cmdlets de informes mediante el uso de filtrado de consulta REST/ODATA2.

Vea [servicios Web de Office 365 Reporting](https://go.microsoft.com/fwlink/p/?LinkId=279926) 

##<a name="message-trace"></a>Seguimiento de mensajes

Se muestra a continuación mensajes de correo electrónico cuando viajan a través de elevación de privilegios. Puede determinar si un mensaje de correo electrónico se ha recibido, rechazado, aplazado o emitido por el servicio. También se muestran las acciones realizadas en el mensaje antes de alcanzar su estado final.  

Puede usar esta información para responder a preguntas del usuario con eficacia, solucionar problemas del flujo de correo, validar los cambios de la directiva y elimina la necesidad de ponerse en contacto con soporte técnico para obtener ayuda.  

Vea el [seguimiento de un mensaje de correo electrónico](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) 

## <a name="audit-logging"></a>Registro de auditoría

Realiza un seguimiento de cambios específicos realizados por administradores de la organización. Estos informes pueden ayudarle a solucionar problemas de configuración o encontrar la causa de los problemas relacionados con el cumplimiento de normas o de seguridad.  ver [informes de auditoría en EOP](auditing-reports-in-eop.md) 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Informes, disponibilidad y latencia de los datos de seguimiento de mensajes

En la tabla siguiente se describe cuándo están disponibles los informes y los datos de seguimiento de mensajes de EOP y durante cuánto tiempo.
  
||||
|:-----|:-----|:-----|
|**Tipo de informe** <br/> |**Datos disponibles (período retrospectivo)** <br/> |**Latencia** <br/> |
|Informes de resumen de protección de correo  <br/> |90 días  <br/> |La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.  <br/> |
|Informes de detalles de protección de correo  <br/> |90 días  <br/> |Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días.  <br/> Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.  <br/> |
|Datos de seguimiento de mensajes  <br/> |90 días  <br/> |Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.  <br/> Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.  <br/> |
   
> [!NOTE]
> Latencia y disponibilidad de los datos es el mismo si se solicitan mediante el centro de administración de Office 365 o PowerShell remoto. 
  


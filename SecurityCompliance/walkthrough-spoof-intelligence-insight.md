---
title: Tutorial suplantación de información sobre inteligencia
ms.author: tracyp
author: MSFTTracyP
ms.date: 7/30/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Vea cómo funciona el nuevo conocimiento de inteligencia de TI de suplantación.
ms.openlocfilehash: cdfdf90779137455e0b74cea5fe41aee7b1b26e5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156072"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Tutorial: información sobre inteligencia de inteligencia de suplantación

Mediante el uso de la información de inteligencia de inteligencia de suplantación, puede determinar rápidamente qué remitentes le envían de forma legítima un correo no autenticado. Al permitirles enviar mensajes suplantados, puede reducir el riesgo de que los falsos positivos vayan a sus usuarios.
  
Además, también puede usar el monitor de inteligencia de suplantación de identidad (spoofing) y administrar pares de dominios permitidos para proporcionar un nivel adicional de seguridad y evitar que lleguen mensajes no seguros a su organización.
  
Puede usar el conocimiento de inteligencia de simulación en el &amp; centro de seguridad y cumplimiento si su cuenta profesional o educativa tiene permisos de administrador global, administrador de seguridad o lector de seguridad de Office 365. Para obtener más información, consulte Permissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
Si no está familiarizado con [los informes y la información del centro de seguridad &amp; y cumplimiento de Office 365](reports-and-insights-in-security-and-compliance.md), es posible que le resulte útil ver cómo puede navegar fácilmente desde un panel hasta una perspectiva y las acciones recomendadas.
  
Puede ver la información de inteligencia de inteligencia de suplantación de más de &amp; un panel en el centro de seguridad y cumplimiento. Independientemente del panel que esté mirando, la visión proporciona los mismos detalles y le permite realizar rápidamente las mismas tareas.
  
Este es uno de los diversos tutoriales del centro &amp; de seguridad y cumplimiento. Para obtener información sobre Cómo desplazarse por los informes y la información, vea los tutoriales de la sección temas relacionados.
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Obtención del conocimiento de inteligencia de suplantación &amp; en el centro de seguridad y cumplimiento

1. Para empezar, necesitará [ir al centro &amp; de seguridad y cumplimiento](go-to-the-securitycompliance-center.md).
    
2. En el centro &amp; de seguridad y cumplimiento, vaya a **Threat Management** \> **Dashboard.**
    
3. En la **** fila Insights, busque la información de inteligencia de inteligencia de suplantación. Si ha habilitado inteligencia de suplantación de identidad, la información tiene el derecho **de tener un derecho de dominio falsificado que no ha superado la autenticación de los últimos 30 días**. Si no ha habilitado la protección contra la suplantación de identidad, la información le pedirá que lo haga mediante el título **Habilitar la protección contra**la suplantación de identidad. 
    
## <a name="about-the-insight-on-the-dashboard"></a>Información sobre el panel

El conocimiento del panel muestra la información de este tipo.
  
![Captura de pantalla de la información sobre inteligencia de suplantación](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Esta visión tiene dos modos:
  
 **Modo Insight**. Si tiene una directiva de suplantación habilitada, la información le mostrará Cuántos correos se vieron afectados por nuestras capacidades de inteligencia empresarial de suplantación en los últimos 30 días. 
  
 **Mode if**. Si no tiene habilitada ninguna directiva de suplantación de identidad, la información le mostrará Cuántos correos se *verían* afectados por nuestras capacidades de inteligencia de suplantación en los últimos 30 días. 
  
En cualquier caso, los dominios suplantados que se muestran en la información se dividen en dos categorías; pares de dominios sospechosos y pares de dominios no sospechosos. Estas categorías se subdividen en tres diferentes recipientes para su revisión. 
  
Un *par de dominios* es una combinación de la dirección "de:" y la infraestructura de envío. 
  
- La dirección "de" es la dirección que muestra la dirección de de su aplicación de correo. Esta dirección identifica al autor del correo electrónico. Es decir, el buzón de la persona o el sistema responsable de escribir el mensaje. A veces, recibe la denominación dirección 5322.From.
    
- La infraestructura de envío o remitente es el dominio de la organización del registro PTR de la dirección IP de envío. Si la dirección IP de envío no tiene registro PTR, el remitente se identifica mediante la IP de envío con la máscara de subred 255.255.255.0 en la notación CIDR (/24). Por ejemplo, si la dirección IP es 192.168.100.100, la dirección IP completa del remitente es 192.168.100.100/24.
    
 Los **pares de dominios sospechosos** incluyen: 
  
- **Suplantación de confianza alta**. Office 365 recibió fuertes señales de que estos dominios son sospechosos, en función de los patrones de envío históricos y la puntuación de reputación de los dominios. Office 365 está muy seguro de que los dominios son suplantación de identidad y que los mensajes que se envían desde estos dominios tienen menos probabilidades de ser legítimos. 
    
- **Simulación de confianza moderada**. Office 365 recibió señales moderadas que estos dominios son sospechosos, en función de los patrones de envío históricos y la puntuación de reputación de los dominios. Office 365 está moderadamente seguro de que los dominios son suplantación de identidad y que los mensajes enviados desde estos dominios son legítimos. Este cubo tiene una probabilidad mayor de contener falsos positivos (FPs) que el bucket de suplantación de confianza alta. 
    
 Los **pares de dominios no sospechosos** incluyen la suplantación de **identidad recuperada**. La suplantación de identidad recuperada son dominios que no han superado las comprobaciones de autenticación explícitas ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) pero que han superado nuestras comprobaciones de autenticación extendidas. Como resultado, Office 365 rescate el correo en su nombre y no se ha llevado a cabo ninguna acción contra la suplantación de identidad en el correo. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Ver información detallada sobre los pares de dominios sospechosos desde el conocimiento de inteligencia de suplantación

1. En el análisis de inteligencia de suplantación de identidad, haga clic en cualquiera de los pares de dominios (alta, moderada o rescatada).
  
Aparece la página suplantar **visión de inteligencia empresarial** , que muestra una lista de remitentes que envían correo no autenticado a su organización. La información de esta página le ayudará a determinar si los mensajes falsos están autorizados o no o si necesita realizar alguna otra acción. Puede ordenar la información por número de mensajes, fecha de la última detección de la suplantación de identidad, etc. (Por ejemplo, haga clic en encabezados de columna, como **número de mensajes** o **última**vista). 
    
2. Seleccione un elemento de la tabla para abrir un panel de detalles que contenga información enriquecida sobre el par de dominios, incluido por qué lo hemos capturado, lo que debe hacer, un resumen de dominio, datos WhoIs sobre el remitente y mensajes de correo electrónico similares que hemos visto en su espacio empresarial del mismo remitente. Desde aquí, también puede Agregar o quitar el par de dominios de la lista de remitentes seguros de **AllowedToSpoof** . 
  
![Captura de pantalla de un dominio en el panel de detalles de inteligencia empresarial de suplantación](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Agregar o quitar un dominio de la lista de remitentes seguros de AllowedToSpoof

Puede Agregar o quitar un dominio de la lista de remitentes seguros de AllowedToSpoof al revisar el par de dominios en el panel de detalles de la información de inteligencia empresarial de suplantación. Simplemente, establezca el botón de alternancia en consecuencia.
  
Esto modifica la combinación única de par de dominios del dominio falso y de la infraestructura de envío y no proporciona cobertura para todo el dominio falso o la infraestructura de envío de forma aislada. Por ejemplo, si agrega el siguiente par de dominios a la lista de permitidos del remitente: " ** gmail.com" y *envía la infraestructura* "TMS *. mx.com",* sólo se permitirá la suplantación de correo desde ese par de dominios. Otros remitentes que intentan imitar "gmail.com" y otros dominios que intentan simular "tms.mx.com" seguirán protegidos por inteligencia de suplantación de identidad. 
  
## <a name="related-topics"></a>Temas relacionados

[Obtener más información sobre la inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md)
  
[Protección contra suplantación de identidad en Office 365](anti-spoofing-protection.md)
  
[Tutorial: desde un panel o a un reporte](from-a-dashboard-to-an-insight.md)
  
[Tutorial: desde un informe detallado a un reporte](from-a-detailed-report-to-an-insight.md)
  
[Tutorial: desde un reporte a un informe detallado](from-an-insight-to-a-detailed-report.md)
  


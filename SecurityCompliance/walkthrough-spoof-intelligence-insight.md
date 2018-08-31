---
title: Entendimiento de inteligencia de suplantación de tutorial
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: Vea cómo funciona el entendimiento de inteligencia de suplantación de la nueva.
ms.openlocfilehash: ca9c4ae6f2d65ef2700a2e02acd5b4f1dfbfe903
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22596099"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Tutorial: suplantación de la inteligencia insight

Mediante el uso de la perspectiva de suplantación de la inteligencia, puede determinar rápidamente qué remitentes se envían legítima que no autenticado correo electrónico. Por lo que les permite enviar mensajes falsos, puede reducir el riesgo de los falsos positivos que se va a los usuarios.
  
Además, también puede utilizar el monitor de suplantación de la inteligencia y administrar pares de dominio permitidos para proporcionar un nivel adicional de seguridad y evitar que los mensajes no seguros que llega en su organización.
  
Puede usar el entendimiento de suplantación de la inteligencia de la seguridad &amp; centro de cumplimiento si la cuenta de trabajo o escuela se han concedido permisos de lectura de seguridad, Administrador de seguridad o administrador global de Office 365. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
  
Si está familiarizado con [informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento de normas](reports-and-insights-in-security-and-compliance.md), que puede resultar útil para ver cómo puede navegar fácilmente desde un panel a un entendimiento y acciones recomendadas.
  
Puede ver el entendimiento de suplantación de la inteligencia de más de un panel en la seguridad &amp; centro de cumplimiento. Independientemente de qué panel que está viendo, la profundidad proporciona los detalles de la misma y le permite realizar con rapidez las mismas tareas.
  
Se trata de uno de varios tutoriales para la seguridad &amp; centro de cumplimiento. A sobre cómo desplazarse por informes y conocimientos, vea los tutoriales en la sección Temas relacionados.
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Introducción a la idea de inteligencia simulado la seguridad &amp; centro de cumplimiento

1. Para empezar, necesitará [vaya a la seguridad &amp; centro de cumplimiento](go-to-the-securitycompliance-center.md).
    
2. En la seguridad &amp; centro de cumplimiento, ir a la **Administración de amenaza** \> **panel.**
    
3. En la fila de **conocimientos** , busque el entendimiento de inteligencia de suplantación. Si ha habilitado la suplantación de la inteligencia, entonces el entendimiento es derecho **dominios Spoofed que no se pudo autenticación de los últimos 30 días**. Si no ha habilitado la suplantación de la protección, el entendimiento le pedirá que hacerlo mediante el título **Habilitar protección de suplantación**. 
    
## <a name="about-the-insight-on-the-dashboard"></a>Acerca de la información en el panel

La información en el panel muestra información similar.
  
![Captura de pantalla de entendimiento de inteligencia de suplantación](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Este entendimiento tiene dos modos:
  
 **Modo de insight**. Si tiene cualquier directiva de suplantación habilitada, a continuación, el entendimiento muestra cuántos correos afectó nuestras capacidades de inteligencia de suplantación durante los últimos 30 días. 
  
 **¿Qué ocurre si el modo**. Si no tiene ninguna directiva de suplantación habilitado, a continuación, el entendimiento muestra cuántos mensajes de correo *tendría* se han visto afectados por nuestras capacidades de inteligencia de suplantación durante los últimos 30 días. 
  
En ambos casos, los dominios simulados que se muestra en la información se dividen en dos categorías; pares de dominio sospechosos y pares de dominio que no sean sospechosos. Estas categorías se subdividen en tres depósitos diferentes para revisar. 
  
Un *par de dominio* es una combinación de la "de:" dirección y la infraestructura de envía. 
  
- La dirección "Desde" es la dirección que se muestra como la dirección de origen por la aplicación de correo. Esta dirección identifica al autor del correo electrónico. Es decir, el buzón de correo de la persona o del sistema responsable de escribir el mensaje. En ocasiones, esto se denomina la dirección 5322.From.
    
- La infraestructura de envío o el remitente, es el dominio organizativo del registro PTR de la dirección IP de envío. Si la dirección IP de envío no tiene ningún registro PTR, a continuación, el remitente es identificado por la dirección IP remitente con el 255.255.255.0 máscara de subred en notación CIDR (/ 24). Por ejemplo, si la dirección IP es 192.168.100.100 192.168.100.100/24 es la dirección IP completa del remitente.
    
 **Pares de dominio sospechosos** se incluyen: 
  
- **Suplantación de alta confianza**. Office 365 ha recibido una señal potente que estos dominios están sospechosos, en función de los patrones de envío históricos y la puntuación de reputación de los dominios. Office 365 es muy seguro de suplantación de los dominios y que los mensajes enviados desde estos dominios están menos probable que legítimo. 
    
- **Suplantación de la confianza moderada**. Office 365 había recibido moderadas señales que estos dominios están sospechosos, en función de los patrones envío históricos y la puntuación de reputación de los dominios. Office 365 es moderadamente seguro de suplantación de los dominios y que los mensajes enviados desde estos dominios son legítimos. Este cubo tiene una mayor posibilidad de que contiene falsos positivos (FPs) que el cubo de suplantación de alta confianza. 
    
 **Pares de dominio sospechosos de no** incluir **recuperado falsos**. Suplantación de recuperada son dominios que no se pudo las comprobaciones de autenticación explícita ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) pero se pasan nuestras comprobaciones de autenticación extendida. Como resultado de ello, Office 365 había recuperado el correo en su nombre y se ha realizado ninguna acción contra la suplantación en el correo. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Ver información detallada acerca de los pares de dominio sospechosos desde la perspectiva de inteligencia de suplantación

1. En el entendimiento de inteligencia de suplantación, haga clic en cualquiera de los pares de dominio (altos, moderados o recuperados).
  
Aparece la página de **Suplantación de la inteligencia Insight** que muestra una lista de los remitentes que envían correo no autenticado en la organización. La información de esta página le ayudará a determinar si están autorizados los mensajes falsos o no o si es necesario realizar ninguna acción. Puede ordenar la información por recuento de mensajes, la fecha en que se detectó por última vez la suplantación, y mucho más. (Haga clic en los encabezados de columna, como **recuento de mensaje** o **visto por última vez**, por ejemplo.) 
    
2. Seleccione un elemento en la tabla para abrir un panel de detalles que contiene información enriquecida sobre el par de dominio, incluyendo ¿por qué se capturó esto, lo que necesita llevar a cabo, un resumen de dominio, la base de datos WhoIs sobre el remitente y mensajes de correo electrónico similar hemos visto en el inquilino del mismo remitente. Desde aquí, también puede elegir agregar o quitar el par de dominio de la lista de remitentes seguros de **AllowedToSpoof** . 
  
![Captura de pantalla de un dominio en el panel de detalles de suplantación de la inteligencia insight](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Agregar o quitar un dominio de la lista de remitentes seguros AllowedToSpoof

Agregar o quitar un dominio de la lista de remitentes seguros AllowedToSpoof mientras revisa el par de dominio en el panel de detalles de la perspectiva de inteligencia de suplantación. Simplemente establece la alternancia según corresponda.
  
Esto modifica la combinación de par de dominio único del dominio falso y la infraestructura de envía y no proporciona cobertura para todo el dominio falso o la infraestructura de envía en el aislamiento. Por ejemplo, si agrega el par de dominio siguientes al remitente 'AllowedToSpoof' lista de permitidos: *Suplantar dominio* "gmail.com" y el *Envío de infraestructura* "memorias *. mx.com",* , a continuación, podrán suplantar sólo correo de par de ese dominio. Otros remitentes intentando suplantar "gmail.com" y otros dominios que "tms.mx.com" intento de suplantar seguirán siendo protegidos por inteligencia de suplantación de la. 
  
## <a name="related-topics"></a>Temas relacionados

[Obtenga más información sobre la inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md)
  
[Protección contra suplantación de identidad en Office 365](anti-spoofing-protection.md)
  
[Tutorial: desde un panel o a un reporte](from-a-dashboard-to-an-insight.md)
  
[Tutorial: desde un informe detallado a un reporte](from-a-detailed-report-to-an-insight.md)
  
[Tutorial: desde un reporte a un informe detallado](from-an-insight-to-a-detailed-report.md)
  


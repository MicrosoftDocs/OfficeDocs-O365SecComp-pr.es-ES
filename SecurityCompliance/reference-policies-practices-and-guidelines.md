---
title: Referencia Políticas, prácticas y directrices
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
description: Microsoft ha desarrollado varias directivas, procedimientos y adoptadas varios procedimientos recomendados del sector para ayudar a proteger a nuestros usuarios de correo electrónico abusivo, no deseado o malintencionado.
ms.openlocfilehash: e552128a06ce942383e7c5410508df61331fb874
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003089"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referencia: Políticas, prácticas y directrices
  
Microsoft se centra en ayudarle a que disfrute de la experiencia web de usuario más confiable. Por ello, Microsoft ha desarrollado diversas políticas y procedimientos, y adoptado varias prácticas recomendadas del sector para ayudar a proteger a nuestros usuarios de correo electrónico abusivo, no deseado o malintencionado. Los remitentes que intenten enviar correo electrónico a usuarios de Office 365 deben asegurarse de que comprenden completamente y siguen las instrucciones de este artículo para colaborar en este esfuerzo y ayudar a evitar posibles problemas de entrega.
  
Si no cumple estas políticas y directrices, es posible que nuestro equipo de soporte técnico no pueda ayudarle. Si cumple las directrices, prácticas y políticas que se presentan en este artículo y sigue experimentando problemas de entrega basados en su dirección IP de remitente, siga los pasos para enviar una solicitud de eliminación de la lista. Para obtener instrucciones, vea [Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados de Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).
  
## <a name="general-microsoft-policies"></a>Directivas generales de Microsoft
<a name="GenMsftPolicies"> </a>

Los correos electrónicos enviados a los usuarios de Office 365 deben cumplir todas las directivas de Microsoft relativas a la transmisión de correo electrónico y al uso de Office 365.
  
- Condiciones de servicio aplicables a Office 365. En concreto, la prohibición de usar el servicio para enviar correo electrónico no deseado o distribuir malware
    
- [Acuerdo de servicios de Microsoft](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a>Regulaciones gubernamentales
<a name="GovtRegulations"> </a>

Los correos electrónicos enviados a los usuarios de Office 365 deben cumplir todas las leyes y regulaciones que rigen las comunicaciones por correo electrónico en la jurisdicción aplicable.
  
- [Ley estadounidense CAN-SPAM: guía de cumplimiento para empresas](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- [Respuestas y responsabilidades de "Anular suscripción": el personal de marketing de correo electrónico debe respetar las solicitudes de "Cancelar suscripción"](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a>Directrices técnicas
<a name="TechGuidelines"> </a>

Los correos electrónicos enviados a Office 365 deben cumplir las recomendaciones aplicables que figuran en los siguientes documentos (algunos vínculos solo están disponibles en inglés).
  
- [RFC 2505: Recomendaciones frente a correo electrónico no deseado para MTA de SMTP](https://www.ietf.org/rfc/rfc2505.txt)
    
- [RFC 2920: Extensión de servicio SMTP para la canalización de comandos](https://www.ietf.org/rfc/rfc2920.txt)
    
Además, los servidores de correo electrónico que se conecten a Office 365 deben cumplir los siguientes requisitos:
  
- El remitente debe cumplir todas las normas técnicas para la transmisión de correo electrónico de Internet, conforme publica el Grupo de trabajo de ingeniería de Internet (IETF) de The Internet Society, incluidos RFC 5321, RFC 5322 y otros. 
    
- Después de recibir un código de respuesta de error SMTP entre 500 y 599 (también conocido como respuesta permanente de no entrega o un NDR), el remitente no debe intentar volver a transmitir ese mensaje a ese destinatario.
    
- Después de varias respuestas de no entrega, el remitente debe dejar de intentar enviar correo electrónico a ese destinatario.
    
- Los mensajes no deben transmitirse a través de servidores proxy o de retransmisión de correo electrónico no seguros.
    
- El mecanismo para darse de baja de listas individuales o de todas las listas alojadas por el remitente debe estar claramente documentado y ser fácil de encontrar y usar por parte de los destinatarios.
    
- No se aceptarán conexiones de espacio IP dinámico.
    
- Los servidores de correo electrónico deben tener registros de DNS inversos válidos.
    
## <a name="reputation-management"></a>Administración de la reputación
<a name="RepManagement"> </a>

Los remitentes, ISP y otros proveedores de servicios deben administrar activamente la reputación de sus direcciones IP salientes.
  
## <a name="office-365-limits"></a>Límites de Office 365
<a name="sectionSection4"> </a>

Los remitentes deben aceptar los límites de Office 365 enumerados en [Límites de Exchange Online Protection](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx).
  
## <a name="email-delivery-resources-and-organizations"></a>Organizaciones y recursos de entrega de correo electrónico
<a name="sectionSection5"> </a>

Microsoft trabaja activamente con los organismos de la industria y los proveedores de servicios a fin de mejorar el ecosistema de Internet y correo electrónico. Estas organizaciones han publicado documentos sobre prácticas recomendadas con los que estamos de acuerdo y recomienda a los remitentes que sigan sus recomendaciones porque mejoran su capacidad para entregar correo electrónico entre varios proveedores de servicios de correo electrónico de todo el mundo.
  
- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)
    
- [Alliance de confianza en línea](https://www.otalliance.org/resources)
    
- [Email Sender &amp; Provider Coalition](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a>Informar sobre abusos y correo no deseado
<a name="AbuseSpamReports"> </a>

Para informar de correo electrónico ilegal, ofensivo, no deseado o malintencionado, [informe deseado las estafas de suplantación de identidad y de correo electrónico en Outlook en el web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Enviar estos tipos de comunicaciones es una infracción de la directiva de Microsoft y en los informes confirmados se llevará a cabo la acción adecuada.
  
## <a name="law-enforcement"></a>Cumplimiento de la ley
<a name="sectionSection7"> </a>

Si es miembro de un órgano de mantenimiento del orden público y quiere ayudar a Microsoft Corporation con documentación legal relacionada con Office 365 o si tiene preguntas sobre la documentación legal que ha enviado a Microsoft, llame al +(1) (425) 722-1299.
  


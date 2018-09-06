---
title: Vínculos seguros ATP de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La característica vínculos seguros proporciona comprobación de tiempo de clic de los hipervínculos en documentos de Office y en los mensajes de correo electrónico. Use los vínculos seguros para proteger la organización de suplantación de identidad y otros ataques.
ms.openlocfilehash: 24960aa20d2870c7aea37a4b76f1792de21f6b5b
ms.sourcegitcommit: a8884b9675559018e1fddec1c0cc2de0bc3bdde5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839950"
---
# <a name="office-365-atp-safe-links"></a>Vínculos seguros ATP de Office 365

Office 365 ATP seguros vínculos (ATP seguros vínculos) (junto con los [Datos adjuntos seguros de Office 365 ATP](atp-safe-attachments.md)) es un conjunto de características de seguridad que se ofrece como parte de [La protección de amenaza avanzada de Office 365](office-365-atp.md) para las organizaciones empresariales. Vínculos seguros ATP puede ayudar a proteger su organización proporcionando comprobación de tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos de Office. Protección se define a través de [vínculos seguros ATP directivas](set-up-atp-safe-links-policies.md) que se han establecido por el equipo de seguridad de Office 365. 
  
Una vez que las directivas de vínculos seguros ATP, los administradores globales de Office 365, los administradores de seguridad y los lectores de seguridad pueden [Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md). La información en los informes puede ayudar al equipo de seguridad lleve a cabo pasos adicionales para proteger su organización o la investigación de incidentes de seguridad.
  
Las nuevas características se están agregando continuamente a los vínculos seguros ATP:
  
- A partir de las últimas de 2017 octubre, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en correo electrónico, así como las direcciones URL en documentos de Office 365 ProPlus, como Word, Excel, PowerPoint y Visio en Windows, así como Office las aplicaciones de iOS y dispositivos Android.
    
- A partir de marzo de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a correo electrónico enviado entre las personas de una organización.
    
- A partir de la segunda parte de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en Office Online (en línea de Word, Excel Online, Online de PowerPoint y OneNote en línea) y Office 365 ProPlus en Mac.
    
- Principio en septiembre de 2018, la característica de [páginas de advertencia de Office 365 ATP](atp-safe-links-warning-pages.md) una nueva combinación de colores, más detalles y la capacidad para seguir a un sitio a pesar de recibir advertencias y recomendaciones. 
         
## <a name="how-atp-safe-links-in-email-works"></a>Cómo funciona la ATP vínculos seguros en el correo electrónico

En un nivel alto, aquí es cómo funciona la protección de vínculos seguros de ATP para las direcciones URL en el correo electrónico (hospedado en Office 365, no local):
  
1. Personas reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.
    
2. Todos los correos electrónicos circula a través de Exchange Online Protection, donde el protocolo de internet (IP) y sobre los filtros, firma-based malware protection, contra correo no deseado y se aplican los filtros de protección contra malware. 
    
3. Correo electrónico llega a las bandejas de entrada de otras personas.
    
4. Un usuario inicia sesión en Office 365 y va a su Bandeja de entrada de correo electrónico.
    
5. El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.
    
6. La característica vínculos seguros ATP inmediatamente comprueba la dirección URL antes de abrir el sitio Web. La dirección URL se identifica como bloqueado, malintencionado o seguros.
    
    - Si la dirección URL es un sitio Web que se incluye en una [lista de direcciones URL de "no volver a escribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se abre el sitio Web. 
    
    - Si la dirección URL es un sitio Web que se incluye en la [lista de direcciones URL bloqueado personalizada](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se abre una [página de advertencia](atp-safe-links-warning-pages.md) . 
    
    - Si la dirección URL a un sitio Web que se ha determinado que ser malintencionado, se abrirá una [página de advertencia](atp-safe-links-warning-pages.md) . 
    
    - Si la dirección URL que se va a un archivo descargable y [vínculos seguros ATP directivas](set-up-atp-safe-links-policies.md) de su organización están configurados para examinar este tipo de contenido, se comprueba el archivo descargable. 
    
    - Si la dirección URL se determina como seguros, se abre el sitio Web.
    
## <a name="how-atp-safe-links-in-office-documents-works"></a>Cómo funciona la ATP vínculos seguros en documentos de Office

En un nivel alto, aquí es cómo funciona la protección de vínculos seguros de ATP para las direcciones URL en aplicaciones de Office 365 ProPlus (versiones actuales de OneNote, Word, Excel y PowerPoint en Windows o Mac, las aplicaciones de Office de iOS o dispositivos Android, Visio en Windows y Office Online):
  
1. Personas tener instalado Office 365 ProPlus en su equipo, smartphone o Tablet PC.
    
2. Un usuario abre un Word, Excel, PowerPoint o Visio e inicia sesión en Office 365 Enterprise mediante su cuenta de trabajo o escuela. El documento contiene las direcciones URL.
    
3. Cuando el usuario hace clic en una dirección URL del documento, se comprueba el vínculo por el servicio de vínculos seguros de ATP.
    
  - Si la dirección URL es un sitio Web que se incluye en una [lista de direcciones URL de "no volver a escribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se toma ese usuario al sitio Web. 
    
  - Si la dirección URL es un sitio Web que se incluye en la [lista de direcciones URL bloqueado personalizada](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se toma el usuario a una [página de advertencia](atp-safe-links-warning-pages.md).
    
  - Si la dirección URL es un sitio Web que se ha determinado que ser malintencionado, se toma el usuario a una [página de advertencia](atp-safe-links-warning-pages.md).
    
  - Si la dirección URL que se va a un archivo descargable y las [directivas de ATP seguros vínculos](set-up-atp-safe-links-policies.md) están configurados para examinar tales descargas, se comprueba el archivo descargable. 
    
  - Si la dirección URL se considera segura, se toma el usuario para el sitio Web.
    
## <a name="how-to-get-atp-safe-links-protection"></a>Cómo obtener protección vínculos seguros de ATP

Características de vínculos seguros de ATP forman parte de la [Protección avanzada de amenaza](office-365-atp.md), incluido en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, protección avanzada de amenaza puede adquirirse como un complemento. Para obtener más información, vea [Descripción del servicio Office 365 plataforma: seguridad de Office 365 &amp; centro de cumplimiento](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento de Office 365 para profesionales](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).
  
Las características de ATP seguros vínculos están activos cuando:
  
- **Las directivas de vínculos seguros de ATP se configuran** para el correo electrónico y para documentos de Word, Excel, PowerPoint y Visio. (Vea [configurar las directivas de ATP vínculos seguros en Office 365](set-up-atp-safe-links-policies.md)).

- **Aplicaciones de cliente de office 365 están configuradas para usar autenticación moderno** con Azure Active Directory autenticación Library. Para obtener más información, vea [Moderno Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016). 
    
- **Los usuarios han iniciado sesión en Office 365** mediante su cuenta de trabajo o escuela. (Vea [iniciar sesión en Office 365 o de Office](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)).
    
- **Que correo electrónico de la organización está hospedado en Office 365**, no en un servidor local. 
    
## <a name="make-sure-atp-safe-links-protection-is-in-place"></a>Asegúrese de que la protección de ATP seguros vínculos está en su lugar

Es una buena manera de ver cómo funciona protección vínculos seguros de ATP para su organización mediante la [visualización de informes de protección avanzada de amenaza](view-reports-for-atp.md). Además, como administrador global o de seguridad, asegúrese de revisar las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md). Las directivas de vínculos seguros ATP determinan si protección se aplica a los hipervínculos en mensajes de correo electrónico sólo, o a las direcciones URL en documentos de Office así como.
  
En la siguiente tabla se describe algunos escenarios de ejemplo donde protección vínculos seguros ATP puede ser o no en su lugar. En todos estos casos, se supone que la organización tiene E5 Enterprise de Office 365.
  
|**Escenario de ejemplo**|**¿Se aplica protección vínculos seguros de ATP en este caso?**|
|:-----|:-----|
|Jean es un miembro de un grupo que tiene directivas de vínculos seguros de ATP que tratan sobre las direcciones URL en correo electrónico y documentos de Office. Jean abre una presentación que alguien envía en 2016 de PowerPoint y, a continuación, hace clic en una dirección URL de la presentación.  <br/> |Sí. Las directivas de vínculos seguros de ATP que se definen se aplican a de Jean grupo, de Jean correo electrónico y documentos de Word, Excel, PowerPoint o Visio que se abre Jean, siempre y cuando Jean ha iniciado sesión en y uso de Office 365 ProPlus en dispositivos Android, iOS o Windows.  <br/> |
|En la organización, no global o la seguridad de Chris los administradores han definido las directivas de vínculos seguros ATP todavía. Chris recibe un correo electrónico que contiene una dirección URL a un sitio Web malintencionado. Chris no conoce la dirección URL es malintencionada y hace clic en el vínculo.  <br/> |No. La directiva predeterminada que se trata las direcciones URL para todas las personas de la organización debe definirse en orden para la protección a estar en su lugar.  <br/> |
|En la organización, no global o la seguridad de Pat administradores han definido o editar las directivas de vínculos seguros ATP todavía. Pat abre un documento de Word y hace clic en una dirección URL en el archivo.  <br/> |Directiva de No. A que incluye documentos de Office debe definirse en orden para la protección a estar en su lugar. Consulte [configurar las directivas de vínculos seguros ATP de Office 365](set-up-atp-safe-links-policies.md).<br/> |
|Organización de Díaz tiene una directiva de vínculos seguros de ATP que tiene `http://tailspintoys.com` aparece como un sitio Web bloqueado. Lee recibe un mensaje de correo electrónico que contiene una dirección URL a `http://tailspintoys.com/aboutus/trythispage`. Lee hace clic en la dirección URL.<br/> |Depende de si todo el sitio y todos sus subpáginas se incluyen en la lista de URL bloquean. Consulte [Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).<br/> |
|Pablo, compañeros de Jean, envía un correo electrónico a Jean, sin saber que el correo electrónico contiene una dirección URL malintencionada.  <br/> |Depende de si se definen las directivas de vínculos seguros de ATP para el correo electrónico enviado dentro de la organización. Consulte [configurar las directivas de vínculos seguros ATP de Office 365](set-up-atp-safe-links-policies.md).<br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Configurar directivas de vínculos seguros de ATP en Office 365](set-up-atp-safe-links-policies.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)
  
[Funciones de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md)
  
[Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md)
  


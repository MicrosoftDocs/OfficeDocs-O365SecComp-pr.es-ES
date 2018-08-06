---
title: Lucha contra el correo no deseado enviado a Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
description: El plan de seguridad para el correo electrónico de Microsoft incluye un enfoque sin igual que abarca diferentes productos. En las plataformas de correo electrónico de Microsoft se aplica tecnología de Exchange Online Protection (EOP) de filtrado de correo no deseado y protección contra suplantación de identidad para proporcionar a los usuarios las últimas herramientas e innovaciones contra el correo no deseado y la suplantación de identidad en toda la red. El objetivo de EOP es ofrecer un servicio de correo electrónico completo y práctico que ayude a detectar el correo no deseado, las amenazas de correo electrónico fraudulento (phishing) y los virus, y que proteja a los usuarios de todo ello.
ms.openlocfilehash: dafcb827a323461936eadcd00c37fabd43005a80
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026357"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Lucha contra el correo no deseado enviado a Office 365

El plan de seguridad para el correo electrónico de Microsoft incluye un enfoque sin igual que abarca diferentes productos. En las plataformas de correo electrónico de Microsoft se aplica tecnología de Exchange Online Protection (EOP) de filtrado de correo no deseado y protección contra suplantación de identidad para proporcionar a los usuarios las últimas herramientas e innovaciones contra el correo no deseado y la suplantación de identidad en toda la red. El objetivo de EOP es ofrecer un servicio de correo electrónico completo y práctico que ayude a detectar el correo no deseado, las amenazas de correo electrónico fraudulento (phishing) y los virus, y que proteja a los usuarios de todo ello.
  
## <a name="the-challenge"></a>El desafío

El correo electrónico se ha convertido en una importante herramienta de comunicación no solo para los consumidores, sino también para los vendedores, el personal de soporte, las organizaciones de ventas y las empresas de cualquier tamaño. A medida que su uso aumenta, también lo hace el abuso. El correo electrónico no deseado y no supervisado puede colapsar las bandejas de entrada y las redes, afectar al grado de satisfacción del usuario y limitar la eficacia de las comunicaciones legítimas. Por eso Microsoft sigue invirtiendo en tecnologías contra el correo no deseado. Sencillamente se trata de contener y filtrar el correo electrónico no deseado.  
  
## <a name="our-efforts"></a>Nuestros esfuerzos

EOP ofrece una serie de pasos para minimizar el impacto negativo que el correo no deseado tiene sobre la experiencia de nuestros usuarios.
  
### <a name="exchange-online-protection-technology"></a>Tecnología de Exchange Online Protection

Para ayudar a reducir el correo electrónico no deseado, EOP incluye protección contra el correo no deseado mediante tecnologías de filtrado de la propiedad de EOP que examinan el correo electrónico para identificar y separar el correo electrónico no deseado del correo legítimo. El filtro de contenido de EOP aprende de las amenazas conocidas de suplantación de identidad y de correo no deseado además de los comentarios de los usuarios de nuestra plataforma de clientes, Outlook.com. Estos tipos de datos ayudan al aprendizaje de las tecnologías de EOP para reconocer el correo electrónico legítimo y el no deseado y son aportaciones clave para la reputación del remitente. Los comentarios continuos de los usuarios de EOP que participan en el programa de clasificación de correo electrónico no deseado garantizan que las tecnologías de EOP estén en un proceso continuo de aprendizaje y mejora.
  
#### <a name="how-does-eop-work"></a>¿Cómo funciona EOP?

Cuando un usuario externo envía un mensaje de correo electrónico a un usuario de EOP, las tecnologías de filtrado de EOP evalúan el contenido del mensaje y asignan una calificación al mensaje basándose en la probabilidad de que el mensaje sea correo electrónico no deseado. Esta clasificación se almacena como una propiedad del mensaje llamada Nivel de confianza contra correo no deseado (SCL) dentro del propio mensaje. La calificación SCL permanece con el mensaje mientras se envía a otras capas de protección contra correo no deseado de EOP. 
  
EOP cuenta con reglas internas establecidas para administrar los mensajes de correo electrónico según varias calificaciones SCL. Si un mensaje tiene una calificación SCL inferior a un determinado umbral, se considera correo no deseado. El mensaje se pondrá en cuarentena o se enviará a la carpeta de correo no deseado del usuario dependiendo de cómo configure el administrador del sistema la opción de entrega de correo no deseado.
  
#### <a name="eop-filters"></a>Filtros de EOP

Además de las tecnologías de filtrado contra correo no deseadas, EOP ofrece también el administrador del sistema la capacidad para establecer los niveles de filtro para personalizar aún más la entrega de correo electrónico a sus cuentas de usuario. Los administradores pueden agregar fácilmente un remitente o nombre de dominio a la lista de dominios y de remitentes seguros para que el correo electrónico de ese remitente o dominio no se trata nunca como correo no deseado con independencia del contenido del mensaje. Para obtener información, vea [remitentes seguros y remitentes bloqueados se enumeran en Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).
  
### <a name="phishing-protection"></a>Protección contra suplantación (phishing)

Phishing (pronunciado "fishing") es una forma de robo de identidad y una de las amenazas que más rápido crece en Internet. Normalmente un mensaje de suplantación de identidad se puede identificar porque solicita información personal o financiera o incluye un vínculo a un sitio web que solicita este tipo de información. EOP ofrece protección contra la suplantación de identidad como parte de las tecnologías de filtrado de la propiedad de EOP. Las tecnologías de filtrado de EOP analizan los correos electrónicos para detectar vínculos fraudulentos o dominios falsificados para proteger a los usuarios de estos tipos de estafas en línea.
  
#### <a name="how-does-phishing-protection-work"></a>¿Cómo funciona la protección contra la suplantación de identidad?

Los mensajes de correo electrónico de suplantación de identidad suelen contener un vínculo que, una vez que se hace clic en él, redirige a los usuarios a un sitio web fraudulento que aparenta ser válido (como el de su institución financiera o servicio en línea). En este sitio de suplantación de identidad se suele pedir a los usuarios que especifiquen información personal, como nombres de usuario, contraseñas o números de la seguridad social. Cualquier información especificada en el sitio de suplantación de identidad ayuda al suplantador a robar su identidad. El uso de marcas y logotipos de confianza reconocidos permite a los suplantadores parecer legítimos. La tecnología de filtrado contra la suplantación de identidad que se ofrece en EOP busca potenciales características de suplantación de identidad en el correo electrónico. Si las detecta, el correo electrónico se mueve a la carpeta de Correo no deseado.
  
Microsoft centra su tecnología contra la suplantación de identidad en dos frentes: primero en evitar que los correos electrónicos de suplantación de identidad lleguen a nuestros usuarios y segundo en eliminar la posibilidad de que sean engañados por mensajes y sitios web falsificados. 
  
> [!TIP]
> Internet Explorer versión 7 y superior bloqueará a los usuarios o les advertirá cuando visiten sitios conocidos o potenciales de suplantación de identidad, de modo que no sean engañados para proporcionar información personal. [Asegúrese de que tiene la versión más reciente de Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx). 
  
#### <a name="authentication"></a>Autenticación

La suplantación de dominios es una manera de imitar una dirección de correo electrónico legítima para que el mensaje fraudulento parezca legítimo. Organizaciones e individuos malintencionados usan la suplantación en estafas de suplantación de identidad para engañar a los usuarios con el fin de que divulguen información personal confidencial. La revelación de dicha información puede llevar al robo de identidad y a otros tipos de fraude.
  
EOP usa Sender Protection Framework (SPF), DomainKeys Identified Mail (DKIM) y Domain-based Message Authentication, Reporting and Conformance (DMARC) y otras autenticaciones implícitas para comprobar que los mensajes provengan realmente de ese dominio del que afirman que provienen. Se recomienda que todos los remitentes usen SPF y DKIM para proteger a sus destinatarios del correo no deseado y de las estafas de suplantación de identidad. Recomendamos a los remitentes que consideren la posibilidad de publicar un DMARC para rechazar o poner en cuarentena el correo enviado por remitentes no autorizados.
  
- Para obtener más información sobre SPF, vea [RFC 7208](https://tools.ietf.org/html/rfc7208) y [Marco de directivas de remitente ](http://www.openspf.org/).
    
- Para obtener más información sobre DKIM, vea [RFC 6376](https://tools.ietf.org/html/rfc6376) y [DKIM.org](http://dkim.org/).
    
- Para obtener más información sobre DMARC, vea [DMARC.org](https://dmarc.org/).
    
### <a name="legislation"></a>Legislación

En Microsoft creemos que el desarrollo de nuevas tecnologías y la autorregulación requieren el apoyo de políticas gubernamentales y marcos legales eficaces. El auge mundial del correo no deseado ha impulsado a varios cuerpos legislativos a regular el correo electrónico comercial. Muchos países o regiones ya cuentan con legislación contra el correo no deseado. En los Estados Unidos existen leyes federales y estatales para la regulación del correo no deseado. Este enfoque complementario está contribuyendo a reducir la cantidad de correo no deseado a la vez que permite que el comercio electrónico legítimo prospere. La ley CAN-SPAM amplía las herramientas disponibles para restringir los mensajes de correo electrónico fraudulentos y engañosos.
  


---
title: Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: Al configurar las directivas de los datos adjuntos seguros ATP, elija entrega dinámica para evitar retrasos de mensaje y permiten a los usuarios obtener una vista previa de datos adjuntos que se están analizando.
ms.openlocfilehash: 23ef316ed35b89ef1fad5e9639dd10e76036a4f3
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965247"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros

Entrega dinámica es una opción que puede seleccionar para. Lea este artículo para obtener más información acerca de la entrega dinámica y las capacidades de vista previa de datos adjuntos en [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).
  
## <a name="how-dynamic-delivery-works"></a>Dinámico cómo funciona la entrega

Al [configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md), puede elegir entre varias opciones, como **bloque**, **Reemplazar**y **Entrega dinámica**. Dependiendo de cómo se configuran las directivas, los destinatarios de correo electrónico pueden experimentar un retraso en la entrega de correo electrónico secundario mientras se examinan los datos adjuntos. Para evitar retrasos de mensaje, elija **Entrega dinámica**.
  
La opción de entrega dinámica elimina los retrasos de correo electrónico mediante el envío el cuerpo de un mensaje de correo electrónico a través de con un marcador de posición para cada dato adjunto de correo electrónico. El marcador de posición permanece hasta que los datos adjuntos se examinan por [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md). Destinatarios de correo electrónico pueden leer y responder a sus mensajes de correo electrónico inmediatamente, sabiendo que se están analizando sus datos adjuntos.
  
La mayoría de los archivos PDF y Office documentos pueden ser una vista previa en modo seguro mientras ATP análisis está en curso. Si un archivo adjunto no es compatible con el controlador de vista previa dinámica de entrega, los destinatarios de correo electrónico ven el marcador de posición de datos adjuntos hasta que se complete el análisis de los datos adjuntos seguros de ATP.
  
Como cada dato adjunto está desactivada, automáticamente se a adjuntar al mensaje de correo electrónico original. Si un archivo adjunto se determina como malintencionado, se envía a cuarentena, donde una persona en el equipo de seguridad de su organización (por ejemplo, un administrador global de Office 365 o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>¿Qué sucede cuando alguien envía un correo electrónico que contiene datos adjuntos?

Suponga que una organización utiliza la entrega dinámica para sus [datos adjuntos seguros de ATP directiva](set-up-atp-safe-attachments-policies.md), y que alguien recibe un correo electrónico que contiene datos adjuntos. Ahora suponga que esa persona está a punto de reenviar el mensaje de correo electrónico a otra persona. ¿Qué sucede? Depende de si los destinatarios adicionales se incluyen en las directivas de los datos adjuntos seguros de ATP.
  
- Si un destinatario está cubierto por una directiva de datos adjuntos seguros de ATP mediante la opción de entrega dinámica, el destinatario ve el marcador de posición, con la posibilidad de obtener una vista previa de archivos compatibles.
    
- Si un destinatario no está cubierto por una directiva de datos adjuntos seguros de ATP, a continuación, el correo electrónico y datos adjuntos se realizarán a través de, sin datos adjuntos seguros de ATP examen o marcadores de posición de datos adjuntos.
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>¿Qué se necesita para que funcione la entrega dinámica?

- Su organización debe tener [La protección de amenaza avanzada de Office 365](office-365-atp.md)
    
- Se deben definir directivas para datos adjuntos seguros de ATP mediante la opción de entrega dinámico (vea [configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))
    
- Correo electrónico de su organización debe estar hospedado en Office 365
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>¿Hay escenarios para la que no está disponible la entrega dinámica?

Hay determinados escenarios en los que no se admite la entrega dinámica. Estos son los siguientes:
  
- Mensajes de correo electrónico que se encuentran en las carpetas públicas
    
- Mensajes de correo electrónico que se enrutan fuera de y, a continuación, realizar una copia en el buzón del usuario mediante las reglas personalizadas
    
- Mensajes que se mueven (automático o manual) fuera del buzón hospedado y en otras ubicaciones, incluidas carpetas archivadas
    
- Mensajes que se eliminan
    
- Carpeta de búsqueda de buzón de correo de un usuario que se encuentra en un estado de error
    
- Entornos en los que un administrador de Exchange Online ha habilitado Exclaimer. (Vea [los mensajes con datos adjuntos no se entregan cuando se usan entrega dinámica ATP y Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))

- Mensajes cifrados con extensiones seguras multipropósito de correo Internet ([S/MIME](s-mime-for-message-signing-and-encryption.md))
    
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)
  
[Configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
  
[Vínculos de ATP seguros en Office 365](atp-safe-links.md)

[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  


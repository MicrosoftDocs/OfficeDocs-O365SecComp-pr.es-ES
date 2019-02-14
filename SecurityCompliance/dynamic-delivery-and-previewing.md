---
title: Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Al configurar las directivas de los datos adjuntos seguros ATP, elija entrega dinámica para evitar retrasos de mensaje y permiten a los usuarios obtener una vista previa de datos adjuntos que se están analizando.
ms.openlocfilehash: ae027986cf5114bd024c679a59975d1e4be52d32
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995151"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Entrega dinámica y obtener una vista previa con Office 365 ATP los datos adjuntos seguros

**Resumen**: entrega dinámico es una opción que se puede seleccionar los datos adjuntos [seguros](atp-safe-attachments.md)de ATP. Lea este artículo para obtener más información acerca de la entrega dinámica y las capacidades de vista previa de datos adjuntos en [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).

Cuando [se configuran las directivas de los datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) para su organización, hay varias opciones sobre cómo se controlan los datos adjuntos de correo electrónico. Éstas incluyen **bloque**, **Reemplazar**y **Entrega dinámica**. Dependiendo de cómo se configuran las directivas de los datos adjuntos seguros de ATP, los destinatarios de correo electrónico podrían experimentar un retraso en la entrega de correo electrónico secundario mientras se examinan los datos adjuntos. Para evitar retrasos de mensaje, elija **Entrega dinámica**.
  
## <a name="how-dynamic-delivery-works"></a>Cómo funciona la entrega dinámica
  
Entrega dinámica elimina los retrasos de correo electrónico mediante el envío el cuerpo de un mensaje de correo electrónico a través de al destinatario con un marcador de posición para cada dato adjunto de correo electrónico. El marcador de posición permanece hasta que una copia de los datos adjuntos se examinan y determinada como segura por [Los datos adjuntos seguros de ATP](atp-safe-attachments.md). 

- Como cada dato adjunto está desactivada, está disponible para abrir o descargar. 

- Si un archivo adjunto se determina como malintencionado, se envía a cuarentena, donde una persona en el equipo de seguridad de su organización (por ejemplo, un administrador global de Office 365 o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).

La mayoría de los archivos PDF y Office documentos pueden ser una vista previa en modo seguro mientras ATP análisis está en curso. Si un archivo adjunto no es compatible con el controlador de vista previa dinámica entrega, los destinatarios de correo electrónico ven un marcador de posición de datos adjuntos hasta que se complete el análisis de los datos adjuntos seguros de ATP.

> [!TIP]
> Si está usando un dispositivo móvil y documentos PDF no se procesan en el controlador de vista previa dinámica entrega en primer lugar, intente iniciar sesión en Office 365 mediante el explorador móvil.

Con la entrega dinámica, personas puedan leer y responder a sus mensajes de correo electrónico inmediatamente, mientras se están analizando sus datos adjuntos. 

Datos adjuntos seguros de ATP que lleve a cabo el examen se coloque en la misma región donde residen los datos de Office 365. Para obtener más información acerca de la zona geográfica de centro de datos, vea [¿dónde están los datos que se encuentra?](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>¿Qué sucede cuando alguien envía un correo electrónico que contiene datos adjuntos?

Suponga que una organización utiliza la entrega dinámica para sus [datos adjuntos seguros de ATP directiva](set-up-atp-safe-attachments-policies.md), y que alguien recibe un correo electrónico que contiene datos adjuntos. Ahora suponga que esa persona reenvía el mensaje de correo electrónico a otra persona. ¿Qué sucede? Depende de si los destinatarios adicionales se incluyen en las directivas de los datos adjuntos seguros de ATP.
  
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
    
- Mensajes de correo electrónico que se mueven (automático o manual) fuera del buzón hospedado y en otras ubicaciones, incluidas carpetas archivadas
    
- Mensajes de correo electrónico que se eliminan
    
- Carpeta de búsqueda de buzón de correo de un usuario que se encuentra en un estado de error
    
- Entornos en los que un administrador de Exchange Online ha habilitado Exclaimer. Para resolver este problema, vea [los mensajes con datos adjuntos no se entregan cuando se usan entrega dinámica ATP y Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- Mensajes cifrados con [Extensiones seguras/multipropósito de correo Internet (S/MIME)](s-mime-for-message-signing-and-encryption.md))


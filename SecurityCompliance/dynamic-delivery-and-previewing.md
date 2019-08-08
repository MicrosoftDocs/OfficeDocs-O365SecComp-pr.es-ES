---
title: Entrega dinámica y vista previa con datos adjuntos seguros de Office 365 ATP
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Cuando configure las directivas de datos adjuntos seguros de ATP, elija la entrega dinámica para evitar retrasos en los mensajes y permitir a los usuarios obtener una vista previa de los datos adjuntos que se están analizando.
ms.openlocfilehash: 203f5082701f1f3eeea36b385918328cb85deb81
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230654"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Entrega dinámica y vista previa con datos adjuntos seguros de Office 365 ATP

## <a name="overview"></a>Información general

La entrega dinámica es una opción que se puede seleccionar para los [datos adjuntos seguros de ATP](atp-safe-attachments.md). Lea este artículo para obtener información sobre las capacidades de entrega y vista previa de datos adjuntos de ATP en los [datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).

Cuando [se configuran directivas de datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md) para la organización, hay varias opciones sobre cómo se administran los datos adjuntos de correo electrónico. Entre estos se incluyen **bloquear**, **reemplazar**y **entrega dinámica**. En función de cómo estén configuradas las directivas de datos adjuntos seguros de ATP, los destinatarios de correo electrónico podrían experimentar un retraso menor en la entrega de correo electrónico mientras se examinan los datos adjuntos. Para evitar retrasos en los mensajes, elija **entrega dinámica**.
  
## <a name="how-dynamic-delivery-works"></a>Cómo funciona la entrega dinámica
  
La entrega dinámica elimina los retrasos del correo electrónico enviando el cuerpo de un mensaje de correo electrónico al destinatario con un marcador de posición para cada adjunto de correo electrónico. El marcador de posición permanece hasta que una copia de los datos adjuntos se analiza y se determina que está protegido por [datos adjuntos seguros ATP](atp-safe-attachments.md). 

- A medida que se borren los datos adjuntos, estará disponible para abrirlos o descargarlos. 

- Si los datos adjuntos se determinan como malintencionados, se envían a cuarentena, donde alguien del equipo de seguridad de su organización (como un administrador global de Office 365 o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).

La mayoría de los PDF y los documentos de Office se pueden mostrar como una vista previa en modo seguro mientras se está realizando el análisis de ATP. Si los datos adjuntos no son compatibles con el previsor de entrega dinámica, los destinatarios de correo electrónico ven un marcador de posición de datos adjuntos hasta que se complete el análisis de datos adjuntos seguros ATP.

> [!TIP]
> Si está usando un dispositivo móvil y los PDF no se representan en primer lugar en el previsualizador de entrega dinámico, intente iniciar sesión en Office 365 con el explorador móvil.

Con la entrega dinámica, los usuarios pueden leer y responder a sus mensajes de correo electrónico inmediatamente, mientras se analizan los datos adjuntos. 

El análisis de datos adjuntos seguros de ATP tiene lugar en la misma región en la que residen los datos de Office 365. Para obtener más información acerca de la geografía del centro de datos, consulte [¿dónde están los datos ubicados?](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>¿Qué sucede cuando alguien reenvía un correo electrónico que contiene datos adjuntos?

Suponga que una organización está usando la entrega dinámica para la [Directiva de datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md)y alguien recibe un correo electrónico que contiene datos adjuntos. Ahora, supongamos que la persona reenvía el mensaje de correo electrónico a otro usuario. ¿Qué sucede? Depende de si los destinatarios adicionales se incluyen en las directivas de datos adjuntos seguros de ATP.
  
- Si un destinatario está cubierto por una directiva de datos adjuntos seguros de ATP mediante la opción de entrega dinámica, el destinatario verá el marcador de posición, con la capacidad de obtener una vista previa de los archivos compatibles.
    
- Si un destinatario no está cubierto por una directiva de datos adjuntos seguros de ATP, el correo electrónico y los datos adjuntos se recorrerán, sin ningún marcador seguro de datos adjuntos de ATP o marcadores de posición de datos adjuntos.
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>¿Qué se necesita para que funcione la entrega dinámica?

- Su organización debe tener la [protección contra amenazas avanzada de Office 365](office-365-atp.md)
    
- Las directivas deben definirse para los datos adjuntos seguros de ATP que usen la opción de entrega dinámica (consulte [configurar las directivas de datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))
    
- El correo electrónico de la organización debe estar hospedado en Office 365. Si bien [se puede usar la protección contra amenazas avanzada de Office 365 con cualquier agente de transferencia de correo SMTP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (como Exchange Server), la opción de entrega dinámica para datos adjuntos seguros de ATP requiere que el correo electrónico de la organización se hospede en Office 365. Si el correo electrónico no está hospedado en Office 365, elija otra [opción de directiva de datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), como **bloquear**.
    
## <a name="additional-considerations"></a>Consideraciones adicionales

Hay algunos escenarios en los que no se admite la entrega dinámica. Entre ellas se incluyen las siguientes:
  
- Mensajes de correo electrónico que están en carpetas públicas
    
- Mensajes de correo electrónico que se redirigen del y después al buzón del usuario mediante reglas personalizadas
    
- Mensajes de correo electrónico que se mueven (de forma automática o manual) del buzón de correo hospedado y a otras ubicaciones, incluidas las carpetas de archivo
    
- Mensajes de correo electrónico que se eliminan
    
- Carpeta de búsqueda del buzón de un usuario que se encuentra en estado de error
    
- Entornos en los que un administrador de Exchange Online ha habilitado exclaimer. Para resolver esto, vea [no se entregan los mensajes con datos adjuntos cuando se usan la entrega y](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery) exclaims dinámicas de ATP

- Mensajes cifrados con [extensiones seguras multipropósito al correo de Internet (S/MIME)](s-mime-for-message-signing-and-encryption.md))

- En los casos en los que no se admite la entrega dinámica, los datos adjuntos seguros de ATP no analizarán los mensajes de correo electrónico. Sin embargo, se comprobará la entrega de mensajes de correo electrónico con datos adjuntos que contengan direcciones URL, en función de la configuración de las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) . En estos casos, se comprueban las direcciones URL de los mensajes de correo electrónico y los archivos de Office.

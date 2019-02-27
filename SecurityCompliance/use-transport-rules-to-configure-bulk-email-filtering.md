---
title: Usar reglas de flujo de correo para configurar el filtrado masivo de correo electrónico en Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo en Exchange Online Protection para el filtrado masivo de correo electrónico.
ms.openlocfilehash: b7144f16df3e7b9f90a24f1ac224ccb20287d918
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275690"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Usar reglas de flujo de correo para configurar el filtrado masivo de correo electrónico en Exchange Online Protection

Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) y [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) para obtener información sobre cómo configurar las directivas de filtro de contenido. 
  
Si desea más opciones para filtrar los mensajes masivos, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para buscar patrones de texto o frases que se encuentran con frecuencia en los correos masivos. Cualquier mensaje que contenga estas características se marcará como correo no deseado. El uso de estas reglas puede ayudar a reducir la cantidad de correo electrónico masivo no deseado que recibe la organización.

> [!IMPORTANT]
> Antes de crear las reglas de flujo de correo documentadas en este tema, recomendamos que primero lea [cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo](what-s-the-difference-between-junk-email-and-bulk-email.md) y [los valores de nivel de queja masiva](bulk-complaint-level-values.md).<br>En los siguientes procedimientos se marca un mensaje como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solamente a destinatarios específicos en la organización. De este modo, la configuración agresiva de filtrado de correo masivo se puede aplicar a unos cuantos usuarios específicos, mientras que el resto de los usuarios (que en su mayor parte reciben el correo masivo por el que se suscribieron) no se verán afectados. 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Crear una regla de flujo de correo para filtrar mensajes de correo electrónico masivo en función de patrones de texto

1. En el Centro de administración de Exchange (EAC), vaya a **Flujo de correo** \> **Reglas**.
    
2. Haga **** ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono Agregar y, a continuación, seleccione **crear una nueva regla**.
    
3. Especifique un nombre para la regla.
    
4. Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo coincide con estos patrones de texto**.
    
5. En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes expresiones regulares que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine: 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   La lista anterior no es un conjunto exhaustivo de expresiones regulares que se encuentran en los correos electrónicos masivos; se pueden agregar o quitar más según sea necesario. Sin embargo, es un buen punto de partida.<br>La búsqueda de palabras o patrones de texto en el asunto o en otros campos de encabezado del mensaje se produce *después* de que el mensaje se haya descodificado del método de codificación de transferencia de contenido MIME que se usó para transmitir el mensaje binario entre los servidores SMTP en texto ASCII. No puede usar las condiciones o excepciones para buscar los valores codificados (normalmente, Base64) codificados del asunto u otros campos de encabezado de los mensajes. 
    
6. En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.
    
7. En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.
    
   Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
    
   Si la acción configurada es poner en cuarentena el mensaje en lugar de enviarlo a la carpeta de correo electrónico no deseado de los destinatarios, el mensaje se enviará a la cuarentena de administrador como una coincidencia de regla de flujo de correo y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante el usuario final. notificaciones de correo no deseado. 
  
   Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).
    
8. Guarde la regla.
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Crear una regla de flujo de correo para filtrar mensajes de correo masivo según frases

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Haga **** ![clic en agregar](media/ITPro-EAC-AddIcon.gif) icono Agregar y, a continuación, seleccione **crear una nueva regla**.
    
3. Especifique un nombre para la regla.
    
4. Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo incluye cualquiera de estas palabras**.
    
5. En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes frases que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine: 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   Esta lista no es un conjunto exhaustivo de frases que se encuentran en los correos electrónicos en masa; se pueden agregar o quitar más según sea necesario. Sin embargo, es un buen punto de partida.
    
6. En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.
    
7. En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.
    
   Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
    
   Si la acción configurada es poner en cuarentena el mensaje en lugar de enviarlo a la carpeta de correo electrónico no deseado de los destinatarios, el mensaje se enviará a la cuarentena de administrador como una coincidencia de regla de flujo de correo y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante el usuario final. notificaciones de correo no deseado. 
  
   Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).

8. Guarde la regla.

## <a name="for-more-information"></a>Más información

[¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md)

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)

[Opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md)

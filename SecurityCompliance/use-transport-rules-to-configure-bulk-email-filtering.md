---
title: Use reglas de flujo de correo para configurar el correo electrónico masivo filtrado en Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: Los administradores pueden aprender a usar las reglas de flujo de correo en Exchange Online Protection para el filtrado de correo electrónico de forma masiva.
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382811"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Use reglas de flujo de correo para configurar el correo electrónico masivo filtrado en Exchange Online Protection

Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) y [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) para obtener información sobre cómo configurar las directivas de filtro de contenido. 
  
Si desea más opciones para filtrar mensajes de forma masiva, puede crear reglas de flujo de correo (también conocida como reglas de transporte) para buscar patrones de texto o frases con frecuencia que se encuentran en mensajes de correo electrónico masivo. Los mensajes que contienen estas características se marcarán como correo no deseado. Estas reglas pueden ayudar a reducir la cantidad de correo electrónico masivo no deseados que recibe de la organización.
  
**Notas**:

- Antes de crear el correo de las reglas de flujo documenta en este tema, se recomienda que lea primero [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) y [los valores de nivel de Reclamación de forma masiva](bulk-complaint-level-values.md). 
  
- En los siguientes procedimientos se marca un mensaje como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solamente a destinatarios específicos en la organización. De este modo, la configuración agresiva de filtrado de correo masivo se puede aplicar a unos cuantos usuarios específicos, mientras que el resto de los usuarios (que en su mayor parte reciben el correo masivo por el que se suscribieron) no se verán afectados. 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Crear regla de flujo de correo para filtrar mensajes de correo electrónico masivo según patrones de texto

1. En el Centro de administración de Exchange (EAC), vaya a **Flujo de correo** \> **Reglas**.
    
2. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y seleccione **Crea una nueva regla**.
    
3. Especifique un nombre para la regla.
    
4. Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo coincide con estos patrones de texto**.
    
5. En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes expresiones regulares que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine: 
    
   - Si no puede ver el contenido de este correo\,
    
   - \\>(seguro )?cancele su suscripción( aquí)?\\</a\\>
    
   - Si no desea recibir más comunicaciones como esta\,
    
   - \\<img height\="?1"? width\="?1"? src\=.?http\://
    
   - Para dejar de recibir estos\s+emails\:http\://
    
   - Para cancelar su suscripción de \w+ (e\-?carta|e?-?mail|boletín)
    
   - ya no (desea )?(que )?(se le envíe|recibir) \w+ email
    
   - Si no puede ver el contenido de este correo\, haga clic aquí
    
   - Para asegurarse de que recibe (sus ofertas diarias|nuestros e-?mails)\, agregue
    
   - Si ya no desea seguir recibiendo estos mensajes de correo electrónico
    
   - para cambiar su (preferencias de suscripción|preferencias o cancelar su suscripción)
    
   - haga clic (aquí para|la) cancelar su suscripción
    
   **Notas**:

   - La lista anterior no es un conjunto exhaustivo de expresiones regulares que se encuentran en mensajes de correo electrónico masivo; más información puede que se agreguen o eliminen según sea necesario. Sin embargo, es un buen punto de partida.
    
   - La búsqueda de palabras o patrones de texto en el asunto o en otros campos de encabezado en el mensaje se produce *después de que* el mensaje ha descodificada desde la transferencia de contenido MIME codificación (método) que se usó para transmitir el mensaje binario entre servidores SMTP de texto ASCII. No se puede usar las condiciones o excepciones para buscar el sin procesar (normalmente, Base64) codificado valores del asunto o en otros campos de encabezado de los mensajes. 
    
6. En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.
    
7. En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.
    
   Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
    
   > [!NOTE]
   > Si la acción configurada es el mensaje en cuarentena en lugar de enviar a carpeta de correo electrónico no deseado de los destinatarios, el mensaje se enviará a la cuarentena de administrador como una coincidencia de regla de flujo de correo y, no estará disponible en la cuarentena de spam del usuario final o a través del usuario final las notificaciones de correo no deseado. 
  
   Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).
    
8. Guarde la regla.
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Crear una regla de flujo de correo para filtrar mensajes de correo electrónico masivo según frases

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y seleccione **Crea una nueva regla**.
    
3. Especifique un nombre para la regla.
    
4. Haga clic en **Más opciones**. En **Aplicar esta regla si**, seleccione **El asunto o el cuerpo** \> **el asunto o el cuerpo incluye cualquiera de estas palabras**.
    
5. En el cuadro de diálogo **especificar palabras o frases**, agregue las siguientes frases que se encuentran generalmente en los correos masivos, de una en una, y haga clic en **aceptar** cuando termine: 
    
   - para cambiar sus preferencias o cancelar su suscripción
    
   - Modifique sus preferencias de correo electrónico o cancele su suscripción
    
   - Este es un correo electrónico promocional
    
   - Está recibiendo este correo porque solicitó una suscripción
    
   - haga clic aquí para cancelar su suscripción
    
   - Recibió este correo electrónico porque está suscrito
    
   - Si ya no desea seguir recibiendo nuestro boletín electrónico
    
   - para cancelar sus suscripción de este boletín
    
   - Si tiene problemas para ver este correo electrónico
    
   - Este es un anuncio
    
   - desea cancelar su suscripción o cambiar su
    
   - vea este correo como una página web
    
   - Está recibiendo este correo electrónico porque está suscrito
    
   **Nota**: una vez más, esta lista no es un conjunto exhaustivo de frases que se encuentran en mensajes de correo electrónico masivo; más información puede que se agreguen o eliminen según sea necesario. Sin embargo, es un buen punto de partida.
    
6. En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.
    
7. En el cuadro de texto **Especificar SCL**, establezca el SCL en **5**, **6** o **9** y haga clic en **Aceptar**.
    
   Si se establece el SCL en 5 o 6 se lleva a cabo la acción **Correo no deseado**, mientras que si se establece el SCL en 9 se lleva a cabo la acción **Correo no deseado de confidencia alta**, tal y como se configuró en la directiva de filtrado de contenido. El servicio llevará a cabo la acción establecida en la directiva de filtrado de contenido. La acción predeterminada es entregar el mensaje en la carpeta de correo electrónico no deseado de los destinatarios, pero se pueden configurar diferentes acciones como se describe en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
    
   > [!NOTE]
   > Si la acción configurada es el mensaje en cuarentena en lugar de enviar a carpeta de correo electrónico no deseado de los destinatarios, el mensaje se enviará a la cuarentena de administrador como una coincidencia de regla de flujo de correo y, no estará disponible en la cuarentena de spam del usuario final o a través del usuario final las notificaciones de correo no deseado. 
  
   Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).

8. Guarde la regla.

## <a name="for-more-information"></a>Más información

[¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md)

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)

[Opciones de filtrado de spam avanzado](advanced-spam-filtering-asf-options.md)

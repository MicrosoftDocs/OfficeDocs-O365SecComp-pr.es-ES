---
title: Uso de reglas de transporte para configurar el filtrado de correo electrónico masivo
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte Configurar las directivas de filtro de correo no deseado y Set-HostedContentFilterPolicy para obtener información sobre cómo configurar las directivas de filtro de contenido.
ms.openlocfilehash: f72fa5cc50ab6aa5447e3af9fabc365457c82973
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027687"
---
# <a name="use-transport-rules-to-configure-bulk-email-filtering"></a>Uso de reglas de transporte para configurar el filtrado de correo electrónico masivo

Puede establecer filtros de contenido en toda la empresa para el correo electrónico masivo y correo no deseado usando las directivas de filtro de contenido de correo electrónico no deseado predeterminadas. Consulte [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) y [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) para obtener información sobre cómo configurar las directivas de filtro de contenido. 
  
Si quiere más opciones para filtrar los mensajes masivos, puede crear reglas de transporte de Exchange para buscar patrones de texto o frases que se encuentran con frecuencia en los correos masivos. Todos los mensajes que contienen estas características se marcarán como correo no deseado. El uso de estas reglas puede ayudar a reducir la cantidad de correo electrónico masivo no deseado que una organización recibe.
  
> [!NOTE]
> Antes de crear las reglas de transporte documentadas en este tema, le recomendamos que lea primero [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) y [Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md). 
  
> [!NOTE]
> En los siguientes procedimientos se marca un mensaje como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solamente a destinatarios específicos en la organización. De este modo, la configuración agresiva de filtrado de correo masivo se puede aplicar a unos cuantos usuarios específicos, mientras que el resto de los usuarios (que en su mayor parte reciben el correo masivo por el que se suscribieron) no se verán afectados. 
  
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Crear una regla de transporte de Exchange para filtrar mensajes de correo masivo según patrones de texto

1. En el Centro de administración de Exchange (EAC), vaya a **Flujo de correo** \> **Reglas**.
    
2. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.png) y seleccione **Crea una nueva regla**.
    
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
    > Si la acción configurada es poner en cuarentena el mensaje en vez de enviarlo a la carpeta Correo no deseado de los destinatarios, el mensaje se enviará a la cuarentena del administrador como coincidencia de regla de transporte y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante notificaciones de correo no deseado del usuario final. 
  
    Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).
    
8. Guarde la regla.
    
### <a name="create-an-exchange-transport-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Crear una regla de transporte de Exchange para filtrar mensajes de correo masivo según frases

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.
    
2. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.png) y seleccione **Crea una nueva regla**.
    
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
    > Si la acción configurada es poner en cuarentena el mensaje en vez de enviarlo a la carpeta Correo no deseado de los destinatarios, el mensaje se enviará a la cuarentena del administrador como coincidencia de regla de transporte y no estará disponible en la cuarentena de correo no deseado del usuario final o mediante notificaciones de correo no deseado del usuario final. 
  
    Para obtener más información acerca de los valores de SCL en el servicio, consulte [Niveles de confianza de correo no deseado](spam-confidence-levels.md).
    
8. Guarde la regla.
    
## <a name="for-more-information"></a>Más información

[¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
[Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md)
  
[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
[Opciones de filtrado de spam avanzado](advanced-spam-filtering-asf-options.md)
  


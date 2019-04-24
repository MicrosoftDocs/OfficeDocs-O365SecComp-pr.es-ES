---
title: Configurar las directivas de filtro de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: La configuración básica del filtro de correo no deseado incluye seleccionar la acción que se va a realizar en los mensajes identificados como correo no deseado y elegir si se deben filtrar los mensajes escritos en idiomas específicos o enviados desde países o regiones específicos.
ms.openlocfilehash: 5773256e18e1910405bcc04a1869f631734447a4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258818"
---
# <a name="configure-your-spam-filter-policies"></a>Configurar las directivas de filtro de correo no deseado
  
La configuración básica del filtro de correo no deseado incluye seleccionar la acción que se debe realizar en los mensajes identificados como correo no deseado. La configuración de la Directiva de filtro de correo no deseado solo se aplica a los mensajes entrantes. Puede editar la Directiva de filtro de correo no deseado predeterminada para configurar las opciones del filtro de correo no deseado en toda la compañía y crear directivas personalizadas de filtro de correo no deseado y, a continuación, aplicarlas a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre la predeterminada. Puede cambiar el orden en el que se ejecutan las directivas personalizadas cambiando la prioridad de cada directiva personalizada; sin embargo, solo se aplicará la Directiva de prioridad más alta si hay varias directivas que cumplan los criterios establecidos.
  
> [!IMPORTANT]
> Para clientes independientes de Exchange Online Protection (EOP): de forma predeterminada, los filtros de correo no deseado de EOP envían mensajes detectados como correo no deseado a la carpeta de correo no deseado de cada destinatario. Sin embargo, para asegurarse de que la acción **mover mensaje a la carpeta correo no deseado** funciona con los buzones locales, debe configurar las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores locales para detectar los encabezados de correo no deseado que agrega EOP. Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
## <a name="what-you-must-know-before-you-begin"></a>Qué debe saber antes de empezar

Tiempo estimado para finalizar: 30 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada contra correo electrónico no deseado en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
  
## <a name="use-the-security--compliance-center-scc-to-configure-spam-filter-policies"></a>Usar el centro de seguridad & cumplimiento (SCC) para configurar directivas de filtro de correo no deseado

1. En el centro de seguridad & cumplimiento (SCC), vaya a **Threat Management** \> **Policy** \> **anti-spam**.
    
2. Realice una de las siguientes acciones en la página **configuración contra correo no deseado** : 
    
      - Revise la directiva predeterminada de toda la compañía en la configuración estándar.
    
      - Haga clic en la pestaña **personalizado** , cambie el selector de **Configuración personalizada** a **activado**y haga clic ![en el](media/ITPro-EAC-AddIcon.gif) botón Agregar icono **crear una directiva** para crear una nueva directiva personalizada de filtro de correo no deseado que se puede aplicar a los usuarios, grupos y Dominios de la organización. También puede editar directivas personalizadas existentes haciendo doble clic en ellas. 
    
3. En el caso de las directivas personalizadas, especifique un nombre para la Directiva. Opcionalmente, también puede especificar una descripción más detallada. El nombre de la directiva predeterminada no se puede cambiar.<br/><br/>Nota: al crear una directiva, todas las opciones de configuración aparecen en una sola pantalla. Por el contrario, cuando edita una directiva, debe desplazarse por varias pantallas. La configuración es la misma en cualquier caso, pero el resto de este procedimiento describe cómo tener acceso a estas opciones cuando edita una directiva. 
  
4. En la página **acciones de correo electrónico masivo y no deseado**, en **Correo no deseado** y **Correo no deseado de confianza alta**, seleccione la acción que se realizará en el correo electrónico no deseado y masivo entrante. De forma predeterminada, **Mover mensajes a la carpeta Correo no deseado** está activada. Los demás valores posibles son: 
    
      - **Eliminar mensaje:** Elimina el mensaje completo, incluidos todos los datos adjuntos. 
        
      - **Mensaje en cuarentena:** Envía el mensaje a la cuarentena en lugar de a los destinatarios previstos. Si selecciona esta opción, en el cuadro de entrada **Mantener el correo no deseado durante (días)**, especifique la cantidad de días durante los cuales se mantendrá el mensaje de correo no deseado en cuarentena. (Automáticamente se borrará después de que transcurra ese tiempo. El valor predeterminado es 15 días, que es el valor máximo. El valor mínimo es 1 día).<br/><br/>Sugerencia: para obtener información sobre cómo los administradores pueden administrar los mensajes de correo electrónico que residen en la cuarentena en el EAC, consulte [Quarantine](quarantine.md) and [Find and Release Quarantined messages as an Administrator](find-and-release-quarantined-messages-as-an-administrator.md). > para obtener información sobre cómo configurar los mensajes de notificación de correo no deseado para que se envíen a los usuarios, consulte Configurar notificaciones de correo no deseado para el [usuario final en EOP](configure-end-user-spam-notifications-in-eop.md) o [configurar notificaciones de correo no deseado para el usuario final en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
      - **Mover el mensaje a la carpeta de correo no deseado:** Envía el mensaje a la carpeta de correo no deseado de los destinatarios especificados. Es la acción predeterminada para ambos los niveles de umbrales de confianza. <br/><br/>**Importante**: para los clientes de Exchange Online Protection (EOP): para que esta acción funcione con buzones locales, debe configurar dos reglas de flujo de correo de Exchange en los servidores locales para detectar los encabezados de correo no deseado agregados por EOP. Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
  
      - **Agregar encabezado X:** Envía el mensaje a los destinatarios especificados, pero agrega texto de encabezado X al encabezado del mensaje para identificar el mensaje como correo no deseado. Si se usa este texto como un identificador, se pueden crear reglas de la bandeja de entrada o usar un dispositivo indirecto para actuar en el mensaje. El texto predeterminado del encabezado X es **Este mensaje parece correo no deseado**.<br/>Puede personalizar el texto del encabezado X mediante el cuadro de entrada **Agregar este texto de encabezado x** . Si personaliza el texto del encabezado X, tenga en cuenta las siguientes condiciones: 
    
      - Si especifica solo el encabezado en el \< *encabezado*\>de formato, donde no hay espacios en el \< *encabezado*\>, se anexarán dos puntos al texto personalizado, seguido del texto predeterminado.       Por ejemplo, si especifica "This-is-My-Custom-header", el texto del encabezado X aparecerá como "This-is-My-Custom-header: este mensaje parece ser correo no deseado". 
        
      - Si incluye espacios en el texto del encabezado personalizado, o si agrega los dos puntos (por ejemplo, "X éste es mi encabezado personalizado" o "X-This-is-My-Custom-header:"), el texto del encabezado X se revierte al valor predeterminado como "X-This-is-spam: este mensaje parece correo no deseado".
    
      - No puede especificar el texto del encabezado con el formato \< *header*  \>:\<  *value*  \>. Si hace esto, se omitirán los valores antes y después de los dos puntos y se mostrará el texto del encabezado X predeterminado en su lugar: "X-This-is-spam: este mensaje parece ser correo no deseado". 
      
      - Tenga en cuenta que los mensajes con este encabezado X se podrían seguir moviendo a la carpeta de correo no deseado de buzón debido a la configuración de buzón no deseado. Para cambiar esto, deshabilite esta característica con set-MailboxJunkEmailConfiguration.
        
      - **Anteponer línea de asunto con el texto:** Envía el mensaje a los destinatarios previstos pero antepone a la línea de asunto el texto que especifique en la **línea de asunto del prefijo con este** cuadro de entrada de texto. Si se usa este texto como un identificador, se pueden crear reglas para filtrar o enrutar los mensajes según sea necesario. 
        
      - **Redirigir el mensaje a la dirección de correo electrónico:** Envía el mensaje a una dirección de correo electrónico designada en lugar de enviarla a los destinatarios previstos. Especifique la dirección de "redirección" en el campo de entrada **Redirigir a esta dirección de correo**. <br/><br/>Nota: para obtener más información acerca de los niveles de confianza de correo no deseado, vea [spam Confidence Levels](spam-confidence-levels.md). 
  
5. En **Correo electrónico masivo**, puede seleccionar un umbral para tratar al correo masivo como correo no deseado. Este umbral se basa en el nivel de queja de correo masivo del mensaje. Puede elegir un valor de umbral de 1 a 9, donde 1 indica la mayor parte del correo electrónico masivo como correo no deseado y 9 permite la entrega de los correos electrónicos más masivos. A continuación, el servicio realiza la acción configurada, por ejemplo, enviar el mensaje a la carpeta Correo electrónico no deseado del destinatario. Consulte [los valores de nivel de queja masiva](bulk-complaint-level-values.md) y [cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo](what-s-the-difference-between-junk-email-and-bulk-email.md) para obtener más información. 
    
6. En la página **Listas de bloqueados**, puede especificar entradas, como remitentes o dominios, que siempre se marcarán como correo no deseado. El servicio aplicará la acción de correo no deseado de alta confianza configurada en el correo electrónico que coincida con estas entradas. 
    
      - Agregue remitentes no deseados a la lista de bloqueados del remitente. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**. 
        
      - Agregue dominios no deseados a la lista de bloqueados del dominio. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**.<br/><br/>**PRECAUCIÓN: Si bloquea dominios de primer nivel, es probable que el correo electrónico que desea se marque como correo no deseado.** 
  
7. En la página **Listas de permitidos**, puede especificar entradas, como remitentes o dominios, que siempre se entregarán en la Bandeja de entrada. El filtro contra correo no deseado no procesa el correo electrónico de estas entradas. 
    
      - Agregue remitentes de confianza a la lista de permitidos del remitente. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Listas de permitidos**. 
        
      - Agregue dominios de confianza a la lista de permitidos del dominio. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Listas de permitidos**.<br/><br/>**PRECAUCIÓN: Si permite dominios de primer nivel, es probable que el correo electrónico que no desea se entregue a la bandeja de entrada.** 
  
8. En la página de **correo no deseado internacional** , puede filtrar los mensajes de correo electrónico escritos en idiomas específicos o enviados desde países o regiones específicos. Puede configurar hasta 86 idiomas distintos y 250 regiones diferentes. El servicio aplicará la acción configurada para el correo no deseado de alta confianza. 
    
9. Active la casilla **Filtrar mensajes de correo electrónico en los idiomas siguientes** para habilitar esta función. Haga ![clic en](media/ITPro-EAC-AddIcon.gif)agregar icono y, a continuación, en el cuadro de diálogo de selección, realice sus elecciones (se admite la selección múltiple). Por ejemplo, si selecciona filtrar los mensajes escritos en árabe (AR) y el **mensaje de cuarentena** es la acción configurada para los mensajes de correo no deseado de alta confianza, todos los mensajes escritos en árabe se pondrán en cuarentena. Haga clic en **Aceptar** para volver al panel **Correo no deseado internacional**. 
    
10. Active la casilla **Filtrar mensajes de correo electrónico de los países o regiones siguientes** para habilitar esta función. Haga ![clic en](media/ITPro-EAC-AddIcon.gif)agregar icono y, a continuación, en el cuadro de diálogo de selección, realice sus elecciones (se admite la selección múltiple). Por ejemplo, si selecciona filtrar todos los mensajes enviados desde Australia (AU) y el mensaje de **cuarentena** es la acción configurada para los mensajes de alta fiabilidad, todos los mensajes que se envíen desde Australia se pondrán en cuarentena. Haga clic en **Aceptar** para volver al panel **Correo no deseado internacional**. <br/><br/>De manera predeterminada, si no se seleccionan opciones internacionales de correo no deseado, el servicio realiza un filtrado normal de correo no deseado en los mensajes enviados en todos los idiomas y desde todas las regiones. Los mensajes se analizan y las acciones configuradas se aplican si se determina que el mensaje es correo no deseado o correo no deseado de confianza alta. 
  
11. En la página **Opciones avanzadas** , puede seleccionar **Activar**, **desactivar**o **probar** para cada opción avanzada de filtrado de correo no deseado. 
    
12. **En** el Los mensajes se filtran activamente de acuerdo con la regla asociada a esa opción. Los mensajes se marcan ya sea como correo no deseado o se aumenta la puntuación del correo no deseado, según las opciones que active. 
    
13. **Desactivar** No se realiza ninguna acción en los mensajes que cumplen los criterios del filtro de correo no deseado. De manera predeterminada, todas las opciones están desactivadas. 
    
14. **Probar** No se realiza ninguna acción en los mensajes que cumplen los criterios del filtro de correo no deseado. Sin embargo, los mensajes se pueden etiquetar agregando un encabezado X antes de entregarlos al destinatario previsto. Este encabezado X le permite saber qué opción de ASF coincide. Si ha especificado **Probar** en cualquiera de las opciones avanzadas, puede configurar que se apliquen las opciones de modo de prueba siguientes si se coincide con una opción habilitada para prueba: 
    
      - **Ninguno** No realiza ninguna acción de modo de prueba en el mensaje. Ésta es la configuración predeterminada. 
        
      - **Agregar el texto del encabezado X de prueba predeterminado** Al seleccionar esta opción, se envía el mensaje a los destinatarios especificados, pero también se agrega un encabezado X especial al mensaje para identificarlo como coincidencia con una opción de filtrado de correo no deseado avanzada específica. 
        
      - **Enviar un mensaje CCO a esta dirección** Al seleccionar esta opción, se envía una copia oculta del mensaje a la dirección de correo electrónico que especifique en el cuadro de entrada. <br/><br/>Para obtener más información acerca de las opciones avanzadas de filtrado de correo no deseado, incluida la descripción de cada opción y el texto de encabezado X asociado a cada una, consulte [Opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md). 
  
15. Solo en el caso de las directivas personalizadas, haga clic en el elemento de menú **aplicar a** y, a continuación, cree una regla basada en condiciones para especificar los usuarios, los grupos y los dominios a los que se aplicará esta Directiva. Puede crear varias condiciones, si son únicas. 
    
      - Para seleccionar usuarios, seleccione **el destinatario es**. En el cuadro de diálogo siguiente, seleccione uno o más remitentes de la compañía en la lista del selector de usuarios y, a continuación, haga clic en **Agregar**. Para agregar remitentes que no estén en la lista, escriba sus direcciones de correo electrónico y, a continuación, haga clic en **Comprobar nombres**. En este cuadro, también puede usar caracteres comodín para varias direcciones de correo electrónico (por ejemplo \* @ : _nombreDominio_). Cuando termine de realizar las selecciones, haga clic en **Aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar grupos, seleccione **el destinatario es un miembro de**. A continuación, en el cuadro de diálogo siguiente, seleccione o especifique los grupos. Haga clic en **aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar dominios, seleccione **el dominio del destinatario es**. A continuación, en el cuadro de diálogo siguiente, agregue los dominios. Haga clic en **aceptar** para volver a la pantalla principal. <br/><br/>Puede crear excepciones dentro de la regla. Por ejemplo, puede filtrar los mensajes de todos los dominios excepto un dominio en particular. Haga clic en **Agregar excepción**y, a continuación, cree las condiciones de excepción de forma similar a como ha creado las otras condiciones.<br/><br/>La aplicación de una directiva de correo no deseado a un grupo solo se admite para los **grupos de seguridad habilitados para correo**. 
  
16. Haga clic en **Guardar**. En el panel de la derecha, aparece un resumen de la configuración de la directiva.

La directiva predeterminada no se puede deshabilitar ni eliminar, y las directivas personalizadas siempre tienen prioridad sobre la directiva predeterminada. En el caso de las directivas personalizadas, puede activar o desactivar las casillas de verificación de la columna **habilitada** para habilitarlas o deshabilitarlas. De forma predeterminada, todas las directivas están habilitadas. Para eliminar una directiva personalizada, seleccione la Directiva, haga clic ![en el](media/ITPro-EAC-DeleteIcon.gif) icono Eliminar icono **eliminar** y, a continuación, confirme que desea eliminar la Directiva.

> [!TIP]
>  Puede cambiar la prioridad (orden de ejecución) de las directivas personalizadas haciendo clic en ![la flecha hacia](media/ITPro-EAC-UpArrowIcon.gif) arriba y ![flecha abajo del icono](media/ITPro-EAC-DownArrowIcon.gif) de flecha abajo. La Directiva que tiene una **prioridad** de **0** se ejecutará primero, seguida de **1**, **2**y así sucesivamente. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Usar PowerShell remoto para configurar directivas de filtro de correo no deseado

También puede configurar y aplicar directivas de filtro de correo no deseado en PowerShell. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) Ver las opciones de filtro de correo no deseado. 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Editar las opciones de filtro de correo no deseado. 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Crear una nueva directiva personalizada de filtro de correo no deseado. 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Eliminar una directiva personalizada de filtro de correo no deseado. 
    
Para aplicar una directiva personalizada de filtro de correo no deseado a usuarios, grupos o dominios, use el cmdlet [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) (para crear una nueva regla de filtro que se pueda aplicar a directivas personalizadas) o el cmdlet [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) (para editar una regla de filtro existente que se pueda aplicar a directivas personalizadas). Use el cmdlet [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) o el cmdlet [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) para habilitar o deshabilitar la regla aplicada a la directiva. 
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para garantizar que el correo no deseado se detecte adecuadamente y se tomen las medidas necesarias, puede enviar un mensaje GTUBE a través del servicio. De manera similar al archivo de prueba del antivirus EICAR, GTUBE ofrece una prueba con la cual puede comprobar si el servicio detecta correo no deseado entrante. El filtro de correo no deseado siempre debe detectar un mensaje GTUBE como correo no deseado y las medidas que se toman respecto del mensaje deben coincidir con su configuración.
  
Incluya el siguiente texto GTUBE en un mensaje de correo en una única línea, sin espacios ni saltos de línea:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Ajustar la directiva de filtro de correo no deseado para evitar falsos positivos y falsos negativos

Puede habilitar las opciones avanzadas de filtrado de correo no deseado si quiere usar un filtrado de correo no deseado más agresivo. Para obtener información sobre la configuración genérica de correo no deseado que se aplica a toda la organización, consulte [Usar listas seguras y otras técnicas para evitar el marcado erróneo de mensajes como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar los problemas de falso negativo](https://go.microsoft.com/fwlink/p/?LinkId=534225). Esta información es útil si tiene control de nivel de administrador y quiere evitar falsos positivos o falsos negativos.
   
## <a name="for-more-information"></a>Más información
<a name="sectionSection6"> </a>

[Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md)
  
[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)
  
[Cuarentena](quarantine.md)
  
[Impedir que el correo electrónico falso positivo se marque como correo no deseado con una lista de IP seguras u otras técnicas](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  


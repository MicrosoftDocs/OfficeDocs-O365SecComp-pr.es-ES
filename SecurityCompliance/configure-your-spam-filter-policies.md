---
title: Configurar las directivas de filtro de correo no deseado
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
description: Configuración de filtro de spam básico incluye seleccionando la acción que se realizará en los mensajes que se identifican como correo no deseado y elegir si va a filtrar los mensajes que se escriben en idiomas específicos o enviados desde ciertos países o regiones.
ms.openlocfilehash: c425be1814f9f04329f30254763cbbb5bd8b861e
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180900"
---
# <a name="configure-your-spam-filter-policies"></a>Configurar las directivas de filtro de correo no deseado
  
Configuración de filtro de spam básico incluye seleccionando la acción que se realizará en los mensajes que se identifican como correo no deseado y elegir si va a filtrar los mensajes que se escriben en idiomas específicos o enviados desde ciertos países o regiones. Configuración de directiva de filtro de correo no deseado es sólo mensajes aplicados a la entrada. Puede editar la directiva de filtro de spam predeterminado para configurar la configuración de filtro de correo no deseado de toda la compañía y crear directivas de filtro de correo no deseado personalizadas y, a continuación, aplicarla a determinados usuarios, grupos o dominios en su organización. Directivas personalizadas siempre tienen prioridad sobre la directiva predeterminada. Puede cambiar el orden en el que se ejecutan sus directivas personalizadas mediante la modificación de la prioridad de cada directiva personalizada.
  
> [!IMPORTANT]
> Para los clientes de Exchange Online Protection (EOP) independiente: de forma predeterminada, los filtros de spam de elevación de privilegios envían los mensajes detectados como correo no deseado a la carpeta de correo no deseado de cada destinatario. Sin embargo, con el fin de asegurarse de que la acción de **mover el mensaje a la carpeta correo no deseado** funciona para los buzones de correo local, debe configurar las reglas de transporte de Exchange en los servidores locales para detectar los encabezados de spam que se agregan mediante la elevación de privilegios. Para obtener información detallada, vea [Asegúrese de que el correo no deseado se enrute a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
## <a name="what-you-must-know-before-you-begin"></a>Lo que debe saber antes de empezar

Tiempo estimado para finalizar: 30 minutos
  
Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada contra correo no deseado en el tema [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-exchange-admin-center-eac-to-configure-spam-filter-policies"></a>Usar el Centro de administración de Exchange (EAC) para configurar directivas de filtro de correo no deseado

1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de correo no deseado**.
    
2. Realice una de las siguientes acciones en la página **general**: 
    
      - Haga doble clic en la directiva predeterminada para editar esta directiva de toda la compañía.
    
      - Haga clic en el icono ![Agregar icono](media/ITPro-EAC-AddIcon.gif) **Nueva** para crear una nueva directiva personalizada de filtro de correo no deseado que se pueda aplicar a usuarios, grupos y dominios de la organización. También puede editar directivas personalizadas existentes haciendo doble clic en ellas. 
    
3. Para directivas personalizadas, especifique un nombre para esta directiva. De forma opcional, también puede especificar una descripción más detallada. No se puede cambiar el nombre de la directiva predeterminada.<br/><br/>Nota: Cuando se crea una directiva, todos los valores de configuración aparecen en una sola pantalla. Por el contrario, cuando se edita una directiva, debe desplazarse a través de varias pantallas. La configuración es la misma en ambos casos, pero el resto de este procedimiento describe cómo tener acceso a estas opciones de configuración cuando se edita una directiva. 
  
4. En la página **acciones de correo electrónico masivo y no deseado**, en **Correo no deseado** y **Correo no deseado de confianza alta**, seleccione la acción que se realizará en el correo electrónico no deseado y masivo entrante. De forma predeterminada, **Mover mensajes a la carpeta Correo no deseado** está activada. Los demás valores posibles son: 
    
      - **Eliminar mensaje** Elimina el mensaje completo, incluyendo todos los datos adjuntos. 
        
      - **Colocar el mensaje en cuarentena** Envía el mensaje a la cuarentena en lugar de a los destinatarios. Si selecciona esta opción, en el cuadro de entrada **Mantener el correo no deseado durante (días)**, especifique la cantidad de días durante los cuales se mantendrá el mensaje de correo no deseado en cuarentena. (Automáticamente se borrará después de que transcurra ese tiempo. El valor predeterminado es 15 días, que es el valor máximo. El valor mínimo es 1 día).<br/><br/>Sugerencia: Para obtener información acerca de cómo los administradores pueden administrar los mensajes de correo electrónico que residen en cuarentena en el CEF, consulte [cuarentena](quarantine.md) y [Buscar y liberar mensajes en cuarentena como administrador](find-and-release-quarantined-messages-as-an-administrator.md). > Para obtener información acerca de cómo configurar los mensajes de notificación de spam que se envíen a los usuarios, vea [Configure para el usuario final las notificaciones en EOP de correo no deseado](configure-end-user-spam-notifications-in-eop.md) o [configurar para el usuario final de correo no deseado notificaciones en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
      - **Mover mensaje a la carpeta Correo no deseado** Entrega el mensaje a la carpeta de Correo no deseado de los destinatarios especificados. Es la acción predeterminada para ambos los niveles de umbrales de confianza.<br/><br/>**Importante: Para los clientes de Exchange Online Protection (EOP): en orden para esta acción para que funcione con buzones locales, debe configurar dos reglas de transporte de Exchange en los servidores locales para detectar los encabezados de spam agregados por elevación de privilegios. Para obtener información detallada, vea [Asegúrese de que el correo no deseado se enrute a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).**
  
      - **Agregar encabezado X** Envía el mensaje a los destinatarios especificados, pero agrega texto de encabezado X en el encabezado del mensaje con el fin de identificar el mensaje como correo no deseado. Este texto se usa como identificador, puede crear reglas de bandeja de entrada, opcionalmente, o usar un dispositivo de dirección descendente para actuar en el mensaje. El texto de encabezado X predeterminado es **aparece este mensaje de correo no deseado**.<br/>Puede personalizar el texto de encabezado X mediante el cuadro de entrada **Agregar este texto de encabezado X** . Si personaliza el texto del encabezado de X, tenga en cuenta las siguientes condiciones: 
    
      - Si especifica sólo el encabezado en el formato \< *encabezado*\>, donde no hay espacios dentro de la \< *encabezado*\>, un punto y coma se anexará al texto personalizado, seguido por el texto predeterminado. Por ejemplo, si especifica "Esta-es-mi-custom-header", el texto del encabezado de X se mostrará como "Esta-es-mi-custom-header: este mensaje parece ser correo no deseado."       
        
      - Si incluye espacios en el texto de encabezado personalizado, o si agrega los dos puntos (como "X es mi encabezado personalizado" o "X-This-is-my-custom-header:"), el texto del encabezado de X se revierte a la predeterminada como "X-esta-es-correo no deseado: este mensaje parece ser correo no deseado."
    
      - No se puede especificar el texto del encabezado en el formato \< *encabezado*  \>:\<  *valor*  \>. Si en este caso, ambos valores antes y después se pasará por alto los dos puntos y el texto de encabezado X predeterminado aparece en su lugar: "X-esta-es-correo no deseado: este mensaje parece ser correo no deseado." 
        
      - **Línea de asunto Prepend con texto** Envía el mensaje a los destinatarios pero antepone la línea de asunto con el texto que especifique en el cuadro de entrada de **línea de asunto con este texto de prefijo** . Este texto se usa como un identificador, opcionalmente puede crear reglas para filtrar o enrutar los mensajes según sea necesario. 
        
      - **Redirigir el mensaje a la dirección de correo electrónico** Envía el mensaje a una dirección de correo designada en vez de a los destinatarios especificados. Especifique la dirección de "redirección" en el campo de entrada **Redirigir a esta dirección de correo**.<br/><br/>Nota: Para obtener más información acerca de los niveles de confianza de spam, consulte [Spam confidence levels](spam-confidence-levels.md). 
  
5. En **correo electrónico masivo**, puede seleccionar un umbral para tratar el correo electrónico masivo como correo no deseado. Este umbral se basa en el nivel de Reclamación masiva del mensaje. Puede elegir una configuración de umbral de 1 a 9, donde 1 indica la mayor parte del correo masivo como correo no deseado y 9 permite la mayor parte del correo masivo entregar. El servicio, a continuación, realiza la acción configurada, como enviar el mensaje a la carpeta de correo no deseado del destinatario. Vea [los valores de nivel de Reclamación de forma masiva](bulk-complaint-level-values.md) y [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) para obtener más detalles. 
    
6. En la página **Listas de bloqueados**, puede especificar entradas, como remitentes o dominios, que siempre se marcarán como correo no deseado. El servicio aplicará la acción de correo no deseado de alta confianza configurada en el correo electrónico que coincida con estas entradas. 
    
      - Agregue remitentes no deseados a la lista de bloqueados del remitente. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**. 
        
      - Agregue dominios no deseados a la lista de bloqueados del dominio. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Aceptar** para volver a la página **Listas de bloqueados**.<br/><br/>**Precaución: Si bloquear dominios de nivel superior, es probable que el correo electrónico que desea que se marcarán como correo no deseado.** 
  
7. En la página **Listas de permitidos**, puede especificar entradas, como remitentes o dominios, que siempre se entregarán en la Bandeja de entrada. El filtro contra correo no deseado no procesa el correo electrónico de estas entradas. 
    
      - Agregue remitentes de confianza a la lista de permitidos del remitente. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Listas de permitidos**. 
        
      - Agregue dominios de confianza a la lista de permitidos del dominio. Haga clic en **Agregar**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en Aceptar para volver a la página **Listas de permitidos**.<br/><br/>**Precaución: Si Permitir dominios de nivel superior, es probable que se entregará el correo electrónico que no desea que una bandeja de entrada.** 
  
8. En la página de **Spam internacional** puede filtrar los mensajes de correo electrónico que se escriben en idiomas específicos o enviados desde ciertos países o regiones. Puede configurar hasta 250 diferentes regiones e idiomas diferentes 86. El servicio aplicará la acción configurada como correo no deseado de alta confianza. 
    
9. Seleccione la casilla de verificación **filtrar los mensajes de correo electrónico escritos en los siguientes idiomas** para habilitar esta funcionalidad. Haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif)y, a continuación, en el cuadro de diálogo de selección, realice sus elecciones (se admite la selección múltiple). Por ejemplo, si selecciona para filtrar mensajes escritos en árabe (AR) y **el mensaje en cuarentena** es la acción configurada para los mensajes de spam de alta confianza, todos los mensajes escritos en árabe se pondrán en cuarentena. Haga clic en **Aceptar** para volver al panel de **Spam internacional** . 
    
10. Active la casilla de verificación **filtrar los mensajes de correo electrónico enviados desde los siguientes países o regiones** para habilitar esta funcionalidad. Haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif)y, a continuación, en el cuadro de diálogo de selección, realice sus elecciones (se admite la selección múltiple). Por ejemplo, si selecciona para filtrar todos los mensajes que se envían desde Australia (AU), y **el mensaje en cuarentena** es la acción configurada para mensajes seguros de alta confianza y, a continuación, todos los mensajes que se envía desde Australia se pondrán en cuarentena. Haga clic en **Aceptar** para volver al panel de **Spam internacional** .<br/><br/>De manera predeterminada, si no se seleccionan opciones internacionales de correo no deseado, el servicio realiza un filtrado normal de correo no deseado en los mensajes enviados en todos los idiomas y desde todas las regiones. Los mensajes se analizan y las acciones configuradas se aplican si se determina que el mensaje es correo no deseado o correo no deseado de confianza alta. 
  
11. En la página **Opciones avanzadas** , puede seleccionar **en**, **desactivado**o **prueba** para cada opción de filtro avanzadas correo no deseado. 
    
12. **En** Los mensajes se filtran activamente según la regla que está asociada con dicha opción. Los mensajes están marcados como correo no deseado o habrá sus calificaciones spam ha aumentado, dependiendo de las opciones de activar. 
    
13. **Desactivar** No se realiza ninguna acción en los mensajes que cumplen los criterios del filtro de correo no deseado. De manera predeterminada, todas las opciones están desactivadas. 
    
14. **Prueba** En los mensajes que cumplen los criterios de filtro de spam se realiza ninguna acción. Sin embargo, los mensajes se pueden etiquetar mediante la adición de un encabezado X antes de que se entregan al destinatario previsto. Este encabezado X le permite saber qué opción de ASF coincidente. Si especificó **probar** para cualquiera de las opciones avanzadas, puede configurar la siguiente configuración de modo de prueba que se aplicará cuando se busca una coincidencia para una opción de prueba habilitada: 
    
      - **Ninguno** No realiza ninguna acción de modo de prueba en el mensaje. Ésta es la configuración predeterminada. 
        
      - **Agregar el valor predeterminado de prueba texto de encabezado X** Si selecciona esta opción envía el mensaje a los destinatarios especificados, pero también agrega un encabezado X especial para el mensaje para identificar como tener coincidente un específico avanzadas correo no deseado filtrado de opción. 
        
      - **Enviar un mensaje CCO a esta dirección** Si selecciona esta opción, envía una copia oculta del mensaje a la dirección de correo electrónico que especifique en el cuadro de entrada. <br/><br/>Para obtener más información sobre el correo no deseado avanzado filtrado de opciones, incluidas las descripciones sobre cada opción y el texto del encabezado de X que está asociado con cada uno de ellos, vea [Opciones de filtrado avanzadas correo no deseado](advanced-spam-filtering-asf-options.md). 
  
15. Para directivas personalizadas sólo, haga clic en el elemento de menú **aplicar a** y, a continuación, crear una regla basada en condición para especificar los usuarios, grupos y dominios que se va a aplicar esta directiva. Puede crear varias condiciones, si son únicos. 
    
      - Para seleccionar los usuarios, seleccione **el destinatario es**. En el cuadro de diálogo posterior, seleccione uno o más remitentes de su compañía en la lista del selector de usuario y, a continuación, haga clic en **Agregar**. Para agregar los remitentes que no están en la lista, escriba sus direcciones de correo electrónico y, a continuación, haga clic en **Comprobar nombres**. En este cuadro, también puede usar caracteres comodín para varias direcciones de correo electrónico (por ejemplo: \* @  _domainname_). Cuando termine de realizar las selecciones, haga clic en **Aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar grupos, seleccione **el destinatario es un miembro de**. A continuación, en el cuadro de diálogo posterior, seleccione o especifique los grupos. Haga clic en **Aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar los dominios, seleccione **el dominio de destinatario es**. A continuación, en el cuadro de diálogo subsiguientes, agregue los dominios. Haga clic en **Aceptar** para volver a la pantalla principal.<br/><br/>Puede crear excepciones dentro de la regla. Por ejemplo, puede filtrar los mensajes de todos los dominios, excepto un determinado dominio. Haga clic en **Agregar excepción**y, a continuación, cree las condiciones de excepción similar a la forma en que ha creado las otras condiciones.<br/><br/>Aplicar una directiva de correo a un grupo se admite únicamente para los **Grupos de seguridad habilitado para correo**. 
  
16. Haga clic en **Guardar**. En el panel de la derecha, aparece un resumen de la configuración de la directiva.

> [!TIP]
>  Puede seleccionar o desactive las casillas de verificación en la columna **activado** para habilitar o deshabilitar las directivas personalizadas. De forma predeterminada, se habilitan todas las directivas. No se puede deshabilitar la directiva predeterminada. > Para eliminar una directiva personalizada, seleccione la directiva, haga clic en el ![icono de eliminación](media/ITPro-EAC-DeleteIcon.gif) icono **Eliminar** y, a continuación, confirme que desea eliminar la directiva. No se puede eliminar la directiva predeterminada. > Directivas personalizadas siempre tienen prioridad sobre la directiva predeterminada. Directivas personalizadas que se ejecutan en el orden inverso en el que los creó (de más antiguo a más reciente), pero puede cambiar la prioridad (orden de marcha) de sus directivas personalizadas haciendo clic en el ![seguridad el icono de flecha](media/ITPro-EAC-UpArrowIcon.gif) flecha arriba y ![icono de la flecha hacia abajo](media/ITPro-EAC-DownArrowIcon.gif) hacia abajo flecha. La directiva que tiene una **prioridad** de **0** se ejecutará en primer lugar, seguido de **1**, a continuación, **2**y así sucesivamente. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Usar PowerShell remoto para configurar directivas de filtro de correo no deseado

También puede configurar y aplicar directivas de filtro de correo no deseado en PowerShell. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
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
  


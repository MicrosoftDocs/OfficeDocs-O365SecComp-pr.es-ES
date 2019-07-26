---
title: Configurar las directivas de filtro de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: La configuración básica del filtro de correo no deseado incluye seleccionar la acción a tomar cuando se identifiquen mensajes como correo no deseado.
ms.openlocfilehash: e06714e4a27601c7606c580551217155688a6169
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854664"
---
# <a name="configure-your-spam-filter-policies"></a>Configurar las directivas de filtro de correo no deseado
La configuración del filtro de correo no deseado incluye seleccionar la acción a tomar cuando se identifiquen mensajes como correo no deseado. La configuración de la directiva de filtro de correo no deseado se aplica solo a los mensajes entrantes. Hay dos tipos:

  - Predeterminada: la directiva de filtro de correo no deseado predeterminada se usa para configurar el filtro de correo no deseado para toda la compañía. No se puede cambiar el nombre de esta directiva y siempre está activada.

  - Personalizada: pueden aplicarse a usuarios, grupos o dominios específicos de su organización. Las directivas personalizadas siempre tienen prioridad sobre la predeterminada. Puede cambiar el orden en el que se ejecutan las directivas personalizadas cambiando la prioridad de cada directiva personalizada. Sin embargo, si hay varias directivas que cumplan el conjunto de criterios, solo se aplicará la directiva de prioridad más alta (es decir, la que tenga el número más cercano a 0).

## <a name="what-you-must-know-before-you-begin"></a>Qué necesita saber antes de comenzar

Tiempo estimado para finalizar: 30 minutos
  
Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx).

La configuración de la Directiva de filtro de correo no deseado se encuentra en el Centro de seguridad y cumplimiento (SCC). Puede obtener más información en [Ir al Centro de seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md). La página de configuración de correo no deseado se encuentra en el SCC \> **Administrador de amenazas** \> **Directiva** \> **sección contra el correo no deseado**.

## <a name="access-and-create-spam-filter-policies"></a>Crear y acceder a directivas de filtro de correo no deseado

En la página Configuración de correo no deseado, puede ver la configuración predeterminada en la pestaña estándar. Para cambiar esta configuración, cambie a la pestaña **Personalizada**. Podrá ver y configurar algunas de las opciones predeterminadas en la Directiva de filtro de correo no deseado predeterminada.

Para habilitar más opciones personalizadas o añadir directivas personalizadas, cambie el selector de **Configuración personalizada a Activado. Esto habilitará el filtro de correo no deseado personalizado. Puede expandir y ver las directivas personalizadas desde aquí.

## <a name="configure-custom-spam-filter-policy-settings"></a>Configurar opciones de directiva de filtro personalizado de correo no deseado

1. Seleccione y haga clic en **Editar directiva** si está editando una directiva; en caso contrario, haga clic en **Crear una directiva.

2. Puede dar un nombre único a las directivas personalizadas, pero no puede cambiar el nombre de las predeterminadas. También puede especificar una descripción más detallada (opcional).

3. En la sección **acciones de correo masivo y correo no deseado**:

  - Seleccione una acción para los tipos **Correo no deseado**, **Correo no deseado de confianza alta**, **Correo de suplantación de identidad** y **Correo electrónico en masa**. Los valores disponibles son los siguientes: 

    - **Mover mensaje a la carpeta Correo no deseado** Entrega el mensaje a la carpeta de Correo no deseado de los destinatarios especificados. Esta es la acción predeterminada para el correo no deseado, el correo no deseado de confianza alta y el correo en masa.<br/><br/>

    > [!NOTE]
    > Para que esta acción funcione en los buzones locales, debe configurar dos reglas de transporte de Exchange en los servidores locales para encontrar los encabezados de correo no deseado que agregó EOP. Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Este paso es esencial para clientes independientes de Protección en línea de Exchange (EOP):

    - **Agregar encabezado X:**  Envía el mensaje a los destinatarios especificados y agrega un texto de encabezado X al encabezado de mensaje para identificarlo como correo no deseado. Si usa este texto como identificador, puede crear reglas de bandeja de entrada o usar un dispositivo indirecto para actuar en el mensaje. El texto predeterminado del encabezado X es **Este mensaje parece correo no deseado**.<br/>Puede personalizar el texto del encabezado X mediante el cuadro de entrada **Agregar este texto de encabezado X**. Si personaliza el texto del encabezado X, tenga en cuenta lo siguiente: 
    
      - Si solo especifica el encabezado con el formato \< *encabezado* \>, sin espacios dentro del \< *encabezado* \>, se anexarán dos puntos al texto personalizado, seguido del texto predeterminado. Por ejemplo, si especifica "Este-es-mi-encabezado-personalizado", el texto del encabezado X aparecerá como "Este-es-mi-encabezado-personalizado: Este mensaje parece correo no deseado". 
        
      - Si incluye espacios dentro del texto del encabezado personalizado o si agrega usted mismo el signo de dos puntos, por ejemplo, "X Este es mi encabezado personalizado" o "Este-es-mi-encabezado-personalizado:", el texto del encabezado X volverá al texto predeterminado: "X-Esto-es-correo-no-deseado: Este mensaje parece correo no deseado".
    
      - No puede especificar el texto del encabezado en el formato \< *encabezado*  \>:\<  *valor*  \>. Si lo hace, se pasarán por alto los valores que aparecen antes y después de los dos puntos y, en su lugar, aparecerá el texto de encabezado X predeterminado: "X-Esto-es-correo-no-deseado: Este mensaje parece correo no deseado." 
      
      - Tenga en cuenta que, según la configuración de correo no deseado, los mensajes con este encabezado X podrían seguir terminando en la carpeta de correo no deseado. Para cambiar esto, deshabilite esta característica con set-MailboxJunkEmailConfiguration.

    - **Anteponer texto a la línea de asunto:** Envía el mensaje a los destinatarios especificados pero antepone a la línea de asunto el texto que se especificó en el cuadro de entrada **Anteponer texto a la línea de asunto**. Al usar este texto como identificador, también puede crear reglas para filtrar o enrutar los mensajes según sea necesario. 

    - **Redirigir el mensaje a la dirección de correo electrónico** Envía el mensaje a una dirección de correo designada en vez de a los destinatarios especificados. Especifique la dirección de «redirección» en el campo de entrada **Redirigir a esta dirección de correo electrónico**.

    - **Eliminar mensaje** Elimina el mensaje completo, incluyendo todos los datos adjuntos. 
        
    - **Colocar el mensaje en cuarentena** Envía el mensaje a la cuarentena en lugar de a los destinatarios. Esta acción es la predeterminada para suplantación de identidad. Si selecciona esta opción, en el cuadro de entrada **Mantener el correo no deseado durante (días)**, especifique la cantidad de días durante los cuales se mantendrá el mensaje de correo no deseado en cuarentena. (Automáticamente se borrará después de que transcurra ese tiempo. El valor predeterminado es 30 días, que es el valor máximo. El valor mínimo es 1 día).<br/><br/>CONSEJO: Para más información sobre cómo los administradores pueden administrar los mensajes de correo que están en cuarentena en el EAC, consulte [Cuarentena](quarantine.md) y [Buscar y liberar mensajes en cuarentena como un administrador](find-and-release-quarantined-messages-as-an-administrator.md). > Para informarse sobre cómo configurar los mensajes de notificación de correo no deseado que se enviarán a los usuarios, consulte [Configurar las notificaciones de correo no deseado para el usuario final en EOP](configure-end-user-spam-notifications-in-eop.md) o Configurar las notificaciones de correo no deseado para el usuario final en Exchange Online. 

  - En Seleccionar el umbral** puede determinar niveles a partir de los cuales se considerará o no el correo masivo como correo no deseado, en función del Nivel de quejas masivas (BCL) del mensaje. Puede elegir un valor de umbral de 1 a 9, donde 1 marca la mayor parte del correo electrónico masivo como correo no deseado y 9 permite entregar la mayoría del correo electrónico masivo. A continuación, el servicio realiza la acción configurada, por ejemplo, enviar el mensaje a la carpeta Correo electrónico no deseado del destinatario. Consulte [Valores de nivel de quejas masivas](bulk-complaint-level-values.md) y [¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico en masa?](what-s-the-difference-between-junk-email-and-bulk-email.md) para obtener más información. 

4. En la página Propiedades de correo no deseado** puede establecer las opciones de modo de prueba de la Directiva mediante las siguientes configuraciones: 
    
      - **Ninguno** No realiza ninguna acción de modo de prueba en el mensaje. Este valor es predeterminado. 
        
      - **Agregar el texto de encabezado X de prueba predeterminado** Si selecciona esta opción, el mensaje se envía a los destinatarios especificados pero se agrega un encabezado X especial al mensaje que lo identifica como una coincidencia con la opción de filtro de correo no deseado avanzada especificada. 
        
      - **Enviar un mensaje CCO a esta dirección** Si selecciona esta opción, se envía una copia oculta del mensaje a la dirección de correo que especificó en el cuadro de entrada. <br/><br/>Para obtener más información acerca de las opciones avanzadas de filtrado de correo no deseado, incluida la descripción de cada opción y el texto de encabezado X asociado a cada una, consulte [Opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md).

5. Solo para directivas personalizadas, haga clic en el elemento de menú **Aplicar a** y cree una regla basada en condiciones para especificar usuarios, grupos o dominios a los que aplicar la directiva. Puede crear varias condiciones siempre que sean únicas. 
    
      - Para elegir los usuarios, seleccione **El destinatario es**. En el cuadro de diálogo posterior, seleccione uno o más remitentes de la compañía en la lista del selector de usuarios y luego haga clic en **Agregar**. Para agregar remitentes que no están en la lista, escriba sus direcciones de correo electrónico y haga clic en **comprobar nombres**. En este cuadro también se pueden usar comodines para incluir varias direcciones de correo electrónico (por ejemplo: \*@ _domainname_). Cuando termine de seleccionar, haga clic en **aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar grupos, seleccione **El destinatario es un miembro de**. Después, en el cuadro de diálogo posterior, seleccione o especifique los grupos. Haga clic en **Aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar dominios, seleccione El dominio del destinatario es**. Después agregue los dominios en el cuadro de diálogo posterior. Haga clic en **Aceptar** para volver a la pantalla principal. <br/><br/>Puede crear excepciones para la regla. Por ejemplo, puede filtrar mensajes de todos los dominios excepto de uno en concreto. Haga clic en **agregar excepción** y cree sus condiciones de excepción de forma parecida a como creó las otras condiciones.<br/><br/>Solo se permite aplicar una directiva de correo no deseado a un grupo para **Grupos de seguridad habilitados para correo electrónico**. 
  
6. Haga clic en **Guardar **. En el panel de la derecha, aparece un resumen de la configuración de la directiva.

La directiva predeterminada no se puede deshabilitar ni eliminar, y las directivas personalizadas siempre tienen prioridad sobre la predeterminada. Puede habilitar o deshabilitar las directivas personalizadas marcando o desmarcando las casillas de la columna **HABILITADO**. De manera predeterminada, todas las directivas están habilitadas. Para eliminar una directiva personalizada, selecciónela, haga clic en el icono ![Icono eliminar](media/ITPro-EAC-DeleteIcon.gif) **Eliminar** y confirme que quiere eliminar la directiva.

> [!TIP]
> Para cambiar la prioridad (orden de ejecución) de las directivas personalizadas, haga clic en la ![ Icono flecha arriba](media/ITPro-EAC-UpArrowIcon.gif) flecha de arriba y la ![Icono flecha abajo](media/ITPro-EAC-DownArrowIcon.gif) flecha de abajo. La directiva con **PRIORIDAD** de **0** se ejecutará primero, seguida de la **1**, la **2** y, así, sucesivamente. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Usar PowerShell remoto para configurar directivas de filtro de correo no deseado

También puede configurar y aplicar directivas de filtro de correo no deseado en PowerShell. Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Para aprender cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Conectarse a Exchange Online Protection con PowerShell remoto](https://go.microsoft.com/fwlink/p/?linkid=627290).
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) Ver las opciones de filtro de correo no deseado. 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Editar las opciones de filtro de correo no deseado. 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Crear una nueva directiva personalizada de filtro de correo no deseado. 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Eliminar una directiva personalizada de filtro de correo no deseado. 
    
Para aplicar una directiva personalizada de filtro de correo no deseado a usuarios, grupos o dominios, use el cmdlet [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) (para crear una nueva regla de filtro que se pueda aplicar a directivas personalizadas) o el cmdlet [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) (para editar una regla de filtro existente que se pueda aplicar a directivas personalizadas). Use el cmdlet [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) o el cmdlet [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) para habilitar o deshabilitar la regla aplicada a la directiva. 
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para garantizar que el correo no deseado se detecte adecuadamente y se tomen las medidas necesarias, puede enviar un mensaje GTUBE a través del servicio. De manera similar al archivo de prueba del antivirus EICAR, GTUBE ofrece una prueba con la cual puede comprobar si el servicio detecta correo no deseado entrante. El filtro de correo no deseado siempre debe detectar un mensaje GTUBE como correo no deseado y las medidas que se toman respecto del mensaje deben coincidir con su configuración.
  
Incluya el siguiente texto GTUBE en un mensaje de correo en una única línea, sin espacios ni saltos de línea:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Ajustar la directiva de filtro de correo no deseado para evitar falsos positivos y falsos negativos

Puede habilitar las técnicas avanzadas de filtrado de correo no deseado si quiere usar un filtrado de correo no deseado más agresivo. Para obtener información sobre la configuración genérica de correo no deseado que se aplica a toda la organización, consulte [Usar listas seguras y otras técnicas para evitar el marcado erróneo de mensajes como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar los problemas de falso negativo](reduce-spam-email.md). Estos son útiles si tiene control de nivel de administrador y desea evitar falsos positivos o negativos falsos.

## <a name="allowblock-lists"></a>Lista de bloqueados y lista de permitidos

En algunas ocasiones, nuestros filtros pueden cometer un error o el sistema puede necesitar tiempo para ponerse al día. En estos casos, la directiva contra el correo no deseado le permite crear listas de permitidos y bloqueados que invaliden la clasificación realizada por el filtro. Esta opción se debe usar con moderación, ya que las listas pueden alcanzar tamaños excesivos, y de forma provisional, ya que nuestro sistema de filtrado debería funcionar correctamente.

Ambas listas se configuran como parte de cualquier directiva de correo no deseado del cliente:

1. En la sección **Listas de permitidos**, puede especificar entradas, como remitentes o dominios, que siempre se entregarán en la Bandeja de entrada. El filtro contra correo no deseado no procesa el correo electrónico de estas entradas. 
    
      - Agregue remitentes de confianza a la lista de permitidos del remitente. Haga clic en **Editar**![Icono Agregar](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **Listas de permitidos**. 
        
      - Agregue dominios de confianza a la lista de permitidos del dominio. Haga clic en **Editar**![Icono agregar](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **Listas de permitidos**. 

> [!CAUTION]
> Nunca use dominios aceptados (dominios de su propiedad) o dominios comunes como Microsoft.com, office.com, etc. en una lista de permitidos. Esto permite a usuarios malintencionados enviar correo indiscriminadamente a su organización.

2. En la página **Listas de bloqueados**, puede especificar entradas, como remitentes o dominios, que siempre se marcarán como correo no deseado. El servicio aplicará la acción de correo no deseado de alta confianza configurada en el correo electrónico que coincida con estas entradas. 
    
      - Agregue remitentes no deseados a la lista de bloqueados del remitente. Haga clic en **Editar**![Icono Agregar](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **Listas de bloqueados**. 
        
      - Agregue dominios no deseados a la lista de bloqueados del dominio. Haga clic en **Editar**![Icono agregar](media/ITPro-EAC-AddIcon.gif) y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **Listas de bloqueados**.

> [!TIP]
>  Puede ocurrir que la organización no esté de acuerdo con la clasificación hecha por el servicio. En este caso, usted puede plantearse mantener la lista de permitidos o bloqueados de forma permanente. Sin embargo, si va a colocar un dominio en la lista de permitidos durante largos períodos de tiempo, debe solicitar al remitente que se asegure de que su dominio está autenticado y, si no lo está, establecer DMARC para rechazarlo.

## <a name="for-more-information"></a>Más información
<a name="sectionSection6"> </a>

[Cómo configurar su dominio de DMARC](use-dmarc-to-validate-email.md)
  
[Cuarentena](quarantine.md)
  
[Impedir falsos positivos de correo electrónico marcado como correo no deseado con una lista segura u otras técnicas](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)

[Niveles de confianza del correo no deseado](spam-confidence-levels.md)
  


---
title: Configurar las directivas de filtro de correo no deseado
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: La configuración básica del filtro de correo no deseado incluye seleccionar la acción que se debe realizar en los mensajes identificados como correo no deseado.
ms.openlocfilehash: a59311ae6bccb1bcb1e949eb825cafc1a740c5da
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600106"
---
# <a name="configure-your-spam-filter-policies"></a>Configurar las directivas de filtro de correo no deseado
La configuración del filtro de correo no deseado incluye la selección de la acción que se debe realizar en los mensajes identificados como correo no deseado. La configuración de la Directiva de filtro de correo no deseado solo se aplica a los mensajes entrantes y hay dos tipos:

  - Valor predeterminado: la Directiva de filtro de correo no deseado predeterminada se usa para establecer la configuración del filtro de correo no deseado de toda la empresa. No se puede cambiar el nombre de esta directiva y siempre está activada.

  - Personalizado: las directivas de filtro de correo no deseado personalizadas pueden ser específicas y aplicarse a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre la predeterminada. Puede cambiar el orden en el que se ejecutan las directivas personalizadas cambiando la prioridad de cada directiva personalizada; sin embargo, solo se aplicará la Directiva de prioridad más alta (es decir, el número más cercano a 0) si varias directivas cumplen los criterios establecidos.

## <a name="what-you-must-know-before-you-begin"></a>Qué debe saber antes de empezar

Tiempo estimado para finalizar: 30 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada contra correo electrónico no deseado en el tema [permisos de características de Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

La configuración de la Directiva de filtro de correo no deseado se encuentran en el centro de seguridad & cumplimiento (SCC). Puede encontrar más información en [el centro de cumplimiento de & de seguridad de Office 365](go-to-the-securitycompliance-center.md). La página Configuración de correo no deseado está dentro de \> la sección **contra correo electrónico no deseado** de la **Directiva** \> de **Administración** \> de amenazas de SCC.

## <a name="access-and-create-spam-filter-policies"></a>Obtener acceso y crear directivas de filtro de correo no deseado

En la página Configuración contra correo no deseado, se puede ver la configuración predeterminada en la ficha estándar. Para cambiar esta configuración, cambie a la pestaña **personalizada** . Podrá ver y configurar algunas de las opciones predeterminadas en la Directiva de filtro de correo no deseado predeterminada.

Para habilitar más configuraciones personalizadas o agregar directivas personalizadas, cambie el selector de **Configuración personalizada** a **activado** para habilitar las directivas de filtro de correo no deseado personalizado. Puede ver las directivas personalizadas existentes si las expande desde aquí.

## <a name="configure-custom-spam-filter-policy-settings"></a>Configurar opciones de directiva de filtro de correo no deseado personalizados

1. Seleccione y haga clic en **Editar Directiva** si está editando una directiva; de lo contrario, haga clic en **crear una directiva** .

2. Puede especificar un nombre único para las directivas personalizadas, pero no puede cambiar el nombre de uno predeterminado. Opcionalmente, también puede especificar una descripción más detallada para cualquier directiva.

3. En la sección **correo electrónico no deseado y acciones en masa** :

  - Seleccione una acción para los tipos de correo electrónico **no deseado**, correo **no deseado de alta confianza**, correo de suplantación de **identidad**y **correo electrónico masivo** . Los valores disponibles son los siguientes: 

    - **Mover el mensaje a la carpeta de correo no deseado:** Envía el mensaje a la carpeta de correo no deseado de los destinatarios especificados. Esta es la acción predeterminada para correo no deseado, correo no deseado de alta confianza y en masa.<br/><br/>

    > [!NOTE]
    > Para que esta acción funcione con buzones locales, debe configurar dos reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en los servidores locales para detectar los encabezados de correo no deseado agregados por EOP. Para obtener más información, vea cómo [asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Este paso es fundamental para los clientes independientes de Exchange Online Protection (EOP).

    - **Agregar encabezado X:** Envía el mensaje a los destinatarios especificados, pero agrega texto de encabezado X al encabezado del mensaje para identificar el mensaje como correo no deseado. Si se usa este texto como un identificador, se pueden crear reglas de la bandeja de entrada o usar un dispositivo indirecto para actuar en el mensaje. El texto predeterminado del encabezado X es **Este mensaje parece correo no deseado**.<br/>Puede personalizar el texto del encabezado X mediante el cuadro de entrada **Agregar este texto de encabezado x** . Si personaliza el texto del encabezado X, tenga en cuenta las siguientes condiciones: 
    
      - Si especifica solo el encabezado en el \< *encabezado*\>de formato, donde no hay espacios en el \< *encabezado*\>, se anexarán dos puntos al texto personalizado, seguido del texto predeterminado.       Por ejemplo, si especifica "This-is-My-Custom-header", el texto del encabezado X aparecerá como "This-is-My-Custom-header: este mensaje parece ser correo no deseado". 
        
      - Si incluye espacios en el texto del encabezado personalizado, o si agrega los dos puntos (por ejemplo, "X éste es mi encabezado personalizado" o "X-This-is-My-Custom-header:"), el texto del encabezado X se revierte al valor predeterminado como "X-This-is-spam: este mensaje parece correo no deseado".
    
      - No puede especificar el texto del encabezado con el formato \< *header*  \>:\<  *value*  \>. Si hace esto, se omitirán los valores antes y después de los dos puntos y se mostrará el texto del encabezado X predeterminado en su lugar: "X-This-is-spam: este mensaje parece ser correo no deseado". 
      
      - Tenga en cuenta que los mensajes con este encabezado X se podrían seguir moviendo a la carpeta de correo no deseado de buzón debido a la configuración de buzón no deseado. Para cambiar esto, deshabilite esta característica con set-MailboxJunkEmailConfiguration.

    - **Anteponer línea de asunto con el texto:** Envía el mensaje a los destinatarios previstos pero antepone a la línea de asunto el texto que especifique en la **línea de asunto del prefijo con este** cuadro de entrada de texto. Si se usa este texto como un identificador, se pueden crear reglas para filtrar o enrutar los mensajes según sea necesario. 

    - **Redirigir el mensaje a la dirección de correo electrónico:** Envía el mensaje a una dirección de correo electrónico designada en lugar de enviarla a los destinatarios previstos. Especifique la dirección de "redirección" en el campo de entrada **Redirigir a esta dirección de correo**.

    - **Eliminar mensaje:** Elimina el mensaje completo, incluidos todos los datos adjuntos. 
        
    - **Mensaje en cuarentena:** Envía el mensaje a la cuarentena en lugar de a los destinatarios previstos. Esta es la acción predeterminada para phish. Si selecciona esta opción, en el cuadro de entrada **Mantener el correo no deseado durante (días)**, especifique la cantidad de días durante los cuales se mantendrá el mensaje de correo no deseado en cuarentena. (Automáticamente se borrará después de que transcurra ese tiempo. El valor predeterminado es 30 días, que es el valor máximo. El valor mínimo es 1 día).<br/><br/>Sugerencia: para obtener información sobre cómo los administradores pueden administrar los mensajes de correo electrónico que residen en la cuarentena en el EAC, consulte [Quarantine](quarantine.md) and [Find and Release Quarantined messages as an Administrator](find-and-release-quarantined-messages-as-an-administrator.md). > para obtener información sobre cómo configurar los mensajes de notificación de correo no deseado para que se envíen a los usuarios, consulte Configurar notificaciones de correo no deseado para el [usuario final en EOP](configure-end-user-spam-notifications-in-eop.md) o [configurar notificaciones de correo no deseado para el usuario final en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 

  - Configurar **Seleccione el umbral** para determinar cómo desea tratar el correo masivo como correo no deseado, en función del nivel de queja masiva (BCL) del mensaje. Puede elegir un valor de umbral de 1 a 9, donde 1 indica la mayor parte del correo electrónico masivo como correo no deseado y 9 permite la entrega de los correos electrónicos más masivos. A continuación, el servicio realiza la acción configurada, por ejemplo, enviar el mensaje a la carpeta Correo electrónico no deseado del destinatario. Consulte [los valores de nivel de queja masiva](bulk-complaint-level-values.md) y [cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo](what-s-the-difference-between-junk-email-and-bulk-email.md) para obtener más información. 

4. En la página de **propiedades de correo no deseado** , puede establecer las opciones del modo de prueba para la Directiva mediante la configuración de: 
    
      - **Ninguno** No realiza ninguna acción de modo de prueba en el mensaje. Ésta es la configuración predeterminada. 
        
      - **Agregar el texto del encabezado X de prueba predeterminado** Al seleccionar esta opción, se envía el mensaje a los destinatarios especificados, pero también se agrega un encabezado X especial al mensaje para identificarlo como coincidencia con una opción de filtrado de correo no deseado avanzada específica. 
        
      - **Enviar un mensaje CCO a esta dirección** Al seleccionar esta opción, se envía una copia oculta del mensaje a la dirección de correo electrónico que especifique en el cuadro de entrada. <br/><br/>Para obtener más información acerca de las opciones avanzadas de filtrado de correo no deseado, incluida la descripción de cada opción y el texto de encabezado X asociado a cada una, consulte [Opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md).

5. Solo en el caso de las directivas personalizadas, haga clic en el elemento de menú **aplicar a** y, a continuación, cree una regla basada en condiciones para especificar los usuarios, los grupos y los dominios a los que se aplicará esta Directiva. Puede crear varias condiciones, si son únicas. 
    
      - Para seleccionar usuarios, seleccione **el destinatario es**. En el cuadro de diálogo siguiente, seleccione uno o más remitentes de la compañía en la lista del selector de usuarios y, a continuación, haga clic en **Agregar**. Para agregar remitentes que no estén en la lista, escriba sus direcciones de correo electrónico y, a continuación, haga clic en **Comprobar nombres**. En este cuadro, también puede usar caracteres comodín para varias direcciones de correo electrónico (por ejemplo \* @ : _nombreDominio_). Cuando termine de realizar las selecciones, haga clic en **Aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar grupos, seleccione **el destinatario es un miembro de**. A continuación, en el cuadro de diálogo siguiente, seleccione o especifique los grupos. Haga clic en **aceptar** para volver a la pantalla principal. 
        
      - Para seleccionar dominios, seleccione **el dominio del destinatario es**. A continuación, en el cuadro de diálogo siguiente, agregue los dominios. Haga clic en **aceptar** para volver a la pantalla principal. <br/><br/>Puede crear excepciones dentro de la regla. Por ejemplo, puede filtrar los mensajes de todos los dominios excepto un dominio en particular. Haga clic en **Agregar excepción**y, a continuación, cree las condiciones de excepción de forma similar a como ha creado las otras condiciones.<br/><br/>La aplicación de una directiva de correo no deseado a un grupo solo se admite para los **grupos de seguridad habilitados para correo**. 
  
6. Haga clic en **Guardar **. En el panel de la derecha, aparece un resumen de la configuración de la directiva.

La directiva predeterminada no se puede deshabilitar ni eliminar, y las directivas personalizadas siempre tienen prioridad sobre la directiva predeterminada. En el caso de las directivas personalizadas, puede activar o desactivar las casillas de verificación de la columna **habilitada** para habilitarlas o deshabilitarlas. De forma predeterminada, todas las directivas están habilitadas. Para eliminar una directiva personalizada, seleccione la Directiva, haga clic ![en el](media/ITPro-EAC-DeleteIcon.gif) icono Eliminar icono **eliminar** y, a continuación, confirme que desea eliminar la Directiva.

> [!TIP]
> Puede cambiar la prioridad (orden de ejecución) de las directivas personalizadas haciendo clic en ![la flecha hacia](media/ITPro-EAC-UpArrowIcon.gif) arriba y ![flecha abajo del icono](media/ITPro-EAC-DownArrowIcon.gif) de flecha abajo. La Directiva que tiene una **prioridad** de **0** se ejecutará primero, seguida de **1**, **2**y así sucesivamente. 
  
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

Puede habilitar técnicas avanzadas de filtrado de correo no deseado si desea seguir un enfoque más agresivo del filtrado de correo no deseado. Para obtener información sobre la configuración genérica de correo no deseado que se aplica a toda la organización, consulte [Usar listas seguras y otras técnicas para evitar el marcado erróneo de mensajes como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar los problemas de falso negativo](reduce-spam-email.md). Esta información es útil si tiene control de nivel de administrador y quiere evitar falsos positivos o falsos negativos.

## <a name="allowblock-lists"></a>Listas permitir o bloquear

En ocasiones, los filtros perderán el mensaje o el tiempo que nuestros sistemas tardará en ponerse en marcha. En estos casos, la Directiva contra correo no deseado tiene una lista permitir y un bloqueo disponible para invalidar el veredicto actual. Esta opción solo debe usarse con moderación, dado que las listas pueden ser no administrables y temporalmente desde que nuestra pila de filtros debe hacer lo que se supone que está haciendo.

Las listas de permitidos y bloqueados se configuran como parte de cualquier directiva contra correo no deseado del cliente:

1. En la sección **listas** de permitidos, puede especificar entradas, como remitentes o dominios, que siempre se entregarán en la bandeja de entrada. El filtro contra correo no deseado no procesa el correo electrónico de estas entradas. 
    
      - Agregue remitentes de confianza a la lista de permitidos del remitente. Haga ****![clic en Editar](media/ITPro-EAC-AddIcon.gif)icono y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **listas** de permitidos. 
        
      - Agregue dominios de confianza a la lista de permitidos del dominio. Haga ****![clic en Editar](media/ITPro-EAC-AddIcon.gif)icono y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea permitir. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **listas** de permitidos. 

> [!CAUTION]
> Nunca debe hacer una lista de los dominios aceptados (dominios de su propiedad) o de dominios comunes como Microsoft.com, office.com, etc., a una lista de permitidos. Esto permite a los falsificadores enviar correo sin restricciones a su organización.

2. En la página **Listas de bloqueados**, puede especificar entradas, como remitentes o dominios, que siempre se marcarán como correo no deseado. El servicio aplicará la acción de correo no deseado de alta confianza configurada en el correo electrónico que coincida con estas entradas. 
    
      - Agregue remitentes no deseados a la lista de bloqueados del remitente. Haga ****![clic en Editar](media/ITPro-EAC-AddIcon.gif)icono y, a continuación, en el cuadro de diálogo de selección, agregue las direcciones del remitente que desee bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **listas** de bloqueados. 
        
      - Agregue dominios no deseados a la lista de bloqueados del dominio. Haga ****![clic en Editar](media/ITPro-EAC-AddIcon.gif)icono y, a continuación, en el cuadro de diálogo de selección, agregue los dominios que desea bloquear. Puede separar varias entradas con un punto y coma o una nueva línea. Haga clic en **Guardar** para volver a la página **listas** de bloqueados.

> [!TIP]
>  Puede haber situaciones en las que su organización no esté de acuerdo con el veredicto que proporciona el servicio. En este caso, es posible que quieras mantener la lista de permitidos o bloqueados permanentes. Sin embargo, si va a poner un dominio en la lista de permitidos durante largos períodos de tiempo, debe decirle al remitente que asegúrese de que su dominio se ha autenticado y establecido en rechazo de DMARC si no lo está.

## <a name="for-more-information"></a>Más información
<a name="sectionSection6"> </a>

[Configurar el dominio para DMARC](use-dmarc-to-validate-email.md)
  
[Cuarentena](quarantine.md)
  
[Impedir que el correo electrónico falso positivo se marque como correo no deseado con una lista de IP seguras u otras técnicas](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)

[Niveles de confianza del correo no deseado](spam-confidence-levels.md)
  


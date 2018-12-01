---
title: Buscar en el registro de auditoría de Office 365 para escenarios comunes de solución de problemas
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
description: Puede usar la herramienta de búsqueda de registro de auditoría de Office 365 que le ayudarán a solucionar problemas comunes, como una investigación que usan una cuenta en peligro o averiguar que configurar el reenvío de correo electrónico para un buzón de correo.
ms.openlocfilehash: 930e311712e49214ca2a51e256c29e5f959deab8
ms.sourcegitcommit: c34f1a0d560117153fc9a7b8da8994bc6fc53791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2018
ms.locfileid: "27123903"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a>Buscar en el registro de auditoría de Office 365 para escenarios comunes de solución de problemas

En este artículo se describe cómo usar la herramienta de búsqueda de registro de auditoría de Office 365 que le ayudarán a solucionar problemas de escenarios comunes de soporte técnico. Esto incluye el uso del registro de auditoría para:

- Busque la dirección IP del equipo usado para tener acceso a una cuenta en peligro
- Determinar quién configurar el reenvío de correo electrónico para un buzón de correo
- Determinar si un usuario elimina los elementos de correo electrónico en sus buzones de correo
- Determinar si un usuario crea una regla de bandeja de entrada

## <a name="using-the-office-365-audit-log-search-tool"></a>Uso de la herramienta de búsqueda de registro de auditoría de Office 365

Cada uno de los escenarios de solución de problemas que se describen en este artículo se basan en el uso de la herramienta de búsqueda de registro de auditoría en el centro de cumplimiento y seguridad de Office 365. En esta sección se enumera los permisos necesarios para buscar el registro de auditoría y se describe los pasos para tener acceso y ejecutar las búsquedas de registro de auditoría. Cada sección de escenario proporciona instrucciones específicas sobre cómo configurar una consulta de búsqueda de registro de auditoría y qué se va a buscar en la información detallada de los registros de auditoría que coinciden con los criterios de búsqueda.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Permisos necesarios para usar la herramienta de búsqueda de registro de auditoría

Se debe asignar el rol registros de auditoría con permiso de vista o los registros de auditoría en Exchange Online para buscar el registro de auditoría de Office 365. De forma predeterminada, estas funciones se asignan a los grupos de funciones de administración de cumplimiento y administración de la organización en la página de **permisos** en el centro de administración de Exchange. Para obtener más información, vea la [función de administrar grupos en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Ejecución de las búsquedas de registro de auditoría

En esta sección se describe los conceptos básicos para crear y ejecutar las búsquedas de registro de auditoría. Siga estas instrucciones como punto de partida para cada escenario de solución de problemas de este artículo. Para obtener instrucciones paso a paso más detalladas, vea [el registro de auditoría en el centro de cumplimiento de seguridad de Office 365 y de búsqueda ](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Vaya a [https://protection.office.com](https://protection.office.com).
  
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.

3. En el panel izquierdo de la seguridad y el centro de cumplimiento, haga clic en **búsqueda & investigación** > **búsqueda de registro de auditoría**.
    
    Se muestra la página de **búsqueda de registro de auditoría** . 
    
    ![Configurar los criterios y, a continuación, haga clic en Buscar para ejecutar la búsqueda](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Puede configurar los siguientes criterios de búsqueda. Tenga en cuenta que cada escenario de solución de problemas en este artículo se recomienda instrucciones específicas para configurar estos campos.
    
    r. **actividades** - haga clic en la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, se muestran sólo los registros de auditoría de las actividades seleccionadas. Selección de **Mostrar los resultados de todas las actividades** mostrará los resultados para todas las actividades que cumplen los otros criterios de búsqueda. También tendrá deje este campo en blanco en algunos de los escenarios de solución de problemas.
    
    b. **fecha de inicio** y **fecha de finalización** : seleccione un intervalo de fecha y hora para mostrar los eventos que se produjeron dentro de ese período. De forma predeterminada, se seleccionan los últimos siete días. La fecha y hora se presentan en formato de hora Universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es de 90 días.

    c. **los usuarios** , haga clic en este cuadro y, a continuación, seleccione uno o varios usuarios para mostrar búsqueda resultados para. Registros de auditoría para la actividad seleccionada realizado por los usuarios que seleccione en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas para todos los usuarios (y las cuentas de servicio) en la organización.
    
    d. el **archivo, carpeta o sitio** - escriba algunos o todos los de un nombre de archivo o carpeta para buscar la actividad relacionada con el archivo de la carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si utiliza una dirección URL, asegúrese de que el tipo de la ruta de acceso de dirección URL completa o si sólo tiene que escribir una parte de la dirección URL, no incluya espacios ni caracteres especiales. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas en la organización. Tenga en cuenta que este campo se deja en blanco en todos los escenarios de solución de problemas en este artículo.
    
5. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
    Se cargan los resultados de búsqueda y, después de unos momentos se muestran en **los resultados** en la página de **búsqueda de registro de auditoría** . Cada una de ellas en las secciones siguientes se proporcionan instrucciones acerca de las cosas que se busca el escenario de solución de problemas específico.

    Para obtener más información acerca de la visualización, filtrado o exportar los resultados de búsqueda de registro de auditoría, consulte:

    - [Ver los resultados de búsqueda](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrar los resultados de búsqueda](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Búsqueda de la dirección IP del equipo usado para tener acceso a una cuenta en peligro

La dirección IP correspondiente a una actividad realizada por cualquier usuario se incluye en la mayoría de los registros de auditoría. También se incluye información acerca del cliente que se usa en el registro de auditoría.

Esta es la configuración de una consulta de búsqueda de registro de auditoría para este escenario:

**Actividades** - si es relevante para su caso, seleccione una actividad específica para buscar. Para solucionar problemas de las cuentas en peligro, considere la posibilidad de seleccionar la actividad de **usuario ha iniciado sesión en el buzón de correo** en **las actividades de buzón de correo de Exchange**. Esto devolverá registros de auditoría que muestra la dirección IP que se utilice al iniciar sesión en el buzón de correo. De lo contrario, deje este campo en blanco para devolver los registros de auditoría para todas las actividades. 

> [!TIP]
> Si deja este campo en blanco devolverá **UserLoggedIn** actividades, que es una actividad de Azure Active Directory que indica que alguien ha iniciado sesión una cuenta de usuario de Office 365. Use el filtrado en los resultados de búsqueda para mostrar los registros de auditoría de **UserLoggedIn** .

**Fecha de inicio** y **fecha de finalización** : seleccione un intervalo de fechas que es aplicable para la investigación.

**Los usuarios** : si está investigar una cuenta en peligro, seleccione el usuario cuya cuenta se ve comprometida. Esto devolverá registros de auditoría para actividades realizadas por esa cuenta de usuario.

**Archivo, carpeta o sitio** - deje este campo en blanco.

Después de ejecutar la búsqueda, la dirección IP de cada actividad se muestra en la columna de **dirección IP** en los resultados de búsqueda. Haga clic en el registro en los resultados de búsqueda para ver información más detallada en la página emergente.

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a>Determinar quién configurar el reenvío de correo electrónico para un buzón de correo

Cuando se configura el reenvío de correo electrónico para un buzón de correo, mensajes de correo electrónico que se envían a los buzones de correo reenviados a otro buzón. Los mensajes se pueden reenviar a los usuarios dentro o fuera de la organización. Cuando se configura el reenvío de correo electrónico en un buzón de correo, el cmdlet de Exchange Online subyacente que se utiliza es **Set-Mailbox**.

Esta es la configuración de una consulta de búsqueda de registro de auditoría para este escenario:

**Actividades** - deje este campo en blanco para que la búsqueda devuelve los registros de auditoría para todas las actividades. Esto es necesario devolver cualquiera de auditoría de registros relacionados con el cmdlet **Set-Mailbox** .

**Fecha de inicio** y **fecha de finalización** : seleccione un intervalo de fechas que es aplicable para la investigación.

**Los usuarios** - a menos que esté investigar un correo electrónico de reenvío de problema para un usuario específico, deje este campo en blanco. Esto ayudará a identificar si se configuró el reenvío de correo electrónico para cualquier usuario.

**Archivo, carpeta o sitio** - deje este campo en blanco.

Después de ejecutar la búsqueda, haga clic en **filtrar los resultados** en la página de resultados de búsqueda. En el cuadro en el encabezado de columna de **actividad** , escriba **Set-Mailbox** para que se muestren solo los registros de auditoría relacionados con el cmdlet **Set-Mailbox** .

![Filtrar los resultados de una búsqueda de registro de auditoría](media/emailforwarding1.png)

En este momento, se debe buscar en los detalles de cada registro de auditoría para determinar si está relacionado con la actividad de transferencia de correo electrónico. Haga clic en el registro de auditoría para mostrar la página de **Detalles del** menú desplegable y, a continuación, haga clic en **obtener más información**. La siguiente captura de pantalla y descripciones información importante se estableció en la información que indica el reenvío de correo electrónico en el buzón de correo.

![Información detallada del registro de auditoría](media/emailforwarding2.png)

r. en el campo **ObjectId** , se estableció el alias del buzón al que el reenvío de correo electrónico se muestra en. Este buzón de correo también se muestra en la columna del **elemento** en la página de resultados de búsqueda.

b. en el campo de **parámetros** , el valor *ForwardingSmtpAddress* indica que se ha configurado el correo electrónico hacia delante en el buzón de correo. En este ejemplo, el correo se se reenvíen a la mike@contoso.com dirección correo electrónico, que está fuera de la organización de alpinehouse.onmicrosoft.com.

c. el valor *True* para el parámetro *DeliverToMailboxAndForward* indica que una copia del mensaje que se envía a sarad@alpinehouse.onmicrosoft.com *y* se reenvía a la dirección de correo electrónico especificada por el *ForwardingSmtpAddress *parámetro, que en este ejemplo es mike@contoso.com. Si el valor para el parámetro *DeliverToMailboxAndForward* se establece en *False*, correo electrónico sólo se reenvía a la dirección especificada por el parámetro *ForwardingSmtpAddress* . No se entrega en el buzón especificado en el campo **ObjectId** .

d. el campo **UserId** indica el usuario que configuró el reenvío de correo electrónico en el buzón especificado en el campo de campo **ObjectId** . Este usuario también se muestra en la columna de **usuario** en la página de resultados de búsqueda. En este caso, parece que el propietario del buzón de establece el reenvío de correo electrónico en su buzón de correo.

Si determina que el reenvío de correo electrónico no debe establecerse en el buzón de correo, puede quitarlo ejecutando el siguiente comando en Exchange Online PowerShell:

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Vea el artículo de [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) para obtener más información acerca de los parámetros relacionados con el reenvío de correo electrónico.

## <a name="determining-if-a-user-deleted-email-items"></a>Determinar si un usuario elimina los elementos de correo electrónico

Antes de eliminaran registros de registro de auditoría acerca de los elementos de correo electrónico se guardan en el registro de auditoría de Office 365, auditoría de buzón de correo debe estar habilitada para cada buzón de usuario de la organización. Además, las acciones de buzón de correo SoftDelete y HardDelete deben estar habilitados para la auditoría. Para obtener instrucciones, vea [Habilitar la auditoría en Office 365 de buzón de correo](enable-mailbox-auditing.md). Si ya está habilitada la auditoría de buzón de correo para los usuarios, siga estos pasos para buscar el registro de auditoría de eventos relacionados con elementos de correo electrónico eliminados.

Esta es la configuración de una consulta de búsqueda de registro de auditoría para este escenario:

**Actividades** - en **las actividades de buzón de correo de Exchange**, seleccione una o ambas de las siguientes actividades:

- **Los mensajes eliminados de la carpeta Elementos eliminados** - esta actividad se corresponde con el buzón de correo de **SoftDelete** acción de auditoría. Esta actividad también se registra cuando un usuario elimina permanentemente un elemento seleccionándolo y presionando la tecla **MAYÚS + SUPR**. Después de que un elemento se elimina de manera permanente, el usuario puede recuperar hasta que expire el período de retención de elementos eliminados.

- **Depurados mensajes desde el buzón de correo** - esta actividad se corresponde con el buzón de correo de **HardDelete** acción de auditoría. Esto se registra cuando un usuario purga un elemento desde la carpeta elementos recuperables. Los administradores pueden utilizar la herramienta de búsqueda de contenido en el centro de cumplimiento y seguridad de Office 365 para buscar y recuperar purgado elementos hasta que expire el período de retención de elementos eliminados o más tiempo si el buzón del usuario se encuentra en suspensión.

**Fecha de inicio** y **fecha de finalización** : seleccione un intervalo de fechas que es aplicable para la investigación.

**Los usuarios** , si selecciona un usuario en este campo, la herramienta de búsqueda de registro de auditoría devolverá registros de auditoría para los elementos de correo electrónico que se han eliminado (SoftDeleted o HardDeleted) por el usuario que se especifique. En algunos casos, el usuario que se elimina un correo electrónico no puede ser el propietario del buzón.

**Archivo, carpeta o sitio** - deje este campo en blanco.

Después de ejecutar la búsqueda, puede filtrar los resultados de búsqueda para mostrar los registros de auditoría para elementos eliminados temporalmente o para elementos eliminados disco duro. Haga clic en el registro de auditoría para mostrar la página de **Detalles del** menú desplegable y, a continuación, haga clic en **obtener más información**. Información adicional acerca de los elementos eliminados, como la línea de asunto y la ubicación del elemento al que se ha eliminado, se muestra en el campo **AffectedItems** . Las capturas de pantalla siguientes muestran un ejemplo del campo **AffectedItems** de un elemento eliminado temporalmente y un elemento de disco duro eliminados.

**Ejemplo de campo de AffectedItems para el elemento eliminado temporalmente**

![Registro de auditoría para el elemento eliminado temporalmente](media/softdeleteditem.png)

**Ejemplo de campo de AffectedItems de disco duro Eliminar elemento**

![Registro de auditoría para el elemento de correo electrónico de disco duro eliminados](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a>Recuperación de elementos de correo electrónico eliminados

Los usuarios pueden recuperar elementos eliminados temporalmente si no ha expirado el período de retención de elementos eliminados. En Exchange Online, el período de retención de elementos eliminado de forma predeterminada es de 14 días, pero los administradores pueden aumentar este valor a un máximo de 30 días. Punto a los usuarios el artículo [recuperar elementos eliminados o correo electrónico en Outlook Web App](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) para obtener instrucciones sobre la recuperación de elementos eliminan.

Como se explica anteriormente, los administradores es posible que pueda recuperar elementos eliminados disco duro si no ha expirado el período de retención de elementos eliminados o si el buzón se encuentra en suspensión, en cuyo caso se conservan los elementos hasta que expire la duración de la suspensión. Cuando se ejecuta una búsqueda de contenido, elementos eliminado temporalmente y disco duro eliminados en la carpeta elementos recuperables se devuelven en los resultados de búsqueda si coinciden con la consulta de búsqueda. Para obtener más información acerca de la ejecución de búsquedas de contenido, consulte [Búsqueda de contenido en Office 365](content-search.md).

> [!TIP]
> Para buscar los elementos de correo electrónico eliminados, de búsqueda para la totalidad o parte de la línea de asunto que se muestra en el campo **AffectedItems** en el registro de auditoría.

## <a name="determining-if-a-user-created-an-inbox-rule"></a>Determinar si un usuario crea una regla de bandeja de entrada

Cuando los usuarios creen una regla de bandeja de entrada para su buzón de Exchange Online, se guarda un registro de auditoría correspondientes en el registro de auditoría. Para obtener más información acerca de las reglas de bandeja de entrada, vea:

- [Usar las reglas de bandeja de entrada de Outlook en la web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Administrar mensajes de correo electrónico en Outlook mediante el uso de reglas](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Esta es la configuración de una consulta de búsqueda de registro de auditoría para este escenario:

**Actividades** - en **las actividades de buzón de correo de Exchange**, seleccione **New-InboxRule crear, modificar o habilitar o deshabilitar la regla de bandeja de entrada**.

**Fecha de inicio** y **fecha de finalización** : seleccione un intervalo de fechas que es aplicable para la investigación.

**Los usuarios** - a menos que esté investigar un usuario específico, deje este campo en blanco. Esto ayudará a identificar nuevas reglas de bandeja de entrada configurar por cualquier usuario.

**Archivo, carpeta o sitio** - deje este campo en blanco.

Después de ejecutar la búsqueda, se muestran los registros de auditoría para esta actividad en los resultados de búsqueda. Haga clic en un registro de auditoría para mostrar la página emergente de **Detalles** y, a continuación, haga clic en **obtener más información**. Información acerca de la configuración de la regla de bandeja de entrada se muestran en el campo de **parámetros** . La siguiente captura de pantalla y descripciones resalta la información acerca de las reglas de bandeja de entrada.

![Registro de auditoría para la nueva regla de bandeja de entrada](media/NewInboxRuleRecord.png)

r. en el campo **ObjectId** , se muestra el nombre completo de la regla de bandeja de entrada. Este nombre incluye el alias del buzón de correo del usuario (por ejemplo, SaraD) y el nombre de la regla de bandeja de entrada (por ejemplo, "mover mensajes de administración").

b. en el campo de **parámetros** , se muestra la condición de la regla de bandeja de entrada. En este ejemplo, la condición es especificada por el parámetro *From* . El valor definido para el parámetro *From* indica que la regla de bandeja de entrada actúa en el correo electrónico enviado por admin@alpinehouse.onmicrosoft.com. Para obtener una lista completa de los parámetros que se puede usar para definir las condiciones de reglas de bandeja de entrada, vea el artículo de [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) .

c. el parámetro *MoveToFolder* especifica la acción de la regla de bandeja de entrada; en este ejemplo, los mensajes recibidos desde admin@alpinehouse.onmicrosoft.com se mueven a la carpeta denominada *AdminSearch*. Vea también el artículo de [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) para obtener una lista completa de los parámetros que puede usar para definir la acción de una regla de bandeja de entrada.

d. el campo **UserId** indicar al usuario que creó la regla de bandeja de entrada especificada en el campo **ObjectId** . Este usuario también se muestra en la columna de **usuario** en la página de resultados de búsqueda.
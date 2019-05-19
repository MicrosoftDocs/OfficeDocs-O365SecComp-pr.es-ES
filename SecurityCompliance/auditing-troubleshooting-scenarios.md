---
title: Buscar en el registro de auditoría de 365 de Office para solucionar escenarios comunes
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: Puede usar la herramienta de búsqueda de registros de auditoría de Office 365 para ayudarle a solucionar problemas comunes, como investigar una cuenta en peligro o averiguar quién ha configurado el reenvío de correo para un buzón.
ms.openlocfilehash: e5c043668d73bdff30dfce962962a015a6748949
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155682"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a>Buscar en el registro de auditoría de 365 de Office para solucionar escenarios comunes

En este artículo se describe cómo usar la herramienta de búsqueda de registros de auditoría de Office 365 para ayudarle a solucionar los escenarios de soporte habituales. Esto incluye el uso del registro de auditoría para:

- Buscar la dirección IP del equipo que se usa para obtener acceso a una cuenta en peligro
- Determinar quién ha configurado el reenvío de correo electrónico para un buzón
- Determinar si un usuario eliminó los elementos de correo electrónico de su buzón
- Determinar si un usuario creó una regla de bandeja de entrada

## <a name="using-the-office-365-audit-log-search-tool"></a>Uso de la herramienta de búsqueda de registros de auditoría de Office 365

Cada uno de los escenarios de solución de problemas descritos en este artículo se basa en el uso de la herramienta de búsqueda de registros de auditoría en el centro de seguridad y cumplimiento de Office 365. En esta sección se enumeran los permisos necesarios para buscar en el registro de auditoría y se describen los pasos para obtener acceso y ejecutar las búsquedas de registros de auditoría. En cada sección de escenario se proporcionan instrucciones específicas sobre cómo configurar una consulta de búsqueda de registros de auditoría y qué buscar en la información detallada de los registros de auditoría que coinciden con los criterios de búsqueda.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Permisos necesarios para usar la herramienta de búsqueda de registros de auditoría

Debe tener asignado el rol registros de auditoría con permiso de vista o registros de auditoría en Exchange Online para buscar en el registro de auditoría de 365 de Office. De forma predeterminada, estos roles se asignan a los grupos de roles administración de cumplimiento y administración de la organización en la página **permisos** del centro de administración de Exchange. Tenga en cuenta que los administradores globales de Office 365 y Microsoft 365 se agregan automáticamente como miembros del grupo de funciones de administración de la organización en Exchange Online. Para obtener más información, vea [administrar grupos de roles en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Ejecución de búsquedas de registro de auditoría

En esta sección se describen los conceptos básicos para crear y ejecutar búsquedas de registros de auditoría. Siga estas instrucciones como punto de partida para cada escenario de solución de problemas de este artículo. Para obtener instrucciones detalladas paso a paso, consulte [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Vaya a [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) e inicie sesión con su cuenta profesional o educativa.
    
    Se muestra la página de **búsqueda de registros de auditoría** . 
    
    ![Configure los criterios y, a continuación, haga clic en buscar para ejecutar la búsqueda](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Puede configurar los siguientes criterios de búsqueda. Tenga en cuenta que cada escenario de solución de problemas de este artículo le recomendará una guía específica para configurar estos campos.
    
    a. **Actividades** : haga clic en la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, solo se muestran los registros de auditoría de las actividades seleccionadas. Al seleccionar **Mostrar resultados para todas las actividades** , se mostrarán los resultados de todas las actividades que cumplan los otros criterios de búsqueda. También tendrá que dejar este campo en blanco en algunos de los escenarios de solución de problemas.
    
    b. Fecha de **Inicio** y **fecha** de finalización: Seleccione un intervalo de fechas y horas para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días están seleccionados de forma predeterminada. La fecha y la hora se presentan en formato de hora universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es de 90 días.

    c. **Usuarios** : haga clic en este cuadro y, a continuación, seleccione uno o más usuarios para los que desea mostrar los resultados de la búsqueda. Los registros de auditoría para la actividad seleccionada realizada por los usuarios que seleccione en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y las cuentas de servicio) de su organización.
    
    d. **Archivo, carpeta o** tipo de sitio todo o parte del nombre de un archivo o carpeta para buscar actividades relacionadas con el archivo de la carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o una carpeta. Si usa una dirección URL, asegúrese de escribir la ruta de acceso completa de la dirección URL o, si solo escribe una parte de la dirección URL, no incluya ningún carácter o espacio especial. Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización. Tenga en cuenta que este campo se deja en blanco en todos los escenarios de solución de problemas de este artículo.
    
5. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
    Los resultados de la búsqueda se cargan y, después de unos segundos, se muestran en **resultados** en la página de **búsqueda de registros de auditoría** . Cada una de las siguientes secciones le proporcionará información sobre las cosas que debe buscar en el escenario de solución de problemas específico.

    Para obtener más información acerca de cómo ver, filtrar o exportar los resultados de la búsqueda de registros de auditoría, vea:

    - [Ver los resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportar resultados de la búsqueda](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Buscar la dirección IP del equipo usado para obtener acceso a una cuenta en peligro

La dirección IP correspondiente a una actividad realizada por cualquier usuario se incluye en la mayoría de los registros de auditoría. La información sobre el cliente usado también se incluye en el registro de auditoría.

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades** : si es relevante para su caso, seleccione una actividad específica que desee buscar. Para solucionar problemas de cuentas comprometidas, considere la posibilidad de seleccionar la actividad **usuario de sesión iniciada** en el buzón en **actividades de buzón de Exchange**. Se devolverán registros de auditoría que muestran la dirección IP que se utilizó al iniciar sesión en el buzón. De lo contrario, deje este campo en blanco para devolver los registros de auditoría de todas las actividades. 

> [!TIP]
> Si deja este campo en blanco, se devolverá **UserLoggedIn** actividades, que es una actividad de Azure Active Directory que indica que alguien ha iniciado sesión en una cuenta de usuario de Office 365. Use el filtrado en los resultados de la búsqueda para mostrar los registros de auditoría de **UserLoggedIn** .

Fecha de **Inicio** y **fecha** de finalización: Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios** : Si está investigando una cuenta en peligro, seleccione el usuario cuya cuenta se haya puesto en peligro. Se devolverán registros de auditoría para las actividades realizadas por esa cuenta de usuario.

**Archivo, carpeta o sitio** : Deje este campo en blanco.

Después de ejecutar la búsqueda, la dirección IP de cada actividad se muestra en la columna **dirección IP** de los resultados de la búsqueda. Haga clic en el registro de los resultados de la búsqueda para ver información más detallada en la página de flotante.

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a>Determinar quién ha configurado el reenvío de correo electrónico para un buzón

Cuando se configura el reenvío de correo electrónico para un buzón, los mensajes de correo electrónico que se envían al buzón se reenvían a otro buzón. Los mensajes se pueden desviar a los usuarios dentro o fuera de la organización. Cuando se configura el reenvío de correo electrónico en un buzón, el cmdlet de Exchange Online subyacente que se usa es **set-Mailbox**.

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades** : Deje este campo en blanco para que la búsqueda devuelva registros de auditoría para todas las actividades. Esto es necesario para devolver los registros de auditoría relacionados con el cmdlet **set-Mailbox** .

Fecha de **Inicio** y **fecha** de finalización: Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios** : a menos que esté investigando un problema de reenvío de correo para un usuario específico, deje este campo en blanco. Esto le ayudará a identificar si el reenvío de correo electrónico se ha configurado para cualquier usuario.

**Archivo, carpeta o sitio** : Deje este campo en blanco.

Después de ejecutar la búsqueda, haga clic en **filtrar resultados** en la página de resultados de búsqueda. En el cuadro en encabezado de columna **actividad** , escriba **set-Mailbox** para que solo se muestren los registros de auditoría relacionados con el cmdlet **set-Mailbox** .

![Filtrado de los resultados de una búsqueda de registros de auditoría](media/emailforwarding1.png)

En este punto, tiene que mirar los detalles de cada registro de auditoría para determinar si la actividad está relacionada con el reenvío de correo electrónico. Haga clic en el registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, haga clic en **más información**. En la siguiente captura de pantalla y descripciones se resalta la información que indica el reenvío de correo electrónico que se estableció en el buzón.

![Información detallada del registro de auditoría](media/emailforwarding2.png)

a. En el campo **objectId** , se muestra el alias del buzón de correo en el que se ha configurado el reenvío de correo electrónico. Este buzón también se muestra en la columna de **elementos** de la página de resultados de búsqueda.

b. En el campo **parámetros** , el valor *ForwardingSmtpAddress* indica que el correo electrónico reenviado se ha establecido en el buzón. En este ejemplo, el correo se envía a la dirección de correo electrónico mike@contoso.com, que está fuera de la organización alpinehouse.onmicrosoft.com.

c. El valor *true* del parámetro *DeliverToMailboxAndForward* indica que una copia del mensaje se entrega a SARAD@alpinehouse.onmicrosoft.com *y* se reenvía a la dirección de correo electrónico especificada por el *ForwardingSmtpAddress *parámetro, que en este ejemplo es Mike@contoso.com. Si el valor del parámetro *DeliverToMailboxAndForward* está establecido en *false*, el correo electrónico sólo se reenvía a la dirección especificada por el parámetro *ForwardingSmtpAddress* . No se entrega al buzón especificado en el campo **objectId** .

d. El campo **userid** indica el usuario que ha configurado el reenvío de correo electrónico en el buzón especificado en el campo **objectId** . Este usuario también se muestra en la columna **usuario** de la página de resultados de búsqueda. En este caso, parece que el propietario del buzón estableció el reenvío de correo electrónico en su buzón.

Si determina que no se debe establecer el reenvío de correo electrónico en el buzón, puede quitarlo ejecutando el siguiente comando en Exchange Online PowerShell:

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Consulte el artículo [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) para obtener más información acerca de los parámetros relacionados con el reenvío de correo electrónico.

## <a name="determining-if-a-user-deleted-email-items"></a>Determinar si un usuario eliminó elementos de correo electrónico

A partir de enero de 2019, Microsoft activa el registro de auditoría de buzones de correo de forma predeterminada para todas las organizaciones de Office 365 y Microsoft. Esto significa que determinadas acciones realizadas por los propietarios de los buzones de correo se registran automáticamente y que los registros de auditoría de buzón correspondientes estarán disponibles cuando los busque en el registro de auditoría de buzones de correo. Antes de que se activara la auditoría de buzones de correo de forma predeterminada, tenía que habilitarla manualmente para cada buzón de usuario de la organización. 

Las acciones de buzón de correo registradas de forma predeterminada incluyen las acciones de buzón SoftDelete y HardDelete realizadas por los propietarios de buzones. Esto significa que puede usar los pasos siguientes para buscar en el registro de auditoría eventos relacionados con elementos de correo electrónico eliminados. Para obtener más información acerca de la auditoría de buzones de correo de forma predeterminada, consulte [Manage Mailbox Auditing](enable-mailbox-auditing.md).

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades** -en **actividades de buzón de Exchange**, seleccione una o las dos actividades siguientes:

- **Mensajes eliminados de la carpeta elementos eliminados** : esta actividad corresponde a la acción de auditoría del buzón de **SoftDelete** . Esta actividad también se registra cuando un usuario elimina permanentemente un elemento seleccionándolo y presionando **Mayús + Supr**. Una vez que un elemento se elimina de forma permanente, el usuario puede recuperarlo hasta que expire el período de retención de elementos eliminados.

- **Mensajes purgados del buzón de correo** : esta actividad corresponde a la acción de auditoría del buzón de **HardDelete** . Este registro se registra cuando un usuario purga un elemento de la carpeta elementos recuperables. Los administradores pueden usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar y recuperar los elementos purgados hasta que expire el período de retención de elementos eliminados si el buzón de correo del usuario está en suspensión.

Fecha de **Inicio** y **fecha** de finalización: Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios** : Si selecciona un usuario en este campo, la herramienta de búsqueda de registros de auditoría devolverá registros de auditoría para los elementos de correo electrónico que el usuario haya eliminado (SoftDeleted o HardDeleted). En algunos casos, es posible que el usuario que elimina un correo electrónico no sea el propietario del buzón.

**Archivo, carpeta o sitio** : Deje este campo en blanco.

Después de ejecutar la búsqueda, puede filtrar los resultados de la búsqueda para mostrar los registros de auditoría de los elementos eliminados temporalmente o de los elementos eliminados permanentemente. Haga clic en el registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, haga clic en **más información**. La información adicional sobre el elemento eliminado, como la línea de asunto y la ubicación del elemento cuando se elimina, se muestra en el campo **AffectedItems** . En las siguientes capturas de pantalla se muestra un ejemplo del campo **AffectedItems** de un elemento eliminado temporalmente y un elemento eliminado permanentemente.

**Ejemplo de campo AffectedItems para un elemento eliminado temporalmente**

![Registro de auditoría para elemento eliminado temporalmente](media/softdeleteditem.png)

**Ejemplo de campo AffectedItems para un elemento eliminado permanentemente**

![Registro de auditoría para elemento de correo electrónico eliminado permanentemente](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a>Recuperación de elementos de correo electrónico eliminados

Los usuarios pueden recuperar elementos eliminados temporalmente si no ha expirado el período de retención de elementos eliminados. En Exchange Online, el período de retención predeterminado de elementos eliminados es de 14 días, pero los administradores pueden aumentar esta configuración a un máximo de 30 días. Apunte a los usuarios al artículo [recuperar elementos eliminados o correo electrónico en Outlook en la web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) para obtener instrucciones sobre cómo recuperar elementos eliminados.

Como se ha explicado anteriormente, los administradores podrían recuperar los elementos eliminados permanentemente si el período de retención de elementos eliminados no ha expirado o si el buzón está en retención, en cuyo caso los elementos se conservan hasta que expira la duración de retención. Cuando se ejecuta una búsqueda de contenido, los elementos eliminados temporalmente y eliminados permanentemente de la carpeta elementos recuperables se devuelven en los resultados de la búsqueda si coinciden con la consulta de búsqueda. Para obtener más información sobre cómo ejecutar búsquedas de contenido, vea [búsqueda de contenido en Office 365](content-search.md).

> [!TIP]
> Para buscar los elementos de correo electrónico eliminados, busque la línea de asunto parcial o la que aparece en el campo **AffectedItems** en el registro de auditoría.

## <a name="determining-if-a-user-created-an-inbox-rule"></a>Determinar si un usuario creó una regla de bandeja de entrada

Cuando los usuarios crean una regla de bandeja de entrada para su buzón de Exchange Online, se guarda un registro de auditoría correspondiente en el registro de auditoría. Para obtener más información acerca de las reglas de la bandeja de entrada, consulte:

- [Usar reglas de la bandeja de entrada en Outlook en la web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Administrar mensajes de correo electrónico en Outlook mediante reglas](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Esta es la manera de configurar una consulta de búsqueda de registros de auditoría para este escenario:

**Actividades** -en **actividades de buzón de Exchange**, seleccione **nueva-InboxRule crear/modificar/habilitar/deshabilitar regla de bandeja de entrada**.

Fecha de **Inicio** y **fecha** de finalización: Seleccione un intervalo de fechas que sea aplicable a su investigación.

**Usuarios** : a menos que esté investigando un usuario específico, deje este campo en blanco. Esto le ayudará a identificar nuevas reglas de la bandeja de entrada configuradas por cualquier usuario.

**Archivo, carpeta o sitio** : Deje este campo en blanco.

Después de ejecutar la búsqueda, se muestran todos los registros de auditoría de esta actividad en los resultados de la búsqueda. Haga clic en un registro de auditoría para mostrar la página flotante de **detalles** y, a continuación, haga clic en **más información**. La información sobre la configuración de las reglas de la bandeja de entrada se muestra en el campo **parámetros** . La siguiente captura de pantalla y descripciones resalta la información sobre las reglas de la bandeja de entrada.

![Registro de auditoría para nueva regla de bandeja de entrada](media/NewInboxRuleRecord.png)

a. En el campo **objectId** , se muestra el nombre completo de la regla de bandeja de entrada. Este nombre incluye el alias del buzón de correo del usuario (por ejemplo, Sara) y el nombre de la regla de bandeja de entrada (por ejemplo, "mover mensajes desde el administrador").

b. En el campo **parámetros** , se muestra la condición de la regla de la bandeja de entrada. En este ejemplo, la condición se especifica mediante el parámetro *from* . El valor definido para el parámetro *from* indica que la regla de la bandeja de entrada actúa en el correo electrónico enviado por admin@alpinehouse.onmicrosoft.com. Para obtener una lista completa de los parámetros que se pueden usar para definir las condiciones de las reglas de la bandeja de entrada, consulte el artículo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) .

c. El parámetro *MoveToFolder* especifica la acción para la regla de bandeja de entrada; en este ejemplo, los mensajes recibidos desde admin@alpinehouse.onmicrosoft.com se mueven a la carpeta denominada *AdminSearch*. Consulte también el artículo [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) para obtener una lista completa de los parámetros que se pueden usar para definir la acción de una regla de bandeja de entrada.

d. El campo **userid** indica el usuario que creó la regla de bandeja de entrada especificada en el campo **objectId** . Este usuario también se muestra en la columna **usuario** de la página de resultados de búsqueda.
---
title: 'Buscar y eliminar mensajes de correo electrónico en su organización de Office 365: Ayuda de administración'
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Usar la búsqueda y purgar la característica en la seguridad de Office 365 &amp; centro de cumplimiento para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización.
ms.openlocfilehash: be83b2e3e765980ae401356b924c26c53386a2b3
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755261"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>Buscar y eliminar mensajes de correo electrónico en su organización de Office 365: Ayuda de administración

**En este artículo está dirigido a administradores. ¿Está intentando buscar elementos en su buzón de correo que desea eliminar? Vea [encontrar un mensaje o un elemento con la búsqueda instantánea](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
Puede usar la característica de búsqueda de contenido en Office 365 para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización. Esto puede ayudarle a buscar y quitar correo electrónico potencialmente dañino o alto riesgo, tales como:
  
- Mensajes que contienen archivos adjuntos peligrosos o virus
    
- Mensajes de suplantación de identidad
    
- Mensajes que contienen datos confidenciales
    
> [!CAUTION]
> Búsqueda y purgar es una característica eficaz que permite a cualquier usuario que se asigna los permisos necesarios para eliminar mensajes de correo electrónico de buzones de la organización. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Para crear y ejecutar una búsqueda de contenido, tiene que ser un miembro del grupo de roles de **exhibición de documentos electrónicos administrador** o tener asignado el rol de administración de **Búsqueda de cumplimiento** . Para eliminar los mensajes, debe ser miembro del grupo de roles de **Administración de la organización** o tener asignado el rol de administración de **Búsqueda y purgar** . Para obtener información sobre cómo agregar usuarios a un grupo de roles, consulte [dar acceso a los usuarios para el centro de cumplimiento de seguridad de Office 365 &](grant-access-to-the-security-and-compliance-center.md).
    
- Se debe usar seguridad & PowerShell de centro de cumplimiento para eliminar los mensajes. Vea el [paso 2](#step-2-connect-to-security-amp-compliance-center-powershell) para obtener instrucciones sobre cómo conectar.
    
- Se puede quitar a un máximo de 10 elementos por buzón de correo a la vez. Debido a que la capacidad de buscar y quitar mensajes está pensada para ser una herramienta de respuesta a incidentes, este límite ayuda a garantizar que los mensajes se quitan rápidamente los buzones de correo. Esta característica no está pensada para limpiar los buzones de usuario. Para eliminar más de 10 elementos, puede usar el comando **Search-Mailbox-DeleteContent** en Exchange Online PowerShell. Consulte [Buscar y eliminar mensajes - ayuda de administración](search-for-and-delete-messagesadmin-help.md).
    
- El número máximo de buzones de correo en una búsqueda de contenido que puede eliminar elementos en mediante una búsqueda y purgar la acción es de 50.000. Si la búsqueda de contenido (que se crea en el [paso 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) tiene más de 50.000 buzones de origen, se producirá un error en la acción de purgar (que se crea en el paso 3). Vea la sección [obtener más información](#more-information) para una sugerencia acerca de cómo realizar una búsqueda y purgar la operación en los buzones de correo más de 50.000. 
    
- El procedimiento descrito en este artículo sólo se puede usar para eliminar los elementos en carpetas públicas y buzones de Exchange Online. No se puede usar para eliminar el contenido de SharePoint o OneDrive para los sitios de negocio.
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Paso 1: Crear una búsqueda de contenido para buscar el mensaje que quiera eliminar

El primer paso es crear y ejecutar una búsqueda de contenido para buscar el mensaje que desea quitar de los buzones de correo en la organización. Puede crear la búsqueda mediante el uso de la seguridad &amp; centro de cumplimiento o mediante la ejecución de los cmdlets **New-ComplianceSearch** y **ComplianceSearch de inicio** . Los mensajes que coinciden con la consulta para esta búsqueda se eliminará mediante la ejecución de la **New-ComplianceSearchAction-purgar** command en el [paso 3](#step-3-delete-the-message). Para obtener información sobre cómo crear una búsqueda de contenido y configuración de las consultas de búsqueda, vea los temas siguientes: 
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Consultas de palabra clave para la búsqueda de contenido](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> Las ubicaciones de contenido que se buscan en la búsqueda de contenido que cree en este paso no pueden incluir SharePoint o OneDrive para los sitios de negocio. Puede incluir sólo los buzones de correo y las carpetas públicas en una búsqueda de contenido que se usará para los mensajes de correo electrónico. Si la búsqueda de contenido incluye sitios, recibirá un error en el paso 3 al ejecutar el cmdlet **New-ComplianceSearchAction** . 
  
### <a name="tips-for-finding-messages-to-remove"></a>Sugerencias para la búsqueda de mensajes para quitar

El objetivo de la consulta de búsqueda es limitar los resultados de la búsqueda para encontrar el mensaje (o mensajes) que quiere quitar. Aquí encontrará algunas sugerencias:
  
- Si conoce el texto exacto o frase utilizada en la línea de asunto del mensaje, utilice la propiedad **Subject** en la consulta de búsqueda. 
    
- Si conoce la fecha exacta (o el intervalo de fechas) del mensaje, incluya la propiedad **Received** en la consulta de búsqueda. 
    
- Si conoce quién envió el mensaje, incluya la propiedad **From** en la consulta de búsqueda. 
    
- Obtener una vista previa de los resultados de búsqueda para comprobar que la búsqueda devuelve sólo el mensaje (o mensajes) que desea eliminar.
    
- Use las estadísticas de estimación de búsqueda (que se muestra en el panel de detalles de la búsqueda en la seguridad &amp; centro de cumplimiento o mediante el cmdlet [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) ) para obtener un recuento del número total de resultados. 
    
Estos son dos ejemplos de consultas para buscar mensajes de correo electrónico sospechosos.
  
- Esta consulta devuelve los mensajes recibidos por los usuarios entre el 13 de abril de 2016 y el 14 de abril de 2016 que contengan las palabras "acción" y "necesario" en la línea de asunto.
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- Esta consulta devuelve los mensajes enviados por chatsuwloginsset12345@outlook.com que contienen la frase exacta "Actualice la información de la cuenta" en la línea de asunto.
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Paso 2: Conectarse a PowerShell de centro de cumplimiento de seguridad &

El siguiente paso es conectar a & PowerShell de centro de cumplimiento de seguridad para su organización. Para obtener instrucciones detalladas, consulte [Conectar a Office 365 seguridad &amp; PowerShell de centro de cumplimiento de normas](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Si su cuenta de Office 365 usa la autenticación multifactor (MFA) o federados de autenticación, no puede usar las instrucciones que aparecen en el tema sobre la conexión a & PowerShell de centro de cumplimiento de seguridad anterior. En su lugar, vea las instrucciones en el tema [conectarse a Office 365 seguridad & PowerShell de centro de cumplimiento de normas mediante la autenticación multifactor](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-3-delete-the-message"></a>Paso 3: Eliminar el mensaje

Una vez que haya creado y refinado una búsqueda de contenido para devolver el mensaje que desea quitar y están conectados a la seguridad &amp; PowerShell de centro de cumplimiento, el paso final consiste en ejecutar el cmdlet **New-ComplianceSearchAction** para eliminar el mensaje. Puede temporalmente o disco duro-eliminar el mensaje. Un mensaje eliminado temporalmente se mueve a la carpeta elementos recuperables de un usuario y se conserva hasta que expire el período de retención de elementos eliminados. Disco duro elimina los mensajes marcados para eliminación permanente del buzón de correo y se quitará permanentemente la próxima vez que se procesa el buzón de correo mediante el Asistente para carpeta administrada. Si está habilitada la recuperación de elemento único para el buzón de correo, se quitará permanentemente elementos eliminados disco duro después de que expire el período de retención de elementos eliminados. Si un buzón de correo se pondrá en espera, se conservarán los mensajes eliminados hasta que expire la duración de retención para el elemento o hasta que se elimina la suspensión desde el buzón de correo.
  
En el siguiente ejemplo, el comando se temporalmente-eliminar los resultados de búsqueda devueltos por una búsqueda de contenido denominado "Quitar mensaje de suplantación de identidad". 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Al disco duro eliminado los elementos devueltos por la búsqueda de contenido de "Quitar mensaje de suplantación de identidad", debe ejecutar este comando:

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Tenga en cuenta que cuando se ejecuta el comando anterior a los mensajes de eliminar por temporalmente o disco duro, la búsqueda especificada por el parámetro *SearchName* es la búsqueda de contenido que creó en el paso 1. 
  
Para obtener más información, vea [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).

## <a name="more-information"></a>Más información

- **¿Cómo obtener el estado de la búsqueda y la operación de eliminación?**

    Ejecute el **Get-ComplianceSearchAction** para obtener el estado de la operación de eliminación. Tenga en cuenta que el objeto que se crea cuando se ejecuta el cmdlet **New-ComplianceSearchAction** es el nombre con este formato: `<name of Content Search>_Purge`. 
    
- **¿Qué sucede después de eliminar un mensaje?**

   Un mensaje que se elimina con el `New-ComplianceSearchAction -Purge -PurgeType HardDelete` comando se mueve a la carpeta de purga y no puede tener acceso el usuario. Después de que el mensaje se mueve a la carpeta de purga, el mensaje se conserva durante el período de retención de elementos eliminados si está habilitada la recuperación de elemento único para el buzón de correo. (En Office 365, recuperación de elemento único está habilitado de forma predeterminada cuando se crea un nuevo buzón de correo.) Después de que expire el período de retención de elementos eliminados, el mensaje está marcado para su eliminación permanente y se purgarán desde Office 365 la próxima vez que se procesa el buzón de correo mediante el Asistente para carpeta administrada. 

   Si usa el `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` de comando, los mensajes se mueven a la carpeta de eliminaciones de la carpeta del usuario elementos recuperables. Se no se purgan inmediatamente de Office 365. El usuario puede recuperar los mensajes en la carpeta Elementos eliminados de la duración basándose en el período de retención de elementos eliminados configurado para el buzón de correo. Después de que finalice este período de retención (o si el usuario purga el mensaje antes de que caduque), el mensaje se mueve a la carpeta de purga y ya no se puede tener acceso el usuario. Una vez en la carpeta de purga, el mensaje se mantiene para la duración basándose en el período de retención de elementos eliminados configurado para el buzón de correo si está habilitada la recuperación de elementos únicos para el buzón de correo. (En Office 365, recuperación de elemento único está habilitado de forma predeterminada cuando se crea un nuevo buzón de correo.) Después de que expire el período de retención de elementos eliminados, el mensaje está marcado para su eliminación permanente y se purgarán desde Office 365 la próxima vez que se procesa el buzón de correo mediante el Asistente para carpeta administrada. 
    
- **¿Qué ocurre si se debe eliminar un mensaje de buzones de correo de más de 50.000?**

    Como se ha indicado anteriormente, puede realizar una búsqueda y purgar la operación en un máximo de 50.000 buzones. Si tiene que realizar una búsqueda y purgar la operación en los buzones de correo más de 50.000, considere la posibilidad de crear filtros de permisos de búsqueda temporal que reducen el número de buzones que podría buscar a menos de 50.000 buzones de correo. Por ejemplo, si su organización contiene los buzones de correo en distintos departamentos, regiones o países, puede crear un filtro de permisos de búsqueda de buzón de correo basado en una de esas propiedades del buzón de correo para buscar un subconjunto de los buzones de correo en la organización. Después de crear el filtro de permisos de búsqueda, debe crear la búsqueda (que se describe en el paso 1) y, a continuación, eliminar el mensaje (que se describe en el paso 3). A continuación, puede editar el filtro para buscar y purgar los mensajes en un conjunto diferente de los buzones de correo. Para obtener más información acerca de cómo crear filtros de búsqueda de permisos, vea [configurar los permisos de filtrado para la búsqueda de contenido](permissions-filtering-for-content-search.md).
    
- **¿Se eliminarán sin indizar elementos incluidos en los resultados de búsqueda?**

    No, el ' New-ComplianceSearchAction-comando Purgar no elimina elementos sin indizar. 
    
- **¿Qué sucede si se elimina un mensaje de un buzón de correo se ha colocado en suspensión en contexto o juicio o que esté asignada a una directiva de retención de Office 365?**

    Después de que el mensaje se purgarán y movido a la carpeta de purga, el mensaje se conserva hasta que expire la duración de la suspensión. Si la duración de retención es ilimitada, a continuación, se conservan los elementos hasta que se elimina la suspensión o se cambia la duración de la suspensión.
    
- **¿Por qué es la búsqueda y quitar flujo de trabajo que se divide entre los distintos grupos de roles de centro de cumplimiento de & de seguridad?**

    Como se explica anteriormente, una persona debe ser miembro del grupo de roles de administrador de exhibición de documentos electrónicos o tener asignado el rol de administración de búsqueda de cumplimiento para buscar los buzones de correo. Para eliminar los mensajes, una persona debe ser miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de búsqueda y purgar. Esto posibilita para controlar quién puede buscar los buzones de correo en la organización y quién puede eliminar los mensajes. 

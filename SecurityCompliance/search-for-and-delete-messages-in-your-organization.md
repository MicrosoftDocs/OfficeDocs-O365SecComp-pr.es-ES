---
title: Buscar y eliminar mensajes de correo electrónico de su organización de Office 365-ayuda para administradores
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Use la característica de búsqueda y depuración en el &amp; centro de seguridad y cumplimiento de Office 365 para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización.
ms.openlocfilehash: 15d67e42e4bdc63838f7ec1701d643391fa5c552
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296863"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>Buscar y eliminar mensajes de correo electrónico de su organización de Office 365-ayuda para administradores

**Este artículo está destinado a los administradores. ¿Está tratando de buscar elementos en el buzón que desea eliminar? Consulte [Buscar un mensaje o elemento con búsqueda instantánea](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
Puede usar la característica de búsqueda de contenido en Office 365 para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización. Esto puede ayudarle a encontrar y eliminar correos electrónicos potencialmente peligrosos o de alto riesgo, como:
  
- Mensajes que contienen virus o datos adjuntos peligrosos
    
- Mensajes de suplantación de identidad
    
- Mensajes que contienen datos confidenciales
    
> [!CAUTION]
> La búsqueda y depuración es una característica eficaz que permite que cualquier usuario que tenga asignados los permisos necesarios elimine mensajes de correo electrónico de los buzones de la organización. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Para crear y ejecutar una búsqueda de contenido, debe ser miembro del grupo de roles de **EDiscovery Manager** o tener asignado el rol de administración de **búsqueda de cumplimiento** . Para eliminar mensajes, debe ser miembro del grupo de roles de **Administración** de la organización o tener asignado el rol de administración de **búsqueda y** depuración. Para obtener información sobre cómo agregar usuarios a un grupo de roles, consulte [proporcionar a los usuarios acceso al centro de cumplimiento de & de seguridad de Office 365](grant-access-to-the-security-and-compliance-center.md).
    
- Debe usar el PowerShell del centro de cumplimiento de & de seguridad para eliminar los mensajes. Consulte el [paso 2](#step-2-connect-to-security-amp-compliance-center-powershell) para obtener instrucciones sobre cómo conectarse.
    
- Se puede quitar un máximo de 10 elementos por buzón de correo al mismo tiempo. Como la capacidad para buscar y quitar mensajes está pensada como una herramienta de respuesta a incidentes, este límite ayuda a garantizar que los mensajes se eliminan rápidamente de los buzones. Esta característica no está pensada para limpiar los buzones de los usuarios. Para eliminar más de 10 elementos, puede usar el comando **Search-Mailbox-DeleteContent** en Exchange Online PowerShell. Consulte [Buscar y eliminar mensajes: ayuda para administradores](search-for-and-delete-messagesadmin-help.md).
    
- El número máximo de buzones en una búsqueda de contenido que puede eliminar elementos en mediante una acción de búsqueda y purga es de 50.000. Si la búsqueda de contenido (que creó en el [paso 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) tiene más de 50.000 buzones de origen, se producirá un error en la acción de purga (que haya creado en el paso 3). Consulte la sección [More Information](#more-information) para ver una sugerencia sobre cómo realizar una operación de búsqueda y depuración en más de 50.000 buzones de correo. 
    
- El procedimiento descrito en este artículo solo puede usarse para eliminar elementos de buzones de correo de Exchange Online y carpetas públicas. No se puede usar para eliminar contenido de sitios de SharePoint o de OneDrive para la empresa.
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Paso 1: Crear una búsqueda de contenido para buscar el mensaje que quiera eliminar

El primer paso consiste en crear y ejecutar una búsqueda de contenido para buscar el mensaje que desea quitar de los buzones de la organización. Puede crear la búsqueda mediante el centro de seguridad &amp; y cumplimiento o mediante la ejecución de los cmdlets **New-compliancesearch** y **Start-ComplianceSearch** . Los mensajes que coinciden con la consulta para esta búsqueda se eliminarán mediante la ejecución del comando **New-ComplianceSearchAction-Purge** en el [paso 3](#step-3-delete-the-message). Para obtener información acerca de la creación de una búsqueda de contenido y la configuración de consultas de búsqueda, vea los siguientes temas: 
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Consultas de palabras clave para la búsqueda de contenido](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> Las ubicaciones de contenido que se buscan en la búsqueda de contenido que crea en este paso no pueden incluir sitios de SharePoint o de OneDrive para la empresa. Solo puede incluir buzones y carpetas públicas en una búsqueda de contenido que se usará para enviar mensajes de correo electrónico. Si la búsqueda de contenido incluye sitios, recibirá un error en el paso 3 cuando ejecute el cmdlet **New-ComplianceSearchAction** . 
  
### <a name="tips-for-finding-messages-to-remove"></a>Sugerencias para buscar mensajes para quitarlos

El objetivo de la consulta de búsqueda es limitar los resultados de la búsqueda para encontrar el mensaje (o mensajes) que quiere quitar. Aquí encontrará algunas sugerencias:
  
- Si conoce el texto o la frase exacta usados en la línea de asunto del mensaje, use la **** propiedad Subject en la consulta de búsqueda. 
    
- Si conoce la fecha exacta (o el intervalo de fechas) del mensaje, incluya la propiedad **Received** en la consulta de búsqueda. 
    
- Si conoce quién envió el mensaje, incluya la propiedad **From** en la consulta de búsqueda. 
    
- Obtenga una vista previa de los resultados de la búsqueda para comprobar que la búsqueda devolvió solo el mensaje (o los mensajes) que desea eliminar.
    
- Use las estadísticas de estimación de búsqueda (que se muestran en el panel de detalles de &amp; la búsqueda en el centro de seguridad y cumplimiento o mediante el cmdlet [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) ) para obtener un recuento del número total de resultados. 
    
Estos son dos ejemplos de consultas para buscar mensajes de correo electrónico sospechosos.
  
- Esta consulta devuelve los mensajes recibidos por los usuarios entre el 13 de abril de 2016 y el 14 de abril de 2016 que contengan las palabras "acción" y "necesario" en la línea de asunto.
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- Esta consulta devuelve los mensajes enviados por chatsuwloginsset12345@outlook.com que contienen la frase exacta "Actualice la información de la cuenta" en la línea de asunto.
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Paso 2: conectarse al centro de seguridad & de cumplimiento de PowerShell

El paso siguiente es conectarse a PowerShell del centro de cumplimiento de seguridad & para su organización. Para obtener instrucciones paso a paso, consulte [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Si su cuenta de Office 365 usa la autenticación multifactor (MFA) o la autenticación federada, no puede usar las instrucciones descritas en el tema anterior sobre cómo conectarse al centro de seguridad & Compliance Center PowerShell. En su lugar, vea las instrucciones del tema [Connect to Office 365 Security _AMP_ Compliance Center PowerShell Using multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-3-delete-the-message"></a>Paso 3: eliminar el mensaje

Una vez que haya creado y perfeccionado una búsqueda de contenido para que se devuelva el mensaje que desea quitar y &amp; esté conectado a PowerShell del centro de cumplimiento de seguridad, el paso final consiste en ejecutar el cmdlet **New-ComplianceSearchAction** para eliminar el mensaje. Puede eliminar el mensaje de forma Soft o difícil. Un mensaje eliminado temporalmente se mueve a la carpeta elementos recuperables de un usuario y se conserva hasta que expira el período de retención de elementos eliminados. Los mensajes eliminados permanentemente se marcan para su eliminación permanente del buzón y se quitarán de forma permanente la próxima vez que el Asistente para carpetas administradas procese el buzón de correo. Si la recuperación de un único elemento está habilitada para el buzón, los elementos eliminados de forma permanente se quitarán permanentemente cuando expire el período de retención de elementos eliminados. Si un buzón se coloca en retención, los mensajes eliminados se conservan hasta que expira la duración de retención del elemento o hasta que se quite la retención del buzón.
  
En el siguiente ejemplo, el comando eliminará temporalmente los resultados de la búsqueda devueltos por una búsqueda de contenido denominada "quitar mensaje de suPlantación de identidad (phishing)". 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Para eliminar de forma permanente los elementos devueltos por la búsqueda de contenido "quitar mensaje de suPlantación de identidad", ejecute este comando:

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Tenga en cuenta que cuando ejecuta el comando anterior en mensajes de eliminación parcial o de eliminación, la búsqueda especificada por el parámetro *SearchName* es la búsqueda de contenido que creó en el paso 1. 
  
Para obtener más información, vea [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).

## <a name="more-information"></a>Más información

- **¿Cómo se obtiene el estado de la operación de búsqueda y eliminación?**

    Ejecute **Get-ComplianceSearchAction** para obtener el estado de la operación de eliminación. Tenga en cuenta que el objeto que se crea al ejecutar el cmdlet **New-ComplianceSearchAction** se denomina con este formato `<name of Content Search>_Purge`:. 
    
- **¿Qué ocurre después de eliminar un mensaje?**

   Un mensaje que se elimina con el `New-ComplianceSearchAction -Purge -PurgeType HardDelete` comando se mueve a la carpeta purgas y el usuario no puede obtener acceso a él. Una vez que el mensaje se ha movido a la carpeta purga, el mensaje se conserva durante el período de retención de elementos eliminados si está habilitada la recuperación de un único elemento para el buzón. (En Office 365, la recuperación de un único elemento está habilitada de forma predeterminada cuando se crea un nuevo buzón). Una vez que expire el período de retención de elementos eliminados, el mensaje se marca para su eliminación permanente y se eliminará de Office 365 la próxima vez que el Asistente para carpetas administradas procese el buzón de correo. 

   Si usa el `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` comando, los mensajes se mueven a la carpeta eliminaciones de la carpeta elementos recuperables del usuario. No se ha purgado inmediatamente de Office 365. El usuario puede recuperar mensajes de la carpeta elementos eliminados durante el período de retención de elementos eliminados configurado para el buzón. Una vez que expire el período de retención (o si el usuario purga el mensaje antes de que expire), el mensaje se mueve a la carpeta purgas y el usuario ya no puede obtener acceso a él. Una vez en la carpeta purga, el mensaje se conserva durante el tiempo basado en el período de retención del elemento eliminado configurado para el buzón si la recuperación de elementos individuales está habilitada para el buzón. (En Office 365, la recuperación de un único elemento está habilitada de forma predeterminada cuando se crea un nuevo buzón). Una vez que expire el período de retención de elementos eliminados, el mensaje se marca para su eliminación permanente y se eliminará de Office 365 la próxima vez que el Asistente para carpetas administradas procese el buzón de correo. 
    
- **¿Qué ocurre si tiene que eliminar un mensaje de más de 50.000 buzones de correo?**

    Como se mencionó anteriormente, puede realizar una operación de búsqueda y depuración en un máximo de 50.000 buzones. Si tiene que realizar una operación de búsqueda y depuración en más de 50.000 buzones de correo, considere la posibilidad de crear filtros de permisos de búsqueda temporales que reduzcan el número de buzones que se buscarían a menos de 50.000 buzones. Por ejemplo, si su organización contiene buzones de correo en distintos departamentos, países o países, puede crear un filtro de permisos de búsqueda de buzones de correo basados en una de esas propiedades de buzón para buscar en un subconjunto de buzones de la organización. Después de crear el filtro de permisos de búsqueda, debe crear la búsqueda (que se describe en el paso 1) y, a continuación, eliminar el mensaje (descrito en el paso 3). A continuación, puede editar el filtro para buscar y purgar los mensajes en un conjunto de buzones diferente. Para obtener más información acerca de la creación de filtros de permisos de búsqueda, consulte [configurar el filtrado de permisos para búsqueda de contenido](permissions-filtering-for-content-search.md).
    
- **¿Se eliminarán los elementos sin indexar incluidos en los resultados de la búsqueda?**

    No, el comando "New-ComplianceSearchAction-Purge" no elimina los elementos sin indexar. 
    
- **¿Qué sucede si se elimina un mensaje de un buzón que se ha colocado en conservación local o retención por juicio o está asignado a una directiva de retención de Office 365?**

    Una vez que el mensaje se purga y se mueve a la carpeta de purgas, el mensaje se conserva hasta que expira la duración de retención. Si la duración de retención es ilimitada, los elementos se conservan hasta que la retención se quita o se cambia la duración de retención.
    
- **¿Por qué el flujo de trabajo de búsqueda y eliminación se divide entre los distintos grupos de roles del centro de seguridad & cumplimiento?**

    Como se ha explicado anteriormente, una persona tiene que ser miembro del grupo de roles eDiscovery Manager o tener asignada la función de administración de búsqueda de cumplimiento para buscar en buzones. Para eliminar mensajes, una persona debe ser miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de búsqueda y dePuración. Esto hace posible controlar quién puede buscar buzones de correo en la organización y quién puede eliminar mensajes. 

---
title: Administrar suspensiones en la exhibición avanzada de documentos electrónicos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e8ec5114983d64e7d717d4b7ab866bfee9d8d488
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154902"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Administrar suspensiones en la exhibición avanzada de documentos electrónicos

Puede usar un caso de exhibición avanzada de documentos electrónicos para crear suspensiones y conservar el contenido que pueda ser relevante para su caso. Con las funciones avanzadas de conservación de la exhibición de documentos electrónicos, puede realizar suspensiones en custodios y sus orígenes de datos. Además, puede poner una retención no confidencial en los buzones y en los sitios de OneDrive para la empresa. También puede poner una retención en el buzón de grupo, el sitio de SharePoint y el sitio de OneDrive para la empresa para un grupo de Office 365. De forma similar, puede poner una retención en el buzón de correo y el sitio asociados a Microsoft Teams. Cuando se colocan ubicaciones de contenido en retención, el contenido se conserva hasta que se libera el custodio, se quita una ubicación de datos específica o se elimina la Directiva de retención por completo.

## <a name="manage-custodian-based-holds"></a>Administración de retenciones basadas en custodios

En algunos casos, puede tener un conjunto de custodios de datos que haya identificado y elegido para preservar. En la exhibición avanzada de documentos electrónicos, cuando estos custodios se colocan en suspensión, el usuario y sus orígenes de datos seleccionados se agregan automáticamente a una directiva de retención de custodio. 

Para ver la Directiva de retención de custodios:

1. En el **centro de seguridad _AMP_ cumplimiento**, haga clic en exhibición de documentos electrónicos **> Advanced eDiscovery** para mostrar la lista de casos de su organización.
   
2. Vaya a la **** pestaña custodios para agregar custodios en su caso. Para obtener información sobre cómo agregar y poner custodios en espera en un caso de exhibición avanzada de documentos electrónicos, vea [Agregar custodios a un caso de exhibición avanzada](add-custodians-to-case.md)de documentos electrónicos. Si ya ha agregado custodios y los ha colocado en espera, vaya al paso 3.
   
3. Vaya a la **** pestaña suspensiones y seleccione la "Directiva de custodios".
   
4. En la página de control flotante, puede ver las estadísticas de retención para la Directiva. También puede realizar acciones como aplicar una consulta a la retención basada en custodios. Para obtener más información acerca de la creación de una consulta de retención y el uso de condiciones, consulte [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md).
 
## <a name="manage-non-custodial-holds"></a>Administrar suspensiones que no son de privación

Al crear una suspensión, tiene las siguientes opciones para limitar el contenido que se almacena en las ubicaciones de contenido especificadas:

  - Se crea una retención infinita en la que todo el contenido se coloca en retención. Como alternativa, puede crear una retención basada en consultas en la que solo se coloca en retención el contenido que coincide con una consulta de búsqueda.
  - Puede especificar un intervalo de fechas para contener solo el contenido enviado, recibido o creado dentro del intervalo de fechas. Como alternativa, puede retener todo el contenido independientemente de Cuándo se haya enviado, recibido o creado.

Para crear una suspensión para un caso de exhibición avanzada de documentos electrónicos:

1. En el **centro de seguridad _AMP_ cumplimiento**, haga clic en exhibición de documentos electrónicos **> Advanced eDiscovery** para mostrar la lista de casos de su organización.
  
2. Haga clic en **abrir** junto al caso en el que desea crear las suspensiones.
  
3. En la Página principal del caso, haga clic en **** la pestaña suspensiones.
  
4. En la **** pestaña suspensiones, haga clic en **crear**.
  
5. En la página nombre de la **retención** , asigne un nombre a la retención. El nombre de la suspensión debe ser exclusivo en la organización.
 
6. Opcional En el cuadro **Descripción** , agregue una descripción de la suspensión.
  
7. Haga clic en **Siguiente**.
  
8. Elija las ubicaciones de contenido que desea poner en retención. Puede poner buzones de correo, sitios y carpetas públicas en retención.

   a. **Correo electrónico de Exchange** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o Teams** de nuevo para especificar los buzones que se deben poner en retención. Use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución (para poner una retención en los buzones de los miembros del grupo) para ponerlos en retención. También puede poner una retención en el buzón asociado para un grupo de Office 365 o un equipo de Microsoft. Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.
 
    > [!NOTE]
    > Al hacer clic en **elegir usuarios, grupos o equipos** para especificar los buzones que se deben poner en espera, el selector de buzón mostrado está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.

    b. **Sitios de SharePoint** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para especificar que los sitios de SharePoint y OneDrive para la empresa se retienen en suspensión. Escriba la dirección URL de cada sitio que quiere suspender. También puede Agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un equipo de Microsoft. Haga clic en **elegir**y, a continuación, en **listo**.
    
     Consulte la sección **preguntas más frecuentes** para obtener sugerencias sobre cómo poner en espera grupos de Office 365 y Microsoft Teams.

    > [!NOTE]
    > En el caso poco probable de que haya cambiado el nombre principal de usuario (UPN) de una persona, la dirección URL de su cuenta de OneDrive también se cambiará para incorporar el nuevo UPN. Si esto ocurre, tendrá que modificar la retención agregando la nueva dirección URL de OneDrive del usuario y quitando la antigua.

     c. **Carpetas públicas de Exchange** : mueva el conmutador de alternancia a la posición todas para poner todas las carpetas públicas de la organización de Exchange online en retención. Tenga en cuenta que no puede elegir carpetas públicas específicas que poner en retención. Deje el modificador de alternancia establecido en **ninguno** si no desea mantener una retención en las carpetas públicas.

9. Cuando haya acabado de agregar ubicaciones de contenido a la suspensión, haga clic en **siguiente**.
  
10. Para crear una retención basada en consultas con condiciones, realice lo siguiente. De lo contrario, haga clic en **siguiente**.
    
    - En el cuadro debajo de **palabras clave**, escriba una consulta de búsqueda en el cuadro para que solo se coloque en retención el contenido que cumpla los criterios de búsqueda. Puede especificar palabras clave, propiedades de mensaje o propiedades de documento, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como AND, OR o NOT. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se colocará en retención.

    - Haga clic en **Agregar** condiciones para agregar una o más condiciones para restringir la consulta de búsqueda para la retención. Cada condición agrega una cláusula a la consulta de búsqueda de KQL que se crea y se ejecuta cuando se crea la suspensión. Por ejemplo, puede especificar un intervalo de fechas para que los documentos de correo electrónico o de sitio creados en el intervalo de fechas se coloquen en suspensión. Una condición se conecta lógicamente a la consulta de palabra clave (especificada en el cuadro de palabra clave) mediante el operador AND. Esto significa que los elementos deben cumplir con la consulta de palabras clave y la condición que se va a poner en retención.

     Para obtener más información acerca de la creación de una consulta de búsqueda y el uso de condiciones, consulte [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions).

12. Después de configurar una retención basada en consultas, haga clic en **siguiente**.
 
13. Revise la configuración y, a continuación, haga clic en **crear esta suspensión**.


## <a name="view-hold-statistics"></a>Ver estadísticas de retención

Después de algún tiempo, se muestra información sobre la nueva suspensión en el panel de detalles **** de la ficha suspensiones para la suspensión seleccionada. Esta información incluye el número de buzones de correo y sitios en espera y estadísticas sobre el contenido que se ha puesto en suspensión, como el número total y el tamaño de los elementos que se encuentran en suspensión y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención ayudan a identificar cuánto contenido está relacionado con el caso de exhibición de documentos electrónicos.

Tenga en cuenta lo siguiente en cuanto a la retención de estadísticas:

- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que se encuentran en retención. Si ha creado una suspensión basada en consulta, esta estadística indica el número de elementos que coinciden con la consulta.
  
- El número de elementos en espera también incluye los elementos sin indexar encontrados en las ubicaciones de contenido. Tenga en cuenta que si crea una suspensión basada en consulta, todos los elementos sin indexar en las ubicaciones de contenido se colocan en retención. Esto incluye los elementos sin indexar que no coinciden con los criterios de búsqueda de una retención basada en consultas y los elementos sin indexar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente a lo que sucede cuando se ejecuta una búsqueda de contenido, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o se excluyen por una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos sin indexar, vea [elementos parcialmente indizados en la búsqueda de contenido en Office 365](../partially-indexed-items-in-content-search.md). 

- Puede obtener las estadísticas de retención más recientes haciendo clic en actualizar estadísticas para volver a ejecutar una estimación de búsqueda que calcula el número actual de elementos en espera.

- Si es necesario, haga clic en actualizar en la barra de herramientas para actualizar las estadísticas de retención en el panel de detalles.

- Es normal que el número de elementos que se retengan se incremente con el transcurso del tiempo porque los usuarios cuyo buzón o sitio está en espera suelen enviar o recibir nuevos mensajes de correo electrónico y crear nuevos documentos de SharePoint y OneDrive para la empresa.

- Si un sitio de SharePoint o una cuenta de OneDrive se mueven a otra región en un entorno multigeográfico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Sin embargo, el contenido del sitio seguirá en espera. Además, si un sitio se mueve a otra región, la dirección URL que se muestra en la retención no se actualizará. Tendrá que editar la retención y actualizar la dirección URL.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

- **¿Cómo puedo asignar un sitio de Microsoft Teams o grupos de Office 365 adicional a un custodio? ¿Y qué ocurre si realiza una retenciones que no son de apoyo en grupos de Office 365 y en Microsoft Teams?** Microsoft Teams se basa en grupos de Office 365. Por lo tanto, colocarlos en espera en un caso de exhibición de documentos electrónicos es muy similar. Tenga en cuenta lo siguiente cuando coloque los grupos de Office 365 y Microsoft Teams en espera.
  - Para colocar contenido ubicado en Office 365 grupos y Microsoft Teams en espera, tiene que especificar el buzón de correo y el sitio de SharePoint que están asociados con un grupo o un equipo.
  
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un grupo de Office 365 o un equipo de Microsoft. Esta es una buena forma de obtener la dirección URL del sitio que está asociada con un grupo de Office 365 o un equipo de Microsoft. Por ejemplo, el siguiente comando muestra las propiedades seleccionadas de un grupo de Office 365 llamado equipo de liderazgo Senior:


    ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet Get-UnifiedGroup, debe tener asignado el rol destinatarios con permiso de vista en Exchange online o ser miembro de un grupo de roles que tenga asignado el rol destinatarios con permiso de vista.

 - Cuando se realiza una búsqueda en el buzón de un usuario, no se buscará ningún grupo de Office 365 o equipo de Microsoft del que el usuario sea miembro. De forma similar, cuando se coloca un grupo de Office 365 o una retención en Microsoft Team, solo el buzón de grupo y el sitio de grupo se colocan en retención; los buzones y los sitios de OneDrive para la empresa de los miembros del grupo no se mantienen en suspensión a menos que los agregue explícitamente como custodios o coloque sus orígenes de datos en espera. Por lo tanto, si necesita poner un grupo de Office 365 o un equipo de Microsoft en espera para un custodio específico, considere la posibilidad de asignar el sitio de grupo y el buzón de grupo al custodio (consulte Managing custodios in Advanced eDiscovery). Si el grupo de Office 365 o el equipo de Microsoft no son atribuibles a un custodio único, considere la posibilidad de agregar el origen a una retención que no sea Private. 
 
 - Para obtener una lista de los miembros de un grupo de Office 365 o de Microsoft Team, puede ver las propiedades de la página Home > Groups en el centro de administración de Office 365. Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell:

   ``` 
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** , debe tener asignado el rol destinatarios con permiso de vista en Exchange online o ser miembro de un grupo de roles que tenga asignado el rol destinatarios con permiso de vista.

- Las conversaciones de canal que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo que está asociado al equipo. De forma similar, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, tiene que poner el buzón de Microsoft Team y el sitio de SharePoint en espera para conservar conversaciones y archivos en un canal.
  
- Como alternativa, las conversaciones que forman parte de la lista de chats en Microsoft Teams se almacenan en el buzón de correo del usuario que participa en el chat.  Los archivos que un usuario comparte en conversaciones de chat se almacenan en el sitio de OneDrive para la empresa del usuario que comparte el archivo. Por lo tanto, tiene que poner los buzones de usuario individuales y los sitios de OneDrive para la empresa en espera para conservar conversaciones y archivos de la lista de chats. 
  
- Todos los canales de equipo o equipo de Microsoft contienen un wiki para la toma de notas y la colaboración. El contenido de la wiki se guarda automáticamente en un archivo con formato. mht. Este archivo se almacena en la biblioteca de documentos de datos wiki de Microsoft Teams en el sitio de SharePoint del equipo. Puede colocar el contenido en el sitio Wiki en espera colocando el sitio de SharePoint del equipo en retención.

  > [!NOTE]
  > La capacidad de retener contenido de wiki para un canal de equipo o equipo de Microsoft (cuando se ubica el sitio de SharePoint del equipo en espera) se presentó el 22 de junio de 2017. Si un sitio de grupo está en suspensión, el contenido de la wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en suspensión y el contenido de la wiki se eliminó antes del 22 de junio de 2017, no se conservó el contenido de la wiki.

---
title: Administrar suspensiones de exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 75ddbcfb401d285dfb7a4b610e3f0709e21946f2
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608370"
---
# <a name="rename-this-page-and-md-file-to-managing-holds"></a>Cambiar el nombre de esta página y el archivo MD a "Administrar suspensiones"

# <a name="holds-in-advanced-ediscovery-preview"></a>Suspensiones en la exhibición de documentos electrónicos avanzada (vista previa)
Puede usar un caso de exhibición de documentos electrónicos avanzada (vista previa) para crear suspensiones para conservar el contenido que puede ser relevante para su caso. Uso de la exhibición de documentos electrónicos avanzada (vista previa) mantenga las funciones, puede colocar las suspensiones en custodia y sus orígenes de datos. Además, puede colocar una suspensión que no sean custodia en los buzones de correo y OneDrive para sitios de negocio. También puede colocar una suspensión en el buzón de correo de grupo, sitios de SharePoint y OneDrive para el sitio de negocio para un grupo de Office 365. De forma similar, puede colocar una suspensión en el sitio que están asociados con Microsoft Teams y buzón de correo. Al colocar las ubicaciones de contenido en espera, contenido se mantiene hasta que suelte a la custodia, eliminar una ubicación de datos específicos o eliminar la directiva de retención por completo.

## <a name="manage-custodian-based-holds"></a>Administrar custodia en función de las suspensiones

En algunos casos, puede que tenga un conjunto de custodia de datos que se ha identificado y elegido conservar. En Avanzadas exhibición de documentos electrónicos (vista previa), cuando estos custodia se coloca en thold, el usuario y sus datos seleccionados orígenes se agregan automáticamente a custodia mantienen directiva. 

Para ver la directiva de retención de custodia:

1. En el **& centro de cumplimiento de seguridad**, haga clic en la **exhibición de documentos electrónicos > avanzada exhibición de documentos electrónicos (vista previa)** para mostrar la lista de los casos de la organización.
   
2. Navegue a la ficha de **custodia** para agregar a custodia dentro de su caso. Para obtener información sobre cómo puede agregar y custodia de lugar en suspensión dentro de un caso de exhibición de documentos electrónicos avanzada (vista previa), visite la sección **Administración de custodia dentro de un caso** . Si ya ha agregado a custodia y colocarlos en espera, desplazarse al paso 3.
   
3. Vaya a la ficha **contiene** y seleccione la directiva de custodia de' '.
   
4. En la barra flotante de detalles, puede ver las estadísticas de la directiva de retención. También se pueden realizar acciones como aplicar una consulta para la retención basada en custodia. Para obtener más información acerca de la creación de una consulta de suspensión y condiciones de uso, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions )
 
## <a name="manage-non-custodial-holds"></a>Administrar suspensiones no custodia
Cuando se crea una suspensión, tiene las siguientes opciones para delimitar el contenido que se encuentra en las ubicaciones de contenido especificadas:
  - Crear una suspensión infinita donde todo el contenido se pondrá en espera. Como alternativa, puede crear una suspensión basada en consultas donde sólo el contenido que coincide con una consulta de búsqueda se pondrá en espera.
  - Puede especificar un intervalo de fechas para retener sólo el contenido que se ha enviado, recibido o crear dentro de ese intervalo de fechas. Como alternativa, puede contener todo el contenido, independientemente de cuando se ha enviado, recibido o creado.

Para crear una suspensión para un caso de exhibición de documentos electrónicos:
  1. En el **& centro de cumplimiento de seguridad**, haga clic en la **exhibición de documentos electrónicos > avanzada exhibición de documentos electrónicos (vista previa)** para mostrar la lista de los casos de la organización.
  
  2. Junto al caso de que desee crear las suspensiones en, haga clic en Abrir.
  
  3. En la ficha**Inicio** para el caso, haga clic en la ficha **contiene** .
  
  4. En la ficha **contiene** , haga clic en **crear**.
  
  5. En el nombre de la página de la suspensión, asigne la suspensión un nombre. El nombre de la suspensión debe ser único en la organización.
 
  6. (Opcional) En el cuadro Descripción, agregue una descripción de la suspensión.
  
  7. Haga clic en **Siguiente**.
  
  8. Elija las ubicaciones de contenido que desee poner en espera. Puede colocar los buzones de correo, sitios y las carpetas públicas en espera. r. **correo electrónico de Exchange** - haga clic en **Elegir usuarios, grupos o equipos** y, a continuación, haga clic en **Elegir usuarios, grupos o equipos de** nuevo. para especificar los buzones de correo para poner en espera. Use el cuadro de búsqueda para encontrar buzones de usuario y grupos de distribución (para colocar una suspensión en los buzones de correo de los miembros del grupo) a poner en espera. También puede colocar una suspensión en el buzón de correo asociado para un grupo de Office 365 o un Microsoft Team. Seleccione el usuario, el grupo, la casilla de verificación de equipo, haga clic en **Elegir**y, a continuación, haga clic en **Listo**.
 
    [!NOTE]
    Al hacer clic en **Elegir usuarios, grupos o equipos** para especificar los buzones de correo para poner en espera, el selector de buzón de correo que se muestra está vacío. Este comportamiento está diseñado para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.


    b. **Sitios de SharePoint** : haga clic en **Elegir sitios** y, a continuación, haga clic en **sitios de elija** nuevo para especificar SharePoint y OneDrive para sitios profesionales para poner en espera. Escriba la dirección URL para cada sitio que desee poner en espera. También puede agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un Microsoft Team. Haga clic en **Elegir**y, a continuación, haga clic en **Listo**.
    
     Vea la sección de **preguntas más frecuentes** para obtener sugerencias sobre la colocación de grupos de Office 365 y Microsoft Teams en espera.

    [!NOTE]
    En el caso excepcional de que ha cambiado el nombre de entidad de seguridad de usuario (UPN) de una persona, también se cambiará la dirección URL de su cuenta de OneDrive para incorporar el UPN nuevo. En este caso, tendrá que modificar la suspensión mediante la adición OneDrive para la nueva dirección URL del usuario y eliminar la antigua.

     c. **carpetas públicas de Exchange** : mueva el conmutador de alternancia a la posición de todos los para colocar todas las carpetas públicas en Exchange Online organización en retención. Tenga en cuenta que no se puede elegir carpetas públicas específicas para poner espera. Deje el conmutador de alternancia establecido en **Ninguno** si no desea colocar una suspensión en las carpetas públicas.

  9. Cuando haya terminado de agregar ubicaciones de contenido a la suspensión, haga clic en **siguiente**.
  
  10. Para crear una suspensión basada en consultas con las condiciones, complete lo siguiente. De lo contrario, simplemente haga clic en **siguiente**. 1.1 en el cuadro palabras clave, tipo de una consulta de búsqueda en el cuadro de modo que sólo el contenido que cumpla los criterios de búsqueda se coloca en suspensión. Puede especificar las palabras clave, propiedades del mensaje o propiedades de documento, como los nombres de archivo. También puede utilizar las consultas más complejas que usan un operador booleano, como AND y OR, o no. Si deja el cuadro de palabra clave vacía, a continuación, todo el contenido que se encuentra en las ubicaciones de contenido especificadas se pondrá en espera.

    1.2, haga clic en **Agregar** condiciones para agregar una o varias condiciones para restringir la consulta de búsqueda para la suspensión. Cada condición agrega una cláusula a la consulta de búsqueda de palabras clave que se crean y ejecutan cuando se crea la suspensión. Por ejemplo, se puede especificar un intervalo de fechas para que los documentos de correo electrónico o un sitio que se crearon en la fecha que se iban se colocan en espera. Una condición lógicamente está conectada a la consulta de palabras clave (especificada en el cuadro de palabra clave) por el operador AND. Que significa que los elementos tienen para satisfacer la consulta de palabra clave y la condición que se va a colocar en suspensión.

     Para obtener más información sobre cómo crear una consulta de búsqueda y las condiciones de uso, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions).

  11. Después de configurar basada en una consulta de suspensión, haga clic en **siguiente**.
 
  12. Revise la configuración y, a continuación, haga clic en **crear esta suspensión**.


## <a name="view-hold-statistics"></a>Ver las estadísticas de espera
Después de algún tiempo, se muestra información acerca de la suspensión nuevo en el panel de detalles en la ficha **contiene** para la suspensión seleccionada. Esta información incluye el número de buzones de correo y sitios en mantenga y estadísticas sobre el contenido que se realizó en, como el número total y el tamaño de los elementos que se pondrá en espera y la última vez que la suspensión se calculaban estadísticas. Estos mantenga estadísticas le ayudarán a que identificar la cantidad de contenido que está relacionada con el caso de exhibición de documentos electrónicos se encuentra.

Tenga en cuenta acerca de las estadísticas de espera lo siguiente:

  - El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que se colocan en espera. Si ha creado una consulta retención basada en, esta estadística indica el número de elementos que coinciden con la consulta.
  - El número de elementos en espera también incluye sin indizar los elementos que se encuentran en las ubicaciones de contenido. Tenga en cuenta que si crea una suspensión basada en consultas, todos los elementos no indizados en las ubicaciones de contenido se colocan en espera. Esto incluye elementos sin indizar que no coincidan con los criterios de búsqueda de una suspensión basada en consultas y no indizados que es posible que quedan fuera de una condición de intervalo de fecha. Esto es diferente de lo que sucede cuando se ejecuta una búsqueda de contenido, en la que sin indizar los elementos que no coinciden con la consulta de búsqueda o se excluyen por una condición de intervalo de fecha no se incluyen en los resultados de búsqueda. Para obtener más información acerca de los elementos sin indizar, consulte [elementos indizados parcialmente en búsqueda de contenido en Office 365] (https://docs.microsoft.com/en-us/office365/SecurityCompliance/partially-indexed-items-in-content-search). 
  - Puede obtener las estadísticas de espera más recientes haciendo clic en Actualizar estadísticas para volver a ejecutar una estimación de búsqueda que se calcula el número actual de elementos en suspensión.
  - Si es necesario, haga clic en actualizar en la barra de herramientas para actualizar las estadísticas de espera en el panel de detalles.
  - Es normal para el número de elementos en suspensión a aumentar con el tiempo debido a que los usuarios cuyos buzones de correo o el sitio se encuentra en suspensión normalmente se enviar o recibir nuevo mensaje de correo electrónico y creación de SharePoint nueva y OneDrive para documentos empresariales.

[!NOTE]
Si se mueve una cuenta de OneDrive o un sitio de SharePoint a una región diferente en un entorno de multi-ubican, las estadísticas de ese sitio no se incluirán en las estadísticas de espera. Sin embargo, el contenido del sitio aún estará en espera. Además, si un sitio se mueve a una región diferente no se actualizarán a la dirección URL que se muestra en la suspensión. Debe editar la suspensión y actualice la dirección URL.

## <a name="faq"></a>Preguntas más frecuentes
- ¿ **Cómo asignar un sitio de Office 365 grupos o Microsoft Teams adicional a custodia? Y ¿qué hay de comercialización que no sean custodia retención en grupos de Office 365 y Microsoft Teams?** Microsoft Teams se basan en grupos de Office 365. Por lo tanto, es muy similar colocándolas en espera en un caso de exhibición de documentos electrónicos. Tenga en cuenta lo siguiente al colocar grupos de Office 365 y Microsoft Teams en espera.
  - Para colocar el contenido que se encuentra en los grupos de Office 365 y Microsoft Teams en espera, es necesario que especifique el buzón de correo y del sitio de SharePoint que asociado con un grupo o un equipo.
  
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un grupo de Office 365 o Microsoft Team. Esto es una buena forma de obtener la dirección URL para el sitio que está asociado con un grupo de Office 365 o un Microsoft Team. Por ejemplo, el siguiente comando muestra las propiedades seleccionadas de un grupo de Office 365 con nombre de equipo directivo superior:

''' powershell

    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    '''

 [!NOTE]
 Para ejecutar el cmdlet Get-UnifiedGroup, tiene que tener asignado el rol de los destinatarios con permiso de vista de Exchange Online o ser miembro de un grupo de roles ha asignado el rol de los destinatarios con permiso de vista.

 - Cuando se busca en el buzón de un usuario, no busca cualquier grupo de Office 365 o Microsoft Team que el usuario es un miembro de. De forma similar, al colocar un grupo de Office 365 o mantenga Microsoft Team, sólo el buzón de correo de grupo y sitios de grupo se colocan en suspensión; los buzones y OneDrive para sitios de profesionales de los miembros del grupo no se pondrá en espera a menos que explícitamente agregarlas como custodia o coloca su suspensión de orígenes de datos. Por lo tanto, si la necesidad de poner un grupo de Office 365 o Microsoft Team en mantiene para custodia específica, considere la posibilidad de asignar el sitio de grupo y el buzón de grupo a la custodia (consulte Administración de custodia de exhibición de documentos electrónicos avanzada (vista previa)). Si el grupo de Office 365 o Microsoft Team no puede atribuirse a una sola custodia, considere la posibilidad de agregar el origen para que no sean custodia suspensión. 
 
 - Para obtener una lista de los miembros de un grupo de Office 365 o Microsoft Team, puede ver las propiedades en la página de grupos de > principal en el centro de administración de Office 365. Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell:

    ''' powershell
    
        Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
        '''

[!NOTE]
Para ejecutar el cmdlet Get-UnifiedGroupLinks, tiene que tener asignado el rol de los destinatarios con permiso de vista de Exchange Online o ser miembro de un grupo de roles ha asignado el rol de los destinatarios con permiso de vista.

- Las conversaciones del canal que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo que está asociado con el equipo. De forma similar, los archivos que comparten los miembros del equipo en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, se debe colocar el buzón de correo de Microsoft Team y sitios de SharePoint en suspensión a conservar las conversaciones y archivos en un canal.
  
- Como alternativa, las conversaciones que forman parte de la lista de Chat en Microsoft Teams se almacenan en el buzón del usuario que participan en la conversación.  Los archivos que un usuario comparte en las conversaciones de Chat se almacenan en la OneDrive para el sitio de la empresa del usuario que comparte el archivo. Por lo tanto, se debe colocar los buzones de usuario individuales y OneDrive para los sitios de negocio de retención para conservar las conversaciones y archivos en la lista de Chat. 
  
- Todos los canales Microsoft Team o equipo contiene un sitio Wiki para colaboración y toma de notas. El contenido de Wiki se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de datos de Wiki de los equipos en el sitio de SharePoint del equipo. Puede colocar el contenido en el sitio Wiki en espera mediante la colocación de sitio de SharePoint del equipo en espera.

[!Note]
La capacidad de conservar el contenido de sitio Wiki para un canal de Microsoft Team o equipo (cuando el sitio de SharePoint del equipo se pone en espera) se lanzó en 22 de junio de 2017. Si un sitio de grupo se encuentra en espera, el sitio Wiki de contenido se conservarán iniciar en dicha fecha. Sin embargo, si un sitio de grupo se encuentra en suspensión y el contenido de Wiki se eliminó antes del 22 de junio de 2017, no se conserva el contenido del sitio Wiki.
   
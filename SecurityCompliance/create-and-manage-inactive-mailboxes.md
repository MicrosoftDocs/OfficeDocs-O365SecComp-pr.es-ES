---
title: Crear y administrar buzones inactivos en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: Puede crear un buzón inactivo en Office 365 aplicar una suspensión o la directiva de retención de Office 365 para el buzón de correo y, a continuación, eliminando la correspondiente cuenta de usuario de Office 365. Se conservan los elementos de un buzón inactivo para la duración de la directiva de retención o suspensión que se aplicó a ella antes de que se ha realizado como inactiva. Para eliminar permanentemente un buzón inactivo, simplemente quite la directiva de retención o suspensión.
ms.openlocfilehash: de67068ded30f63e46a8a94c1030d45a12b56a2e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740842"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>Crear y administrar buzones inactivos en Office 365

Office 365 permite conservar el contenido de los buzones eliminados. Esta característica se denomina [buzones inactivos](inactive-mailboxes-in-office-365.md). Buzones de correo inactivos permiten conservar el correo electrónico de los empleados anterior después de salir de su organización. Un buzón de correo, se convierte en inactivo cuando un juicio o una directiva de retención de Office 365 (creado en la seguridad de Office 365 &amp; centro de cumplimiento) se aplica a los buzones de correo antes de que se elimine la cuenta de usuario de Office 365 correspondiente. El contenido de un buzón inactivo se conserva para la duración de la suspensión a la que se realizó en el buzón de correo antes de que se ha realizado como inactiva. Esto permite que los administradores, responsables del cumplimiento normativo y registros a usar la búsqueda de contenido en la seguridad de los jefes de &amp; centro de cumplimiento para buscar y exportar el contenido de un buzón de correo inactivo. Buzones de correo inactivos no pueden recibir correo electrónico y no se muestran en la libreta de direcciones compartida de la organización o en otras listas.
  
> [!NOTE]
> Hemos pospuesto la fecha límite del 1 de julio de 2017 para crear conservaciones locales con el fin de desactivar buzones, pero más adelante este año o a principios del año que viene ya no podrá crear conservaciones locales en Exchange Online. A partir de ese momento, solo podrán usarse retenciones por juicio y directivas de retención de Office 365 para crear buzones inactivos. Aun así, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanente de buzones inactivos al quitar la conservación local. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Para definir un buzón de correo como inactiva, se debe asignar una licencia de Exchange Online Plan 2 para que un juicio o una directiva de retención de Office 365 se puede aplicar al buzón antes de que se elimine. Licencias de Exchange Online Plan 2 forman parte de un suscripciones a Office 365 Enterprise E3 y E5. Si un buzón se asigna una licencia de Exchange Online Plan 1 (que forma parte de una suscripción a Office 365 Enterprise E1), tendría que asignar una licencia independiente de archivado de Exchange Online para que se puede aplicar una suspensión para el buzón de correo antes de que se elimine. Para obtener más información, vea [Archivado de Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).
    
- La licencia asociada con el buzón de Exchange Online eliminado estará disponible después de eliminar la cuenta de usuario de Office 365 correspondiente. A continuación, puede [asignar licencias a los usuarios de Office 365 para la empresa](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) a otro usuario. 
    
- Si no se aplica una retención por juicio o una directiva de retención de Office 365 en un buzón antes de eliminarlo, su contenido no se conservará y no podrá detectarse. Aun así, el buzón eliminado se puede recuperar en un plazo de 30 días a partir de su eliminación, pero el buzón junto con su contenido se eliminará permanentemente transcurrido dicho plazo, si no se recupera.
    
- Para obtener más información acerca de la suspensión por litigio, vea [conservación local y suspensión por litigio](https://go.microsoft.com/fwlink/p/?LinkId=846124). Para obtener más información acerca de las directivas de retención de Office 365 en la seguridad &amp; centro de cumplimiento, vea [Introducción a las directivas de retención en Office 365](retention-policies.md).
  
## <a name="create-an-inactive-mailbox"></a>Crear un buzón inactivo

Convertir en un buzón de correo inactivos consta de dos pasos: (1) colocar el buzón de correo en juicio o aplicar una directiva de retención de Office 365 a ella y (2) eliminar el buzón o la cuenta de usuario de Office 365 correspondiente. Después de que el buzón de correo está inactivo, su contenido se conserva hasta que se quite la directiva de retención o suspensión.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>Paso 1: poner un buzón en retención por juicio o aplicar una directiva de retención de Office 365

Si se coloca un buzón en retención por juicio o si se aplica una directiva de retención de Office 365, se conserva el contenido del buzón antes de eliminarlo. Ambos tipos de retenciones conservarán todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de elementos modificados. Los elementos eliminados y modificados se conservan en el buzón inactivo durante un período de tiempo especificado o hasta que se elimine permanentemente el buzón inactivo mediante la eliminación de la retención o la directiva de retención aplicada a los buzones inactivos.
  
Si ya se ha colocado una retención en un buzón, o si ya se le ha aplicado una directiva de retención de Office 365, lo único que hay que hacer es eliminar la cuenta de usuario de Office 365 correspondiente, como se explica en el paso 2.
  
Para consultar los procedimientos detallados para poner un buzón en retención por juicio o aplicar una directiva de retención de Office 365, vea:
  
- [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Introducción a las directivas de retención en Office 365](retention-policies.md)
    
> [!NOTE]
> Para las retenciones por juicio y las directivas de retención de Office 365, puede crear una retención indefinida o una retención con duración definida. En una retención indefinida, el contenido del buzón inactivo se conservará siempre, hasta que se elimine la retención o hasta que se cambie la duración de la retención. Una vez quitada la retención o la directiva de retención (y siempre y cuando hayan pasado más de 30 días desde que el buzón se eliminara), el buzón inactivo se marcará para su eliminación permanente y su contenido se dejará de conservar o detectar. En una retención o directiva de retención de Office 365 con duración definida, se especifica lo que va a durar dicha retención. Esta duración se establece para cada elemento, y se calcula a partir de la fecha en que un elemento de buzón se ha recibido o creado. Una vez que ha expirado la retención para un elemento de buzón, y ese elemento se ha movido a la carpeta Elementos recuperables del buzón inactivo o se encuentra en ella, el elemento se elimina permanentemente (purga) del buzón inactivo. 
  
### <a name="step-2-delete-the-mailbox"></a>Paso 2: Eliminar el buzón.

Después de que el buzón de correo se pondrá en espera o se le aplica una directiva de retención de Office 365, el siguiente paso es eliminar el buzón de correo. Es la mejor forma de eliminar un buzón de correo eliminar la cuenta de usuario de Office 365 correspondiente en el centro de administración de Office 365. Para obtener información acerca de cómo eliminar cuentas de usuario de Office 365, vea [Eliminar un usuario de la organización](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
  
> [!NOTE]
> También puede eliminar el buzón de correo mediante el cmdlet **Remove-Mailbox** en Exchange Online PowerShell. Para obtener más información, vea [eliminar o restaurar los buzones de usuario en Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Ver una lista de buzones de correo inactivos


Para ver una lista de los buzones inactivos en su organización:
  
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> ** retención **.
    
3. En la página de **retención** , haga clic en **más**![puntos suspensivos de la barra de navegación](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)y, a continuación, haga clic en **buzones de correo inactivos**.
    
    ![En la página de retención, haga clic en más y, a continuación, haga clic en buzones de correo inactivos para mostrar una lista de buzones de correo inactivos](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Se abrirá la página de **buzones inactivos** . Tenga en cuenta que se muestra el número total de buzones inactivos en su organización. 
    
    ![Se muestra una lista de todos los buzones inactivos en la organización](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar la lista de buzones de correo inactivos.

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

Puede hacer clic en ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Exportar** para ver o descargar un archivo CSV que contiene información adicional acerca de los buzones inactivos en su organización. 
  
También puede ejecutar el siguiente comando para exportar la lista de buzones de correo inactivos y otra información a un archivo CSV. En este ejemplo, se crea el archivo CSV en el directorio actual.

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> Es posible que un buzón inactivo es posible que tenga la misma dirección SMTP como un buzón de usuario activo. En este caso, el valor de la propiedad **DistinguishedName** o **ExchangeGuid** puede utilizarse para identificar de forma única un buzón de correo inactivo. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Buscar y exportar el contenido de un buzón inactivo

Tener acceso al contenido del buzón inactivo mediante la herramienta de búsqueda de contenido en la seguridad &amp; centro de cumplimiento. Al buscar en un buzón de correo inactivo, puede crear una consulta de búsqueda de palabra clave para buscar elementos específicos o puede devolver todo el contenido del buzón de correo inactivo. Puede obtener una vista previa de los resultados de búsqueda o exportar los resultados de búsqueda a un archivo de datos de Outlook (PST) o como mensajes de correo electrónico individuales. Para obtener procedimientos paso a paso para buscar los buzones de correo y exportar los resultados de búsqueda, vea los temas siguientes:
  
- [Búsqueda de contenido en Office 365](content-search.md)
    
- [Exportar los resultados de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md)
    
A continuación presentamos algunas cosas que debe tener en cuenta al buscar buzones inactivos.
  
- Si una búsqueda de contenido incluye un buzón de usuario y ese buzón, a continuación, se convierte en inactivo, continuará la búsqueda de contenido buscar el buzón de correo inactivo cuando vuelva a ejecutar la búsqueda después de que quede inactiva.
    
- En algunos casos, un usuario puede tener un buzón de correo activa y un buzón inactivo que tienen la misma dirección SMTP. En este caso, se buscarán sólo el buzón específico que seleccione como una ubicación para una búsqueda de contenido. En otras palabras, si el buzón de un usuario se agrega a una búsqueda, no se puede suponer que se buscará en sus buzones activos e inactivos; se buscarán sólo el buzón de correo que se agregue explícitamente a la búsqueda.
    
- Se recomienda encarecidamente que no tenga un buzón activo y el buzón de correo inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP que está asignada actualmente a un buzón de correo inactivo, se recomienda que recuperar el buzón de correo inactivo o restaurar el contenido de un buzón inactivo en un buzón de correo activo (o el archivo de un buzón de active) y, a continuación, elimine el buzón de correo inactivo.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Después de un buzón de correo se realiza como inactiva, puede cambiar la duración de la suspensión o la directiva de retención de Office 365 aplicada para el buzón de correo inactivo. Para obtener procedimientos paso a paso, consulte [cambiar la duración de retención para un buzón inactivo en Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar un buzón inactivo

Si un empleado anterior devuelve a su organización, o si se contrata a un nuevo empleado a cabo en las responsabilidades de cargo del empleado abandonada, puede recuperar el contenido del buzón de correo inactivo. Al recuperar un buzón inactivo, el buzón de correo se convierte en un nuevo buzón de correo, se conservan el contenido y la estructura de carpetas de buzón de correo inactivo y el buzón de correo está vinculada a una nueva cuenta de usuario. Una vez recuperado, ya no existe el buzón de correo inactivo. Para procedimientos paso a paso y obtener más información acerca de sucede al recuperar un buzón inactivo, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar el contenido de un buzón inactivo en otro buzón de correo

Si lleva a otro empleado en las responsabilidades de trabajo de un empleado anterior, o si otra persona necesita tener acceso al contenido del buzón de correo inactivo, puede restaurar (o combinación) el contenido del buzón de correo inactivo a un buzón existente. Al restaurar un buzón inactivo, el contenido se copia en otro buzón. El buzón de correo inactivo se conserva y sigue siendo un buzón de correo inactivo. Aún se puede buscar en el buzón de correo inactivo uso de exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón, o puede ser recuperado o eliminado en una fecha posterior. Para obtener procedimientos paso a paso, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

Si ya no necesita conservar el contenido de un buzón de correo inactivo, puede eliminar permanentemente el buzón de correo inactivo por quitar la suspensión o la eliminación de la directiva de retención de Office 365 aplicada para el buzón de correo inactivo. Si el buzón de correo se ha eliminado de hace más de 30 días, el buzón se marcará para su eliminación permanente después de quitar la suspensión y el buzón de correo se convertirán en no recuperable. Si se ha eliminado el buzón de correo en los últimos 30 días, aún puede recuperar el buzón de correo después de quitar la directiva de retención o suspensión. Para obtener procedimientos paso a paso para quitar una suspensión o una directiva de retención de Office 365 para eliminar permanentemente un buzón inactivo, vea [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md).
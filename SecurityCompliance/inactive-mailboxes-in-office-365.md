---
title: Información general sobre los buzones inactivos en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: Obtenga información sobre cómo conservar el contenido de los buzones de correo para los antiguos empleados al convertir el buzón en un buzón inactivo. Para ello, puede colocar el buzón en retención por juicio o aplicar una directiva de retención de Office 365 al buzón y, a continuación, quitar la cuenta de Office 365 correspondiente.
ms.openlocfilehash: 12688cb1c0f1d165c21736ce5a6130245db36a06
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000803"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Información general sobre los buzones inactivos en Office 365

Es posible que su organización tenga que conservar el correo electrónico de los antiguos empleados después de que abandonen la organización. En función de los requisitos de retención de su organización, es posible que tenga que conservar el contenido de los buzones de correo durante unos meses o años después de que finalice el empleo, o puede que necesite retener el contenido de los buzones de correo indefinidamente. Independientemente del tiempo que necesite para conservar el correo electrónico, puede crear buzones inactivos en Office 365 para conservar el buzón de los antiguos empleados. 
  
## <a name="what-are-inactive-mailboxes"></a>¿Qué son los buzones inactivos?

Cuando un empleado deja la organización (o pasa por un período de ausencia extendido), puede quitar su cuenta de Office 365. Los datos del buzón del empleado se conservan durante 30 días después de quitar la cuenta. Durante este período, puede recuperar los datos del buzón de correo eliminando la cuenta. TransCurrido el plazo de 30 días, los datos se eliminan de forma permanente.
  
Pero si su organización necesita conservar el contenido de los buzones de correo para los antiguos empleados, puede convertir el buzón en un buzón inactivo colocando el buzón en retención por juicio o aplicando una directiva de retención de Office 365 al buzón en el centro de seguridad & cumplimiento y, a continuación, quita la cuenta de Office 365 correspondiente. El contenido de un buzón inactivo se conserva durante toda la retención por juicio que se aplica en el buzón o el período de retención de la Directiva de retención de Office 365 que se le ha aplicado antes de que se elimine el buzón. Todavía puede recuperar la cuenta de usuario correspondiente durante un período de 30 días. Sin embargo, después de 30 días, el buzón inactivo se conserva en Office 365 hasta que se quite la Directiva de retención o retención. 
  
**Importante:** Hemos pospuesto el plazo de 1 de julio de 2017 para crear nuevas reTenciones locales y hacer que un buzón sea inactivo. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. En ese momento, solo se pueden usar las suspensiones por juicio y las directivas de retención de Office 365 para crear un buzón inactivo. No obstante, se seguirán admitiendo los buzones inactivos existentes que estén en conservación local y podrá seguir administrando las conservaciones locales de buzones inactivos. Esto incluye el cambio de la duración de las conservaciones locales y la eliminación de forma permanentemente de buzones inactivos al quitar la conservación local. 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>Buzones de correo inactivos y directivas de retención de 365 de Office

Además de la retención por juicio, el uso de la nueva característica de la Directiva de retención de Office 365 en el centro de seguridad & cumplimiento es otra forma de poner un buzón inactivo. Para usar una directiva de retención para crear un buzón inactivo: 
  
- Debe aplicarse a los buzones de correo de Exchange o a las ubicaciones de Skype empresarial (porque el contenido relacionado con Skype se almacena en el buzón de correo del usuario). 
    
- Debe configurarse para conservar contenido o conservar y, a continuación, eliminar contenido. Si se configura una directiva de retención para que solo elimine contenido, un buzón al que se aplica la Directiva no se desactivará cuando se elimine el buzón.
    
- Puede estar basada en consultas para que conserve solo los elementos que coinciden con una consulta de búsqueda. 
    
Para obtener más información acerca de la configuración de las directivas de retención de Office 365, vea [información general sobre las directivas de retención en Office 365](retention-policies.md).
  
Si usa una directiva de retención de Office 365 para establecer un buzón inactivo, Office 365 seguirá procesando la Directiva de retención en el buzón inactivo. Esto significa que si la Directiva de retención está configurada para conservar y, a continuación, eliminar contenido, los elementos se moverán a la carpeta elementos recuperables cuando expire la duración de retención y, a continuación, se purguen del buzón inactivo. Si la Directiva de retención de Office 365 no está configurada para elementos eliminados, los elementos que el usuario no haya eliminado permanentemente (antes de que el buzón se haya inactivo) no se moverán a la carpeta elementos recuperables y se conservarán indefinidamente después de la el buzón de correo pasa a estar inactivo. 
  
Puede considerar la posibilidad de crear una directiva de retención de Office 365 específica para los buzones inactivos. Estas son algunas de las razones por las que debe tener esto y cosas que tener en cuenta.
  
- Puede configurar la Directiva de retención para conservar el contenido de los buzones de correo solo cuando sea necesario para cumplir los requisitos de los antiguos empleados de la organización.
    
- Es una forma sencilla de identificar los buzones inactivos, ya que la Directiva de retención solo se aplicará a los buzones inactivos.
    
- Podrá identificar fácilmente la Directiva de retención que está asignada a los buzones inactivos en su organización. Esto hará que sea más fácil cambiar la configuración de retención (o eliminación) si es necesario. También facilitará la eliminación permanente de un buzón inactivo, ya que sólo se puede quitar de la Directiva mediante el centro de seguridad & cumplimiento. De lo contrario, tiene que usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo o usar PowerShell del centro de cumplimiento de & de seguridad para excluir un buzón inactivo de una directiva de retención de Office 365 de toda la organización.
    
- Si crea una directiva de retención de Office 365 específica para buzones inactivos, puede Agregar un máximo de 1.000 buzones de correo a la Directiva. Si es una organización de gran tamaño, es posible que tenga que crear más de una directiva de retención de Office 365 para usarla para los buzones inactivos.
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Buzones inactivos y casos de exhibición de documentos electrónicos

Si una retención asociada a un caso de exhibición de documentos electrónicos en el centro de cumplimiento de seguridad & se coloca en un buzón y, a continuación, se elimina el buzón o la cuenta de Office 365 del usuario, el buzón se convertirá en un buzón inactivo. Sin embargo, no se recomienda usar suspensiones de casos de exhibición de documentos electrónicos para convertir un buzón en inactivo. Esto se debe a que los casos de eDiscovery están pensados para casos específicos y de tiempo limitado relacionados con problemas legales. En algún momento, es probable que finalice un caso legal y se quitarán las suspensiones asociadas al caso y se cerrará el caso de exhibición de documentos electrónicos. De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y, a continuación, se suelta la retención o el caso de exhibición de documentos electrónicos se cierra (o se elimina), el buzón inactivo se eliminará permanentemente. Además, no puede crear una suspensión de eDiscovery basada en tiempo. Esto significa que el contenido de un buzón inactivo se conservará indefinidamente o hasta que se quite la retención y se elimine el buzón inactivo. Por lo tanto, se recomienda usar una retención por juicio o una directiva de retención de Office 365 para los buzones inactivos.
  
Para obtener más información sobre los casos y las suspensiones de eDiscovery, vea [casos de eDiscovery](ediscovery-cases.md).
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>Buzones de correo inactivos y etiquetas de Office 365

Las etiquetas de Office 365 ayudan a clasificar los datos de correo electrónico de su organización para el gobierno y aplicar reglas de retención basadas en esa clasificación. Una etiqueta puede aplicarse a un elemento de correo electrónico manualmente por los usuarios o automáticamente por los administradores, y un elemento de correo electrónico solo puede tener asignada una etiqueta única. Si un único elemento de correo electrónico del buzón de un usuario tiene asignada una etiqueta y se elimina el buzón o la cuenta de Office 365 del usuario, el buzón se convertirá en un buzón inactivo. Al igual que ocurre con las suspensiones de casos de eDiscovery, no se recomienda usar etiquetas para convertir un buzón en inactivo. En su lugar, le recomendamos que use una retención por juicio o una directiva de retención de Office 365. Tenga en cuenta que, en el caso de las etiquetas, es posible que no se dé cuenta de que se ha aplicado una etiqueta a un elemento de correo electrónico y, a continuación, se ha realizado un buzón inactivo al eliminar la cuenta del usuario. 
  
Para obtener más información acerca de las etiquetas, vea [información general sobre las etiquetas en Office 365](labels.md).
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Buzones inactivos y directivas de retención de MRM de Exchange

Si se aplicó una directiva de retención de Exchange (la característica de administración de registros de mensajería, o MRM, en Exchange Online) al buzón de correo cuando se inactivo, cualquier directiva de eliminación (que sea una etiqueta de retención configurada con una acción de retención de **eliminación** ) se seguir procesándose en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se moverán a la carpeta Elementos recuperables cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta elementos recuperados se conservarán indefinidamente. 
  
Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecerán en el buzón principal cuando expire el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente. 
  
## <a name="creating-an-inactive-mailbox"></a>Creación de un buzón inactivo

Para convertir un buzón en inactivo, se le debe asignar una licencia de Exchange Online (plan 2), de modo que se pueda aplicar una directiva de retención por juicio u Office 365 al buzón antes de eliminarlo. Una vez eliminado el buzón de correo, la licencia de Exchange online que estuviera asociada a él estará disponible para asignarlo a un nuevo usuario. Los buzones inactivos no necesitan licencias en curso.
  
En la tabla siguiente se resume el proceso de creación de un buzón inactivo para diferentes escenarios de retención. Para obtener más información, vea [administrar buzones inactivos en Office 365](create-and-manage-inactive-mailboxes.md).
  
|**Para...**|**Haga esto...**|**Resultado**|
|:-----|:-----|:-----|
|Conservar el contenido del buzón indefinidamente después de que un empleado abandone la organización  <br/> | Coloque el buzón en retención por juicio o aplique una directiva de retención de Office 365 al buzón.  <br/>  No especifique una duración de retención para la retención por juicio o no configure la Directiva de retención de Office 365 para eliminar elementos; como alternativa, puede usar una directiva de retención que retenga elementos para siempre.  <br/>  Quite la cuenta de Office 365 del usuario  <br/> |Todo el contenido del buzón inactivo, incluidos los elementos de la carpeta elementos recuperables, se conserva indefinidamente.  <br/> |
|Conservar el contenido de los buzones de correo durante un período específico después de que un empleado abandone la organización y, a continuación, elimínelo  <br/> | Aplique una directiva de retención de Office 365 al buzón.  <br/>  Configure la Directiva de retención para conservar y, a continuación, elimine los elementos cuando expire el período de retención.  <br/>  Quite la cuenta de Office 365 del usuario  <br/> |Cuando expira el período de retención de un elemento de buzón de correo, el elemento se mueve a la carpeta elementos recuperables y, a continuación, se elimina de forma permanente (purga) del buzón inactivo cuando expira el período de retención de elementos eliminados (para buzones de Exchange). El período de retención de la Directiva de retención de Office 365 se puede configurar en función de la fecha original en que se ha recibido o creado un elemento de buzón, o bien cuando se modificó por última vez.  <br/> |
   
**Nota:** Si ya se ha realizado una retención por juicio en un buzón o si ya se ha aplicado una directiva de retención de Office 365, todo lo que tiene que hacer es eliminar la cuenta de usuario de Office 365 correspondiente para crear un buzón inactivo. 
  
## <a name="managing-inactive-mailboxes"></a>Administrar buzones inactivos

Después de convertir un buzón en inactivo, puede realizar varias tareas de administración en buzones inactivos.
  
- **Cambiar la duración de retención para un buzón inactivo** Una vez que un buzón se convierte en inactivo, puede cambiar la duración de retención de la retención por juicio o la Directiva de retención de Office 365 aplicada al buzón inactivo. Para conocer los procedimientos paso a paso, vea [cambiar la duración de retención para un buzón inactivo en Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
    
- **Recuperar un buzón inactivo** Si un antiguo empleado (o un empleado de una baja de ausencia) vuelve a su organización o si se contrata a un nuevo empleado para que realice las responsabilidades laborales del antiguo empleado, puede recuperar el contenido del buzón inactivo. Al recuperar un buzón inactivo, el buzón se convierte en un nuevo buzón, el contenido y la estructura de carpetas del buzón inactivo se conservan y el buzón se vincula a una nueva cuenta de usuario. Una vez recuperado, el buzón inactivo deja de existir. Para conocer los procedimientos paso a paso e información sobre lo que sucede cuando se recupera un buzón inactivo, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
- **Restaurar un buzón inactivo** Si otro empleado asume las responsabilidades laborales de un antiguo empleado o si otra persona necesita acceso al contenido del buzón inactivo, puede restaurar (o combinar) el contenido del buzón inactivo en un buzón existente. Cuando se restaura un buzón inactivo, el contenido se copia a otro buzón. El buzón inactivo se conserva y sigue siendo un buzón inactivo. El buzón inactivo todavía se puede buscar con herramientas de eDiscovery, su contenido se puede restaurar a otro buzón de correo y se puede recuperar o eliminar en una fecha posterior. Para conocer los procedimientos paso a paso, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
    
- **Eliminar un buzón inactivo** Cuando ya no necesite conservar el contenido de un buzón inactivo, puede eliminarlo de forma permanente si quita todas las suspensiones o las directivas de retención de Office 365 que se aplican al buzón inactivo. Si un buzón se ha hecho inactivo hace más de 30 días, se marcará para su eliminación permanente después de quitar la retención. Si el buzón de correo se inactivo en los últimos 30 días, puede volver a activarlo después de quitar la retención o la Directiva de retención. Para conocer los procedimientos paso a paso, consulte [eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md).
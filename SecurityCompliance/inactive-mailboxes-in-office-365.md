---
title: Información general de buzones inactivos en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: Obtenga información acerca de la retención de contenido de buzones de correo de los antiguos empleados activando el buzón de correo en un buzón de correo inactivo. Puede hacer esto colocando el buzón de correo en juicio o aplicar una directiva de retención de Office 365 para el buzón de correo y, a continuación, elimina la correspondiente cuenta de Office 365.
ms.openlocfilehash: 5b421e32df99a10d13528fe7a75e6a0e8fb54fdc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536267"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Información general de buzones inactivos en Office 365

Su organización puede necesitar conservar el correo electrónico de los empleados anterior después de salir de la organización. Según los requisitos de retención de la organización, es posible que necesite conservar el contenido de los buzones de para unos meses o años después de que termina de empleo o es posible que tenga que conservar el contenido del buzón indefinidamente. Independientemente de cuánto tiempo debe conservar el correo electrónico, puede crear buzones inactivos en Office 365 para conservar el buzón de correo de antiguos empleados. 
  
## <a name="what-are-inactive-mailboxes"></a>¿Qué son los buzones inactivos?

Cuando un empleado abandona la organización (o se coloca en una baja de ausencia extendida), puede quitar su cuenta de Office 365. Datos de buzón de correo del empleado se conservan durante 30 días después de que se ha quitado la cuenta. Durante este período, aún puede recuperar los datos de buzones de correo por recuperar la cuenta. Después de 30 días, los datos se eliminan permanentemente.
  
Pero si su organización necesita conservar el contenido de los buzones de los antiguos empleados, puede convertir el buzón de correo en un buzón inactivo colocar el buzón de correo en juicio o aplicando una directiva de retención de Office 365 para el buzón de correo en la seguridad de Office 365 &amp; Centro de cumplimiento y, a continuación, elimina la correspondiente cuenta de Office 365. El contenido de un buzón inactivo se conserva para la duración de la suspensión por litigio coloca en el buzón de correo o el período de retención de la directiva de retención de Office 365 que se ha aplicado antes de que se eliminó el buzón de correo. Aún puede recuperar la cuenta de usuario correspondiente para un período de 30 días. Sin embargo, después de 30 días, el buzón de correo inactivo se conserva en Office 365 hasta que se quite la directiva de retención o suspensión. 
  
**Importante:** Nos hemos pospuso la fecha límite de 1 de julio de 2017 para la creación de nuevos suspensiones en contexto para definir un buzón de correo como inactiva. Pero más adelante este año o el principio del próximo año, no podrá crear nuevos suspensiones en contexto en Exchange Online. En ese momento, sólo las directivas de retención por litigio contiene y Office 365 pueden usarse para crear un buzón de correo inactivo. Sin embargo, aún se admitirá buzones inactivos existentes que se encuentran en retención local, y puede continuar administrar el suspensiones en contexto en buzones de correo inactivos. Esto incluye el cambio de la duración de una retención local y eliminar permanentemente un buzón inactivo quitando la retención local. 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>Buzones de correo inactivos y las directivas de retención de Office 365

Además de la suspensión por litigio, uso de la nueva característica de directiva de retención de Office 365 en la seguridad &amp; centro de cumplimiento es otra forma de definir un buzón de correo como inactiva. Para utilizar una directiva de retención para hacer que un buzón inactivo: 
  
- Tiene que se aplicará a los buzones de Exchange o Skype para las ubicaciones de negocio (debido a que el contenido relacionado con Skype se almacena en el buzón del usuario). 
    
- Debe estar configurada para conservar el contenido o conservar y, a continuación, el contenido eliminado. Si se configura una directiva de retención para eliminar acaba de contenido, un buzón de correo que se aplica la directiva a no quedan inactivo cuando se elimina el buzón de correo.
    
- Puede ser basada en consultas de modo que conserva sólo los elementos que coincidan con una consulta de búsqueda. 
    
Para obtener más información acerca de cómo configurar las directivas de retención de Office 365, vea [Introducción a las directivas de retención en Office 365](retention-policies.md).
  
Si se utiliza una directiva de retención de Office 365 para hacer que un buzón inactivo, Office 365 seguirán procesar la directiva de retención en el buzón de correo inactivo. Esto significa que si se configura la directiva de retención para retener y, a continuación, eliminar contenido, los elementos se mueven a la carpeta elementos recuperables cuando expire la duración de retención y, a continuación, se purgan finalmente desde el buzón de correo inactivo. Si no se ha configurado la directiva de retención de Office 365 para elementos eliminados, a continuación, los elementos que aún no se ha eliminado permanentemente por el usuario (antes de que se ha realizado el buzón de correo inactivo) no se moverán a la carpeta elementos recuperables y se retendrá indefinidamente después de la buzón de correo quede inactiva. 
  
Considere la posibilidad de crear una directiva de retención de Office 365 específicamente para buzones de correo inactivos. A continuación presentamos algunas de las razones para realizar esta acción y cosas que hay que tener en cuenta.
  
- Puede configurar la directiva de retención para conservar el contenido de los buzones solo siempre que sea necesario para satisfacer los requisitos de su organización para ex empleados de.
    
- Es un método sencillo para identificar buzones inactivos debido a que sólo se aplicará la directiva de retención a buzones de correo inactivos.
    
- Podrá identificar fácilmente la directiva de retención que se asigna a buzones inactivos en su organización. Esto que sea más fácil si es necesario, cambiar la configuración de retención (o eliminación). También hará sea más fácil eliminar permanentemente un buzón inactivo debido a que sólo puede quitarlo de la directiva mediante el uso de la seguridad &amp; centro de cumplimiento. De lo contrario, debe usar Exchange Online PowerShell para quitar un juicio de un buzón inactivo o usar seguridad &amp; PowerShell de centro de cumplimiento para excluir un buzón inactivo de una directiva de retención de Office 365 de toda la organización.
    
- Si crea una directiva de retención de Office 365 específicamente para buzones de correo inactivos, puede agregar un máximo de 1.000 buzones de correo a la directiva. Si usted es una organización muy grande, debe crear más de una directiva de retención de Office 365 que se usará para buzones de correo inactivos.
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Buzones de correo inactivos y suspensiones de casos de exhibición de documentos electrónicos

Si una suspensión a la que está asociado con un caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento se coloca en un buzón de correo y, a continuación, en el buzón de correo o se elimina la cuenta de usuario Office 365, el buzón de correo se convertirá en un buzón de correo inactivo. Sin embargo, no recomendamos usar caso de exhibición de documentos electrónicos contiene para definir un buzón de correo como inactiva. Eso es porque los casos de exhibición de documentos electrónicos están diseñados para casos específicos, el límite de tiempo relacionado con un problema legal. En algún momento, probablemente finalizará un caso legal y las suspensiones asociadas con el caso se quitará y se cerrará el caso de exhibición de documentos electrónicos. De hecho, si una suspensión que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y, a continuación, se libera la suspensión o la exhibición de documentos electrónicos caso está cerrado (o elimina), se eliminará permanentemente el buzón de correo inactivo. Además, no se puede crear una suspensión de exhibición de documentos electrónicos basada en tiempo. Que es medio contenido en un buzón inactivo se conservará para siempre o hasta que se elimina la suspensión y se elimina el buzón de correo inactivo. Por lo tanto, se recomienda usar un juicio o una directiva de retención de Office 365 para buzones de correo inactivos.
  
Para obtener más información acerca de los casos de exhibición de documentos electrónicos y las suspensiones, vea [casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](ediscovery-cases.md).
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>Buzones de correo inactivos y etiquetas de Office 365

Etiquetas en Office 365 le ayudarán a clasificar los datos de correo electrónico en la organización para el gobierno y exigir la aplicación de reglas de retención basadas en dicha clasificación. Una etiqueta se puede aplicar a un elemento de correo electrónico manualmente por los usuarios o automáticamente por los administradores y un elemento de correo electrónico sólo puede tener etiqueta único asignada a él. Si un elemento de correo electrónico única en el buzón del usuario tiene una etiqueta asignada a ella y el buzón de correo o se elimina la cuenta de usuario Office 365, el buzón de correo se convertirá en un buzón de correo inactivo. Al igual que las suspensiones de casos de exhibición de documentos electrónicos, no es recomendable utilizar etiquetas para definir un buzón de correo como inactiva. En su lugar, se recomienda que utilice un juicio o una directiva de retención de Office 365. Tenga en cuenta que en el caso de etiquetas, es posible que no se den cuenta que una etiqueta se ha aplicado a un elemento de correo electrónico y, a continuación, poner un buzón inactivo a sin darse cuenta cuando se elimina la cuenta de usuario. 
  
Para obtener más información acerca de las etiquetas, vea [información general de las etiquetas en Office 365](labels.md).
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Buzones de correo inactivos y las directivas de retención de MRM de Exchange

Si se ha aplicado una directiva de retención de Exchange (la característica de administración de registros de mensajería o MRM, en Exchange Online) al buzón de correo cuando se realizó inactiva, va las directivas de eliminación (que están configuradas con una acción de retención **Eliminar** las etiquetas de retención) continuar que va a procesar en el buzón de correo inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se moverán a la carpeta elementos recuperables cuando expire el período de retención. Esos elementos se purgan desde el buzón de correo inactivo cuando expire la duración de la suspensión. Si no se especifica una duración de retención para el buzón de correo inactivo, se conservarán los elementos de la carpeta recuperar elementos indefinidamente. 
  
Por el contrario, se omiten las directivas de archivo (que están configuradas con una acción de retención **MoveToArchive** las etiquetas de retención) que se incluyen en la directiva de retención asignada a un buzón de correo inactivo. Esto significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecerá en el buzón principal cuando expire el período de retención. No se está mover para el buzón de archivo o a la carpeta elementos recuperables en el buzón de archivo. Se puede conservar indefinidamente. 
  
## <a name="creating-an-inactive-mailbox"></a>Creación de un buzón inactivo

Para definir un buzón de correo como inactiva, se debe asignar una licencia de Exchange Online (Plan 2) para que se puede aplicar una directiva de retención juicio u Office 365 para el buzón de correo antes de que se elimine. Después de elimina el buzón de correo, la licencia de Exchange Online que estaba asociada con él estará disponible para asignar a un nuevo usuario. Buzones de correo inactivos no requieren licencias continuadas.
  
La tabla siguiente resume el proceso de poner un buzón inactivo para escenarios de retención diferente. Para obtener más información, vea [administrar buzones inactivos en Office 365](create-and-manage-inactive-mailboxes.md).
  
|**Para...**|**Haga lo siguiente:**|**Resultado**|
|:-----|:-----|:-----|
|Conservar el contenido del buzón indefinidamente después de que un empleado deja la organización  <br/> | Coloque el buzón de correo en juicio o aplicar una directiva de retención de Office 365 para el buzón de correo.  <br/>  No se especifica una duración de retención para el juicio o no configurar la directiva de retención de Office 365 para eliminar los elementos; También puede usar una directiva de retención que conserva los elementos de una eternidad.  <br/>  Quite la cuenta de Office 365 del usuario  <br/> |Todo el contenido en el buzón de correo inactivo, incluidos los elementos en la carpeta elementos recuperables, se conserva indefinidamente.  <br/> |
|Conservar el contenido de los buzones durante un período específico después de que un empleado deja la organización y, a continuación, elimínelo.  <br/> | Aplicar una directiva de retención de Office 365 para el buzón de correo.  <br/>  Configurar la directiva de retención para retener y, a continuación, eliminar elementos cuando expire el período de retención.  <br/>  Quite la cuenta de Office 365 del usuario  <br/> |Cuando expire el período de retención para un elemento de buzón de correo, el elemento se mueve a la carpeta elementos recuperables y, a continuación, se elimina permanentemente (purga) desde el buzón de correo inactivo cuando expire el período de retención de elementos eliminados (para los buzones de Exchange). El período de retención de la directiva de retención de Office 365 se puede configurar en función de la fecha original de un elemento de buzón de correo se ha recibido o creado, o cuándo se modificó por última vez.  <br/> |
   
**Nota:** Si un juicio ya está colocado en un buzón de correo, o si ya se aplica una directiva de retención de Office 365 a ella, todo lo que debe hacer es eliminar la cuenta de usuario de Office 365 correspondiente para crear un buzón de correo inactivo. 
  
## <a name="managing-inactive-mailboxes"></a>Administrar buzones inactivos

Después de definir un buzón de correo como inactiva, puede realizar diversas tareas de administración de buzones de correo inactivos.
  
- **Cambiar la duración de retención para un buzón inactivo** Después de un buzón de correo se realiza como inactiva, puede cambiar la duración de retención de la directiva de retención juicio u Office 365 aplicada para el buzón de correo inactivo. Para obtener procedimientos paso a paso, consulte [cambiar la duración de retención para un buzón inactivo en Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
    
- **Recuperar un buzón inactivo** Si un antiguo empleado (o un empleado en una baja de ausencia) se devuelve a su organización, o si se contrata a un nuevo empleado a cabo en las responsabilidades de cargo del empleado anterior, puede recuperar el contenido del buzón de correo inactivo. Al recuperar un buzón inactivo, el buzón de correo se convierte en un nuevo buzón de correo, se conservan el contenido y la estructura de carpetas de buzón de correo inactivo y el buzón de correo está vinculada a una nueva cuenta de usuario. Una vez recuperado, ya no existe el buzón de correo inactivo. Para obtener información acerca de lo que sucede cuando recuperar un buzón inactivo y procedimientos paso a paso, vea [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
- **Restaurar un buzón inactivo** Si lleva a otro empleado en las responsabilidades de trabajo de un empleado anterior, o si otra persona necesita tener acceso al contenido del buzón de correo inactivo, puede restaurar (o combinación) el contenido del buzón de correo inactivo a un buzón existente. Al restaurar un buzón inactivo, el contenido se copia en otro buzón. El buzón de correo inactivo se conserva y sigue siendo un buzón de correo inactivo. Aún se puede buscar en el buzón de correo inactivo con las herramientas de exhibición de documentos electrónicos, su contenido se puede restaurar en otro buzón, y puede ser recuperado o eliminado en una fecha posterior. Para obtener procedimientos paso a paso, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
    
- **Eliminar un buzón inactivo** Cuando ya no necesite conservar el contenido de un buzón de correo inactivo, puede eliminar permanentemente quitando todas las suspensiones o las directivas de retención de Office 365 aplicadas para el buzón de correo inactivo. Si un buzón de correo se realizó inactivo más de 30 días desde hace, se marcará para su eliminación permanente después de quitar la suspensión. Si el buzón de correo se realizó inactivo dentro de los últimos 30 días, puede convertirla en active nuevamente después de la eliminación de la directiva de retención o suspensión. Para conocer los procedimientos paso a paso, vea [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md).
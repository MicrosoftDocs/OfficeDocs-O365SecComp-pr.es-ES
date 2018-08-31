---
title: Las directivas de la seguridad de Office 365 de la alerta &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/8/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
description: Crear directivas de alerta en la seguridad de Office 365 &amp; centro de cumplimiento para supervisar las posibles amenazas, la pérdida de datos y el problema de permisos. A continuación, puede ver y administrar las alertas que se generan cuando los usuarios realizan actividades que coinciden con las condiciones de una directiva de alerta.
ms.openlocfilehash: 1404f03fdc59583fdf402f2cdc6209f4d55c23f3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536146"
---
# <a name="alert-policies-in-the-office-365-security-amp-compliance-center"></a>Las directivas de la seguridad de Office 365 de la alerta &amp; centro de cumplimiento

Puede usar la nueva directiva de alerta y herramientas de alerta de escritorio en la seguridad de Office 365 &amp; centro de cumplimiento para crear directivas de alerta y, a continuación, ver las alertas que se generan cuando los usuarios realizan actividades que coinciden con las condiciones de una directiva de alerta. Alerta de directivas se basan en y expanden la funcionalidad de alertas de actividad según lo que le permite clasificar la directiva de alerta, aplicar la directiva a todos los usuarios de su organización, establecer un nivel de umbral cuando se desencadena una alerta y decidir si desea recibir correo electrónico o no notificaciones. También hay una página de **alertas de vista** de la seguridad &amp; centro de cumplimiento, donde puede ver y filtrar las alertas, establecer un estado de la alerta que le ayudarán a administrar alertas y, a continuación, descartar las alertas después de haber solucionado o resuelto el incidente subyacente. También nos hemos expandido el tipo de eventos que se pueden crear alertas para. Por ejemplo, puede crear directivas de alerta para realizar un seguimiento de los incidentes de pérdida de datos y la actividad de malware. Por último, también hemos incluido un número de directivas de alerta predeterminadas que le ayudan a supervisar asignar privilegios de administrador en Exchange Online, ataques de malware y poco habituales niveles de eliminaciones de archivos y uso compartido externo. 
  
> [!NOTE]
> Directivas de alerta están disponibles para las organizaciones con una suscripción a Office 365 Enterprise E1, E3 o E5. Sin embargo, algunas funciones avanzadas sólo está disponible para las organizaciones con una suscripción E5, o para las organizaciones que tienen una suscripción E1 o E3 y una suscripción de complemento de Office 365 amenaza inteligencia o cumplimiento de normas avanzadas de Office 365. En este tema, se resaltará la funcionalidad que requiere una suscripción E5 o el complemento. 
  
## <a name="how-alert-policies-work"></a>Cómo funciona alert trabajo de directivas

Este es un breve resumen del trabajo de alerta cómo las directivas y las alertas que son los desencadenadores cuando el usuario o un administrador de actividad coinciden con las condiciones de una directiva de alerta.
  
![Información general de cómo alerta de las directivas de trabajo](media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)
  
1. Un administrador de la organización crea, configura y activa en una directiva de alerta mediante la página de **directivas de alerta** en la seguridad &amp; centro de cumplimiento. También puede crear directivas de alerta mediante el cmdlet **New-ProtectionAlert** en PowerShell. 
    
2. Un usuario realiza una actividad que coincide con las condiciones de una directiva de alerta. En el caso de los ataques de malware, los mensajes de correo electrónico infectados enviados a los usuarios de su organización activarán una alerta.
    
3. Office 365 genera una alerta que se muestra en la página **Ver avisos** en la seguridad &amp; centro de cumplimiento. Además, si se habilitan las notificaciones de correo electrónico para la directiva de alerta, Office 365 envía una notificación a destinatarios de una lista. 
    
4. Un administrador que administra las alertas en la seguridad &amp; centro de cumplimiento. Administrar alertas consta de asignar un estado de la alerta para ayudar a realizar un seguimiento y administrar cualquier investigación.
    

  
## <a name="alert-policy-settings"></a>Configuración de la directiva de la alerta

Una directiva de alerta consta de un conjunto de reglas y las condiciones que definen el usuario o la actividad de administración que se generará una alerta, una lista de los usuarios que se activará la alerta si al llevar a cabo la actividad, y tiene el umbral que define cuántas veces la actividad que se produzca antes de una se activará n alerta. También clasificar la directiva y asignar un nivel de gravedad. Estos dos valores le ayudan a administrar las directivas de alerta (y las alertas que se desencadenan cuando se cumplen las condiciones de directiva) porque se puede filtrar en estas opciones de configuración cuando la administración de directivas y visualización de las alertas en la seguridad &amp; centro de cumplimiento. Por ejemplo, puede ver las alertas que coinciden con las condiciones de la misma categoría o alertas de vista con el mismo nivel de gravedad.
  
Para ver y crear directivas de alerta, vaya a **las alertas de** \> **las directivas de alerta** en la seguridad &amp; centro de cumplimiento. 
  
![En la seguridad &amp; centro de Complinace, haga clic en alertas, a continuación, haga clic en la alerta de directivas para ver y crear directivas de alerta](media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)
  
Una directiva de alerta consta de los siguientes parámetros y condiciones.
  
- **Realiza un seguimiento de actividad de la alerta** - crear una directiva para realizar un seguimiento de una actividad o en algunos casos, algunas actividades relacionadas, tales un uso compartido de un archivo con un usuario externo por compartirla, asignar permisos de acceso o la creación de un vínculo anónimo. Cuando un usuario realiza la actividad definida por la directiva, se activará una alerta en función de la configuración de umbral de alerta.
    
    > [!NOTE]
    > Las actividades que puede realizar un seguimiento dependen de la suscripción a Office 365 Enterprise de su organización. En general, las actividades relacionadas con las campañas de malware y ataques de suplantación de identidad requieren una suscripción E5 o una suscripción a E1 o E3 con una suscripción de complemento de inteligencia de amenaza. 
  
- **Condiciones de actividad** - para la mayoría de las actividades, puede definir condiciones adicionales que se deben cumplir para que se desencadena una alerta. Condiciones comunes incluyen IP direcciones (para que una alerta se desencadena cuando el usuario realiza la actividad en un equipo con una dirección IP específica o dentro de un intervalo de direcciones IP), si se desencadena una alerta si un usuario específico o a los usuarios realizan esa actividad y si la actividad se realiza en un nombre de archivo específico o la dirección URL. También puede configurar una condición que se desencadene una alerta cuando la actividad se lleva a cabo por cualquier usuario de la organización. Tenga en cuenta que las condiciones disponibles dependen de la actividad seleccionada.
    
- **Cuando se desencadena la alerta** - puede establecer una configuración que define ¿con qué frecuencia se puede producir una actividad antes de que se desencadena una alerta. Esto le permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de directiva, cuando se supera un umbral determinado, o cuando la aparición de la actividad que se realiza un seguimiento de la alerta se convierte en poco habitual para nuestra organización. 
    
    ![Configurar cómo se desencadenan alertas, en función de cuándo se produce la actividad, un umbral o actividad poco habitual para su organización](media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)
  
    Si selecciona la opción basada en la actividad inusual, Office 365 establece un valor de línea de base que define la frecuencia normal para la actividad seleccionada; se tarda hasta 7 días para establecer una línea base, durante el cual no se pueden generar alertas. Una vez establecida la línea de base, se activará una alerta cuando la frecuencia de la actividad hace un seguimiento mediante la directiva de alerta en gran medida supera el valor de la línea de base. Puede establecer una línea base para las actividades relacionadas con la auditoría (por ejemplo, las actividades de archivos y carpetas), en función de un solo usuario o en función de todos los usuarios de la organización; para las actividades relacionadas con el malware, puede establecer una línea base en función de una familia de malware única, un solo destinatario o todos los mensajes en la organización.
    
    > [!NOTE]
    > La capacidad para configurar directivas de alerta en función de un umbral o en función de una actividad inusual requiere una suscripción E5 o una suscripción a E1 o E3 con una suscripción de complemento de inteligencia de amenaza o cumplimiento avanzada. Las organizaciones con una suscripción a E1 y E3 sólo pueden crear una directiva de alerta donde se activará una alerta cada vez que se produce una actividad. 
  
- **Categoría de alerta** - favorecer el seguimiento y la administración de las alertas generadas por una directiva, puede asignar una de las siguientes categorías a una directiva.
    
  - Gobierno de datos
    
  - Protección ante la pérdida de datos
    
  - Permisos
    
  - Administración de amenazas
    
  - Otros
    
    Cuando se produce una actividad que coincide con las condiciones de la directiva de alerta, la alerta que se genera se cuente con la categoría definida en esta configuración. Esto permite realizar un seguimiento y administrar las alertas que tienen la misma configuración de categoría en la página **Ver avisos** en la seguridad &amp; debido a que se puede ordenar y alertas de filtro basan en la categoría del centro de cumplimiento. 
    
- **Gravedad de alerta** - Similar a la categoría de alerta, para asignar un atributo de gravedad ( **bajo**, **medio**o **alto**) a las directivas de alerta. Al igual que la categoría de alerta, cuando se produce una actividad que coincide con las condiciones de la directiva de la alerta, la alerta que se genera se cuente con el mismo nivel de gravedad que se establece para la directiva de alerta. Una vez más, esto permite realizar un seguimiento y administrar las alertas que tienen el mismo valor de gravedad en la página **Ver avisos** . Por ejemplo, puede filtrar la lista de alertas para que se muestran sólo las alertas con una gravedad **alta** . 
    
    > [!TIP]
    > Al configurar una directiva de alerta, considere la posibilidad de asignar una gravedad superior a las actividades que pueden provocar consecuencias gravemente negativas, como la detección de malware después de la entrega a los usuarios, visualización de datos confidenciales o clasificados, uso compartido de datos con usuarios externos, u otras actividades que pueden dar lugar a las amenazas de seguridad o la pérdida de datos. Esto puede ayudarle a dar prioridad a las alertas y las acciones que hay que realizar para investigar y resolver las causas subyacentes. 
  
- **Notificaciones por correo electrónico** - puede configurar la directiva de modo que las notificaciones de correo electrónico se envían (o no envía) a una lista de los usuarios cuando se desencadena una alerta. También puede establecer un límite de notificación diaria para que una vez que se alcanzó el número máximo de notificaciones, no hay más se envían de la alerta durante ese día. En adicionales para las notificaciones de correo electrónico usted u otro administrador puede ver las alertas que se desencadenan por una directiva en la página **Ver avisos** . Considere la posibilidad de habilitar las notificaciones de correo electrónico para las directivas de alerta de una categoría específica o que tienen un valor mayor de gravedad. 
  
## <a name="default-alert-policies"></a>Directivas de alerta predeterminado

Office 365 proporciona directivas de alerta integradas que ayudan a identificar infracción de permisos de administración de Exchange, la actividad de malware y los riesgos de gobierno de datos. En la página de **directivas de alerta** , el nombre de estas directivas integradas están en negrita y el tipo de directiva se define como **sistema**. Estas directivas están activadas de forma predeterminada. Puede desactivar estas directivas (o volver a aquel en), configurar una lista de destinatarios para enviar notificaciones de correo electrónico a y establecer un límite de notificación diaria. Las demás configuraciones de estas directivas no pueden editarse.
  
En la siguiente tabla se enumera y se describe las directivas de alerta predeterminados disponibles e indica la suscripción de Office 365 Enterprise necesaria para cada uno de ellos. Tenga en cuenta que algunas directivas de alerta predeterminadas están disponibles si su organización tiene la suscripción de complemento apropiado además de una suscripción a E1 o E3. 
  
|**Directiva de alerta predeterminada**|**Descripción**|**Suscripción a Office 365 Enterprise**|
|:-----|:-----|:-----|
|**Creación de regla de reenvío y redireccionamiento** <br/> |Genera una alerta cuando una persona de su organización crea una regla de bandeja de entrada para su buzón que reenvía o redirige los mensajes a otra cuenta de correo electrónico. Esta directiva sólo realiza un seguimiento de las reglas de bandeja de entrada que se crean utilizando Outlook Web App o Exchange Online PowerShell. Esta directiva tiene una configuración de gravedad **baja** . Para obtener más información de uso de las reglas de bandeja de entrada para reenviar y redirigir el correo electrónico en Outlook Web App, vea [usar las reglas de Outlook Web App para reenviar mensajes automáticamente a otra cuenta](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).<br/> |E1, E3 o E5  <br/> |
|**Elevación de privilegios de administración de Exchange** <br/> |Genera una alerta cuando alguien se asigna permisos administrativos en la organización de Exchange Online; Por ejemplo, si un usuario se agrega a la función de administración de la organización grupo en Exchange Online. Esta directiva tiene una configuración de gravedad **baja** .<br/> |E1, E3 o E5  <br/> |
|**Los mensajes se han retrasado** <br/> |Genera una alerta cuando Office 365 no puede entregar mensajes de correo electrónico a la organización local o un socio de servidores mediante el uso de un conector. Cuando esto ocurre, el mensaje se ponen en cola en Office 365. Esta alerta se desencadena cuando hay 2.000 mensajes o más que ha formado por más de una hora. Esta directiva tiene una configuración de gravedad **alta** .<br/> |E1, E3 o E5  <br/> |
|**Campaña de malware detectado después de la entrega** <br/> |Genera una alerta cuando se entrega un número inusualmente grande de los mensajes que contengan malware a buzones de la organización. Si se produce este evento, Office 365 quita los mensajes infectados de buzones de Exchange Online. Esta directiva tiene una configuración de gravedad **alta** .<br/> |Suscripción de complemento E5 o información sobre amenazas de Office 365  <br/> |
|**Campaña de malware detectado y bloqueado** <br/> |Genera una alerta cuando alguien ha intentado enviar un número considerable de mensajes de correo electrónico que contiene un determinado tipo de malware a los usuarios de su organización. Si se produce este evento, los mensajes infectados están bloqueados por Office 365 y no se entregó a buzones de correo. Esta directiva tiene una configuración de gravedad **baja** .<br/> |Suscripción de complemento E5 o información sobre amenazas de Office 365  <br/> |
|**Campaña de malware detectado en SharePoint y OneDrive** <br/> |Genera una alerta cuando se detecta un volumen inusualmente alto de código malintencionado o virus en archivos que se encuentran en los sitios de SharePoint o cuentas de OneDrive en su organización. Esta directiva tiene una configuración de gravedad **alta** .<br/> |Suscripción de complemento E5 o información sobre amenazas de Office 365  <br/> |
|**Actividad de archivo inusual de usuarios externos** <br/> |Genera una alerta cuando un normalmente gran número de actividades se realiza en los archivos de SharePoint o OneDrive por los usuarios externos a su organización. Esto incluye actividades, como obtener acceso a archivos, descarga de archivos y eliminación de archivos. Esta directiva tiene una configuración de gravedad **alta** .<br/> |Suscripción de complemento E5, o información sobre amenazas de Office 365 o cumplimiento avanzada  <br/> |
|**Volumen poco habitual de uso compartido de archivos externos** <br/> |Genera una alerta cuando un normalmente gran número de archivos de SharePoint o OneDrive se comparte con los usuarios externos a su organización. Esta directiva tiene una configuración de gravedad **Media** .<br/> |Suscripción de complemento E5, o información sobre amenazas de Office 365 o cumplimiento avanzada  <br/> |
|**Volumen poco habitual de eliminación de archivos** <br/> |Genera una alerta cuando se elimina un número inusualmente grande de archivos en SharePoint o OneDrive dentro de un marco de hora corta. Esta directiva tiene una configuración de gravedad **Media** .<br/> |Suscripción de complemento E5, o información sobre amenazas de Office 365 o cumplimiento avanzada  <br/> |
|**Aumento inusual en el correo electrónico que se notifiquen como phishing** <br/> |Genera una alerta cuando hay un aumento significativo en el número de personas de la organización utilizando el complemento en el mensaje de informe en Outlook a los mensajes de informe, como correo de suplantación de identidad. Esta directiva tiene una configuración de gravedad **alta** . Para obtener más información acerca de este complemento, consulte [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).<br/> |Suscripción de complemento E5 o información sobre amenazas de Office 365  <br/> |
   
Tenga en cuenta que la actividad inusual supervisada por algunas de las directivas integradas se basa en el mismo proceso tal y como se describió anteriormente establecer el umbral de alerta. Office 365 establece un valor de línea de base que define la frecuencia normal de actividad "normal". A continuación, se desencadenan alertas cuando la frecuencia de las actividades que hace un seguimiento mediante la directiva de alerta integrada en gran medida supera el valor de la línea de base.
 
## <a name="viewing-alerts"></a>Visualización de alertas

Cuando una actividad realizada por los usuarios de su organización coincide con la configuración de una directiva de alerta, se genera una alerta y se muestra en la página **Ver avisos** en la seguridad &amp; centro de cumplimiento. Dependiendo de la configuración de una directiva de alerta, también se envía una notificación de correo electrónico a una lista de usuarios especificados cuando se desencadena una alerta. Para cada alerta, el panel en la página **Ver avisos** muestra el nombre de la directiva de alerta correspondiente, la categoría y gravedad de la alerta (definida en la directiva de alerta) y el número de veces que se ha producido una actividad que resulta en la alerta que se está genera; Este valor se basa en la configuración de umbral de la directiva de alerta. El panel también muestra el estado de cada alerta. Vea la sección [Administrar alertas](#managing-alerts) para obtener más información acerca del uso de la propiedad status para administrar las alertas. 
  
Para ver alertas, vaya a **las alertas de** \> **Ver avisos** en la seguridad &amp; centro de cumplimiento. 
  
![En la seguridad &amp; centro de Complinace, haga clic en alertas, a continuación, haga clic en Ver avisos para ver las alertas](media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)
  
Puede usar los siguientes filtros para ver un subconjunto de todas las alertas en la página **Ver avisos** . 
  
- **Estado** : Use este filtro para mostrar las alertas que se les asigna un estado determinado; el estado predeterminado es **activo**. Usted u otro administrador puede cambiar el valor de estado.
    
- **Directivas** - este filtro se usa para mostrar las alertas que coinciden con la configuración de una o varias directivas de alerta. O bien, sólo se pueden mostrar todas las alertas para todas las directivas de alerta.
    
- **Intervalo de tiempo** - Utilice este filtro para mostrar las alertas que se generaron dentro de un intervalo de tiempo y una fecha específica.
    
- **Gravedad** - este filtro se usa para mostrar las alertas que se le asigna una gravedad específica.
    
- **Categoría** - este filtro se usa para mostrar las alertas desde una o varias categorías de alerta.
    

  
## <a name="managing-alerts"></a>Administrar alertas
<a name="managingalerts"> </a>

Después de que las alertas se han generado y que se muestra en la página **Ver avisos** en la seguridad &amp; centro de cumplimiento, puede detectar, investigar y resolverlos conflictos. A continuación presentamos algunas tareas que puede realizar para administrar las alertas. 
  
- **Asignar un estado de alertas** - puede asignar uno de los siguientes estados para recibir alertas: **activa** (el valor predeterminado), **Investigating**, **resuelto**o **Dismissed**. A continuación, puede filtrar en esta opción para mostrar alertas con la misma configuración de estado. Esta configuración de estado puede ayudar a realizar un seguimiento del proceso de administración de alertas.
    
- **Ver detalles de alerta** : puede hacer clic en una alerta para mostrar una página emergente con detalles acerca de la alerta. La información detallada depende de la directiva de alerta correspondiente, pero normalmente incluye lo siguiente: nombre de la operación real que desencadenan la alerta (por ejemplo, un cmdlet), una descripción de la actividad que desencadenan la alerta, el usuario (o lista de usuarios) que desencadenan la alerta y el nombre (y vínculo a) de la correspondiente de directiva de la alerta.
    
  - El nombre de la operación real que desencadenan la alerta, como un cmdlet o una operación de registro de auditoría.
    
  - Una descripción de la actividad que desencadenan la alerta.
    
  - El usuario que desencadena la alerta; Esto se incluye únicamente para las directivas de alerta que se configuran para realizar un seguimiento de un solo usuario o una sola actividad.
    
  - Se realizó el número de veces que se realiza un seguimiento de la actividad por la alerta. Tenga en cuenta que este número no es posible que coinciden con ese número real de alertas relacionados que aparecen en la página de vista de alertas debido a que es posible que se han activado las alertas adicionales.
    
  - Un vínculo a una lista de actividades que incluye un elemento para cada actividad que se llevó a cabo que desencadenan la alerta. Cada entrada de esta lista identifica cuando se produjo la actividad, el nombre de operación real, (por ejemplo, "FileDeleted") y el usuario que realizó la actividad, el objeto (por ejemplo, un archivo, un caso de exhibición de documentos electrónicos o un buzón de correo) que se realizó la actividad y la dirección IP dirección del equipo del usuario. Para malware relacionadas con las alertas, este vínculos a una lista de mensajes.
    
  - El nombre (y vínculo a) de la directiva de alerta correspondiente.
    
- **Suprimir notificaciones de correo electrónico** - puede desactivar (o suprimir) las notificaciones de correo electrónico de la página emergente para una alerta. Cuando se suprimen las notificaciones de correo electrónico, Office 365 no enviar notificaciones cuando las actividades o los eventos que coinciden con las condiciones de la directiva de alerta. Sin embargo, las alertas seguirán desencadenador cuando las actividades realizadas por los usuarios coinciden con las condiciones de la directiva de alerta. También puede desactivar las notificaciones de correo electrónico mediante la edición de la directiva de alerta.
    
- **Resolver las alertas** - puede marcar una alerta como resuelto en la página emergente para una alerta (que establece el estado de la alerta a **resuelto**). A menos que cambie el filtro, no se muestran alertas resueltos en la página **Ver avisos** . 
    

  


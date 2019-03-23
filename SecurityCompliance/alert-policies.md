---
title: Directivas de alerta en el centro de &amp; seguridad y cumplimiento de Office 365
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
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
description: Cree directivas de alerta en el centro de &amp; seguridad y cumplimiento de Office 365 para supervisar posibles amenazas, pérdidas de datos y problemas de permisos. A continuación, puede ver y administrar las alertas que se generan cuando los usuarios realizan actividades que cumplen las condiciones de una directiva de alertas.
ms.openlocfilehash: c1ae7829b447ebf20f51764257656fe1ff2a3873
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2019
ms.locfileid: "30789425"
---
# <a name="alert-policies-in-the-office-365-security-amp-compliance-center"></a>Directivas de alerta en el centro de &amp; seguridad y cumplimiento de Office 365

Puede usar las nuevas herramientas de la Directiva de alerta y del panel de alertas del &amp; centro de seguridad y cumplimiento de Office 365 para crear directivas de alerta y, a continuación, ver las alertas que se generan cuando los usuarios realizan actividades que cumplen las condiciones de una directiva de alertas. Las directivas de alerta se basan y amplían la funcionalidad de las alertas de actividad permitiéndole clasificar la Directiva de alertas, aplicar la Directiva a todos los usuarios de la organización, establecer un nivel de umbral para cuando se desencadene una alerta y decidir si desea recibir o no el correo electrónico notificaciones. También hay una página **Ver alertas** en el centro de &amp; seguridad y cumplimiento donde puede ver y filtrar las alertas, establecer un estado de alerta que le ayude a administrar las alertas y, a continuación, descartar las alertas después de resolver o resolver el incidente subyacente. También hemos ampliado el tipo de eventos para los que puede crear alertas. Por ejemplo, puede crear directivas de alerta para realizar un seguimiento de las actividades de malware y los incidentes de pérdida de datos. Por último, también hemos incluido una serie de directivas de alerta predeterminadas que le ayudarán a supervisar los privilegios de administración en Exchange Online, los ataques de malware y los niveles inusuales de eliminaciones de archivos y uso compartido externo. 
  
> [!NOTE]
> Las directivas de alerta están disponibles para las organizaciones con una suscripción de Office 365 Enterprise u Office 365 US Government E1/G1, E3/G3 o E5/G5. Sin embargo, algunas funciones avanzadas solo están disponibles para las organizaciones con una suscripción a E5/G5 o para las organizaciones que tienen una suscripción a E1/G1 o E3/G3 y un complemento de protección contra amenazas avanzada (ATP) de Office 365 u Office 365 avanzado. scription. En este tema se resalta la funcionalidad que requiere una suscripción a E5/G5 o un complemento. Además, tenga en cuenta que las directivas de alerta están disponibles en los entornos de Office 365 GCC, GCC High y DoD estadounidense Government.
  
## <a name="how-alert-policies-work"></a>Cómo funcionan las directivas de alertas

A continuación, se presenta una introducción rápida sobre cómo funcionan las directivas de alertas y las alertas que se desencadenan cuando la actividad de usuario o de administrador cumpla las condiciones de una directiva de alerta.
  
![Información general sobre cómo funcionan las directivas de alertas](media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)
  
1. Un administrador de su organización crea, configura y activa una directiva de alertas mediante la página **directivas de alerta** en el centro de seguridad & cumplimiento. También puede crear directivas de alerta con el cmdlet **New-ProtectionAlert** en PowerShell. Para crear directivas de alerta, debe tener asignado el rol configuración de la organización o la función administrar alertas en el centro de seguridad & cumplimiento.
    
2. Un usuario realiza una actividad que coincide con las condiciones de una directiva de alerta. En el caso de ataques de malware, los mensajes de correo electrónico infectados que se envían a los usuarios de su organización activarán una alerta.
    
3. Office 365 genera una alerta que se muestra en la página **Ver alertas** del centro de &amp; seguridad y cumplimiento. Además, si las notificaciones de correo electrónico están habilitadas para la Directiva de alertas, Office 365 envía una notificación a los destinatarios de la lista. Las alertas que un administrador u otros usuarios pueden ver en la página **Ver alertas** está determinada por los roles asignados al usuario. Para obtener más información, consulte la sección [permisos de RBAC necesarios para ver alertas](#rbac-permissions-required-to-view-alerts) .
    
4. Un administrador administra alertas en el centro &amp; de seguridad y cumplimiento. La administración de alertas consiste en asignar un estado de alerta para ayudar a realizar un seguimiento y administrar cualquier investigación.
    
## <a name="alert-policy-settings"></a>Configuración de la Directiva de alerta

Una directiva de alertas se compone de un conjunto de reglas y condiciones que definen la actividad de usuario o de administrador que generará una alerta, una lista de usuarios que desencadenarán la alerta si realizan la actividad y el umbral que define cuántas veces tiene que producirse la actividad antes de un n se desencadena la alerta. También puede clasificar la Directiva y asignarle un nivel de gravedad. Estas dos opciones de configuración ayudan a administrar las directivas de alerta (y las alertas que se desencadenan cuando se cumplen las condiciones de la Directiva) porque se puede filtrar en esta configuración cuando se administran directivas y se ven alertas en el centro de seguridad &amp; y cumplimiento. Por ejemplo, puede ver las alertas que coinciden con las condiciones de la misma categoría o ver alertas con el mismo nivel de gravedad.
  
Para ver y crear directivas de alerta, vaya a **alertas** \> **** de alertas en el &amp; centro de seguridad y cumplimiento. 
  
![En el centro &amp; de Complinace de seguridad, haga clic en alertas y, a continuación, en directivas de alerta para ver y crear directivas de alertas.](media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)
  
Una directiva de alertas consta de los siguientes valores y condiciones.
  
- **Actividad en la que se realiza el seguimiento de la alerta** : cree una directiva para realizar un seguimiento de una actividad o, en algunos casos, de algunas actividades relacionadas, como compartir un archivo con un usuario externo, mediante el uso compartido de la misma, la asignación de permisos de acceso o la creación de un vínculo anónimo. Cuando un usuario realiza la actividad definida por la Directiva, se activa una alerta en función de la configuración del umbral de alerta.
    
    > [!NOTE]
    > Las actividades que puede realizar el seguimiento dependen del plan Office 365 Enterprise u Office 365 US Government de su organización. En general, las actividades relacionadas con las campañas de malware y los ataques de suplantación de identidad requieren una suscripción a E5/G5 o una suscripción a E1/G1 o E3/G3 con una suscripción complementaria de inteligencia sobre amenazas. 
  
- **Condiciones de actividad** : para la mayoría de las actividades, puede definir condiciones adicionales que se deben cumplir para que una alerta se desencadene. Las condiciones comunes incluyen las direcciones IP (por lo que se desencadena una alerta cuando el usuario realiza la actividad en un equipo con una dirección IP específica o dentro de un intervalo de direcciones IP), si se activa una alerta si un usuario o usuarios específicos realizan dicha actividad y si la actividad se realiza en un nombre de archivo o dirección URL específicos. También puede configurar una condición que desencadene una alerta cuando un usuario de la organización realice la actividad. Tenga en cuenta que las condiciones disponibles dependen de la actividad seleccionada.
    
- **Cuando se activa la alerta** , puede configurar una opción que defina la frecuencia con la que se puede producir una actividad antes de que se desencadene una alerta. Esto le permite configurar una directiva para generar una alerta cada vez que una actividad coincida con las condiciones de la Directiva, cuando se supere un umbral determinado, o cuando la ocurrencia de la actividad que está realizando el seguimiento de la alerta es inusual para la organización. 
    
    ![Configurar el modo en que se desencadenan las alertas, en función de Cuándo se produce la actividad, un umbral o una actividad inusual para la organización](media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)
  
    Si selecciona la configuración en función de actividad inusual, Office 365 establece un valor de línea base que define la frecuencia normal para la actividad seleccionada; el establecimiento de esta línea base tarda hasta 7 días en el que no se generarán alertas. Una vez establecida la referencia, se desencadenará una alerta cuando la frecuencia de la actividad a la que se realiza el seguimiento por parte de la Directiva de alerta supere en gran medida el valor de línea base. Para actividades relacionadas con la auditoría (como actividades de archivos y carpetas), puede establecer una línea base basada en un único usuario o en función de todos los usuarios de la organización; para actividades relacionadas con el malware, puede establecer una línea base en una única familia de malware, un solo destinatario o todos los mensajes de la organización.
    
    > [!NOTE]
    > La capacidad de configurar directivas de alerta basadas en un umbral o en una actividad inusual requiere una suscripción a E5/G5 o una suscripción a E1/G1 o E3/G3 con una suscripción de Office 365 ATP o un complemento de cumplimiento avanzado. Las organizaciones con una suscripción a E1/G1 y E3/G3 solo pueden crear una directiva de alertas en la que se desencadene una alerta cada vez que se produzca una actividad. 
  
- **Categoría de alerta** : para ayudar con el seguimiento y la administración de las alertas generadas por una directiva, puede asignar una de las siguientes categorías a una directiva.
    
  - Gobierno de datos
    
Office 365 ATP P2-prevención de pérdida de datos

  - Flujo de correo
    
  - Permisos
    
  - Administración de amenazas
    
  - Otros
    
  Cuando se produce una actividad que coincide con las condiciones de la Directiva de alertas, la alerta que se genera se etiqueta con la categoría definida en esta configuración. Esto le permite realizar un seguimiento y administrar las alertas que tienen la misma configuración de categoría en la página **Ver alertas** del centro de seguridad & cumplimiento, porque puede ordenar y filtrar las alertas basándose en la categoría. 
    
- **Gravedad** de la alerta: similar a la categoría de alerta, asigna un atributo de gravedad ( **baja**, **media**o **alta**) a las directivas de alerta. Al igual que la categoría de alerta, cuando se produce una actividad que coincide con las condiciones de la Directiva de alerta, la alerta que se genera se etiqueta con el mismo nivel de gravedad que se ha establecido para la Directiva de alerta. De nuevo, esto le permite realizar un seguimiento y administrar las alertas que tienen la misma configuración de gravedad en la página **Ver alertas** . Por ejemplo, puede filtrar la lista de alertas para que solo se muestren las alertas con una gravedad **alta** . 
    
    > [!TIP]
    > Al configurar una directiva de alerta, considere la posibilidad de asignar una gravedad mayor a las actividades que puedan dar como resultado consecuencias negativas, como la detección de malware tras la entrega a los usuarios, la visualización de datos confidenciales o clasificados, el uso compartido de datos con usuarios externos. u otras actividades que pueden provocar la pérdida de datos o las amenazas de seguridad. Esto puede ayudarle a priorizar las alertas y las acciones que realiza para investigar y resolver las causas subyacentes. 
  
- **Notificaciones de correo electrónico** : puede configurar la Directiva para que las notificaciones de correo electrónico se envíen (o no se envíen) a una lista de usuarios cuando se desencadene una alerta. También puede establecer un límite de notificación diario para que una vez que se haya alcanzado el número máximo de notificaciones, no se envíen más notificaciones para la alerta durante ese día. En otras notificaciones de correo electrónico, usted u otros administradores pueden ver las alertas desencadenadas por una directiva en la página **Ver alertas** . Considere la posibilidad de habilitar notificaciones de correo electrónico para directivas de alerta de una categoría específica o que tengan una configuración de gravedad más alta. 
  
## <a name="default-alert-policies"></a>Directivas de alertas preDeterminadas

Office 365 proporciona directivas de alerta integradas que ayudan a identificar los permisos de administrador de Exchange, la actividad de malware y los riesgos de gobierno de datos. En la página **directivas de alerta** , el nombre de estas directivas integradas están en negrita y el tipo de Directiva se define como **sistema**. Estas directivas están activadas de forma predeterminada. Puede desactivar estas directivas (o volver a iniciarla), configurar una lista de destinatarios a los que enviar notificaciones por correo electrónico y establecer un límite de notificación diario. No se pueden editar las demás opciones de configuración de estas directivas.
  
En la tabla siguiente se enumeran y describen las directivas de alertas predeterminadas disponibles y la categoría a la que está asignada cada Directiva. Tenga en cuenta que esa categoría se usa para determinar qué alertas puede ver un usuario en la página ver alertas. Para obtener más información, consulte la sección [permisos de RBAC necesarios para ver alertas](#rbac-permissions-required-to-view-alerts) .  

La tabla también indica los planes de Office 365 Enterprise y Office 365 US Government, necesarios para cada uno. Tenga en cuenta que hay disponibles algunas directivas de alerta predeterminadas si su organización tiene la suscripción complementaria correspondiente además de una suscripción a E1/G1 o E3/G3. 
  
|**Directiva de alertas predeterminada**|**Descripción**|**Category**|**Suscripción de Office 365 Enterprise**|
|:-----|:-----|:-----|:-----|
|**Se ha detectado un clic en una dirección URL potencialmente malintencionada** <br/> |Genera una alerta cuando un usuario protege a un usuario de [Office 365 ATP los vínculos seguros](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) de la organización hace clic en un vínculo malintencionado. Este evento se desencadena cuando Office 365 ATP identifica los cambios en la dirección URL o cuando los usuarios invalidan las páginas de vínculos seguros de ATP de Office 365 (en función de la Directiva de vínculos seguros de Office 365 ATP de la organización). Esta directiva de alerta tiene una configuración de gravedad **alta** . Para obtener más información, consulte [configurar las directivas de vínculos seguros de Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies).  <br/> |Administración de amenazas <br/> |Office 365 ATP P2/E5/G5  <br/> |
|**Creación de una regla de reenvío/redireccionamiento** <br/> |Genera una alerta cuando una persona de la organización crea una regla de bandeja de entrada para su buzón que reenvía o redirige los mensajes a otra cuenta de correo electrónico. Esta directiva solo realiza un seguimiento de las reglas de la bandeja de entrada que se crean con Outlook en la web (anteriormente conocido como Outlook Web App) o Exchange Online PowerShell. Esta directiva tiene una configuración de gravedad **baja** . Para obtener más información sobre el uso de reglas de la bandeja de entrada para reenviar y redirigir correo electrónico en Outlook en la web, vea [usar reglas en Outlook en la web para reenviar mensajes automáticamente a otra cuenta](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).  <br/> |Administración de amenazas <br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**búsqueda de exhibición de documentos electrónicos iniciada o exportada** <br/> |Genera una alerta cuando alguien usa la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento. Se desencadena una alerta cuando se realizan las siguientes actividades de búsqueda de contenido: <br/><br/>• Se inicia una búsqueda de contenido<br/>• Los resultados de una búsqueda de contenido se exportan<br/>• Se exporta un informe de búsqueda de contenido<br/><br/>Las alertas también se activada cuando las actividades de búsqueda de contenido anteriores se realizan en asociación con un caso de exhibición de documentos electrónicos. Esta directiva tiene una configuración de gravedad **media** . Para obtener más información acerca de las actividades de búsqueda de contenido, vea [buscar actividades de eDiscovery en el registro de auditoría de Office 365](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities). <br/> |Administración de amenazas<br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**Privilegio de administración de elevación de Exchange** <br/> |Genera una alerta cuando se asignan permisos administrativos a un usuario en la organización de Exchange Online; por ejemplo, si se agrega un usuario al grupo de funciones de administración de la organización en Exchange Online. Esta directiva tiene una configuración de gravedad **baja** .  <br/> |Permisos <br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**Los mensajes se han retrasado** <br/> |Genera una alerta cuando Office 365 no puede entregar mensajes de correo electrónico a su organización local o a servidores asociados mediante un conector. Cuando esto ocurre, el mensaje se coloca en la cola en Office 365. Esta alerta se desencadena cuando hay 2.000 mensajes o más que se han puesto en cola durante más de una hora. Esta directiva tiene una configuración de gravedad **alta** .  <br/> |Flujo de correo<br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|**Campaña de malware detectada tras la entrega** <br/> |Genera una alerta cuando se entrega un número inusualmente grande de mensajes que contienen malware a los buzones de la organización. Si se produce este evento, Office 365 quita los mensajes infectados de los buzones de correo de Exchange Online. Esta directiva tiene una configuración de gravedad **alta** .  <br/> |Administración de amenazas<br/> |Suscripción complementaria E5/G5 o la P2 de Office 365 ATP  <br/> |
|**Campaña de malware detectada y bloqueada** <br/> |Genera una alerta cuando alguien intenta enviar un número inusualmente elevado de mensajes de correo electrónico que contienen un determinado tipo de malware a los usuarios de la organización. Si se produce este evento, los mensajes infectados están bloqueados por Office 365 y no se entregan a los buzones de correo. Esta directiva tiene una configuración de gravedad **baja** .  <br/> |Administración de amenazas<br/> |Suscripción complementaria E5/G5 o la P2 de Office 365 ATP  <br/> |
|**Campaña de malware detectada en SharePoint y OneDrive** <br/> |Genera una alerta cuando se detecta un volumen inusualmente alto de malware o virus en los archivos ubicados en los sitios de SharePoint o en las cuentas de OneDrive de la organización. Esta directiva tiene una configuración de gravedad **alta** .  <br/> |Administración de amenazas<br/> |Suscripción complementaria E5/G5 o la P2 de Office 365 ATP  <br/> |
|**Actividad de archivo de usuario externo inusual** <br/> |Genera una alerta cuando los usuarios que se encuentran fuera de la organización realizan un gran número de actividades en los archivos de SharePoint o OneDrive. Esto incluye actividades como obtener acceso a archivos, descargar archivos y eliminar archivos. Esta directiva tiene una configuración de gravedad **alta** .  <br/> |Gobierno de datos<br/> |La suscripción a E5 o un complemento avanzado de cumplimiento para E5/G5 o la suscripción de Office 365 ATP P2  <br/> |
|**Volumen inusual de uso compartido de archivos externos** <br/> |Genera una alerta cuando se comparte con usuarios fuera de la organización un número normalmente grande de archivos en SharePoint o OneDrive. Esta directiva tiene una configuración de gravedad **media** .  <br/> |Gobierno de datos<br/> |La suscripción a E5 o un complemento avanzado de cumplimiento para E5/G5 o la suscripción de Office 365 ATP P2  <br/> |
|**Volumen inusual de eliminación de archivo** <br/> |Genera una alerta cuando se elimina un número inusualmente grande de archivos en SharePoint o OneDrive en un breve período de tiempo. Esta directiva tiene una configuración de gravedad **media** .  <br/> |Gobierno de datos <br/> |La suscripción a E5 o un complemento avanzado de cumplimiento para E5/G5 o la suscripción de Office 365 ATP P2  <br/> |
|**Aumento inusual de correo electrónico notificado como phish** <br/> |Genera una alerta cuando hay un aumento significativo en el número de personas de la organización mediante el complemento de mensajes de informe en Outlook para notificar los mensajes como phishing mail. Esta directiva tiene una configuración de gravedad **alta** . Para obtener más información sobre este complemento, vea [use the Report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).  <br/> |Administración de amenazas<br/> |Suscripción complementaria E5/G5 o la P2 de Office 365 ATP  <br/> |
|**El usuario restringió el envío de correo electrónico** <br/> |Genera una alerta cuando una persona de la organización tiene restringido el envío de correo saliente. Normalmente, esto se produce cuando una cuenta está en peligro y el usuario aparece en la página **usuarios restringidos** en el centro de seguridad & cumplimiento. (Para obtener acceso a esta página, vaya a **Threat Management > Review >** reStricted users). Esta directiva tiene una configuración de gravedad **alta** . Para obtener más información acerca de los usuarios restringidos, consulte [quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](https://docs.microsoft.com/office365/securitycompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email).  <br/> |Administración de amenazas<br/> |E1/G1, E3/G3 o E5/G5  <br/> |
|||||
   
Tenga en cuenta que la actividad inusual supervisada por algunas de las directivas integradas se basa en el mismo proceso que la configuración del umbral de alerta que se describió anteriormente. Office 365 establece un valor de línea base que define la frecuencia normal para la actividad "normal". A continuación, se desencadenan alertas cuando la frecuencia de las actividades a las que hace referencia la Directiva de alerta integrada supera en gran medida el valor de línea base.
 
## <a name="viewing-alerts"></a>Ver alertas

Cuando una actividad realizada por los usuarios de la organización coincide con la configuración de una directiva de alerta, se genera una alerta y se muestra en la página **Ver alertas** del centro de seguridad &amp; y cumplimiento. En función de la configuración de una directiva de alerta, también se envía una notificación por correo electrónico a una lista de los usuarios especificados cuando se desencadena una alerta. Para cada alerta, el panel de la página **Ver alertas** muestra el nombre de la Directiva de alerta correspondiente, la gravedad y la categoría de la alerta (definida en la Directiva de alerta) y el número de veces que se ha producido una actividad que ha dado lugar a que la alerta se genera Este valor se basa en la configuración de umbral de la Directiva de alerta. El panel también muestra el estado de cada alerta. Consulte la sección [Administrar alertas](#managing-alerts) para obtener más información sobre el uso de la propiedad status para administrar las alertas. 
  
Para ver las alertas, vaya a **alertas** \> **Ver alertas** en el &amp; centro de seguridad y cumplimiento. 
  
![En el centro &amp; de Complinace de seguridad, haga clic en alertas y, a continuación, en ver alertas para ver alertas](media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)
  
Puede usar los siguientes filtros para ver un subconjunto de todas las alertas en la página **Ver alertas** . 
  
- **Estado** : Use este filtro para mostrar las alertas que tienen asignado un estado concreto; el estado predeterminado es **activo**. Usted u otros administradores pueden cambiar el valor de estado.
    
- **Directiva** : Use este filtro para mostrar alertas que coinciden con el valor de una o más directivas de alerta. O bien, solo puede mostrar todas las alertas de todas las directivas de alertas.
    
- **Intervalo de tiempo** : Use este filtro para mostrar las alertas que se generaron en un intervalo de fechas y horas específico.
    
- **Severity** : Use este filtro para mostrar alertas a las que se les haya asignado una gravedad específica.
    
- **Categoría** : Use este filtro para mostrar alertas de una o varias categorías de alertas.

- **Origen** : Use este filtro para mostrar las alertas desencadenadas por las directivas de alerta en el centro de seguridad & cumplimiento o las alertas desencadenadas por las directivas de seguridad de aplicaciones de nube de Office 365 o ambas. Para obtener más información sobre las alertas de seguridad de la aplicación de nube de Office 365, consulte la sección [visualización de alertas de Cloud App Security](#viewing-cloud-app-security-alerts) .

## <a name="rbac-permissions-required-to-view-alerts"></a>Permisos de RBAC necesarios para ver las alertas

> [!NOTE]
> La funcionalidad que se describe en esta sección se implementará en las organizaciones que comienzan el 20 de febrero de 2019 y se completará en todo el mundo a finales de marzo de 2019.

Los permisos de control de acceso de base de roles (RBAC) asignados a los usuarios de la organización determinan las alertas que puede ver un usuario en la página **Ver alertas** . ¿Cómo se consigue? Las funciones de administración asignadas a los usuarios (según su pertenencia a grupos de roles en el centro de seguridad & cumplimiento) determinan las categorías de alertas que puede ver un usuario en la página **Ver alertas** . Estos son algunos ejemplos:

- Los miembros del grupo de roles de administración de registros solo pueden ver las alertas generadas por las directivas de alertas que tienen asignada la categoría **gobierno de datos** .

- Los miembros del grupo de roles de administrador de cumplimiento no pueden ver alertas generadas por las directivas de alerta asignadas a la categoría **Administración de amenazas** . 

- Los miembros del grupo de roles eDiscovery Manager no pueden ver las alertas porque ninguno de los roles asignados proporciona permisos para ver las alertas de cualquier categoría de alerta.

Este diseño (basado en los permisos RBAC) le permite determinar qué alertas pueden ver (y administrar) los usuarios de roles de trabajo específicos de su organización. 

En la siguiente tabla se enumeran las funciones necesarias para ver las alertas de las seis categorías de alertas diferentes. En la primera columna de la tabla se enumeran todos los roles del centro de seguridad & cumplimiento.  Una marca de verificación indica que un usuario que tiene asignada esa función puede ver alertas de la categoría de alerta correspondiente que aparece en la fila superior.

Para ver a qué categoría se asigna una directiva de alerta predeterminada, consulte la tabla de la sección [directivas de alertas](#default-alert-policies) predeterminadas.

|<br/>|Gobierno de datos|Prevención de pérdida de datos|Flujo de correo|Permisos|Administración de amenazas|Otros | 
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Registros de auditoría <br/> |         ||         |         |         |         |
|Administración de casos <br/>|         |         |         |         |         |         |
|Administrador de cumplimiento<br/>|![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Búsqueda de cumplimiento<br/>|         |         |         |         |         |         |
|Administración de dispositivos<br/>|         |         |         |         |         |         |
|Administración de disposición<br/>|         |         |         |         |         |         |
|Administración de cumplimiento de DLP<br/>|         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |
|Exportar<br/>|         |         |         |         |         |         |
|Retención<br/>|         |         |         |         |         |         |
|Administrar alertas<br/>|         |         |         |         |         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configuración de la organización|         |         |         |         |         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Vista previa <br/>|         |         |         |         |         |         |
|Administración de registros <br/>|![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Administración de retención <br/>| ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|Revisar <br/>|         |         |         |         |         |         |
|DesCifrado de RMS<br/>|         |         |         |         |         |         |
|Administración de funciones<br/>|         |         |         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |
|Búsqueda y dePuración<br/>|         |         |         |         |         |         |
|Administrador de seguridad<br/>||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| | ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Lector de seguridad<br/>|         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| | ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|Vista de garantía del servicio<br/>|         |         |         |         |         |         |
|Administrador de revisión de supervisión<br/>|         |         |         |         |         |         |
|Registros de auditoría de solo vista<br/>|         |         |         |         |         |         |
|Administración de dispositivos de solo vista<br/>|         |         |         |         |         |         |
|Administración de cumplimiento de DLP de solo vista<br/>|         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |
|Ver-solo administrar alertas<br/>|         |         |         |         |         |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Destinatarios con permiso de vista<br/>|         |         |  ![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         ||         |
|Administración de registros de solo vista<br/>|![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|View-Only reTention Management<br/>|![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|         |         |         |         |         |
|         |         |         |         |         |         |

**Sugerencia:** Para ver los roles asignados a cada uno de los grupos de roles predeterminados, ejecute los siguientes comandos en Security & Compliance Center PowerShell: 

```
$RoleGroups = Get-RoleGroup

$RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
```
También puede ver las funciones asignadas a un grupo de funciones en el centro de seguridad & cumplimiento. Vaya a la página de **permisos** y haga clic en un grupo de roles. Los roles asignados se enumeran en la página de flotante.


## <a name="managing-alerts"></a>Administración de alertas

Después de generar y mostrar las alertas en la página **Ver alertas** del centro de &amp; seguridad y cumplimiento, puede clasificarlas, investigarlas y resolverlas. Estas son algunas de las tareas que puede realizar para administrar las alertas. 
  
- **Asignar un estado a alertas** : puede asignar uno de los siguientes Estados a Alerts: **Active** (el valor predeterminado), **investigando**, **resuelto**o desechado. **** A continuación, puede filtrar según esta configuración para que se muestren las alertas con la misma configuración de estado. Esta configuración de estado puede ayudar a realizar un seguimiento del proceso de administración de alertas.
    
- **Ver detalles de alertas** : puede hacer clic en una alerta para mostrar una página de control flotante con detalles sobre la alerta. La información detallada depende de la Directiva de alerta correspondiente, pero normalmente incluye lo siguiente: nombre de la operación real que desencadenó la alerta (por ejemplo, un cmdlet), una descripción de la actividad que desencadenó la alerta, el usuario (o la lista de usuarios) Quién desencadenó la alerta y el nombre (y vincular a) de la Directiva de alerta correspondiente.
    
  - Nombre de la operación real que desencadenó la alerta, como un cmdlet o una operación de registro de auditoría.
    
  - Descripción de la actividad que desencadenó la alerta.
    
  - El usuario que desencadenó la alerta; Esto solo se incluye para las directivas de alerta que se configuran para realizar el seguimiento de un único usuario o de una actividad única.
    
  - El número de veces que se ha realizado la actividad de la que se realizó el seguimiento en la alerta. Tenga en cuenta que es posible que este número no concuerda con el número real de alertas relacionadas que aparecen en la página ver alertas porque es posible que se hayan desencadenado alertas adicionales.
    
  - Un vínculo a una lista de actividades que incluye un elemento para cada actividad que haya realizado la activación de la alerta. Cada entrada de esta lista identifica Cuándo se produjo la actividad, el nombre de la operación real (por ejemplo, "FileDeleted") y el usuario que realizó la actividad, el objeto (por ejemplo, un archivo, un caso de exhibición de documentos electrónicos o un buzón) en el que se realizó la actividad, y la IP Dirección del equipo del usuario. En el caso de alertas relacionadas con malware, se vincula a una lista de mensajes.
    
  - El nombre (y vincular a) de la Directiva de alerta correspondiente.
    
- **Suprimir notificaciones por correo electrónico** : puede desactivar (o suprimir) las notificaciones de correo electrónico de la página de control flotante para una alerta. Cuando se suprimen las notificaciones de correo electrónico, Office 365 no enviará notificaciones cuando se realicen actividades o eventos que cumplan las condiciones de la Directiva de alertas. Sin embargo, las alertas seguirán activando cuando las actividades realizadas por los usuarios coinciden con las condiciones de la Directiva de alertas. También puede desactivar las notificaciones de correo electrónico editando la Directiva de alertas.
    
- **Resolver alertas** : puede marcar una alerta como resuelta en la página de control flotante para una alerta (que establece el estado de la alerta como **resuelto**). A menos que cambie el filtro, las alertas resueltas no se mostrarán en la página **Ver alertas** . 
    
## <a name="viewing-cloud-app-security-alerts"></a>Visualización de alertas de Cloud App Security
  
Las alertas que se desencadenan con Office 365 Cloud App Security Policies ahora se muestran en la página **Ver alertas** del centro de seguridad & cumplimiento. Esto incluye las alertas que se desencadenan por las directivas y alertas de actividad que se desencadenan con las directivas de detección de anomalías en Office 365 Cloud App Security. Esto significa que puede ver todas las alertas en el centro de cumplimiento de seguridad &. Tenga en cuenta que la seguridad de la aplicación de nube de Office 365 solo está disponible para las organizaciones con una suscripción a Office 365 Enterprise E5 o Office 365 US Government G5. Para obtener más información, vea [información general sobre Office 365 Cloud App Security](office-365-cas-overview.md).

Además, las organizaciones que tienen Microsoft Cloud App Security como parte de una suscripción a Enterprise Mobility + Security E5 o como un servicio independiente también pueden ver las alertas de Cloud App Security relacionadas con los servicios y aplicaciones de Office 365 en la &? n de seguridad. Centro de cumplimiento.

Para mostrar solo alertas de Cloud App Security en el centro de seguridad & cumplimiento, use el filtro **origen** y seleccione **Cloud App Security**.

![Usar el filtro de origen para mostrar solo alertas de Cloud App Security](media/FilterCASAlerts.png)

Al igual que una alerta desencadenada por una directiva de alertas del centro de cumplimiento de & de seguridad, puede hacer clic en alerta de Cloud App Security para mostrar una página de control flotante con detalles sobre la alerta. La alerta incluye un vínculo para ver los detalles y administrar la alerta en Cloud App Security portal y un vínculo a la Directiva de seguridad de la aplicación de nube correspondiente que activó la alerta. Consulte [revisar y emprender acciones sobre las alertas de Office 365 Cloud App Security](review-office-365-cas-alerts.md).

![Detalles de alertas contienen vínculos al portal de Cloud App Security](media/CASAlertDetail.png)

> [!IMPORTANT]
> Al cambiar el estado de una alerta de Cloud App Security en el centro de seguridad & cumplimiento no se actualizará el estado de resolución de la misma alerta en Cloud App Security portal. Por ejemplo, si marca el estado de la alerta como **resuelto** en el centro de seguridad & cumplimiento, el estado de la alerta en Cloud App Security Portal no cambia. Para resolver o descartar una alerta de Cloud App Security, administre la alerta en Cloud App Security portal.

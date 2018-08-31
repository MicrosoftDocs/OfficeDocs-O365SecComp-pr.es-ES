---
title: Crear alertas de actividad en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: Agregar y administrar alertas de actividad en la seguridad &amp; centro de cumplimiento para que Office 365 se envíen notificaciones por correo electrónico cuando los usuarios realizan actividades específicas en Office 365.
ms.openlocfilehash: 409c1ff4c7fdd0d2d071bdb2eab08ec49357ed8a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536589"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a>Crear alertas de actividad en la seguridad de Office 365 &amp; centro de cumplimiento

Puede crear una alerta de actividad que se va a enviar una notificación de correo electrónico cuando los usuarios realizan actividades específicas en Office 365. Alertas de actividad son similares a la búsqueda de eventos en el registro de auditoría de Office 365, excepto en que se le enviará un mensaje de correo electrónico cuando un evento para una actividad que se ha creado una alerta para sucede. 
  
 **¿Por qué usar alertas de actividad en lugar de buscar el registro de auditoría?** Puede haber ciertos tipos de actividad o realizadas por usuarios específicos que realmente desea conocer. En lugar de tener que recordar buscar el registro de auditoría para esas actividades, puede usar las alertas de actividad para que Office 365 enviarle un mensaje de correo electrónico cuando los usuarios realizan dichas actividades. Por ejemplo, puede crear una alerta de actividad para avisarle cuando un usuario elimina los archivos de SharePoint o puede crear una alerta que le notifique cuando un usuario elimina permanentemente los mensajes de su buzón. La notificación de correo electrónico enviada a la incluye información sobre qué actividad se llevó a cabo y el usuario que la ha realizado. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe tener asignado el rol de la configuración de la organización en la seguridad &amp; centro de cumplimiento para administrar las alertas de actividad. De forma predeterminada, este rol se asigna a los grupos de roles de administrador de cumplimiento de normas y administración de la organización. Para obtener más información acerca de cómo agregar miembros a grupos de roles, consulte [dar a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento](grant-access-to-the-security-and-compliance-center.md).
    
- Usted (u otro administrador) debe activar el registro de auditoría para la organización antes de empezar a usar las alertas de actividad. Para ello, haga clic en **Iniciar grabación de usuario y la actividad de administración** en la página **alertas de actividad** . (Si no ve este vínculo, auditoría ha ya se ha activado para la organización.) También puede activar la auditoría en la página de **búsqueda de registro de auditoría** en la seguridad &amp; centro de cumplimiento (vaya a **búsqueda &amp; investigación** \> **búsqueda de registro de auditoría**). Sólo debe hacer esto una vez para su organización.
    
- Puede usar la página de **alertas** en la seguridad &amp; centro de cumplimiento para crear alertas sólo para la actividad de los usuarios que aparecen en la libreta de direcciones de su organización. No puede usar esta página para crear alertas para la actividad de los usuarios externos. 
    
- Ver la [información más](#more-information) de sección para obtener una lista de escenarios comunes (y la actividad específica para supervisar) que pueden crear alertas para. 
    
- Puede crear alertas para las mismas actividades que puede buscar en el registro de auditoría de Office 365. 
    
## <a name="create-an-activity-alert"></a>Crear una alerta de actividad

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En el panel izquierdo, haga clic en **alertas**y, a continuación, haga clic en **Administrar alertas**.
    
4. En la página **alertas de actividad** , haga clic en **Agregar una alerta**.
    
    ![Agregar una alerta de actividad](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
5. Complete los campos siguientes para crear una alerta:
    
    a. **nombre** - escriba un nombre para la alerta. Los nombres de alertas deben ser únicos dentro de la organización.
    
    b. **Descripción** (opcional): se Describe la alerta, como las actividades y los usuarios que está realizando un seguimiento, y los usuarios que las notificaciones de correo electrónico se envían a. Las descripciones proporcionan un modo rápido y fácil para describir el propósito de la alerta para otros administradores.
    
    c. **Enviar esta alerta cuándo** - haga clic en **Enviar esta alerta cuándo** y, a continuación, configurar estos dos campos:
    
    - **Actividades** - haga clic en la lista desplegable de lista para mostrar las actividades que puede crear una alerta para. Se trata de la misma lista de actividades que se muestra al buscar en el registro de auditoría de Office 365. Puede seleccionar uno o más actividades específicas o puede hacer clic en el nombre del grupo de actividad para seleccionar todas las actividades en el grupo. Para obtener una descripción de estas actividades, vea la sección "Auditar actividades" en [el registro de auditoría en el centro de cumplimiento de seguridad de Office 365 y de búsqueda](search-the-audit-log-in-security-and-compliance.md#audited-activities). Cuando un usuario realiza alguna de las actividades que ha agregado a la alerta, se envía una notificación de correo electrónico. 
    
     - **Los usuarios** - haga clic en este cuadro y, a continuación, seleccione uno o varios usuarios. Si los usuarios de este cuadro de llevar a cabo las actividades que ha agregado al cuadro de **actividades** , se enviará una alerta. Deje el cuadro **usuarios** en blanco para enviar una alerta cuando cualquier usuario de la organización lleva a cabo las actividades especificadas por la alerta. 
    
    d. **Enviar esta alerta a** - haga clic en **Enviar esta alerta**y, a continuación, haga clic en el cuadro **destinatarios** y escriba un nombre para agregar un usuarios que recibirán una notificación de correo electrónico cuando un usuario (especificado en el cuadro **usuarios** ) realiza una actividad (especificado en el Cuadro de **actividades** ). Tenga en cuenta que se agregan a la lista de destinatarios de forma predeterminada. Puede quitar el nombre de esta lista.
    
6. Haga clic en **Guardar** para crear la alerta. 
    
    La nueva alerta se muestra en la lista en la página **alertas de actividad** . 
    
    ![Se muestra una lista de alertas en la página de alertas de actividad en la seguridad &amp; centro de cumplimiento](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    El estado de la alerta se establece en **On**. Tenga en cuenta que también se enumeran los destinatarios que recibirán una notificación de correo electrónico cuando se envía una alerta. 
  
## <a name="turn-off-an-activity-alert"></a>Desactivar una alerta de actividad

Puede desactivar una alerta de actividad para que no se envía una notificación de correo electrónico. Después de desactivar la alerta de actividad, aún se muestra en la lista de alertas de actividad para su organización y, aún puede ver sus propiedades.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En el panel izquierdo, haga clic en **alertas**y, a continuación, haga clic en **Administrar alertas de actividad**.
    
4. En la lista de alertas para su organización, haga clic en la alerta que desea desactivar.
    
5. En la página **Editar alerta** , haga clic en el conmutador de alternancia **en** para cambiar el estado a **desactivar**y, a continuación, haga clic en **Guardar**.
    
    El estado de la alerta en las páginas de alertas de actividad está establecido en **Off**. 
    
Para activar una alerta de actividad, repita estos pasos y haga clic en el conmutador de alternancia **desactivada** para cambiar el estado **activado**.
  
## <a name="more-information"></a>Más información

- Este es un ejemplo de la notificación de correo electrónico que se envía a los usuarios que se especifican en la Sent esta alerta al campo (y que aparece en **los destinatarios** en la página **alertas de actividad** ) en la seguridad &amp; centro de cumplimiento. 
    
    ![Ejemplo de un notificaciones de correo electrónico enviado para una alerta de actividad](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Son de aquí las alertas de algunas actividades de documentos y correo electrónico comunes que puede crear una actividad de. Las tablas se describe la actividad, el nombre de la actividad para crear una alerta para y el nombre del grupo de actividades que aparece bajo la actividad en la lista desplegable de **actividades** . Para ver una lista completa de las actividades que se pueden crear alertas de actividad para, vea la sección "Auditar actividades" en [el registro de auditoría en el centro de cumplimiento de seguridad de Office 365 y de búsqueda](search-the-audit-log-in-security-and-compliance.md#audited-activities).
    
    > [!TIP]
    > Es posible que desee crear una alerta de actividad para una sola actividad que se lleva a cabo por cualquier usuario. O es posible que desee crear una alerta de actividad que realizar un seguimiento de varias actividades realizadas por uno o más usuarios. 
  
    En la siguiente tabla se enumera algunas actividades comunes relacionadas con los documentos de SharePoint o OneDrive para la empresa.
    
    |**Cuando un usuario hace esto...**|**Crear una alerta para esta actividad**|**Grupo de actividades**|
    |:-----|:-----|:-----|
    |Visualiza un documento de un sitio.  <br/> |Archivo de acceso  <br/> |Actividades de archivo y carpeta  <br/> |
    |Edita o cambia un documento.  <br/> |Archivo modificado  <br/> |Actividades de archivo y carpeta  <br/> |
    |Comparte un documento con un usuario fuera de la organización.  <br/> |Compartir el archivo, carpeta o sitio  <br/> Y  <br/> Crear invitación de uso compartido  <br/> Para obtener más información, vea [uso de uso compartido de auditoría en el registro de auditoría de Office 365](use-sharing-auditing.md).  <br/> |Actividades de solicitud de acceso y uso compartido  <br/> |
    |Carga o descarga un documento.  <br/> |Archivo cargado  <br/> O  <br/> Archivo descargado  <br/> |Actividades de archivo y carpeta  <br/> |
    |Cambia los permisos de acceso a un sitio.  <br/> |Permisos de sitio modificado  <br/> |Actividades de administración del sitio  <br/> |

    En la siguiente tabla se enumera algunas actividades comunes relacionados con el correo electrónico en Exchange Online.

    |**Cuando un usuario hace esto...**|**Crear una alerta para esta actividad**|**Grupo de actividades**|
    |:-----|:-----|:-----|
    |Permanentemente (purga) elimina un correo electrónico mensaje desde su buzón.  <br/> |Mensajes purgados desde el buzón de correo  <br/> | Actividades de buzón de correo de Exchange  <br/> |
    |Envía un mensaje de correo electrónico desde un buzón compartido.  <br/> |Envía el mensaje con permisos Enviar como  <br/> Y  <br/> Envía el mensaje con los permisos Enviar en nombre  <br/> | Actividades de buzón de correo de Exchange  <br/> |
   
- También puede usar los cmdlets **New-ActivityAlert** y **Set-ActivityAlert** en seguridad &amp; PowerShell de centro de cumplimiento para crear y editar las alertas de actividad. Si utiliza estos cmdlets para crear o editar alertas de actividad, tenga en cuenta lo siguiente: 
    
  - Si usa un cmdlet para agregar una actividad a la alerta de que no se enumeran en la lista desplegable de **actividades** , se muestra un mensaje en la página de propiedades de la alerta que dice, "esta alerta tiene operaciones personalizadas no aparece en el selector de". 
    
  - Es una buena razón para usar los cmdlets para crear o editar una alerta de actividad enviar notificaciones por correo electrónico a una persona ajena a su organización. Este usuario externo se enumerarán en la lista de destinatarios de la alerta. Pero si se quita este usuario externo de la alerta, que el usuario no se vuelven a agregar a la alerta mediante el uso de **alerta de editar** página en la seguridad &amp; centro de cumplimiento. Aquí tiene que volver a agregar el usuario externo con el cmdlet **Set-ActivityAlert** , o use el cmdlet **New-ActivityAlert** para agregar el usuario externo mismo (o diferente) a una nueva alerta. 
    
  


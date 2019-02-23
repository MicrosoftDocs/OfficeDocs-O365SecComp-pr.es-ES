---
title: Crear alertas de actividad en el centro de &amp; seguridad y cumplimiento de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: Agregue y administre alertas de actividad en &amp; el centro de seguridad y cumplimiento para que Office 365 le envíe notificaciones por correo electrónico cuando los usuarios realicen actividades específicas en Office 365.
ms.openlocfilehash: 25262105332b5317ddf29d49e0364faed57f3d3a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214910"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a>Crear alertas de actividad en el centro de &amp; seguridad y cumplimiento de Office 365

Puede crear una alerta de actividad que le envíe una notificación por correo electrónico cuando los usuarios realicen actividades específicas en Office 365. Las alertas de actividad son similares a la búsqueda de eventos en el registro de auditoría de Office 365, excepto que se le enviará un mensaje de correo electrónico cuando se produzca un evento para una actividad para la que ha creado una alerta. 
  
 **¿Por qué usar alertas de actividad en lugar de buscar en el registro de auditoría?** Puede haber ciertos tipos de actividades o actividades realizadas por usuarios específicos que realmente desee conocer. En lugar de tener que recordar que debe buscar en el registro de auditoría las actividades, puede usar alertas de actividad para que Office 365 le envíe un mensaje de correo electrónico cuando los usuarios realicen esas actividades. Por ejemplo, puede crear una alerta de actividad que le avise cuando un usuario elimine archivos en SharePoint o puede crear una alerta que le avise cuando un usuario elimine mensajes de su buzón de forma permanente. La notificación de correo electrónico que se envía a usted incluye información sobre la actividad que se ha realizado y el usuario que la realizó. 

> [!NOTE]
> Le recomendamos que empiece a usar directivas de alerta en el centro de seguridad & cumplimiento en lugar de crear nuevas alertas de actividad. Las directivas de alerta proporcionan funciones adicionales, como la capacidad de crear una directiva de alerta que active una alerta cuando un usuario realice una actividad específica y muestre alertas en la página **Ver alertas** del centro de seguridad & cumplimiento. Para obtener más información, consulte [Alert policies en el centro &amp; de seguridad y cumplimiento de Office 365](alert-policies.md).
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe tener asignado el rol configuración de la organización en el &amp; centro de seguridad y cumplimiento para administrar las alertas de actividad. De forma predeterminada, este rol se asigna a los grupos de roles administrador de cumplimiento y administración de la organización. Para obtener más información acerca de cómo agregar miembros a los grupos de roles, consulte [conceder acceso &amp; a los usuarios al centro de seguridad y cumplimiento de Office 365](grant-access-to-the-security-and-compliance-center.md).
    
- Usted (u otro administrador) debe activar primero el registro de auditoría de su organización para poder empezar a usar alertas de actividad. Para ello, haga clic en **empezar a registrar la actividad de usuario y de administrador** en la página de **alertas de actividades** . (Si no ve este vínculo, ya se ha activado la auditoría en su organización). También puede activar la auditoría en la página de **búsqueda del registro de auditoría** en el &amp; centro de seguridad y cumplimiento (vaya a **búsqueda de registro de auditoría**de investigación \> de **búsqueda &amp; ** ). Solo tiene que hacer esto una vez para su organización.
  
- Puede crear alertas para las mismas actividades que puede buscar en el registro de auditoría de Office 365. Consulte la sección [More Information](#more-information) para obtener una lista de los escenarios comunes (y la actividad específica para supervisar) para los que puede crear alertas. 
    
- Puede usar la página de **alertas de actividades** en el &amp; centro de seguridad y cumplimiento para crear alertas solo para las actividades realizadas por los usuarios que aparecen en la libreta de direcciones de la organización. No puede usar esta página para crear alertas para actividades realizadas por usuarios externos que no se enumeran en la libreta de direcciones. 
    
## <a name="create-an-activity-alert"></a>Crear una alerta de actividad

1. Vaya a [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En la **Página alertas de actividad** , ![haga clic](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) en agregar icono **nuevo**.

   Se muestra la página de control flotante para crear una alerta de actividad.

    
    ![Crear una alerta de actividad](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Complete los siguientes campos para crear una alerta de actividad:
    
    a. **nombre** : escriba un nombre para la alerta. Los nombres de alerta deben ser únicos dentro de la organización.
    
    b. **Descripción** (opcional): describir la alerta, como las actividades y los usuarios de los que se realiza un seguimiento, y los usuarios a los que se envían las notificaciones por correo electrónico. Las deScripciones proporcionan una forma rápida y sencilla de describir el propósito de la alerta a otros administradores.
    
    c. **tipo de alerta** : Asegúrese de que está seleccionada la opción **personalizada** . 

    d. **enviar esta alerta cuando** haga clic en **enviar esta alerta cuando** y, a continuación, configure estos dos campos:
    
    - **Actividades** : haga clic en la lista desplegable para mostrar las actividades para las que puede crear una alerta. Se trata de la misma lista de actividades que se muestra al buscar en el registro de auditoría de Office 365. Puede seleccionar una o más actividades específicas o puede hacer clic en el nombre del grupo de actividades para seleccionar todas las actividades del grupo. Para obtener una descripción de estas actividades, consulte la sección "actividades auditadas" en [Buscar el registro de auditoría en el centro de seguridad _AMP_ cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md#audited-activities). Cuando un usuario realiza alguna de las actividades que ha agregado a la alerta, se envía una notificación por correo electrónico. 
    
     - **Usuarios** : haga clic en este cuadro y, a continuación, seleccione uno o más usuarios. Si los usuarios de este cuadro realizan las actividades que agregó al cuadro **actividades** , se enviará una alerta. Deje el cuadro **usuarios** en blanco para enviar una alerta cuando un usuario de la organización realice las actividades especificadas por la alerta. 

    e. **enviar esta alerta a** : haga clic en **enviar esta alerta**y, a continuación, haga clic en el cuadro **destinatarios** y escriba un nombre para agregar a los usuarios que recibirán una notificación por correo electrónico cuando un usuario (especificado en el cuadro **usuarios** ) realice una actividad (especificada en el campo Cuadro **actividades** ). Tenga en cuenta que se agrega a la lista de destinatarios de forma predeterminada. Puede quitar su nombre de esta lista.
    
5. Haga clic en **Guardar** para crear la alerta. 
    
    La nueva alerta se muestra en la lista de la página de **alertas de actividades** . 
    
    ![Se muestra una lista de alertas en la página de alertas de actividades del &amp; centro de seguridad y cumplimiento](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    El estado de la alerta se establece **en activado**. Tenga en cuenta que los destinatarios que recibirán una notificación de correo electrónico cuando se envíe una alerta también se mostrarán en la lista. 
  
## <a name="turn-off-an-activity-alert"></a>Desactivar una alerta de actividad

Puede desactivar una alerta de actividad para que no se envíe una notificación de correo electrónico. Después de desactivar la alerta de actividad, sigue apareciendo en la lista de alertas de actividad de la organización, y todavía puede ver sus propiedades.
  
1. Vaya a [https://protection.office.com/#/managealerts](https://protection.office.com/#/managealerts).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En la lista de alertas de actividad de su organización, haga clic en la alerta que desea desactivar.
    
4. En la página **Editar alerta** , haga clic **** en el conmutador al alternar para cambiar el estado a desactivado y, a continuación, haga clic en **Guardar**. ****
    
    El estado de la alerta en las páginas de **alertas de actividades** está establecido en desactivado. **** 
    
Para volver a activar una alerta de actividad, repita estos pasos y haga clic en el conmutador **desactivar** alternancia para cambiar el estado a **activado**.
  
## <a name="more-information"></a>Más información

- Este es un ejemplo de la notificación de correo electrónico que se envía a los usuarios especificados en el campo enviado esta alerta a (y que **** se enumeran en destinatarios en la página de alertas &amp; de **actividad** ) en el centro de seguridad y cumplimiento. 
    
    ![Ejemplo de notificación de correo electrónico enviada para una alerta de actividad](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Estas son algunas de las actividades de documento y correo electrónico comunes para las que puede crear una alerta de actividad. En las tablas se describe la actividad, el nombre de la actividad para la que se va a crear una alerta y el nombre del grupo de actividad en el que se muestra la actividad en la lista desplegable **actividades** . Para ver una lista completa de las actividades para las que puede crear alertas de actividad, consulte la sección "actividades auditadas" en [Buscar el registro de auditoría en el centro de seguridad _AMP_ cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md#audited-activities).
    
    > [!TIP]
    > Es posible que desee crear una alerta de actividad para una sola actividad realizada por cualquier usuario. O bien, es posible que desee crear una alerta de actividad que realice un seguimiento de varias actividades realizadas por uno o más usuarios. 
  
    En la tabla siguiente se enumeran algunas actividades comunes relacionadas con el documento en SharePoint o OneDrive para la empresa.
    
    |**Cuando un usuario hace esto...**|**Crear una alerta para esta actividad**|**Grupo de actividad**|
    |:-----|:-----|:-----|
    |Ve un documento en un sitio.  <br/> |Archivo de acceso  <br/> |Actividades de archivos y carpetas  <br/> |
    |Modifica o modifica un documento.  <br/> |Archivo modificado  <br/> |Actividades de archivos y carpetas  <br/> |
    |Comparte un documento con un usuario de fuera de la organización.  <br/> |Compartir archivo, carpeta o sitio  <br/> Y  <br/> Invitación para uso compartido creada  <br/> Para obtener más información, vea [usar la auditoría de uso compartido en el registro de auditoría de Office 365](use-sharing-auditing.md).  <br/> |Actividades de solicitud de acceso y uso compartido  <br/> |
    |Carga o descarga un documento.  <br/> |Archivo cargado  <br/> Y/o  <br/> Archivo desCargado  <br/> |Actividades de archivos y carpetas  <br/> |
    |Cambia los permisos de acceso a un sitio.  <br/> |Permisos de sitio modificados  <br/> |Actividades de administración del sitio  <br/> |

    En la tabla siguiente se enumeran algunas actividades comunes relacionadas con el correo electrónico en Exchange Online.

    |**Cuando un usuario hace esto...**|**Crear una alerta para esta actividad**|**Grupo de actividad**|
    |:-----|:-----|:-----|
    |Elimina de forma permanente (purga) un mensaje de correo electrónico de su buzón.  <br/> |Mensajes purgados del buzón  <br/> | Actividades de buzón de Exchange  <br/> |
    |Envía un mensaje de correo electrónico desde un buzón compartido.  <br/> |Mensaje enviado con los permisos enviar como  <br/> Y  <br/> Mensaje enviado con los permisos enviar en nombre de  <br/> | Actividades de buzón de Exchange  <br/> |
   
- También puede usar los cmdlets **New-ActivityAlert** y **set-ActivityAlert** en el centro &amp; de seguridad y cumplimiento de PowerShell para crear y editar alertas de actividad. Tenga en cuenta lo siguiente si usa estos cmdlets para crear o editar alertas de actividad: 
    
  - Si usa un cmdlet para agregar una actividad a la alerta que no aparece en la lista desplegable **actividades** , se muestra un mensaje en en la página de propiedades de la alerta que indica: "esta alerta tiene operaciones personalizadas no incluidas en el selector". 
    
  - Una buena razón para usar los cmdlets para crear o editar una alerta de actividad es enviar notificaciones por correo electrónico a alguien fuera de la organización. Este usuario externo se mostrará en la lista de destinatarios de la alerta. Pero si quita este usuario externo de la alerta, ese usuario no puede volver a agregarse a la alerta mediante editar la página de **alerta** en el &amp; centro de seguridad y cumplimiento. Tendrá que volver a agregar el usuario externo mediante el cmdlet **set-ActivityAlert** , o bien usar el cmdlet **New-ActivityAlert** para agregar el mismo usuario externo (o diferente) a una nueva alerta. 
    
  


---
title: Auditar el uso compartido para buscar recursos compartidos con usuarios externos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection: M365-security-compliance
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 'El uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa. Los administradores ahora pueden usar la auditoría de uso compartido en el registro de auditoría de Office 365 para identificar recursos que se han compartido con usuarios fuera de la organización. '
ms.openlocfilehash: 54fa32ec9ed16a65354eb845421c56f6d58559e4
ms.sourcegitcommit: c8ea7c0900e69e69bd5c735960df70aae27690a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "36258573"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Auditar el uso compartido para buscar recursos compartidos con usuarios externos

El uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa, y se usa ampliamente en organizaciones de Office 365. Los administradores pueden usar la auditoría de uso compartido en el registro de auditoría de Office 365 para determinar cómo se usa el uso compartido en su organización. 
  
## <a name="the-sharepoint-sharing-schema"></a>El esquema de uso compartido de SharePoint

Los eventos de uso compartido (sin incluir eventos relacionados con la Directiva de uso compartido y los vínculos de uso compartido) son distintos de los eventos relacionados con archivos y carpetas de una forma principal: un usuario está realizando una acción que tiene un efecto en otro usuario. Por ejemplo, cuando un usuario de recursos A concede el acceso de usuario B a un archivo. En este ejemplo, el usuario A es el usuario que *actúa* y el usuario B es el *usuario de destino*. En el esquema de archivos de SharePoint, la acción del usuario que actúa solo afecta al propio archivo. Cuando el usuario A abre un archivo, la única información necesaria en el evento **FileAccessed** es el usuario que actúa. Para solucionar esta diferencia, hay un esquema independiente, denominado esquema de *uso compartido de SharePoint*, que recopila más información sobre los eventos de uso compartido. Esto garantiza que los administradores tengan visibilidad sobre quién compartió un recurso y el usuario con el que se compartió el recurso. 
  
El esquema de uso compartido proporciona dos campos adicionales en un registro de auditoría relacionados con el uso compartido de eventos: 
  
- **TargetUserOrGroupType:** Identifica si el usuario o el grupo de destino es un miembro, invitado, SharePointGroup, SecurityGroup o asociado.

- **TargetUserOrGroupName:** Almacena el UPN o el nombre del usuario o grupo de destino con el que se compartió un recurso (usuario B en el ejemplo anterior). 

Estos dos campos, además de otras propiedades del esquema del registro de auditoría de Office 365, como User, Operation y Date, pueden decir el artículo completo sobre el *que* el usuario compartió *qué* recurso con *quién* y *Cuándo*. 
  
Hay otra propiedad de esquema que es importante para la historia de uso compartido. Al exportar los resultados de la búsqueda de registros de auditoría, la columna **AuditData** del archivo CSV exportado almacena información sobre los eventos de uso compartido. Por ejemplo, cuando un usuario comparte un sitio con otro usuario, esto se consigue agregando el usuario de destino a un grupo de SharePoint. La columna **AuditData** captura esta información para proporcionar contexto a los administradores. Consulte el [paso 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) para obtener instrucciones sobre cómo analizar la información en la columna **AuditData** .

## <a name="sharepoint-sharing-events"></a>Eventos de uso compartido de SharePoint

El uso compartido se define cuando un usuario (el usuario que *actúa* ) desea compartir un recurso con otro usuario (el usuario de *destino* ). Los registros de auditoría relacionados con el uso compartido de un recurso con un usuario externo (un usuario que está fuera de la organización y no tienen una cuenta de invitado en el Azure Active Directory de la organización) se identifican mediante los siguientes eventos, que se registran en el Office 365 registro de auditoría:

- **SharingInvitationCreated:** Un usuario de la organización intentó compartir un recurso (probablemente un sitio) con un usuario externo. Esto da como resultado una invitación a uso compartido externa enviada al usuario de destino. No se concede acceso al recurso en este punto.

- **SharingInvitationAccepted:** El usuario externo ha aceptado la invitación para uso compartido enviada por el usuario que actúa y ahora tiene acceso al recurso.

- **AnonymousLinkCreated:** Se crea un vínculo anónimo (también denominado vínculo "cualquiera") para un recurso. Dado que se puede crear un vínculo anónimo y, a continuación, copiarlo, es razonable suponer que cualquier documento con un vínculo anónimo se ha compartido con un usuario de destino.

- **AnonymousLinkUsed:** Como su nombre indica, este evento se registra cuando se utiliza un vínculo anónimo para obtener acceso a un recurso. 

- **SecureLinkCreated:** Un usuario ha creado un "vínculo personas específicas" para compartir un recurso con una persona específica. Este usuario de destino puede ser alguien externo a su organización.

- **AddedToSecureLink:** Se ha agregado un usuario a un vínculo de personas específico. Este usuario de destino puede ser alguien externo a su organización.

## <a name="sharing-auditing-work-flow"></a>Flujo de trabajo de auditoría de uso compartido
  
Cuando un usuario (el que actúa como usuario) desea compartir un recurso con otro usuario (el usuario de destino), SharePoint (o OneDrive para la empresa) comprueba en primer lugar si la dirección de correo electrónico del usuario de destino ya está asociada a una cuenta de usuario en el directorio de la organización. Si el usuario de destino está en el directorio (y tiene una cuenta de usuario invitado correspondiente), SharePoint hace lo siguiente:
  
-  Se asignan inmediatamente los permisos de usuario de destino para obtener acceso al recurso agregando el usuario de destino al grupo de SharePoint adecuado y se registra un evento **AddedToGroup** . 
    
- Envía una notificación de uso compartido a la dirección de correo electrónico del usuario de destino.
    
- Registra un evento **SharingSet** . Este evento tiene un nombre descriptivo de "archivo, carpeta o sitio compartido" en **actividades de solicitud de acceso y uso compartido** en el selector de actividades de la herramienta de búsqueda de registros de auditoría. Consulte la captura de pantalla del [paso 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Si una cuenta de usuario para el usuario de destino no está en el directorio, SharePoint hace lo siguiente: 
    
   - Registra uno de los siguientes eventos en función de cómo se comparte el recurso:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (este evento se registra sólo cuando el recurso compartido es un sitio)
    
   - Cuando el usuario de destino acepta la invitación para compartir que se le envía (haciendo clic en el vínculo de la invitación), SharePoint registra un evento **SharingInvitationAccepted** y le asigna los permisos de usuario de destino para obtener acceso al recurso. Si se envía un vínculo anónimo al usuario de destino, el evento **AnonymousLinkUsed** se registra después de que el usuario de destino use el vínculo para obtener acceso al recurso. Para vínculos seguros, se registra un evento **FileAccessed** cuando un usuario externo utiliza el vínculo para obtener acceso al recurso.

También se registra información adicional sobre el usuario de destino, como la identidad del usuario a la que se redirige la invitación y el usuario que realmente la acepta. En algunos casos, estos usuarios (o direcciones de correo electrónico) pueden ser diferentes. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Identificación de recursos compartidos con usuarios externos

Un requisito común para los administradores es crear una lista de todos los recursos que se han compartido con usuarios fuera de la organización. Mediante el uso de la auditoría de uso compartido en Office 365, los administradores pueden generar esta lista. Aquí se muestra cómo hacerlo.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Paso 1: buscar eventos de uso compartido y exportar los resultados a un archivo CSV

El primer paso es buscar eventos de uso compartido en el registro de auditoría de Office 365. Para obtener más información (incluidos los permisos necesarios) sobre cómo buscar en el registro de auditoría, vea [Buscar en el registro de auditoría del centro de seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en búsqueda de**registros de auditoría**de **búsqueda**  > .
    
    Se muestra la página de **búsqueda de registros de auditoría** . 
    
4. En **actividades**, haga clic en **compartir y obtener acceso a actividades de solicitud** para buscar eventos relacionados con el uso compartido. 
    
    ![En actividades, seleccione compartir y actividades de solicitud de acceso](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Seleccione un intervalo de fecha y hora para buscar los eventos de uso compartido que se produjeron dentro de ese período. 
    
6. Haga clic en **Buscar** para ejecutar la búsqueda. 
    
7. Cuando la búsqueda termine de ejecutarse y se muestren los resultados, haga clic en **exportar resultados** \> **descargar todos los resultados**.
    
    Una vez seleccionada la opción exportar, se muestra un mensaje en la parte inferior de la ventana que le pregunta si desea abrir o guardar el archivo CSV.
    
8. Haga clic en **Guardar** \> y guardar **como** y guarde el archivo CSV en una carpeta del equipo local. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Paso 2: usar el editor de PowerQuery para dar formato al registro de auditoría exportado

El paso siguiente es usar la característica transformación de JSON en el editor de Power Query en Excel para dividir cada propiedad en la columna **AuditData** (que consta de un objeto JSON de varias propiedades) en su propia columna. Esto le permite filtrar columnas para ver los registros relacionados con el uso compartido

Para obtener instrucciones paso a paso, consulte "paso 2: dar formato al registro de auditoría exportado mediante el editor de Power Query" en [exportar, configurar y ver registros de auditoría](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Paso 3: filtrar el archivo CSV para los recursos compartidos con usuarios externos

El siguiente paso consiste en filtrar el archivo CSV por los distintos eventos relacionados con el uso compartido que se han descrito anteriormente en la sección [eventos de uso compartido de SharePoint](#sharepoint-sharing-events) . Como alternativa, puede filtrar la columna **TargetUserOrGroupType** para mostrar todos los registros en los que el valor de esta propiedad es **Guest**. 

Una vez que haya seguido las instrucciones del paso anterior para preparar el archivo CSV con el editor de PowerQuery, haga lo siguiente:
    
1. Abra el archivo de Excel que creó en el paso 2. 

2. En la pestaña **Inicio** , haga clic en **ordenar & filtro**y, a continuación, haga clic en **filtrar**.
    
3. En la lista desplegable **ordenar & filtro** de la columna **operaciones** , desactive todas las selecciones, seleccione uno o más de los siguientes eventos relacionados con el uso compartido y, a continuación, haga clic en **Aceptar**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel muestra las filas de los eventos seleccionados.
    
4. Vaya a la columna llamada **TargetUserOrGroupType** y selecciónela. 
    
5. En la lista desplegable **ordenar & filtro** , desactive todas las selecciones, seleccione **TargetUserOrGroupType: invitado**y haga clic en **Aceptar**.
    
    Ahora Excel muestra las filas para compartir eventos y donde el usuario de destino está fuera de la organización, porque los usuarios externos se identifican por el valor **TargetUserOrGroupType: Guest**. 
  
> [!TIP]
> Para los registros de auditoría que se muestran, la columna **objectId** identifica el recurso que se ha compartido con el usuario de destino; por ejemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.

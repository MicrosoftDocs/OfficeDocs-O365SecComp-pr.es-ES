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
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 'El uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa. Ahora, los administradores pueden usar la auditoría de uso compartido en el registro de auditoría de Office 365 para determinar cómo se usa el uso compartido en su organización. '
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435249"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Auditar el uso compartido para buscar recursos compartidos con usuarios externos

El uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa, y se usa ampliamente en organizaciones de Office 365. Ahora, los administradores pueden usar la auditoría de uso compartido en el registro de auditoría de Office 365 para determinar cómo se usa el uso compartido en su organización. 
  
## <a name="the-sharepoint-sharing-schema"></a>El esquema de uso compartido de SharePoint

Los eventos de uso compartido (excluir la Directiva de uso compartido y los eventos de vínculo de uso compartido) son distintos de los eventos relacionados con archivos y carpetas de una forma principal: un usuario está realizando una acción que tiene algún efecto en otro usuario. Por ejemplo, el usuario A concede el acceso de usuario B a un archivo. En este ejemplo, el usuario A es el usuario que *actúa* y el usuario B es el *usuario de destino*. En el esquema de archivos de SharePoint, la acción del usuario que actúa solo afecta al propio archivo. Cuando el usuario A abre un archivo, la única información necesaria en el evento **FileAccessed** es el usuario que actúa. Para solucionar esta diferencia, hay un esquema independiente, denominado esquema de *uso compartido de SharePoint*, que recopila más información sobre los eventos de uso compartido. Esto garantiza que los administradores tengan más información sobre quién compartió un recurso y el usuario con el que se compartió el recurso. 
  
El esquema de uso compartido proporciona dos campos adicionales en el registro de auditoría relacionados con el uso compartido de eventos: 
  
- **TargetUserOrGroupName** : almacena el UPN o el nombre del usuario o grupo de destino con el que se compartió un recurso (usuario B en el ejemplo anterior). 
    
- **TargetUserOrGroupType** : identifica si el usuario o el grupo de destino es un miembro, un invitado, un grupo o un socio. 
    
Estos dos campos, además de otras propiedades del esquema del registro de auditoría de Office 365, como User, Operation y Date, pueden decir el artículo completo sobre el *que* el usuario compartió *qué* recurso con *quién* y *Cuándo*. 
  
Hay otra propiedad de esquema que es importante para la historia de uso compartido. La propiedad **EventData** almacena información adicional acerca de los eventos de uso compartido. Por ejemplo, cuando un usuario comparte un sitio con otro usuario, esto se consigue agregando el usuario de destino a un grupo de SharePoint. La propiedad **EventData** captura esta información adicional para proporcionar contexto a los administradores. 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>Modelo de uso compartido de SharePoint y eventos de uso compartido

El uso compartido se define mediante tres eventos independientes: **SharingSet**, **SharingInvitationCreated**y **SharingInvitaitonAccepted**. Este es el flujo de trabajo de cómo se registran los eventos de uso compartido en el registro de auditoría de Office 365. 
  
![Diagrama de flujo de cómo funciona la auditoría de uso compartido](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
Cuando un usuario (el que actúa como usuario) desea compartir un recurso con otro usuario (el usuario de destino), SharePoint (o OneDrive para la empresa) comprueba en primer lugar si la dirección de correo electrónico del usuario de destino ya está asociada a una cuenta de usuario en el directorio de la organización. Si el usuario de destino está en el directorio de la organización, SharePoint hace lo siguiente:
  
-  Asigna inmediatamente los permisos de usuario de destino para obtener acceso al recurso. 
    
- Envía una notificación de uso compartido a la dirección de correo electrónico del usuario de destino.
    
- Registra un evento **SharingSet** . 
    
 Si una cuenta de usuario para el usuario de destino no está en el directorio de la organización, SharePoint hace lo siguiente: 
  
- Crea una invitación para uso compartido y la envía a la dirección de correo electrónico del usuario de destino.
    
- Registra un evento **SharingInvitationCreated** . 
    
    > [!NOTE]
    > El evento **SharingInvitationCreated** siempre está asociado con el uso compartido externo o invitado cuando el usuario de destino no tiene acceso al recurso que se ha compartido. 
  
Cuando el usuario de destino acepta la invitación para compartir que se le envía (haciendo clic en el vínculo de la invitación), SharePoint registra un evento **SharingInvitationAccepted** y le asigna los permisos de usuario de destino para obtener acceso al recurso. También se registra información adicional sobre el usuario de destino, como la identidad del usuario a la que se envió la invitación y el usuario que realmente aceptó la invitación. En algunos casos, estos usuarios (o direcciones de correo electrónico) pueden ser diferentes. 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>Identificación de recursos compartidos con usuarios externos

Un requisito común para los administradores es crear una lista de todos los recursos que se han compartido con usuarios fuera de la organización. Mediante el uso de la auditoría de uso compartido en Office 365, los administradores ahora pueden generar esta lista. Aquí se muestra cómo hacerlo.
  
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

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>Paso 2: filtrar el archivo CSV para los recursos compartidos con usuarios externos

El paso siguiente es filtrar el archivo CSV para los eventos **SharingSet** y **SharingInvitationCreated** , así como mostrar los eventos en los que la propiedad **TargetUserOrGroupType** es **Guest**. Para ello, use la herramienta Power Query editor de Excel. Para obtener instrucciones paso a paso, consulte [exportar, configurar y ver registros de registro de auditoría](export-view-audit-log-records.md). 

Una vez que haya seguido las instrucciones del tema anterior para preparar el archivo CSV, haga lo siguiente:
    
1. Abra el archivo CSV que preparó con el editor de Power Query. 

2. En la pestaña **Inicio** , haga clic en **ordenar & filtro**y, a continuación, haga clic en **filtrar**.
    
3. En la lista desplegable **ordenar & filtro** de la columna **operaciones** , desactive todas las selecciones, seleccione **SharingSet** y **SharingInvitationCreated**y haga clic en **Aceptar**.
    
    Excel muestra las filas de los eventos **SharingSet** y **SharingInvitationCreated** . 
    
4. Vaya a la columna llamada **TargetUserOrGroupType** y selecciónela. 
    
5. En la lista desplegable **ordenar & filtro** , desactive todas las selecciones, seleccione **TargetUserOrGroupType: invitado**y haga clic en **Aceptar**.
    
    Ahora Excel muestra las filas de los eventos **SharingInvitationCreated** y **SharingSet** , y donde el usuario de destino está fuera de la organización, porque los usuarios externos se identifican mediante el valor **TargetUserOrGroupType: Guest**. 
    
En la siguiente tabla se muestran todos los usuarios de la organización que compartía recursos con un usuario invitado dentro de un intervalo de fechas especificado.
  
![Compartir eventos en el registro de auditoría de Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
Aunque no se incluye en la tabla anterior, la propiedad **objectId** identifica el recurso que se ha compartido con el usuario de destino; por ejemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
  
> [!TIP]
> Si desea identificar cuándo un usuario invitado ha recibido realmente permisos para obtener acceso a un recurso (en lugar de solo los recursos que compartiron con ellos), repita los pasos 2, 3 y 4, y filtre en la **SharingInvitationAccepted** y **SharingSet** eventos en el paso 5. 

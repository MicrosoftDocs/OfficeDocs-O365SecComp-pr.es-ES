---
title: Auditar el uso compartido para buscar recursos compartidos con usuarios externos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
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
ms.openlocfilehash: 08b511acdf74edac5b2d595d1b60bdd84d630918
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31813951"
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

El uso compartido se define realmente mediante tres eventos independientes: **SharingSet**, **SharingInvitationCreated**y **SharingInvitaitonAccepted**. Este es el flujo de trabajo de cómo se registran los eventos de uso compartido en el registro de auditoría de Office 365. 
  
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

El primer paso es buscar eventos de uso compartido en el registro de auditoría de Office 365. Para obtener más información (incluidos los permisos necesarios) sobre cómo buscar en el registro de auditoría, vea [Buscar en el registro de auditoría del centro de seguridad _AMP_ cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del centro de seguridad & cumplimiento, haga clic en búsqueda de**registros de auditoría**de **búsqueda**  > .
    
    Se muestra la página de **búsqueda de registros de auditoría** . 
    
4. En **actividades**, haga clic en **compartir actividades** para buscar solo eventos de uso compartido. 
    
    ![En actividades, seleccione actividades de uso compartido.](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Seleccione un intervalo de fecha y hora para buscar los eventos de uso compartido que se produjeron dentro de ese período. 
    
6. Haga clic en **Buscar** para ejecutar la búsqueda. 
    
7. Cuando la búsqueda termine de ejecutarse y se muestren los resultados, haga clic en **exportar resultados** \> **descargar todos los resultados**.
    
    Una vez seleccionada la opción exportar, se muestra un mensaje en la parte inferior de la ventana que le pregunta si desea abrir o guardar el archivo CSV.
    
8. Haga clic en **Guardar** \> y guardar **como** y guarde el archivo CSV en una carpeta del equipo local. 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>Paso 2: filtrar el archivo CSV para los recursos compartidos con usuarios externos

El paso siguiente es filtrar el archivo CSV para los eventos **SharingSet** y **SharingInvitationCreated** , así como mostrar los eventos en los que la propiedad **TargetUserOrGroupType** es **Guest**. Para ello, debe usar la característica Power Query de Excel. El siguiente procedimiento se realiza en Excel 2016. 
  
1. En Excel 2016, abra un libro en blanco.
    
2. Haga clic en la pestaña **datos** . 
    
3. Haga clic en **nueva consulta** \> **desde archivo** \> **CSV**.
    
    ![En la pestaña datos, seleccione Nueva consulta, seleccione desde archivo y, después, seleccione desde CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. Abra el archivo CSV que ha descargado en el paso 1.
    
    El archivo CSV se abre en el editor de consultas. Tenga en cuenta que hay cuatro columnas: **tiempo**, **usuario**, **acción**y **detalle**. La columna de **detalle** es un campo de múltiples propiedades. El paso siguiente es crear una nueva columna para cada una de las propiedades de la columna de **detalle** . 
    
5. Seleccione la columna **detalles** y, a continuación, en la pestaña **Inicio** , haga clic en **dividir columna** \> **por**delimitador.
    
    ![En la pestaña Inicio, haga clic en dividir columna y, a continuación, haga clic en por delimitador](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. En la ventana **dividir columna por** delimitador, haga lo siguiente: 
    
      - En **seleccionar o escribir**delimitador, seleccione **coma**.
    
      - En **dividir**, seleccione **en cada aparición del**delimitador.
    
7. Haga clic en **Aceptar**.
    
    La columna de **detalle** se divide en varias columnas. Cada columna nueva tiene el nombre **detalle. 1**, **detalle. 2**, **detalle. 3**y así sucesivamente. Observará que los valores de cada celda de las columnas **detail. n** van precedidos por el nombre de la propiedad; por ejemplo, **operación: SharingSet**, **Operation: SharingInvitationAccepted**y **Operation: SharingInvitationCreated**.
    
    ![La columna de detalle se divide en varias columnas, una para cada propiedad](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. En la pestaña **archivo** , haga clic en **cerrar &amp; carga** para cerrar el editor de consultas y abrir el archivo en un libro de Excel. 
    
    El paso siguiente es filtrar el archivo para que solo se muestren los eventos **SharingSet** y **SharingInvitationCreated** . 
    
9. Vaya a la pestaña **Inicio** y, a continuación, seleccione la columna **acción** . 
    
10. En la lista desplegable **filtro &amp; ** de ordenación, desactive todas las selecciones, seleccione **SharingSet** y **SharingInvitationCreated**y haga clic en **Aceptar**.
    
    Excel muestra las filas de los eventos **SharingSet** y **SharingInvitationCreated** . 
    
11. Vaya a la columna llamada **detail. 17** (o a cualquier columna que contenga la propiedad **TargetUserOrGroupType** ) y selecciónela. 
    
12. En la lista desplegable **filtro &amp; ** de ordenación, desactive todas las selecciones, seleccione **TargetUserOrGroupType: invitado**y haga clic en **Aceptar**.
    
    Ahora Excel muestra las filas de los eventos **SharingInvitationCreated** y **SharingSet** , y donde el usuario de destino está fuera de la organización, porque los usuarios externos se identifican mediante el valor **TargetUserOrGroupType: Guest**. 
    
En la siguiente tabla se muestran todos los usuarios de la organización que compartía recursos con un usuario invitado dentro de un intervalo de fechas especificado.
  
![Compartir eventos en el registro de auditoría de Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
Aunque no se incluye en la tabla anterior, la columna **detail. 10** (o la columna que contiene la propiedad **objectId** ) identifica el recurso que se ha compartido con el usuario de destino; por ejemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
  
> [!TIP]
> Si desea identificar cuándo un usuario invitado ha recibido realmente permisos para obtener acceso a un recurso (en lugar de solo los recursos que compartiron con ellos), repita los pasos 10, 11 y 12, y filtre en la **SharingInvitationAccepted** y **SharingSet **eventos en el paso 10. 

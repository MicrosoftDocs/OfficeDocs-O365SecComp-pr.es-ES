---
title: Uso compartido de auditoría en el registro de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 'Uso compartido es una actividad clave en SharePoint Online y OneDrive para la empresa. Los administradores ahora pueden usar uso compartido de auditoría en el registro de auditoría de Office 365 para determinar cómo el uso compartido se está usando en su organización. '
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536306"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Uso compartido de auditoría en el registro de auditoría de Office 365

El uso compartido una actividad clave en SharePoint Online y OneDrive para la empresa, y se utiliza ampliamente en las organizaciones de Office 365. Los administradores ahora pueden usar uso compartido de auditoría en el registro de auditoría de Office 365 para determinar cómo el uso compartido se está usando en su organización. 
  
## <a name="the-sharepoint-sharing-schema"></a>El esquema de uso compartido de SharePoint

Eventos de uso compartidos (excluido de directiva de uso compartido y uso compartido de vinculación eventos) son diferentes de los eventos relacionados con archivos y carpetas en una forma principal: un usuario está tomando una acción que tiene algunos efecto en otro usuario. Por ejemplo, un usuario proporciona acceso de usuario B a un archivo. En este ejemplo, el usuario A es el *que actúa el usuario* y usuario B es el *usuario de destino*. En el esquema de archivo de SharePoint, acción del usuario activo sólo afecta del propio archivo. Cuando el usuario A abre un archivo, la única información necesaria en el evento **FileAccessed** es el usuario activo. Para solucionar esta diferencia, hay un esquema independiente, denominado el *esquema de uso compartido de SharePoint*, que captura más información sobre el uso compartido de eventos. Esto garantiza que los administradores tienen más claro entendimiento en que un recurso compartido y el usuario, el recurso se ha compartido con. 
  
El esquema de uso compartido proporciona dos campos adicionales en el registro de auditoría relacionados con el uso compartido de eventos: 
  
- **TargetUserOrGroupName** - almacena el UPN o el nombre del usuario de destino o del grupo que se ha compartido un recurso con (usuario B en el ejemplo anterior). 
    
- **TargetUserOrGroupType** - identifica si el usuario de destino o el grupo es un miembro, invitado, grupo o socio. 
    
Esquema del registro de auditoría de estos dos campos, además de otras propiedades de Office 365, como usuario, operación y la fecha pueden indicar a la historia completa acerca de *qué* usuario shared *qué* recursos con *quién* y *cuándo*. 
  
Hay otra propiedad de esquema que es importante para la historia de uso compartida. La propiedad **EventData** almacena información adicional sobre el uso compartido de eventos. Por ejemplo, cuando un usuario comparte un sitio con otro usuario, esto se logra agregando el usuario de destino a un grupo de SharePoint. La propiedad **EventData** captura esta información adicional para proporcionar contexto para los administradores. 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>El modelo de uso compartido y uso compartido de eventos de SharePoint

Uso compartido está definido realmente por tres eventos independientes: **SharingSet**, **SharingInvitationCreated**y **SharingInvitaitonAccepted**. Aquí el flujo de trabajo para los eventos de uso compartidos de cómo se registran en el registro de auditoría de Office 365. 
  
![Diagrama de flujo del funcionamiento de uso compartido de auditoría](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
Cuando un usuario (el usuario activo) desea compartir un recurso con otro usuario (el usuario de destino), SharePoint (o OneDrive para la empresa) comprueba primero si la dirección de correo electrónico del usuario de destino ya está asociada con una cuenta de usuario en el directorio de la organización. Si el usuario de destino se encuentra en el directorio de la organización, SharePoint hace lo siguiente:
  
-  Asigna inmediatamente los permisos de usuario de destino para tener acceso al recurso. 
    
- Envía una notificación de uso compartida en la dirección de correo electrónico del usuario de destino.
    
- Registra un evento **SharingSet** . 
    
 Si una cuenta de usuario para el usuario de destino no está en el directorio de la organización, SharePoint hace lo siguiente: 
  
- Crea una invitación para compartir y envía a la dirección de correo electrónico del usuario de destino.
    
- Registra un evento **SharingInvitationCreated** . 
    
    > [!NOTE]
    > El evento **SharingInvitationCreated** más siempre está asociado con el uso compartido externo o de invitado cuando el usuario de destino no tiene acceso al recurso que se ha compartido. 
  
Cuando el usuario de destino acepta la invitación para compartir que se ha enviado a ellos (haciendo clic en el vínculo en la invitación), SharePoint registra un evento **SharingInvitationAccepted** y asigna los permisos de usuario de destino para tener acceso al recurso. También se registra información adicional sobre el usuario de destino, como la identidad del usuario que se envió la invitación y el usuario que realmente había aceptado la invitación. En algunos casos, estos usuarios (o direcciones de correo electrónico) pueden ser diferentes. 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>Cómo identificar los recursos compartidos con los usuarios externos

Un requisito común para los administradores es crear una lista de todos los recursos que se han compartido con los usuarios fuera de la organización. Mediante el uso de uso compartido de auditoría en Office 365, los administradores pueden generar ahora esta lista. Aquí es cómo.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Paso 1: Buscar eventos de uso compartido y exportar los resultados a un archivo CSV

El primer paso es buscar el registro de auditoría de Office 365 para el uso compartido de eventos. Para obtener más detalles (incluidos los permisos necesarios) acerca de la búsqueda en el registro de auditoría, consulte [el registro de auditoría de búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación**y, a continuación, haga clic en **búsqueda de registro de auditoría**.
    
    Se muestra la página de **búsqueda de registro de auditoría** . 
    
4. En **las actividades**, haga clic en **las actividades de uso compartido** para buscar sólo para uso compartido de eventos. 
    
    ![En actividades, seleccione las actividades de uso compartido](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Seleccione un intervalo de fechas y horas para encontrar los eventos de uso compartidos que se ha producido dentro de ese período. 
    
6. Haga clic en **Buscar** para ejecutar la búsqueda. 
    
7. Cuando finalice la búsqueda está ejecutando y los resultados se muestran, haga clic en **exportar los resultados de** \> **Descargar todos los resultados**.
    
    Después de seleccionar la opción de exportación, se muestra un mensaje en la parte inferior de la ventana que le pide que abra o guarde el archivo CSV.
    
8. Haga clic en **Guardar** \> **Guardar como** y guarde el archivo CSV en una carpeta en el equipo local. 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>Paso 2: Filtrar el archivo CSV para recursos compartidos con los usuarios externos

El siguiente paso para filtrar el CSV para los eventos **SharingSet** y **SharingInvitationCreated** y para mostrar los eventos donde es la propiedad **TargetUserOrGroupType** **invitado**. Para ello, debe usar la característica de consulta de alimentación en Excel. El siguiente procedimiento se realiza en Excel 2016. 
  
1. En Excel 2016, abra un libro en blanco.
    
2. Haga clic en la pestaña **Datos**. 
    
3. Haga clic en **Nueva consulta** \> **de archivo** \> **De CSV**.
    
    ![En la ficha datos, seleccione nueva consulta, seleccione desde archivo y, a continuación, seleccione desde CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. Abra el archivo CSV que ha descargado en el paso 1.
    
    El archivo CSV se abre en el Editor de consultas. Tenga en cuenta que no hay cuatro columnas: **tiempo**, **usuario**, **acción**y **Ver todos los detalles**. La columna **detalle** es un campo de propiedad múltiple. El siguiente paso es crear una nueva columna para cada una de las propiedades en la columna **todos los detalles** . 
    
5. Seleccione la columna **detalle** y, a continuación, en la ficha **Inicio** , haga clic en **División de columna** \> **Por delimitador**.
    
    ![En la ficha Inicio, haga clic en división de columna y, a continuación, haga clic en por delimitador](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. En la ventana de **División de columna por delimitador** , haga lo siguiente: 
    
      - En, **Seleccione o escriba el carácter delimitador**, seleccione **comas**.
    
      - En **dos paneles**, seleccione **en cada aparición de delimitador**.
    
7. Haga clic en **Aceptar**.
    
    La columna de **detalle** se divide en varias columnas. Cada nueva columna se denomina **Detail.1**, **Detail.2**, **Detail.3**y así sucesivamente. Se puede observar que los valores de cada celda de las columnas **Detail.n** llevan el prefijo con el nombre de la propiedad; Por ejemplo, **Operación: SharingSet**, **SharingInvitationAccepted: operación**y **Operación: SharingInvitationCreated**.
    
    ![La columna de detalle se divide en varias columnas, uno para cada propiedad](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. En la pestaña **archivo** , haga clic en **Cerrar &amp; carga** para cerrar el Editor de consultas y abra el archivo en un libro de Excel. 
    
    El siguiente paso es filtrar el archivo para mostrar únicamente los eventos **SharingSet** y **SharingInvitationCreated** . 
    
9. Vaya a la ficha **Inicio** y, a continuación, seleccione la columna **acción** . 
    
10. En la **ordenar &amp; filtro** lista desplegable, desactive todas las selecciones, a continuación, seleccione **SharingSet** y **SharingInvitationCreated**y haga clic en **Aceptar**.
    
    Excel muestra las filas para los eventos **SharingSet** y **SharingInvitationCreated** . 
    
11. Vaya a la columna con el nombre **Detail.17** (o la columna que contiene la propiedad **TargetUserOrGroupType** ) y selecciónelo. 
    
12. En la **ordenar &amp; filtro** lista desplegable, desactive todas las selecciones, a continuación, seleccione **TargetUserOrGroupType:Guest**y haga clic en **Aceptar**.
    
    Ahora Excel muestra las filas para los eventos de **SharingInvitationCreated** y **SharingSet** y donde el usuario de destino está fuera de la organización, debido a que los usuarios externos se identifican mediante el valor **TargetUserOrGroupType:Guest**. 
    
La siguiente tabla muestran todos los usuarios de la organización que los recursos compartidos con un usuario invitado dentro de un intervalo de fechas especificado.
  
![Registro de auditoría de eventos de uso compartidos en Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
Aunque no se incluye en la tabla anterior, la columna **Detail.10** (o la columna que contiene la propiedad **ObjectId** ) identifica el recurso que se ha compartido con el usuario de destino; Por ejemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
  
> [!TIP]
> Si desea identificar cuando un usuario invitado se realmente asignó permisos para tener acceso a un recurso (en contraposición a sólo los recursos que where compartido con ellos), repita los pasos 10, 11 y 12 y filtrar la **SharingInvitationAccepted** y **SharingSet **eventos en el paso 10. 

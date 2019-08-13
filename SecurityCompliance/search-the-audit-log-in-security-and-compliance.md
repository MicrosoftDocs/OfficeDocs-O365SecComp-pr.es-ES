---
title: Buscar el registro de auditoría en el Centro de seguridad y cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 'Use el Centro de seguridad y cumplimiento para buscar el registro de auditoría unificado para ver la actividad de usuarios y administradores en su organización de Office 365. '
ms.openlocfilehash: 79309a2145db53f38d5d3c3c29777571d56910ae
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "36165696"
---
# <a name="search-the-audit-log-in-the-security--compliance-center"></a>Buscar el registro de auditoría en el Centro de seguridad y cumplimiento

## <a name="introduction"></a>Introducción

¿Necesita averiguar si un usuario ha visto un documento determinado o si ha purgado un elemento de su buzón? Si es así, puede usar el Centro de seguridad &amp; cumplimiento de Office 365 para buscar el registro de auditoría unificado para ver la actividad de usuarios y administradores en su organización de Office 365. ¿Por qué un registro de auditoría unificado? Porque puede buscar los siguientes tipos de actividades administrativas y de usuario en Office 365:
  
- Actividad de usuario en SharePoint Online y OneDrive para Empresas
    
- Actividad del usuario en Exchange en línea (registro de auditoría del buzón de Exchange)
  
- Actividad de administración en SharePoint en línea
    
- Actividad de administrador en Azure Active Directory (el servicio de directorio para Office 365)
    
- Actividad de administración en Exchange en línea (registro de auditoría de administración de Exchange)
    
- Actividad de usuario y de administrador en Sway
    
- Actividades de eDiscovery en el Centro de seguridad y cumplimiento
    
- Actividad de usuario y administrador en Power BI
    
- Actividad de usuario y administrador en Microsoft Teams

- Actividad de usuario y administrador en Dynamics 365
    
- Actividad de usuario y administrador en Yammer
 
- Actividad de usuario y administrador en Microsoft Flow
    
- Actividad de usuario y administrador en Microsoft Stream

- Actividad de analista y administrador en Microsoft Workplace Analytics

- Actividad de usuario y administrador en Microsoft PowerApps
    
   
## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de leer los siguientes elementos antes de iniciar la búsqueda del registro de auditoría de Office 365.
  
- Usted (u otro administrador) debe activar primero el registro de auditoría en Office 365 para poder empezar a buscar dicho registro. Para activarlo, haga clic en **Iniciar el registro de la actividad del usuario y administrador**en la **página de búsqueda**de el Centro de seguridad y cumplimiento. (SI usted no ve este link, la auditoría ya se habrá activado para su organización) Después de que lo active, se muestra un mensaje que dice que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que hacer esto una vez. 
    
    > [!NOTE]
    > Estamos en el proceso de activar la auditoría de forma predeterminada. Hasta entonces, puede activarla como se describió anteriormente. 
  
- Usted debe tener asignado el rol de Registros de auditoría o Registros de auditoría de solo lectura en Exchange en línea para buscar el registro de auditoría de Office 365. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página de**permisos**del centro de administración de Exchange. Nota: los Administradores globales en el Office 365 y Microsoft 365 pasan automáticamente a ser miembros del grupo de rol de funciones de la Administración de la organización en el servicio de Exchange en línea. Para darle a un usuario la capacidad de buscar el registro de auditoría de Office 365 con el mínimo nivel de privilegios, puede crear un grupo de roles personalizado en Exchange en línea, agregar el rol de Registros de auditoría o Registros de auditoría de solo lectura y, después, agregar el usuario como miembro del nuevo grupo de roles. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://go.microsoft.com/fwlink/p/?LinkID=730688).
    
    > [!IMPORTANT]
    > Si asigna a un usuario el rol de Registros de auditoría o Registros de auditoría de solo lectura en la página de **permisos** del centro de seguridad y cumplimiento, no podrán buscar el registro de auditoría de Office 365 Tiene que asignar los permisos en Exchange en línea. Esto se debe a que el cmdlet subyacente que se usa para buscar en el registro de auditoría es un cmdlet Exchange en línea. 
  
- Cuando un usuario o administrador realiza una actividad auditada, se genera un registro de auditoría y se almacena en el registro de auditoría de Office 365 de su organización. La cantidad de tiempo que se retiene un registro de auditoría (y que se puede buscar en el registro de auditoría) depende de la suscripción a Office 365 y, específicamente, del tipo de licencia que se ha asignado a un usuario específico.

     - **Office 365 E3:** Los registros de auditoría se conservan durante 90 días. Eso significa que puede buscar el registro de auditoría para las actividades que se han realizado en los últimos 90 días.

     - **Office 365 E5:** Los registros de auditoría también se conservan durante 90 días. La retención mantenimiento de registros de auditoría para un año puede estar disponible en ocasiones para usuarios de E5 y usuarios con una licencia de E3 y una licencia de complemento a Cumplimiento avanzado de Office 365.

        > [!NOTE]
        > El programa de la versión preliminar privada para el período de retención de un año para los registros de auditoría de las organizaciones E5 (o para los usuarios de las organizaciones E3 que tienen licencias de complemento a Cumplimiento avanzado) está cerrado a la nueva inscripción. Este artículo se actualizará cuando el período de retención de un año se encuentre disponible en vista previa pública o se publique para la disponibilidad general.

- Si desea desactivar la búsqueda en el registro de auditoría de Office 365 de su organización, puede ejecutar el comando siguiente en el PowerShell remoto conectado a su organización Exchange en línea:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Para volver a activar la búsqueda de auditoría, puede ejecutar el comando siguiente en PowerShell de Exchange en línea :
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    Para obtener más información, consulte[Desactivar la búsqueda de registros de auditoría en Office 365](turn-audit-log-search-on-or-off.md).
    
- Como se indicó anteriormente, el cmdlet subyacente que se ha usado para buscar en el registro de auditoría es un cmdlet de Exchange en línea, que es **Search-UnifiedAuditLog**. Eso significa que puede usar este cmdlet para buscar en el registro de auditoría de Office 365 en lugar de usar la página de**Búsqueda en el registro de auditoría** del centro de Seguridad y cumplimiento. Tiene que ejecutar este cmdlet en el PowerShell remoto conectado a su organización de Exchange en línea. Para obtener más información, consulte[Search-UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776). 

    Para obtener información sobre cómo exportar los resultados de búsqueda devueltos por el cmdlet **Search-UnifiedAuditLoga un archivo CSV, consulte la sección "sugerencias para exportar y ver el registro de auditoría" exportar, configurar y ver el registro de auditoría registros.  

- Si desea descargar mediante programación los datos del registro de auditoría de Office 365, le recomendamos que use la API de Actividad de administración de Office 365 en lugar de usar un script de PowerShell. La API de Actividad de administración de Office 365 es un servicio REST de la web que puede usar para desarrollar operaciones, soluciones de supervisión de seguridad y cumplimiento para su organización. Para obtener más información, consulte[la referencia de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
    
- La entrada del registro de auditoría correspondiente puede tardar en aparecer en los resultados de búsqueda un máximo de 30 minutos o 24 horas después de que se produzca el evento. En la siguiente tabla, se muestra el tiempo que tarda para los distintos servicios en Office 365..
    
    |**Servicio de Office 365**|**30 minutos**|**24 horas**|
    |:-----|:-----|:-----|
    |Esquema de Protección e Inteligencia contra amenazas  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
    |Azure Active Directory (eventos de inicio de sesión de usuario)  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Azure Active Directory (eventos administrativos)  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
    |Prevención de pérdida de datos  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       <br/>| |
    |Dynamics 365 CRM <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |eDiscovery  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Exchange en línea  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Microsoft Flow  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Project  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Stream  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Teams  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Power BI  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Centro de seguridad y cumplimiento  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |SharePoint en línea y OneDrive para Empresas  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Sway  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Workplace Analytics<br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> || 
    |Yammer  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (AD) es el servicio de directorio para Office 365. El registro de auditoría unificado contiene actividades de usuario, dominio, aplicación, grupo y de directorio que se han realizado en el Centro de administración de Microsoft 365 o en el Portal de administración de Azure. Para obtener una lista completa de los eventos de Azure AD, consulte[Eventos del informe de auditoría de Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).
    
- El registro de auditoría de Power BI no está habilitado de forma predeterminada. Para buscar actividades de Power BI en el registro de auditoría de Office 365, debe habilitar la auditoría en el portal de administración de Power BI. Para obtener instrucciones, consulte la sección "registros de auditoría"[en el portal de administración de Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).
    
    
## <a name="search-the-audit-log"></a>Búsquedas en el registro de auditoría

Aquí se muestra el proceso para buscar el registro de auditoría en Office 365.
  
[Paso 1: Ejecute una búsqueda de registros de auditoría](#step-1-run-an-audit-log-search)
  
[Paso 2: Vea los resultados de la búsqueda](#step-2-view-the-search-results)

[Paso 3: Filtre los resultados de la búsqueda](#step-3-filter-the-search-results)

[Paso 4: Exportar los resultados de búsqueda a un archivo](#step-4-export-the-search-results-to-a-file)



  
### <a name="step-1-run-an-audit-log-search"></a>Paso 1: Ejecute una búsqueda de registros de auditoría

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
    > [!TIP]
    > Use una sesión de exploración privada (no una sesión normal) para obtener acceso al centro de seguridad y cumplimiento, ya que esto evitará que las credenciales con las que inició sesión actualmente sean usadas. Para abrir una ventana de Exploración de InPrivate en Internet Explorer o en Microsoft Edge, pulse las teclas CTRL+SHIFT+P. Para abrir una sesión de explorador privada en Google Chrome (denominada ventana de incógnito), presione CTRL+MAYÚS+N. 
  
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **buscar**, y luego haga clic en**buscar el registro de auditoría**.
    
    La página del**registro de auditoría de búsqueda**será mostrada. 
    
    ![Configure los criterios y luego, haga clic en Buscar para ejecutar el informe.](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > Primeramente tiene que activar el registro de auditoría antes de que pueda ejecutar una búsqueda de registros de auditoría. Si se muestra el vínculo**Iniciar el registro de la actividad administrativa y de usuario**, haga clic en él para activar la auditoría. Si no ve este vínculo, la auditoría ya se ha activado para la organización. 
  
4. Configurar los siguientes criterios de búsqueda: 
    
    a. **Actividades** Haga clic en la lista desplegable para mostrar las actividades que puede buscar. Las actividades administrativas y de usuario se organizan en grupos de actividades relacionadas. Puede seleccionar actividades específicas o puede hacer clic en el nombre del grupo de actividades para seleccionar todas las actividades del grupo. También puede hacer clic en una actividad seleccionada para borrar la selección. Después de que ejecute la búsqueda, solo se muestran las entradas seleccionadas del registro de auditoría de las actividades. Al seleccionar**Mostrar los resultados de todas las actividades**, se mostrarán los resultados de todas las actividades que el usuario o el grupo de usuarios seleccionado ha realizado. 
    
    Se registran más de 100 actividades administrativas y de usuario en el registro de auditoría de Office 365. Haga clic en la pestaña de**Actividades auditadas**en el tema de este artículo para ver las descripciones de todas las actividades en cada uno de los diferentes servicios de Office 365. 
    
    b. **Fecha de inicio** y **Fecha de finalización** Los últimos siete días son seleccionados de manera predeterminada. Seleccione un intervalo de fecha y hora para mostrar los eventos que han sucedido en ese período. La fecha y la hora se presentan en formato de Hora universal coordinada (UTC). El intervalo máximo de fecha que puede especificar es 90 días. Se muestra un error si el intervalo de fecha seleccionado es superior a 90 días. 
    
    > [!TIP]
    > Si está usando el intervalo de fecha máximo de 90 días, seleccione la hora actual para la **Fecha de inicio**. De otro modo, recibirá un error que dice que la fecha de inicio es anterior a la fecha de finalización. Si ha activado la auditoría en los últimos 90 días, el intervalo máximo de fecha no puede comenzar antes de la fecha en la que se ha activado la auditoría. 
  
    c. **Usuarios**Haga clic en este cuadro y luego, seleccione uno o más usuarios para mostrarles los resultados de búsqueda. Las entradas del registro de auditoría de la actividad seleccionada que han realizado los usuarios que selecciona en este cuadro, se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas de todos los usuarios (y cuentas de servicio) de su organización. 
    
    d. **Archivo, carpeta o sitio**: Escriba algunos o todos los nombres de carpeta o de archivo para buscar las actividades relacionadas con el archivo de la carpeta que contengan la palabra clave especifica. También puede especificar una dirección URL de un archivo o carpeta. Si usa una dirección URL, asegúrese de escribir la dirección URL completa, o si escribe solo una parte de esta, de no incluir espacios ni caracteres especiales. 
    
    Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas de la organización.
    
   **SUGERENCIAS**

   - Si busca todas las actividades relacionadas con un **sitio**, añada el símbolo comodín (\*) detrás de la dirección URL para que se devuelvan todas las entradas del sitio; por ejemplo, **"https://contoso-my.sharepoint.com/personal/*"**.

   - Si está buscando todas las actividades relacionadas con un **archivo**, agregue el símbolo comodín (\*) antes del nombre de archivo para devolver todas las entradas para ese archivo; por ejemplo,** "* Customer_Profitability_Sample.csv"**.
    

    
5. Haga clic en **Búsqueda** para ejecutar la búsqueda mediante sus criterios de búsqueda.  
    
    Los resultados de búsqueda se cargan y, después de unos minutos, se muestran en **Resultados**. Cuando finaliza la búsqueda, se muestra el número de resultados que se ha encontrado. En el**panel resultados** se mostrará un máximo de 5 000 eventos en incrementos de 150 eventos. Si hay más de 5 000 eventos que cumplen los criterios de búsqueda, se muestran los 5 000 eventos más recientes. 
    
    ![El número de resultados se muestra cuando haya terminado la búsqueda](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>Sugerencias para buscar el registro de auditoría

- Puede seleccionar actividades específicas de búsqueda haciendo clic en el nombre de la actividad. O puede buscar todas las actividades en un grupo (como **Actividades de archivos y carpetas**) haciendo clic en el nombre de grupo. Si se selecciona una actividad, puede hacer clic en ella para cancelar la selección. También puede usar el cuadro de búsqueda para mostrar las actividades que contengan la palabra clave que usted escriba.
    
    ![Haga clic en el nombre de grupo de actividades para seleccionar todas las actividades](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- Tiene que seleccionar **Mostrar resultados para todas las actividades** en la lista de**Actividades** para mostrar los eventos del registro de auditoría de administración de Exchange. Los eventos de este registro de auditoría muestran un nombre de cmdlet (por ejemplo,**Set-Mailbox**) en la columna de**Actividad**en los resultados. Para obtener más información, haga clic en la pestaña** actividades auditadas**de este tema y luego haga clic en**actividades de administración de Exchange**.
    
    De forma similar, hay algunas actividades de auditoría que no tienen un elemento correspondiente en la lista **Actividades**. Si sabe el nombre de la operación para estas actividades, puede buscarlas todas y luego filtrar los resultados escribiendo el nombre de la operación en el cuadro de la columna de**Actividad**. Consulte [Paso 3: Filtrar los resultados de búsqueda](#step-3-filter-the-search-results) para obtener más información sobre cómo filtrar los resultados. 
    
- Haga clic en **Borrar** para borrar los criterios actuales de búsqueda. El intervalo de fecha vuelve al predeterminado de los últimos siete días. También puede hacer clic en **Borrar todo para mostrar los resultados de todas las actividades** para cancelar todas las actividades seleccionadas. 
    
- Si 5 000 resultados son encontrados, puede suponer que probablemente existen más de 5,000 eventos que cumplen los criterios de búsqueda. Puede restringir los criterios de búsqueda y volver a ejecutar la búsqueda para devolver menos resultados o puede exportar todos los resultados de búsqueda al seleccionar **Exportar resultado**\>**Descargar todos los resultados**.

  
### <a name="step-2-view-the-search-results"></a>Paso 2: Ver los resultados de la búsqueda

Los resultados de una búsqueda de registro de auditoría se muestran en **Resultados** en la página **Búsqueda de registros de auditoría**. Como se mencionó anteriormente se muestran un máximo de 5 000 eventos (más recientes) en incrementos de 150 eventos. Para mostrar más eventos puede usar la barra de desplazamiento en el panel **Resultados** o también puede presionar **Mayús+Fin** para mostrar los siguientes 150 eventos. 
  
Los resultados contienen la siguiente información sobre cada evento que la búsqueda ha devuelto.
  
- **Fecha:** La fecha y la hora (en formato UTC) cuando se ha realizado el evento. 
    
- **Dirección IP:** La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6. 
    
- **Usuario:** El usuario (o cuenta de servicio) que ha realizado la acción que ha desencadenado el evento. 
    
- **Actividad:** La actividad que ha realizado el usuario. Este valor corresponde a las actividades que ha seleccionado en la lista desplegable de **Actividades**. Para un evento del registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange. 
    
- **Elemento:** El objeto que se ha creado o modificado como resultado de la actividad correspondiente. Por ejemplo, el archivo que se ha visto o modificado, o la cuenta de usuario que se ha actualizado. No todas las actividades tienen un valor en esta columna. 
    
- **Detalle:** Información adicional sobre una actividad. Nuevamente, no todas las actividades tendrán un valor. 
    
> [!TIP]
> Haga clic en un encabezado de columna en **Resultados** para ordenarlos. Puede ordenar los resultados de la A hasta la Z o de la Z hasta la A. Haga clic en el encabezado**Fecha** para ordenar los resultados del más antiguo al más nuevo o al revés. 
  
#### <a name="view-the-details-for-a-specific-event"></a>Ver los detalles de un evento específico

Puede ver más detalles sobre un evento al hacer clic en el registro de eventos de la lista de resultados de búsqueda. Se muestra una página de**detalles** que contiene las propiedades detalladas del registro de eventos. Las propiedades que se muestran dependen del servicio de Office 365 en el que se produce el evento. Para mostrar esos detalles, haga clic en**Más información**. Para descripciones, consulte[Propiedades detalladas del registro de auditoría de Office 365](detailed-properties-in-the-office-365-audit-log.md)
  
![Haga clic en Obtener más información para ver las propiedades detalladas del registro de eventos de auditoría.](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>Paso 3: Filtrar los resultados de la búsqueda

Además de ordenar, también puede filtrar los resultados de una búsqueda de registro de auditoría. Esta es una característica excelente que puede ayudarle a filtrar rápidamente los resultados específicos de un usuario o actividad. Puede crear inicialmente una amplia búsqueda y, después, filtrar rápidamente los resultados para ver los eventos específicos. Luego puede restringir los criterios de búsqueda, y volver a ejecutar la búsqueda para volver a un conjunto de resultados más pequeño y conciso.
  
Para filtrar los resultados:
  
1. Ejecute una búsqueda de registros de auditoría.
    
2. Cuando se muestren los resultados, haga clic en **Filtrar resultados**.
    
    Los cuadros de palabra clave se muestran en cada encabezado de columna.
    
3. Haga clic en uno de lo cuadros que se visualizan en las cabeceras de columna y escriba una palabra o frase, dependiendo de la columna que esté filtrando. Los resultados se volverán a ajustar de manera dinámica para mostrar los eventos que coincidan con su filtro.
    
    ![Escriba una palabra en el filtro para mostrar los eventos que coincidan con el filtro](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. Para borrar un filtro, haga clic en la**X**en el cuadro de filtro o haga clic en **Ocultar filtrado**.
    
> [!TIP]
> Para mostrar los eventos del registro de auditoría de administración de Exchange, escriba un**-** (guion) en el cuadro de filtro**Actividad**. Esto mostrará los nombres de los cmdlet, que se muestran en la columna**Actividad** de los eventos de administración de Exchange. Luego usted puede ordenar los nombres de cmdlet en orden alfabético. 

### <a name="step-4-export-the-search-results-to-a-file"></a>Paso 4: Exportar los resultados de búsqueda a un archivo

Puede exportar los resultados de una búsqueda de registro de auditoría a un archivo de valores separados por comas (CSV) en su computadora local. Puede abrir este archivo en Microsoft Excel y usar características como buscar, ordenar, filtrar y dividir una sola columna (que contiene múltiples propiedades) en columnas múltiples.
  
1. Ejecute una búsqueda de registro de auditoría, y luego revise los criterios de búsqueda hasta que tenga los resultados deseados.
    
2. Haga clic en **Exportar resultados** y seleccione una de las siguientes opciones: 
    
     - **Guardar los resultados cargados:** Elija esta opción para exportar solo las entradas que se muestran en los**Resultados**en la página de**búsqueda de registros de auditoría**. El archivo CSV que se descarga contiene las mismas columnas (y datos) que se muestran en la página (Fecha, Usuario, Actividad, Elemento y Detalles). Se incluye una columna adicional (denominada **Más**) en el archivo CSV que contiene más información de la entrada del registro de auditoría. Como está exportando los mismos resultados que se han cargado (y visualizado) en la página**Búsqueda de registros de auditoría**, un máximo de 5 000 entradas son exportadas. 
    
     - **Descargar todos los resultados:** Elija esta opción para exportar todas las entradas del registro de auditoría de Office 365 que cumplen los criterios de búsqueda. Para obtener un conjunto amplio de resultados de búsqueda, elija esta opción para descargar todas las entradas del registro de auditoría además de los 5 000 resultados que se muestran en la página de**Búsqueda de registros de auditoría**. Esta opción descargará los datos sin procesar del registro de auditoría a un archivo CSV, y contiene información adicional de la entrada del registro de auditoría en una columna denominada**AuditData**. Puede tardar más en descargar el archivo si elige esta opción de exportación ya que el archivo puede ser mucho más grande que el que se descarga si eligiera otra opción.
    
       > [!IMPORTANT]
       > Puede descargar un máximo de 50 000 entradas en un archivo CSV desde una única búsqueda de registros de auditoría. Si se descargan 50 000 entradas en el archivo CSV, probablemente puede suponer que existen más de 50 000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, pruebe a usar un intervalo de fecha para reducir el número de entradas de registro de auditoría. Puede que tenga que ejecutar varias búsquedas con intervalos de fecha de menor tamaño para exportar más de 50 000 entradas. 
  
3. Después de que seleccione una opción de exportación, se muestra un mensaje en la parte inferior de la ventana que le solicita que abra el archivo CSV, lo guarde en la carpeta de descargas o que lo guarde en una carpeta específica.
 
#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>Obtener más información sobre exportar y visualizar resultados de búsqueda del registro de auditoría

- Si descarga todos los resultados, el archivo CSV contiene una columna denominada **AuditData**, que contiene información adicional sobre cada evento. Los datos en esta columna se componen de un objeto JSON que contiene varias propiedades del registro de auditoría. Cada*propiedad: valor*par del objeto JSON es separado por una coma. Puede usar la herramienta de transformación de JSON en el editor de Power Query en Excel para dividir la columna**AuditData **en columnas múltiples de forma que cada propiedad del objeto JSON tenga su propia columna. Esto le permitirá ordenar y filtrar en una o más de estas propiedades. Para obtener instrucciones paso a paso para usar el editor de Power Query para transformar el objeto JSON, consulte[exportar, configurar y ver los archivos de registros de auditoría](export-view-audit-log-records.md). 
    
    Después de que divida la columna **AuditData**, puede filtrar en la columna de**Operaciones** para mostrar las propiedades detalladas de un tipo de actividad específico. 
    
- La opción **Descargar todos los resultados** descarga los datos sin procesar del registro de auditoría de Office 365 en un archivo CSV. Este archivo contiene diferentes nombres de columna (CreationDate, Identificadores de usuario, Operaciones, AuditData) que los del archivo que se descarga si selecciona la opción **Guardar resultados cargados**. Los valores de los dos archivos CSV diferentes para la misma actividad también podrían ser distintos. Por ejemplo, la actividad de la columna **Acción**en el archivo CSV y podría tener un valor diferente que el nombre "sencillo" de usuario que se muestra en la columna de**Actividad** de la página de **Búsqueda de registros de auditoría**. Por ejemplo, MailboxLogin vs. el usuario ha iniciado sesión en el buzón.

- Cuando descargue todos los resultados de una consulta de búsqueda que contenga eventos de diferentes servicios de Office 365, la columna**AuditData**del archivo CSV contiene diferentes propiedades dependiendo del servicio en que se ha realizado la acción. Por ejemplo, las entradas de los registros de auditoría de Exchange y Azure AD incluyen una propiedad denominada**ResultStatus** que indica si la acción se ha realizado correctamente o no. Esta propiedad no se incluye para los eventos en SharePoint. De manera similar, los eventos de SharePoint tienen una propiedad que identifica la dirección URL del sitio para las actividades relacionadas con la carpeta y el archivo. Para mitigar este comportamiento, considere la posibilidad de usar diferentes búsquedas para exportar los resultados de las actividades de un único servicio. 
    
    Para obtener una descripción de las propiedades que se enumeran en la columna **AuditData** del archivo CSV cuando descarga todos los resultados, y el servicio se aplica en cada uno, consulte[Propiedades detalladas del registro de auditoría de Office 365](detailed-properties-in-the-office-365-audit-log.md).

## <a name="audited-activities"></a>Actividades auditadas

Las tablas de esta sección describen las actividades que se auditan en Office 365. Puede buscar estos eventos al buscar el registro de auditoría en el centro de seguridad y cumplimiento.
  
En estas tablas se agrupan actividades relacionadas o las actividades de un servicio específico de Office 365. La tabla incluye el nombre sencillo que se muestra en la lista desplegable de**Actividades**y el nombre de la operación correspondiente que aparece en la información detallada de una grabación de auditoría y en el archivo CSV cuando exporta los resultados de búsqueda. Para descripciones de la información detallada, consulte las[ Propiedades detalladas del registro de auditoría de Office 365](detailed-properties-in-the-office-365-audit-log.md)
  
Haga clic en uno de los vínculos siguientes para ir a una tabla en particular.
  
||||
|:-----|:-----|:-----|
|[Actividades de páginas y archivos](#file-and-page-activities)<br/> |[Actividades de carpetas](#folder-activities)<br/> |[Lista de actividades de SharePoint](#sharepoint-list-activities)<br/>|
|[Actividades de solicitud de acceso y uso compartido](#sharing-and-access-request-activities)<br/> |[Actividades de sincronización](#synchronization-activities)<br/> |[Actividades de permisos del sitio](#site-permissions-activities)<br/> |
|[Actividades de administración del sitio](#site-administration-activities)<br/> |[Actividades de buzón de Exchange](#exchange-mailbox-activities)<br/> |[Actividades de Sway](#sway-activities) <br/> |
|[Actividades de administración de usuarios](#user-administration-activities) <br/> |[Actividades de administración de grupos de Azure AD](#azure-ad-group-administration-activities) <br/> |[Actividades de administración de aplicaciones](#application-administration-activities) <br/> |
|[Actividades de administración de roles](#role-administration-activities) <br/> |[Actividades de administración de directorios](#directory-administration-activities) <br/>|[Actividades de eDiscovery](#ediscovery-activities) <br/> |
|[Actividades de eDiscovery avanzado](#advanced-ediscovery-activities)<br/> |[Actividades de Power BI](#power-bi-activities) <br/> |[Microsoft Workplace Analytics](#microsoft-workplace-analytics-activities)<br/>|
|[Actividades de Microsoft Teams](#microsoft-teams-activities) <br/> |[Actividades de Yammer](#yammer-activities) <br/> |[Actividades de Microsoft Flow](#microsoft-flow-activities) <br/>|
|[Actividades Microsoft PowerApps](#microsoft-powerapps)<br/>|[Actividades de Microsoft Stream](#microsoft-stream-activities) <br/>|[Actividades de administración de Exchange](#exchange-admin-audit-log)<br/>|
||||
  
### <a name="file-and-page-activities"></a>Actividades de páginas y archivos
  
En la siguiente tabla se describen las actividades de archivos y páginas en SharePoint en línea y OneDrive para la empresa.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Archivo al que se tiene acceso  <br/> |FileAccessed  <br/> |Cuenta de sistema o usuario que tiene acceso al archivo.  <br/> |
|(ninguno)  <br/> |FileAccessedExtended  <br/> |Esto está relacionado con la actividad "Archivo al que se tiene acceso" (FileAccessed). Se registra un evento FileAccessedExtended cuando la misma persona tiene acceso continuamente a un archivo durante un largo período (hasta 3 horas). El objetivo del registro de eventos FileAccessedExtended es reducir el número de eventos FileAccessed que se registran cuando se tiene acceso continuamente a un archivo. Esto ayuda a reducir el ruido de varios registros FileAccessed para lo que básicamente es la misma actividad de usuario y le permite centrarse en el evento FileAccessed inicial (el más importante).  <br/> |
|Etiqueta cambiada de política de cumplimiento <br/> |ComplianceSettingChanged<br/> |Se aplicó o se quitó una etiqueta de retención de un documento. Este evento se activa cuando una etiqueta de retención es aplicada manual o automáticamente a un mensaje.<br/> |
|Estado de registro cambiado a bloqueado<br/> |LockRecord<br/> |El estado de registro de una etiqueta de retención que clasifica un documento como un registro ha siso bloqueado. Esto significa que el documento no se puede modificar ni eliminar. Solo los usuarios que tengan al menos asignado el permiso de colaborador para un sitio podrán cambiar el estado de registro de un documento.<br/> |
|Cambiado el estado del registro a bloqueado<br/> |UnlockRecord<br/> |El estado de registro de una etiqueta de retención que clasifica un documento como un registro ha sido bloqueado. Esto significa que el documento puede ser modificado o eliminado. Solo los usuarios que tengan al menos asignado el permiso de colaborador para un sitio podrán cambiar el estado de registro de un documento.<br/><br/> |
|Archivo verificado  <br/> |FileCheckedIn  <br/> |El usuario inserta en el repositorio un documento que se extrajo de una biblioteca de documentos.  <br/> |
|Archivo extraído del repositorio  <br/> |FileCheckedOut  <br/> |El usuario extrae un documento ubicado en una biblioteca de documentos. Los usuarios pueden extraer y modificar documentos que se han compartido con ellos.  <br/> |
|Archivo copiado  <br/> |FileCopied  <br/> |El usuario copia un documento desde un sitio. El archivo copiado puede guardarse en otra carpeta en el sitio.  <br/> |
|Archivo eliminado  <br/> |FileDeleted  <br/> |El usuario elimina un documento de un sitio.  <br/> |
|Archivo eliminado de la papelera de reciclaje  <br/> |FileDeletedFirstStageRecycleBin  <br/> |El usuario elimina un archivo de la papelera de reciclaje de un sitio.  <br/> |
|Archivo eliminado de la papelera de reciclaje de segundo nivel  <br/> |FileDeletedSecondStageRecycleBin  <br/> |El usuario elimina un archivo de la papelera del segundo nivel de la papelera de reciclaje de un sitio.  <br/> |
|Política de cumplimiento de etiqueta borrada<br/> |ComplianceRecordDelete<br/> |Un documento que se clasificó como un registro fue eliminado. Un documento se considera un registro cuando se le aplica una etiqueta de retención que clasifica el contenido como un registro. <br/> |
|Desfase detectado de la sensibilidad del documento  <br/>|DocumentSensitivityMismatchDetected<br/>|El usuario carga un documento clasificado con una etiqueta de sensibilidad que tiene una prioridad mayor que la que se ha aplicado al sitio en el que se carga el documento. Este evento no se activa si la etiqueta de sensibilidad que se aplica a un sitio tiene una prioridad más alta que la etiqueta de sensibilidad que se ha aplicado a un documento cargado en el sitio. Para obtener más información acerca de la prioridad de las etiquetas de sensibilidad, consulte la sección "prioridad de etiqueta" en[Introducción a las etiquetas de carácter](sensitivity-labels.md#label-priority-order-matters).<br/>|
|Malware detectado en archivo  <br/> |FileMalwareDetected  <br/> |El antivirus de SharePoint detecta el malware en un archivo.  <br/> |
|Extracción del archivo descartada  <br/> |FileCheckOutDiscarded  <br/> |El usuario descarta (o deshace) la extracción del repositorio de un archivo. Eso significa que cualquier cambio que haya realizado en el archivo cuando estaba extraído del repositorio se descarta y no se guarda en la versión del documento de la biblioteca de documentos.  <br/> |
|Archivo descargado  <br/> |FileDownloaded  <br/> |El usuario descarga un documento de un sitio.  <br/> |
|Archivo modificado  <br/> |FileModified  <br/> |La cuenta del sistema o usuario modifica el contenido o las propiedades de un documento ubicado en un sitio.  <br/> |
|(ninguno)  <br/> |FileModifiedExtended  <br/> |Esto está relacionado con la actividad "Archivo modificado" (FileModified). Se registra un evento FileModifiedExtended cuando la misma persona modifica constantemente un archivo durante un largo período de tiempo (hasta 3 horas). El objetivo del registro de eventos FileModifiedExtended es reducir el número de eventos FileModified que se registran cuando se modifica continuamente un archivo. Esto ayuda a reducir el ruido de varios registros de FileModified para lo que básicamente es la misma actividad de usuario, y le permite centrarse en el evento FileModified inicial (el más importante).  <br/> |
|Archivo movido  <br/> |FileMoved  <br/> |El usuario mueve un documento de su ubicación actual en un sitio a una nueva ubicación.  <br/> |
|(ninguno)  <br/> |FilePreviewed  <br/> |El usuario obtiene la vista previa de un documento de SharePoint o de OneDrive para un sitio de Empresas. Estos sucesos suelen producirse en grandes volúmenes basándose en una sola actividad, como ver una galería de imágenes.  <br/> |
|Todas las versiones menores del archivo recicladas  <br/> |FileVersionsAllMinorsRecycled  <br/> |El usuario elimina todas las versiones secundarias del historial de versiones de un archivo. Las versiones eliminadas se mueven a la Papelera de reciclaje del sitio.  <br/> |
|Todas las versiones del archivo recicladas  <br/> |FileVersionsAllRecycled  <br/> |El usuario elimina todas las versiones del historial de versiones de un archivo. Las versiones eliminadas se mueven a la Papelera de reciclaje del sitio.  <br/> |
|Versión del archivo reciclada  <br/> |FileVersionRecycled  <br/> |El usuario elimina una versión del historial de versiones de un archivo. La versión eliminada se mueve a la Papelera de reciclaje del sitio.  <br/> |
|Archivo al que se le ha cambiado el nombre  <br/> |FileRenamed  <br/> |El usuario cambia el nombre de un documento en un sitio.  <br/> |
|Archivo restaurado  <br/> |FileRestored  <br/> |El usuario restaura un documento de la papelera de reciclaje de un sitio.   <br/> |
|Archivo cargado  <br/> |FileUploaded  <br/> |El usuario carga un documento a una carpeta de un sitio.   <br/> |
|Página visualizada  <br/> |PageViewed  <br/> |El usuario visualiza una página en un sitio. No incluye el uso de un explorador web para ver los archivos ubicados en una biblioteca de documentos.  <br/> |
|(ninguno)  <br/> |PageViewedExtended  <br/> |Esto está relacionado con la actividad "Página visualizada" (PageViewed). Se registra un evento PageViewedExtended cuando la misma persona visualiza continuamente una página web durante un periodo extendido (hasta 3 horas). El objetivo del registro de eventos PageViewedExtended es reducir el número de eventos PageViewed que se registran cuando se visualiza una página continuamente. Esto ayuda a reducir el ruido de varios registros de PageViewed para lo que básicamente es la misma actividad de usuario, y le permite centrarse en el evento inicial PageViewed(el más importante).  <br/> |
|Ver señalado por el cliente <br/>|ClientViewSignaled<br/>|El cliente de un usuario (como un sitio web o una aplicación móvil) ha señalado que el usuario ha visto la página indicada. Esta actividad a menudo se registra después de un evento de PagePrefetched para una página. <br/><br/>**Nota**: Como el cliente señaliza eventos ClientViewSignaled, en lugar del servidor, es posible que el servidor no pueda registrar el evento y, por lo tanto, puede que no aparezca en el registro de auditoría. También es posible que la información del registro de auditoría no sea confiable. Sin embargo, dado que la identidad del usuario se valida por símbolo usado para crear la señal, la identidad del usuario que aparece en el registro de auditoría correspondiente es precisa. |
|(ninguno) <br/>|PagePrefetched<br/>|El cliente de un usuario (como el sitio web o la aplicación móvil) ha solicitado la página indicada para ayudar a mejorar el rendimiento si el usuario lo explora. Este evento se registra para indicar que el contenido de la página se ha puesto para el cliente del usuario. Este evento no es una indicación definitiva de que el usuario ha navegado hasta la página. Cuando el contenido de la página es emitido por el cliente (de acuerdo con la solicitud del usuario), debe generarse un evento ClientViewSignaled. No todos los clientes son compatibles con la búsqueda previa, y por lo tanto, algunas actividades que se buscan previamente se pueden registrar como eventos PageViewed.<br/>|
||||
  
### <a name="folder-activities"></a>Actividades de carpetas
  
La siguiente tabla describe las actividades de archivos y páginas en SharePoint en línea y OneDrive para empresas.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Carpeta copiada  <br/> |FolderCopied  <br/> |El usuario copia una carpeta de un sitio a otra ubicación en SharePoint o en OneDrive para Empresas.  <br/> |
|Carpeta creada  <br/> |FolderCreated  <br/> |El usuario crea una carpeta en un sitio.  <br/> |
|Carpeta eliminada  <br/> |FolderDeleted  <br/> |El usuario elimina una carpeta de un sitio.  <br/> |
|Carpeta eliminada de la papelera de reciclaje  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |El usuario elimina una carpeta de la papelera de reciclaje de un sitio.  <br/> |
|Carpeta eliminada de la papelera de reciclaje de segundo nivel  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |El usuario elimina una carpeta de la papelera de reciclaje de segundo nivel de un sitio.  <br/> |
|Carpeta modificada  <br/> |FolderModified  <br/> |El usuario modifica una carpeta en un sitio. Esto incluye la modificación de los metadatos de carpeta, como el cambio de etiquetas y propiedades.  <br/> |
|Carpeta movida  <br/> |FolderMoved  <br/> |El usuario mueve una carpeta a una ubicación diferente del sitio.  <br/> |
|Carpeta con el nombre cambiado  <br/> |FolderRenamed  <br/> |El usuario cambia el nombre de una carpeta en un sitio.  <br/> |
|Carpeta restaurada  <br/> |FolderRestored  <br/> |El usuario restaura una carpeta eliminada de la papelera de reciclaje de un sitio.  <br/> |
||||
  
### <a name="sharepoint-list-activities"></a>Lista de actividades de SharePoint
  
En la siguiente tabla se describen las actividades relacionadas cuando los usuarios interactúan con listas y elementos de lista en SharePoint en línea.

|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
| Lista creada              | ListCreated              | Un usuario ha creado una lista de SharePoint.|
| Columna de lista creada       | ListColumnCreated        | Un usuario ha creado una columna de lista de SharePoint. Una columna de lista es una columna que está adjunta a una o más listas de SharePoint. |
| Lista de tipo de contenido de lista creado | ListContentTypeCreated   | Lista de tipo de contenido creado por un usuario. Una lista de tipo de contenido es un tipo de contenido que está adjunta a una o más listas de SharePoint.|
| Lista de ítems creada         | ListItemCreated          | Un usuario creó un elemento en una lista de SharePoint existente.|
| Una columna de sitio creada.       | SiteColumnCreated        | Un usuario ha creado una columna de sitio de SharePoint. Una columna de sitio es una columna que no está adjunta a una lista. Las columnas de sitio también son estructuras de metadatos que se pueden usar en cualquier lista en una web determinada.|
| Tipo de contenido de sitio creado | Sitio de ContentType creado | Tipo de contenido de sitio creado por un usuario. Un tipo de contenido de sitio es un tipo de contenido que está adjunto al sitio principal.|
| Lista eliminada              | ListDeleted              | Un usuario borró una lista de SharePoint.|
| Eliminar Columna de lista        | Columna de lista eliminada      | Un usuario borró una columna de lista de SharePoint.|
| Lista de tipo de contenido eliminado | ListContentTypeDeleted   | Un usuario borró una lista de tipo de contenido. |
| Eliminar Lista de elementos          | Lista de elementos eliminada        | Un usuario borró una lista de elementos de SharePoint.|
| Columna de sitio eliminada.       | SiteColumnDeleted        | Un usuario borró una columna de sitio de SharePoint. |
| Tipo de contenido de sitio eliminado | SiteContentTypeDeleted   | Un usuario borró un sitio de tipo de contenido.|
| Lista de elementos reciclados        | ListItemRecycled         | Un usuario movió una lista de elementos de SharePoint a la papelera de reciclaje.|
| Lista restaurada             | ListRestored             | Un usuario restauró una lista de SharePoint a la papelera de reciclaje.|
| Lista de elementos restaurada        | ListItemRestored         | Un usuario restauró una lista de SharePoint de la papelera de reciclaje.|
| Lista actualizada              | ListUpdated              | Un usuario ha actualizado una lista de SharePoint modificando una o más propiedades.|
| Columna de lista actualizada       | ListColumnUpdated        | Un usuario ha actualizado una lista de columna de SharePoint modificando una o más propiedades.|
| Lista de tipo de contenido actualizado | ListContentTypeUpdated   | Un usuario ha actualizado una lista de tipo de contenido de SharePoint modificando una o más propiedades.|
| Lista de elementos actualizada         | ListItemUpdated          | Un usuario ha actualizado una lista de elementos de SharePoint modificando una o más propiedades.|  
| Una columna de sitio actualizada.       | SiteColumnUpdated        | Un usuario ha actualizado una de columna de sitio de SharePoint modificando una o más propiedades.|
| Tipo de contenido de sitio actualizado | SiteContentTypeUpdated   | Un usuario ha actualizado una lista de tipo de contenido modificando una o más propiedades.|
||||

### <a name="sharing-and-access-request-activities"></a>Actividades de solicitud de acceso y uso compartido
  
La siguiente tabla describe las actividades de solicitud de acceso y uso compartido de usuarios en SharePoint en línea y OneDrive para empresas. Para los eventos compartidos, la columna de**Detalles**según losResultados identifica el nombre del usuario o grupo con el que se ha compartido el elemento y si el usuario o grupo es un miembro o un invitado de su organización. Para obtener más información, consulte[Usar la auditoría de uso compartido en el registro de auditoría de Office 365](use-sharing-auditing.md).
  
> [!NOTE]
> Los usuarios pueden ser *miembros* o *invitados*basados en la propiedad UserType del objeto de usuario. Un miembro es normalmente un empleado, y un invitado es normalmente un colaborador externo de la organización. Cuando un usuario acepta una invitación de uso compartido (y todavía no forma parte de la organización), se crea una cuenta de invitado para él en el directorio de la organización. Una vez que el usuario invitado tenga una cuenta en su directorio, los recursos pueden compartirse directamente con él (sin requerir una invitación). 
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Nivel de permiso agregado a la colección de sitios  <br/> |PermissionLevelAdded  <br/> |Un nivel de permisos se agregó a una colección de sitios.  <br/> |
|Solicitud de acceso aceptada  <br/> |AccessRequestAccepted  <br/> |Una solicitud de acceso a un sitio, carpeta o documento que se ha aceptado y al usuario solicitante se le ha concedido el acceso.  <br/> |
|Invitación de uso compartido aceptada  <br/> |SharingInvitationAccepted  <br/> |El usuario (miembro o invitado) ha aceptado una invitación de uso compartido y se le ha concedido acceso a un recurso. Este evento incluye información sobre el usuario al que se ha invitado y la dirección de correo electrónico que se ha usado para aceptar la invitación (podrían ser diferentes). Esta actividad a menudo está acompañada por un segundo evento que describe cómo se le ha concedido acceso al usuario al recurso, por ejemplo, al agregar el usuario a un grupo que tiene acceso al recurso.  <br/> |
|Invitación de uso compartido bloqueada  <br/> |SharingInvitationBlocked  <br/> | Una invitación para compartir enviada por un usuario de su organización está bloqueada por una normativa de uso compartido externa que permite o niega el uso compartido externo basándose en el dominio del usuario de destino. En este caso, la invitación para compartir se bloqueó porque:  <br/>  El dominio del usuario de destino no está incluido en la lista de dominios permitidos.  <br/>  O bien:  <br/>  El dominio del usuario de destino está incluido en la lista de dominios bloqueados.  <br/>  Para obtener más información acerca de cómo permitir o bloquear el uso compartido externo en función de los dominios, consulte [Dominios restringidos para el uso compartido en SharePoint en línea y OneDrive para Empresas](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9).  <br/> |
|Solicitud de acceso creada  <br/> |AccessRequestCreated  <br/> |El usuario solicita acceso a un sitio, carpeta o documento al que no tiene permiso para acceder.  <br/> |
|Vínculo creado que se puede compartir de la empresa   <br/> |CompanyLinkCreated  <br/> |El usuario ha creado un vínculo empresarial de recursos. los vínculos empresariales solo pueden usarse por los miembros de su organización. No pueden ser usados por invitados.  <br/> |
|Vínculo anónimo creado  <br/> |AnonymousLinkCreated  <br/> |El usuario ha creado un vínculo anónimo a un recurso. Cualquier persona con este vínculo puede tener acceso al recurso sin tener que autenticarse.  <br/> |
|Vínculo de seguridad creado  <br/> |SecureLinkCreated  <br/> |Se ha creado un vínculo de uso compartido seguro para este elemento.  <br/> |
|Invitación de uso compartido creada  <br/> |SharingInvitationCreated  <br/> |El usuario ha compartido un recurso en o con un usuario que no está en el directorio de su organización.   <br/> |
|Vínculo de seguridad eliminado  <br/> |SecureLinkDeleted  <br/> |Un vínculo para uso compartido seguro se ha eliminado.  <br/> |
|Solicitud de acceso denegada   <br/> |AccessRequestDenied  <br/> |Una solicitud de acceso a un sitio, una carpeta o un documento se ha denegado.  <br/> |
|Vínculo quitado que se puede compartir de la empresa  <br/> |CompanyLinkRemoved  <br/> |El usuario ha quitado un vínculo de toda la empresa a un recurso. El vínculo ya no puede usarse para tener acceso al recurso.  <br/> |
|Vínculo anónimo quitado  <br/> |AnonymousLinkRemoved  <br/> |El usuario ha quitado un vínculo anónimo a un recurso. El vínculo ya no puede usarse para tener acceso al recurso.  <br/> |
|Sitio, carpeta o archivo compartidos  <br/> |SharingSet  <br/> |El usuario (miembro o invitado) ha compartido un archivo, carpeta o sitio en SharePoint o OneDrive con un usuario en el directorio de la organización. El valor de la columna **Detalles**para esta actividad identifica el nombre del usuario que el recurso ha compartido y si este usuario es un miembro o un invitado. Esta actividad a menudo está acompañada por un segundo evento que describe cómo se le ha concedido acceso al usuario a los recursos. Por ejemplo, al agregar el usuario a un grupo que tiene acceso al recurso.  <br/> |
|Solicitud de acceso actualizada  <br/> |AccessRequestUpdated  <br/> |Se actualizó una solicitud de acceso a un elemento.  <br/> |
|Vínculo anónimo actualizado   <br/> |AnonymousLinkUpdated  <br/> |El usuario ha actualizado un vínculo anónimo a un recurso. El campo actualizado se incluye en la propiedad EventData cuando exporta los resultados de búsqueda.  <br/> |
|Invitación de uso compartido actualizada  <br/> |SharingInvitationUpdated  <br/> |Se actualizó una invitación para uso compartido externo.  <br/> |
|Vínculo anónimo usado  <br/> |AnonymousLinkUsed  <br/> |Un usuario anónimo ha tenido acceso a un recurso mediante un vínculo anónimo. La identidad del usuario puede ser desconocida, pero puede obtener otros detalles como la dirección IP del usuario.  <br/> |
|Sitio, carpeta o archivo no compartido  <br/> |SharingRevoked  <br/> |El usuario (miembro o invitado) no ha compartido un archivo, carpeta o sitio que se había compartido previamente con otro usuario.  <br/> |
|Vínculo usado que se puede compartir de la empresa  <br/> |CompanyLinkUsed  <br/> |El usuario ha tenido acceso a un recurso mediante un vínculo de toda la empresa.  <br/> |
|Vínculo seguro usado  <br/> |SecureLinkUsed  <br/> |Un usuario usó un vínculo seguro.  <br/> |
|Usuario añadido a vínculo seguro  <br/> |AddedToSecureLink  <br/> |Se ha agregado un usuario a la lista de entidades que pueden usar un vínculo de uso compartido seguro.  <br/> |
|Usuario quitado de un vínculo seguro  <br/> |RemovedFromSecureLink  <br/> |Se ha quitado un usuario de la lista de entidades que pueden usar un vínculo de uso compartido seguro.  <br/> |
|Invitación de uso compartido retirada  <br/> |SharingInvitationRevoked  <br/> |El usuario ha retirado una invitación de uso compartido a un recurso.   <br/> |
||||
  
### <a name="synchronization-activities"></a>Actividades de sincronización
  
La siguiente tabla enumera la sincronización de archivos de actividades en SharePoint en línea y OneDrive para empresas.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Equipo permitido para sincronizar archivos  <br/> |ManagedSyncClientAllowed  <br/> |El usuario establece correctamente una relación de sincronización con un sitio. La relación de sincronización es correcta porque el equipo del usuario es un miembro de un dominio que se ha agregado a la lista de dominios (denominada * lista de destinatarios seguros*) que puede obtener acceso a las bibliotecas de documentos de su organización.  <br/> Para obtener más información sobre esta característica, vea [Usar cmdlets de Windows PowerShell para habilitar la sincronización de OneDrive para los dominios que están en la lista de destinatarios seguros](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|Computadora bloqueada de los archivos de sincronización  <br/> |UnmanagedSyncClientBlocked  <br/> |El usuario intenta establecer una relación de sincronización con un sitio desde una computadora que no es un miembro del dominio de la organización o es un miembro de un dominio que no se ha agregado a la lista de dominios (denominada la *lista de destinatarios seguros) *que puede tener acceso a las librerías de documentos de su organización. La relación de sincronización no se permite y el equipo del usuario queda bloqueado para sincronizar, descargar o cargar archivos en una biblioteca de documentos.  <br/> Para obtener más información sobre esta característica, vea [Usar cmdlets de Windows PowerShell para habilitar la sincronización de OneDrive para los dominios que están en la lista de destinatarios seguros](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|Archivos descargados al equipo  <br/> |FileSyncDownloadedFull  <br/> |El usuario establece una relación de sincronización y descarga archivos correctamente la primera vez a su equipo desde la biblioteca de documentos.  <br/> |
|Cambios de archivos descargados al equipo  <br/> |FileSyncDownloadedPartial  <br/> |El usuario descarga correctamente cualquier cambio a los archivos de una librería de documentos. Esta actividad indica que cualquier cambio que se realice en los archivos de la librería de documentos se descarga en el equipo del usuario. Solo se descargaron los cambios porque la biblioteca de documentos se había descargado anteriormente por el usuario (como se indica en la actividad **Archivos descargados al equipo**).  <br/> |
|Archivos cargados a la biblioteca de documentos  <br/> |FileSyncUploadedFull  <br/> |El usuario establece una relación de sincronización y carga archivos correctamente la primera vez desde su equipo a la biblioteca de documentos.  <br/> |
|Cambios de archivos cargados a la biblioteca de documentos  <br/> |FileSyncUploadedPartial  <br/> |El usuario carga correctamente los cambios a una librería de documentos. Este evento indica que cualquier cambio realizado en la versión local de un archivo de una biblioteca de documentos se carga correctamente en dicha biblioteca. Solo se cargaron los cambios porque esos archivos se habían cargado anteriormente por el usuario (como se indica en la actividad **Archivos cargados a la librería de documentos**).  <br/> |
||||

### <a name="site-permissions-activities"></a>Actividades de sitios de permisos 

La siguiente tabla enumera eventos relacionan asignar permisos en SharePoint con usar grupos para dar (y revocar) acceso a sitios.

|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Administradores de la colección de sitios agregados  <br/> |SiteCollectionAdminAdded  <br/> |El administrador de la colección de sitios o el propietario agrega una persona como administrador de la colección de sitios a un sitio. Los administradores de colección de sitios tienen permisos de control total para la colección de sitios y todos los sub sitios. Esta actividad también se registra cuando un administrador concede acceso a la cuenta de OneDrive de un usuario (editando el perfil de usuario en el Centro de administración de SharePoint o[ mediante el Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data#part-1---get-access-to-the-former-employees-onedrive-for-business-documents)). <br/> |
|Usuario o grupo agregado al grupo de SharePoint  <br/> |AddedToGroup  <br/> |El usuario ha agregado a un miembro o un invitado a un grupo de SharePoint. Esto puede haber sido una acción intencionada o el resultado de otra actividad, como un evento de uso compartido.  <br/> |
|Herencia de nivel de permisos interrumpida  <br/> |PermissionLevelsInheritanceBroken  <br/> |Se cambió a un elemento de forma que ya no hereda niveles de permisos de su elemento primario.  <br/> |
|Herencia de uso compartido interrumpida  <br/> |SharingInheritanceBroken  <br/> |Se cambió a un elemento de forma que ya no hereda permisos de uso compartido de su elemento primario.  <br/> |
|Grupo creado  <br/> |GroupAdded  <br/> |El administrador o el propietario del sitio crea un grupo para un sitio o realiza una tarea que da como resultado un grupo que se está creando. Por ejemplo, la primera vez que un usuario crea un vínculo para compartir un archivo, se agrega un grupo del sistema al sitio de OneDrive para la Empresa del usuario. Este evento también puede ser un resultado de que un usuario crease un vínculo con permisos de edición para un archivo compartido.  <br/> |
|Grupo eliminado  <br/> |GroupRemoved  <br/> |El usuario elimina un grupo de un sitio.   <br/> |
|Configuración de solicitud de acceso modificada  <br/> |WebRequestAccessModified  <br/> |La configuración de solicitud de acceso fueron modificadas en un sitio.  <br/> |
|Configuración modificada "los miembros pueden compartir"   <br/> |WebMembersCanShareModified  <br/> |Los **miembros pueden compartir** la configuración se ha modificado en un sitio.  <br/> |
|Nivel de permiso modificado en la colección de sitios  <br/> |PermissionLevelModified  <br/> |Un nivel de permisos se modificó en una colección de sitios.  <br/> |
|Permisos de sitio modificados  <br/> |SitePermissionsModified  <br/> |El administrador o el propietario del sitio (o la cuenta de sistema) cambia el nivel de permisos que se asignan a un grupo en un sitio. Esta actividad también se registra si todos los permisos son removidos de un grupo.  <br/><br/> **Nota**:Esta operación se ha dejado de usar en SharePoint en línea. Para buscar eventos relacionados, puede buscar otras actividades relacionadas con el permiso como **Administradores de la colección de sitios agregados**, **Usuario o grupo agregado a un grupo de SharePoint**,**Usuario permitido para crear grupos**, **Grupo creado** y **Grupo eliminado.|
|Nivel de permiso eliminado de la colección de sitios  <br/> |PermissionLevelRemoved  <br/> |Un nivel de permisos se eliminó de una colección de sitios.  <br/> |
|Administradores de la colección de sitios removidos  <br/> |SiteCollectionAdminRemoved <br/> |El administrador de la colección de sitios o el propietario remueve una persona como administrador de la colección de sitios a un sitio. Esta actividad también se registra cuando un administrador se remueve así mismo de la lista de colección de administradores a la cuenta de OneDrive de un usuario (editando el perfil de usuario en el Centro de administración de SharePoint).  Para devolver esta actividad en los resultados de búsqueda del registro de auditoría, tiene que buscar todas las actividades. <br/> |
|Usuario o grupo removido al grupo de SharePoint  <br/> |RemovedFromGroup  <br/> |El usuario ha removido un miembro o invitado de un grupo de SharePoint. Esto puede haber sido una acción intencionada o el resultado de otra actividad, como un evento sin uso compartido.  <br/> |
|Permisos de administrador del sitio solicitados  <br/> |SiteAdminChangeRequest  <br/> |Las solicitudes de usuario se agregan como un administrador de la colección de sitios para una colección de sitios. Los administradores de colección de sitios tienen permisos de control total para la colección de sitios y todos los sub sitios.  <br/> |
|Herencia de uso compartido restaurada  <br/> |SharingInheritanceReset  <br/> |Se aplicó un cambio para que un elemento herede los permisos de uso compartido del elemento primario.  <br/> |
|Grupo actualizado  <br/> |GroupUpdated  <br/> |El administrador o el propietario cambia la configuración de un grupo para un sitio. Esto puede incluir cambiar el nombre del grupo, quién puede ver o editar la pertenencia al grupo y cómo se controlan las solicitudes de pertenencia.  <br/> |
||||

  
### <a name="site-administration-activities"></a>Actividades de administración del sitio
  
En la tabla siguiente se enumeran los eventos que se producen de las tareas de administración del sitio en SharePoint en línea.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Ubicación de datos añadidos permitidos<br/>|AllowedDataLocationAdded|Un administrador global o de SharePoint ha agregado una ubicación de datos permitida en un entorno multi geo. <br/>|
|Agente de usuario exento agregado  <br/> |ExemptUserAgentSet  <br/> |El administrador global o de SharePoint agrega un agente de usuario a la lista de agentes de usuario exentos en el Centro de administración de SharePoint.  <br/> |
|Se ha agregado el administrador de ubicación geográfica<br/>|GeoAdminAdded<br/>|Un administrador global o de SharePoint agregó un usuario como administrador geográfico de una ubicación. <br/>|
|Usuario permitido para crear grupos  <br/> |AllowGroupCreationSet  <br/> |El administrador de sitios o el propietario agrega un nivel de permisos a un sitio que permite que un usuario al que se le ha asignado ese permiso cree un grupo para ese sitio.  <br/> |
|Desplazamiento geográfico de sitio cancelado  <br/> |SiteGeoMoveCancelled  <br/> |Un administrador global o de SharePoint canceló correctamente un desplazamiento geográfica de un sitio de SharePoint o de OneDrive. La capacidad multi geográfica le permite una organización de Office 365 abarcar diversas ubicaciones geográficas de centro de datos de Office 365, que se denominan geográficas Para obtener más información, consulte [Funcionalidades multi geográficas en OneDrive y SharePoint en línea en Office 365](https://go.microsoft.com/fwlink/?linkid=860840).  <br/> |
|Normativa de uso compartido cambiada  <br/> |SharingPolicyChanged  <br/> |Un administrador global o de SharePoint cambió una normativa de uso compartido de SharePoint mediante el portal de administración de Office 365, el portal de administración de SharePoint, o el shell de administración de SharePoint en línea. Se registrará cualquier cambio en la configuración de la directiva de uso compartido de su organización. La normativa cambiada se identifica en el campo**ModifiedProperties** en las propiedades detalladas del registro de eventos.  <br/> |
|Directiva de acceso del dispositivo cambiada  <br/> |DeviceAccessPolicyChanged  <br/> |Un administrador global o de SharePoint cambió la directiva de dispositivos no administrados para su organización. Esta directiva controla el acceso a SharePoint, OneDrive y Office 365 desde dispositivos que no se ha unido a su organización. La configuración de esta directiva requiere una suscripción de Enterprise Mobility + Security. Para obtener más información, consulte [Controlar el acceso desde dispositivos no administrados](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622).  <br/> |
|Agente de usuario exento cambiado  <br/> |CustomizeExemptUsers  <br/> |El administrador global o de SharePoint ha personalizado la lista de agentes de usuario exentos en el Centro de administración de SharePoint. Puede especificar qué agentes de usuario están exentos de recibir una página web completa para indexar. Esto significa que cuando un agente de usuario que ha especificado como exento encuentra un formulario de InfoPath, el formulario se devolverá como un archivo XML en lugar de como una página web completa. Esto acelera la indexación de formularios de InfoPath.  <br/> |
|Directiva de acceso de red cambiada  <br/> |NetworkAccessPolicyChanged  <br/> |Un administrador global o de SharePoint cambió la normativa de acceso basado en la ubicación (también denominada un límite de red de confianza) en el Centro de administración SharePoint o mediante el PowerShell de SharePoint en línea. Este tipo de controles de normativa tienen acceso a recursos de SharePoint y OneDrive de la organización en función de los intervalos de direcciones IP que especifique. Para obtener más información, consulte [Controlar el acceso a datos de SharePoint en línea y OneDrive en función de las ubicaciones de red](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f).  <br/> |
|Desplazamiento geográfico de sitio completado  <br/> |SiteGeoMoveCompleted  <br/> |El desplazamiento geográfico de un sitio que fue programado por un administrador global de su organización se ha completado correctamente. La capacidad multi geográfica le permite una organización de Office 365 abarcar diversas ubicaciones geográficas de centro de datos de Office 365, que se denominan geográficas Para obtener más información, consulte [Funcionalidades multi geográficas en OneDrive y SharePoint en línea en Office 365](https://go.microsoft.com/fwlink/?linkid=860840).  <br/> |
|Conexión a enviar creada  <br/> |SendToConnectionAdded  <br/> |Un administrador global o de SharePoint crea una nueva conexión a enviar en la página administración de registros en el Centro de administración de SharePoint. Una conexión Enviar a especifica la configuración de un repositorio de documentos o un centro de registros. Cuando crea una conexión Enviar a, un Organizador de contenido puede enviar documentos a la ubicación especificada.  <br/> |
|Colección de sitios creada  <br/> |SiteCollectionCreated  <br/> |Un administrador global o de SharePoint crea una colección de sitios en su organización de SharePoint en línea o un usuario aplica el sitio de OneDrive para empresas.  <br/> |
|Orphaned hub site borrado<br/>|HubSiteOrphanHubDeleted<br/>|Un administrador global o de SharePoint ha eliminado un orphan hub site, que es un centro que no tiene ningún sitio asociado. Un orphaned hub es probable que se deba a la eliminación del centro del sitio original  <br/>|
|Conexión a enviar eliminada  <br/> |SendToConnectionRemoved  <br/> |El administrador global o de SharePoint elimina una conexión a enviar en la página Administración de registros en el Centro de administración de SharePoint.  <br/> |
|Sitio eliminado  <br/> |SiteDeleted  <br/> |El administrador del sitio elimina un sitio.  <br/> |
|Vista previa del documento habilitada  <br/> |PreviewModeEnabledSet  <br/> |El administrador del sitio habilita la vista previa del documento para un sitio.  <br/> |
|Flujo de trabajo heredado habilitado  <br/> |LegacyWorkflowEnabledSet  <br/> |El propietario o administrador del sitio agrega el tipo de contenido de tarea de SharePoint 2013 Workflow al sitio. Los administradores globales también pueden habilitar los flujos de trabajo para toda la organización en el Centro de administración de SharePoint.  <br/> |
|Petición a Office habilitada  <br/> |OfficeOnDemandSet  <br/> |El administrador del sitio habilita Office a petición, lo que permite a los usuarios obtener acceso a la última versión de las aplicaciones de escritorio de Office. Office a petición se habilita en el Centro de administración de SharePoint y requiere una suscripción a Office 365 que incluye aplicaciones de Office completas e instaladas.  <br/> |
|Origen de resultados habilitado para las búsquedas de personas<br/>|PeopleResultsScopeSet<br/>|El administrador del sitio crea el origen de resultados de las búsquedas de personas para un sitio.<br/>|
|Fuentes RSS habilitadas  <br/> |NewsFeedEnabledSet  <br/> |El administrador o el propietario del sitio habilita las fuentes RSS para un sitio. Los administradores globales pueden habilitar las fuentes RSS para toda la organización en el Centro de administración de SharePoint.  <br/> |
|Sitio unido al centro del sitio<br/>|HubSiteJoined<br/>|El propietario de un sitio lo asocia a un sitio central.<br/>|
|Sitio central registrado<br/>|HubSiteRegistered<br/>|Un administrador global o de SharePoint crea un sitio central. El resultado es que el sitio se registra para ser un sitio central. <br/>|
|Ubicación de datos permitidos removidos<br/>|AllowedDataLocationDeleted<br/>|Un administrador global o de SharePoint ha removido una ubicación de datos permitida en un entorno multi geográfico.<br/>|
|Se ha removido el administrador de ubicación geográfica<br/>|GeoAdminDeleted<br/>|Un administrador global o de SharePoint removió a un usuario como administrador geográfico de una ubicación.<br/>|
|Sitio renombrado  <br/> |SiteRenamed  <br/> |El administrador o el propietario del sitio cambia el nombre de un sitio  <br/> |
|Desplazamiento geográfico de sitio programado  <br/> |SiteGeoMoveScheduled  <br/> |Un administrador global o de SharePoint desplazó geográficamente con éxito un sitio de SharePoint o de OneDrive. La capacidad multi geográfica le permite una organización de Office 365 abarcar diversas ubicaciones geográficas de centro de datos de Office 365, que se denominan geográficas Para obtener más información, consulte [Funcionalidades multi geográficas en OneDrive y SharePoint en línea en Office 365](https://go.microsoft.com/fwlink/?linkid=860840).  <br/> |
|Establecer sitio del host  <br/> |HostSiteSet  <br/> |Un administrador global o de SharePoint cambia el sitio designado para hospedar sitios personales o de OneDrive para empresas.   <br/> |
|Configurar una cuota de almacenamiento para una ubicación geográfica  <br/> |GeoQuotaAllocated<br/> |Un administrador global o de SharePoint configuró cuota de almacenamiento para ubicación geográfica en un entorno multi geográfico.<br/> |
|Sitio no unido desde el sitio central.<br/>|HubSiteUnjoined<br/>|El propietario de un sitio lo disocia de un sitio a un sitio central.<br/>|
|Sitio central no registrado<br/>|HubSiteUnregistered<br/>|Un administrador global o de SharePoint elimina el registro del sitio como un sitio central. Si se elimina el registro de un sitio central, dejará de funcionar como un sitio central. <br/>|
||||
  
### <a name="exchange-mailbox-activities"></a>Actividades de buzón de Exchange
  
La siguiente tabla enumera las actividades que pueden registrarse mediante el registro de auditoría del buzón de correo. Las actividades de buzón realizadas por el propietario del buzón, usuario delegado o administrador, son registradas automáticamente en el registro de auditoría de Office 365 por 90 días. Es posible para un administrador desactivar el registro de auditoría de buzón para todos los usuarios de su organización. En este caso, no se registra ninguna acción de cualquier usuario en el buzón. Para más información, consulte [Administrar auditoría del buzón](enable-mailbox-auditing.md)..

 También puede buscar actividades de buzón usando el cmdlet[ Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)en el PowerShell de Exchange en línea. 
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Permisos de buzón de delegado agregados  <br/> |AddMailboxPermissions  <br/> |Un administrador asignó el permiso de FullAccess del buzón a un usuario (conocido como delegado) para el buzón de otra persona. El permiso FullAccess permite al delegado abrir el buzón de la otra persona, así como leer y administrar el contenido del buzón.  <br/> |
|Se ha agregado o quitado un usuario con acceso delegado a la carpeta calendario<br/> |UpdateCalendarDelegation<br/> |Se ha agregado o quitado un usuario como delegado hacia el calendario del buzón de otro usuario. La delegación de calendario otorga a otra persona en la misma organización permisos para administrar el calendario del propietario del buzón. <br/> |
|Se agregaron permisos a la carpeta<br/> |AddFolderPermissions<br/> |Un permiso de la carpeta se ha cambiado. Los permisos de carpeta controlan qué usuarios de su organización pueden tener acceso las carpetas de un buzón de correo y los mensajes que contienen.<br/> |
|Mensajes copiados a otra carpeta  <br/> |Copiar  <br/> |Se ha copiado un mensaje a otra carpeta.  <br/> |
|Elementos del buzón creado  <br/> |Crear  <br/> |Se crea un elemento en la carpeta de Calendario, Contactos, Notas o Tareas en el buzón. Por ejemplo, se crea una nueva solicitud de reunión. No se audita la creación, el envío ni la recepción de un mensaje. Además, no se audita la creación de una carpeta del buzón.  <br/> |
|Se ha creado una nueva regla de bandeja de entrada en la aplicación web de Outlook  <br/> |NewInboxRule<br/> |El propietario de un buzón u otro usuario con acceso al buzón creó una regla de la bandeja de entrada en la aplicación web de Outlook Web.<br/> |
|Mensajes eliminados de la carpeta elementos eliminados  <br/> |SoftDelete  <br/> |Un mensaje se ha eliminado de manera permanente o se ha eliminado de la carpeta Elementos eliminados. Estos elementos se mueven a la carpeta Elementos recuperables. Los mensajes también se mueven a la carpeta elementos recuperables cuando un usuario lo selecciona y presiona **Mayús+Supr**.  <br/> |
|Mensaje etiquetado como un registro  <br/> |ApplyRecordLabel<br/> |Un mensaje se clasificó como un registro. Esto ocurre cuando una etiqueta de retención que clasifica el contenido como un registro se aplica manual o automáticamente a un mensaje.<br/> |
|Mensajes movidos a otra carpeta  <br/> |Mover  <br/> |Se ha movido un mensaje a otra carpeta.  <br/> |
|Mensajes movidos a la carpeta Elementos eliminados  <br/> |MoveToDeletedItems  <br/> |Un mensaje se ha eliminado y movido a la carpeta Elementos eliminados.  <br/> |
|Permiso de carpeta modificada  <br/> |UpdateFolderPermissions  <br/> |Un permiso de la carpeta se ha cambiado. Los permisos de carpeta controlan qué usuarios de su organización pueden tener acceso a las carpetas del buzón de correo y los mensajes que contienen.  <br/> |
|Regla de bandeja de entrada modificada de la aplicación web de Outlook <br/> |SetInboxRule<br/> |El propietario de un buzón u otro usuario con acceso al buzón modificó una regla de la bandeja de entrada usando la aplicación web de Outlook.<br/> |
|Mensajes que se han purgado del buzón  <br/> |HardDelete  <br/> |Un mensaje se ha purgado de la carpeta Elementos recuperables (eliminado permanentemente del buzón).  <br/> |
|Permisos de buzón de delegado quitados  <br/> |Remove-MailboxPermission  <br/> |Un administrador quitó el permiso FullAccess (que se asignó a un delegado) del buzón de una persona. Una vez que se haya quitado el permiso FullAccess, el delegado no podrá abrir el buzón de la otra persona ni acceder a ningún contenido.  <br/> |
|Permisos quitados de la carpeta<br/> |RemoveFolderPermissions<br/> |Un permiso de la carpeta se ha removido. Los permisos de carpeta controlan qué usuarios de su organización pueden tener acceso las carpetas de un buzón de correo y los mensajes que contienen.<br/> |
|Mensaje enviado mediante los permisos de Enviar como  <br/> |SendAs  <br/> |Un mensaje se ha enviado con el permiso Enviar como. Esto significa que otro usuario envió el mensaje como si viniera del propietario del buzón.  <br/> |
|Mensaje enviado mediante los permisos en nombre de  <br/> |SendOnBehalf  <br/> |Un mensaje se ha enviado con el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje a nombre del propietario del buzón. El mensaje indica al destinatario a nombre de quién se ha enviado el mensaje y quién lo ha enviado realmente.  <br/> |
|Reglas de la bandeja de entrada actualizadas desde el cliente de Outlook<br/> |UpdateInboxRules<br/> |El propietario de un buzón u otro usuario con acceso al buzón, modificó una regla de la bandeja de entrada en el Outlook del cliente.<br/> |
|Mensaje actualizado  <br/> |Actualizar  <br/> |Un mensaje o sus propiedades han cambiado.  <br/> |
|Usuario que ha iniciado sesión en un buzón  <br/> |MailboxLogin  <br/> |El usuario inició sesión en su buzón.  <br/> |
||||

### <a name="sway-activities"></a>Actividades de Sway
  
En la siguiente tabla se enumeran las actividades de usuario y de administrador de Sway. Sway es una aplicación de Office 365 que ayuda a los usuarios a recopilar, aplicar formato y compartir ideas, historias y presentaciones en un lienzo interactivo basado en la web. Para obtener más información, consulte [Preguntas más frecuentes sobre Sway: ayuda del administrador](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075).
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|El nivel de uso compartido de Sway ha cambiado  <br/> |SwayChangeShareLevel  <br/> |El usuario cambió el nivel de uso compartido de un Sway. Este evento captura al usuario cambiando el ámbito del uso compartido asociado con un Sway; por ejemplo, público frente a dentro de la organización.  <br/> |
|Sway creado  <br/> |SwayCreate  <br/> |El usuario crea un Sway.  <br/> |
|Sway eliminado  <br/> |SwayDelete  <br/> |El usuario elimina un Sway.  <br/> |
|Duplicación de Sway deshabilitada  <br/> |SwayDisableDuplication  <br/> |El usuario deshabilita la duplicación de un Sway.  <br/> |
|Sway duplicado  <br/> |SwayDuplicate  <br/> |El usuario duplica un Sway.  <br/> |
|Sway editado  <br/> |SwayEdit  <br/> |El usuario edita un Sway.  <br/> |
|Duplicación de Sway habilitada  <br/> |EnableDuplication  <br/> |El usuario habilita la duplicación de un Sway. La capacidad de un usuario para habilitar la duplicación de un Sway está habilitada de manera predeterminada.  <br/> |
|Uso compartido de Sway revocado  <br/> |SwayRevokeShare  <br/> |El usuario deja de compartir un Sway al revocar su acceso a él. Revocar el acceso cambia los vínculos asociados a un Sway.  <br/> |
|Sway compartido  <br/> |SwayShare  <br/> |El usuario intenta compartir un Sway. Este evento captura la acción del usuario de hacer clic en un destino de uso compartido específico dentro del menú de uso compartido de Sway. El evento no indica si el usuario ha completado la acción de uso compartido.  <br/> |
|Uso compartido externo de Sway desactivado  <br/> |SwayExternalSharingOff  <br/> |El administrador deshabilita el uso compartido externo de Sway para toda la organización mediante el Centro de administración de Microsoft 365.  <br/> |
|Uso compartido externo de Sway activado  <br/> |SwayExternalSharingOn  <br/> |El administrador habilita el uso compartido externo de Sway para toda la organización mediante el uso del Centro de administración de Microsoft 365.  <br/> |
|Servicio de Sway desactivado  <br/> |SwayServiceOff  <br/> |El administrador deshabilita Sway para toda la organización mediante el Centro de administración de Microsoft 365.  <br/> |
|Servicio de Sway encendido  <br/> |SwayServiceOn  <br/> |El administrador habilita Sway para toda la organización mediante el Centro de administración de Microsoft 365 (El servicio de Sway está habilitado de manera predeterminada).  <br/> |
|Sway visualizado  <br/> |SwayView  <br/> |El usuario visualiza un Sway.  <br/> |
||||

  
### <a name="user-administration-activities"></a>Actividades de administración de usuarios
  
En la tabla siguiente se enumeran las actividades de administración de usuarios que se registran cuando un administrador agrega o cambia una cuenta de usuario al usar el Centro de administración de Microsoft 365 o el Portal de administración de Azure.
  
|**Actividad**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Usuario agregado  <br/> |Agregar usuario  <br/> |Se ha creado una cuenta de usuario de Office 365.  <br/> |
|Licencia de usuario cambiada  <br/> |Cambiar licencia de usuario  <br/> |La licencia que se ha asignado a un usuario ha cambiado. Para ver qué licencias han cambiado, vea la actividad correspondiente **Usuario actualizado**.  <br/> |
|Contraseña de usuario cambiada  <br/> |Cambiar contraseña de usuario  <br/> |Un administrador cambió la contraseña para un usuario.  <br/> |
|Usuario eliminado  <br/> |Eliminar usuario  <br/> |Una cuenta de usuario de Office 365 ha sido eliminada.  <br/> |
|Restablecer contraseña de usuario  <br/> |Restablecer contraseña de usuario  <br/> |Un administrador restableció la contraseña de un usuario.  <br/> |
|Establecer una propiedad que fuerce al usuario a cambiar la contraseña  <br/> |Forzar el cambio de la contraseña de usuario  <br/> |Un administrador estableció la propiedad que obliga a un usuario a cambiar su contraseña la próxima vez que inicie sesión en Office 365.  <br/> |
|Establecer propiedades de licencia  <br/> |Establecer propiedades de licencia  <br/> |Un administrador modificó las propiedades de una licencia asignada a un usuario.  <br/> |
|Usuario actualizado  <br/> |Actualizar usuario  <br/> |Un administrador cambia una o más propiedades de una cuenta de usuario. Para obtener una lista de las propiedades de usuario que pueden actualizarse, consulte la sección "Actualizar atributos de usuario" en [Eventos del informe de auditoría de Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).  <br/> |
||||
  
### <a name="azure-ad-group-administration-activities"></a>Actividades de administración de grupos de Azure AD
  
En la siguiente tabla se enumeran las actividades de administración de grupos que se registran cuando un administrador o un usuario agrega o cambia un grupo de Office 365 o cuando un administrador crea un grupo de seguridad mediante el uso del Centro de administración de Microsoft 365 o el Portal de administración de Azure. Para obtener más información sobre los grupos de Office 365, consulte[Ver, crear y eliminar grupos en el Centro de administración de Microsoft Office 365](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7).
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Grupo agregado  <br/> |Agregar grupo  <br/> |Se ha creado un grupo.  <br/> |
|Miembro agregado a un grupo  <br/> |Agregar miembro a un grupo  <br/> |Un miembro se ha agregado a un grupo.  <br/> |
|Grupo eliminado  <br/> |Eliminar grupo  <br/> |Se ha eliminado un grupo.  <br/> |
|Miembro quitado de un grupo  <br/> |Quitar miembro de un grupo  <br/> |Un miembro se ha quitado de un grupo.  <br/> |
|Grupo actualizado  <br/> |Actualizar grupo  <br/> |Una propiedad de un grupo se ha cambiado.  <br/> |
||||
   
### <a name="application-administration-activities"></a>Actividades de administración de aplicaciones
  
En la siguiente tabla se enumeran las actividades de administración de aplicaciones que se registran cuando un administrador agrega o cambia una aplicación que se ha registrado en Azure AD. Cualquier aplicación que se base en Azure AD para la autenticación debe registrarse en el directorio.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Entrada de delegación agregada  <br/> |Agregar entrada de delegación  <br/> |Un permiso de autenticación se ha creado o concedido a una aplicación en Azure AD.  <br/> |
|Servicio principal agregado  <br/> |Agregar servicio principal  <br/> |Una aplicación se ha registrado en Azure AD. Una aplicación es representada mediante un servicio principal en el directorio.  <br/> |
|Credenciales agregadas a una entidad de servicio   <br/> |Agregar credenciales de entidad de servicio  <br/> |Las credenciales se han agregado a una entidad de servicio en Azure AD. Una entidad de servicio representa una aplicación del directorio.  <br/> |
|Entrada de delegación removida  <br/> |Remover entrada de delegación  <br/> |Un permiso de autenticación se ha removido de una aplicación en Azure AD.  <br/> |
|Entidad de servicio removida del directorio  <br/> |Remover entidad de servicio  <br/> |Una aplicación se ha eliminado o no se ha su registro de Azure AD. Una aplicación es representada mediante un servicio principal en el directorio.  <br/> |
|Credenciales removidas de un servicio principal  <br/> |Remover credenciales de servicio principal  <br/> |Las credenciales se han removido de un servicio principal en Azure AD. Una entidad de servicio representa una aplicación del directorio.  <br/> |
|Establecer entrada de delegación  <br/> |Establecer entrada de delegación  <br/> |Un permiso de autenticación se ha actualizado en una aplicación en Azure AD.  <br/> |
||||

### <a name="role-administration-activities"></a>Actividades de administración de roles
  
En la siguiente tabla se enumeran las actividades de administración de roles de Azure AD que se registran cuando un administrador controla los roles de administración en el Centro de administración de Microsoft 365 o en el Portal de administración de Azure.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Agregar un miembro a un rol  <br/> |Agregar miembro de rol a un rol  <br/> |Se ha agregado un usuario a un rol de administrador en Office 365.  <br/> |
|Se ha removido un usuario de un rol de directorio   <br/> |Quitar miembro de rol de un rol  <br/> |Se ha removido un usuario desde un rol de administrador en Office 365.  <br/> |
|Establecer la información de contacto de la empresa  <br/> |Establecer la información de contacto de la empresa  <br/> |Se han actualizado las preferencias de contacto a nivel empresarial de su organización de Office 365. Esto incluye las direcciones de correo electrónico para el correo electrónico relacionado con las suscripciones enviadas mediante Office 365, así como las notificaciones técnicas sobre los servicios de Office 365.  <br/> |
||||
   
### <a name="directory-administration-activities"></a>Actividades de administración de directorios
  
En la siguiente tabla se enumeran las actividades relacionadas con los dominios y los directorios de Azure AD que se registran cuando un administrador controla la organización de Office 365 en el Centro de administración de Microsoft 365 o en el Portal de administración de Azure.
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Dominio agregado a la empresa  <br/> |Agregar dominio a la empresa  <br/> |Se ha agregado un dominio a la organización de Office 365.  <br/> |
|Se ha agregado un socio al directorio  <br/> |Agregar un socio a la empresa  <br/> |Se ha agregado un socio (administrador delegado) a su organización de Office 365.  <br/> |
|Dominio removido de la empresa  <br/> |Remover dominio de la empresa  <br/> |Se ha removido un dominio a la organización de Office 365.  <br/> |
|Se ha removido un socio del directorio  <br/> |Remover un socio de la empresa  <br/> |Se ha removido un socio (administrador delegado) de la organización de Office 365.  <br/> |
|Establecer información de la organización  <br/> |Establecer información de la organización  <br/> |Se ha actualizado la información de la empresa para la organización de Office 365. Esto incluye las direcciones de correo electrónico para el correo electrónico relacionado con las suscripciones enviadas mediante Office 365, así como las notificaciones técnicas sobre los servicios de Office 365.  <br/> |
|Establecer autenticación de dominio  <br/> |Establecer autenticación de dominio  <br/> |Se ha cambiado la configuración de la autenticación de dominio para la organización de Office 365.  <br/> |
|Se ha actualizado la configuración de federación para un dominio  <br/> |Se ha establecido la configuración de federación en un dominio  <br/> |Se ha cambiado la configuración de federación (uso compartido externo) para la organización de Office 365.  <br/> |
|Establecer normativas de contraseña  <br/> |Establecer normativas de contraseña  <br/> |Se han cambiado las restricciones de caracteres y longitud para las contraseñas de usuario de su organización de Office 365.  <br/> |
|Sincronización de Azure AD activada   <br/> |Establecer la marca DirSyncEnabled en la empresa  <br/> |Se ha establecido la propiedad que habilita un directorio para la Sincronización de Azure AD.  <br/> |
|Dominio actualizado  <br/> |Actualizar dominio  <br/> |Se ha actualizado la configuración de un dominio en su organización de Office 365.  <br/> |
|Dominio comprobado  <br/> |Comprobar dominio  <br/> |Se ha comprobado que su organización es la propietaria de un dominio.  <br/> |
|Se ha comprobado el dominio comprobado por correo electrónico  <br/> |Comprobar el dominio comprobado por correo electrónico  <br/> |Se ha usado la verificación de correo electrónico para comprobar que su organización es la propietaria de un dominio.  <br/> |
||||
   
### <a name="ediscovery-activities"></a>Actividades de eDiscovery
  
La búsqueda de contenido y las actividades relacionadas con eDiscovery que son realizadas en el centro de seguridad y cumplimento o ejecutando los cmdlets correspondientes de PowerShell que están archivados en el registro de auditoría. Esto incluye las siguientes actividades:
  
- Crear y administrar casos de exhibición de documentos electrónicos
    
- Crear, iniciar y editar búsquedas de contenido
    
- Realizar acciones de búsqueda de contenido, como la vista previa, la exportación y la eliminación de resultados de búsqueda
    
- Configurar el filtrado de permisos para la búsqueda de contenido
    
- Administrar el rol de administrador de la exhibición de documentos electrónicos
    
Para obtener una lista y una descripción detallada de las actividades de exhibición de documentos electrónicos que están registradas, vea [Buscar actividades de exhibición de documentos electrónicos en el registro de auditoría de Office 365](search-for-ediscovery-activities-in-the-audit-log.md).
  
> [!NOTE]
> Lleva un máximo de 30 minutos para eventos que resultan de las actividades indicadas en **Actividades de eDiscovery** en la lista desplegable **Actividades** que se muestre en los resultados de búsqueda. Por el contrario, lleva hasta 24 horas para los eventos correspondientes de actividades cmdlet de eDiscovery que aparezcan en los resultados de búsqueda. 
  
### <a name="advanced-ediscovery-activities"></a>Actividades de eDiscovery avanzado

En la siguiente tabla se enumeran las actividades realizadas por los profesionales jurídicos y de IT que realizan tareas en eDiscovery avanzado en Microsoft 365. Para más información, consulte[ información sobre la solución de eDiscovery avanzado en Microsoft 365](compliance20/overview-ediscovery-20.md).

|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
| Agregar datos a otro conjunto de revisión<br/>         | AddWorkingSetQueryToWorkingSet<br/>  |  El usuario ha agregado documentos de un conjunto de revisiones a un conjunto de revisiones diferente.<br/>|
| Datos agregados a otro conjunto de revisión <br/>                | AddQueryToWorkingSet<br/>            |  El usuario agregó los resultados de una búsqueda de contenido asociada con un caso de eDiscovery avanzado a un conjunto de revisiones.<br/>|
| Datos agregados que no son de Office 365 a un conjunto de revisión<br/>  | AddNonOffice365DataToWorkingSet<br/> |  Datos agregados que no son de Office 365 a un conjunto de revisión.<br/>|
| Documentos corregidos agregados para revisar el conjunto<br/> | AddRemediatedData<br/>               |  El usuario carga documentos que tuvieron errores de indexación corregidos para un conjunto de revisiones.<br/>|
| Datos analizados en el conjunto de revisiones <br/>             | RunAlgo<br/>                         |  El usuario ejecuta el análisis en los documentos de un conjunto de revisiones. <br/>|
| Documento anotados en el conjunto de revisiones <br/>        | AnnotateDocument<br/>                |  El usuario anotó un documento en un conjunto de revisiones. La anotación incluye contenido redactado en un documento. <br/>|
| Conjuntos de carga comparados <br/>                      | LoadComparisonJob<br/>               |El usuario comparó dos conjuntos de carga distintos en un conjunto de revisiones. Un conjunto de carga es cuando los datos de una búsqueda de contenido asociados al caso se agregan a un conjunto de revisiones.  <br/>|
| Documentos redactados convertidos en PDF<br/>      | BurnJob<br/>                         |El usuario convirtió todos los documentos redactados en un conjunto de revisión en archivos PDF.<br/>|
| Creado el conjunto de revisiones<br/>                       | CreateWorkingSet<br/>                |El usuario creó un conjunto de revisiones.<br/>|
| Conjunto de búsqueda de revisiones creado<br/>                | CreateWorkingSetSearch<br/>          |El usuario creó una consulta de búsqueda para buscar en los documentos de un conjunto de revisiones. <br/>|
| Etiqueta creada<br/>                              | CreateTag<br/>                       |El usuario creó un grupo de etiquetas en un conjunto de revisiones. Un grupo de etiquetas puede contener una o más etiquetas pequeñas. Las etiquetas se usan para etiquetar documentos en el conjunto de revisiones.<br/>|
| Conjunto de búsqueda de revisiones creado <br/>               | DeleteWorkingSetSearch<br/>          |El usuario eliminó una consulta de búsqueda en un conjunto de revisiones.<br/>|
| Etiquetas eliminadas<br/>                              | DeleteTag<br/>                       |El usuario eliminó un grupo de etiquetas en un conjunto de revisiones.<br/>|
| Documento descargado<br/>                      | DownloadDocument<br/>                |El usuario ha descargado un documento de un conjunto de revisiones.<br/>|
| Etiqueta editada <br/>                              | DownloadDocument<br/>                |El usuario cambió una etiqueta en un conjunto de revisiones.<br/>|
| Documentos exportados desde un conjunto de revisión <br/>      | ExportJob<br/>                       |Documentos de usuario exportados desde un conjunto de revisión.<br/>|
| Configuración de carcaza modificados <br/>                   | UpdateCaseSettings<br/>              | Los usuarios modificaron la configuración de una carcaza. Las opciones de configuración de carcazas incluyen información de casos, permisos de acceso y configuraciones que controlan el comportamiento de búsqueda y análisis.<br/>|
| Conjunto de búsqueda de revisiones modificado<br/>               | UpdateWorkingSetSearch<br/>          |  El usuario editó una consulta de búsqueda en un conjunto de revisiones.<br/>|
| Conjunto de búsqueda de revisiones previstas <br/>             | PreviewWorkingSetSearch<br/>         |  Usuario obtiene una vista previa de los resultados de una consulta de búsqueda en un conjunto de revisiones.<br/>|
| Documentos erróneos corregidos <br/>              | ErrorRemediationJob<br/>             |  El usuario corrige los archivos que contienen errores de escritura.. <br/>|
| Documento etiquetado<br/>                          | TagFiles<br/>                        |  El usuario etiquetó un documento en un conjunto de revisiones.<br/>|
| Resultados etiquetados de una consulta<br/>                | TagJob<br/>                          |  EL usuario etiqueta todos los documentos que coinciden con los criterios de la consulta de búsqueda en un conjunto de revisiones.<br/>|
| Documento anotados en el conjunto de revisiones<br/>            | ViewDocument<br/>                    |  El usuario visualizó un documento en un conjunto de revisiones.<br/>|
|||

### <a name="power-bi-activities"></a>Actividades de Power BI
  
Puede buscar el registro de auditoría actividades en Power BI. Para obtener información sobre las actividades de Power BI, consulte la sección "Actividades auditadas por Power BI"[en el uso de la auditoría en su organización](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi).
  
El registro de auditoría de Power BI no está habilitado de forma predeterminada. Para buscar actividades de Power BI en el registro de auditoría de Office 365, debe habilitar la auditoría en el portal de administración de Power BI. Para obtener instrucciones, consulte la sección "registros de auditoría"[en el portal de administración de Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).
  
### <a name="microsoft-workplace-analytics-activities"></a>Actividades de Microsoft Workplace Analytics

El Workplace Analytics ofrece información sobre cómo los grupos colaboran en la organización de Office 365. En la siguiente tabla se enumeran las actividades realizadas por los usuarios que tengan asignado el rol de administrador o de analista en Workplace Analytics. Los usuarios a los que se les ha asignado el rol de Analista tienen acceso total a todas las características del servicio y usan el producto para realizar el análisis. Los usuarios que tengan asignado el rol de administrador pueden configurar las opciones de privacidad y los valores predeterminados del sistema y podrán preparar, cargar y comprobar datos en la organización en Workplace Analytics Para obtener más información, consulte[Workplace Analytics](https://docs.microsoft.com/es-ES/workplace-analytics/index-orig).

|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Vínculo de acceso de OData  <br/> |AccessedOdataLink <br/> |El analista ha accedido al vínculo OData para una consulta.|
|Consulta cancelada <br/> |CanceledQuery <br/> |El analista canceló una consulta en ejecución.|
|Exclusión de reuniones creada <br/> |MeetingExclusionCreated <br/> |El analista creó una regla de exclusión de la reunión.|
|Resultado eliminado <br/> |DeletedResult <br/> |El analista ha eliminado un resultado de la consulta.|
|Reporte descargado <br/> |DownloadedReport <br/> |El analista ha descargado un archivo de resultado de la consulta.|
|Consulta ejecutada <br/> |ExecutedQuery <br/> |El analista ha ejecutado una consulta.|
|Configuración de acceso a datos actualizada <br/> |UpdatedDataAccessSetting <br/> |Configuración de acceso a datos de administrador actualizada|
|Configuración de privacidad actualizada <br/> |UpdatedPrivacySetting <br/> |Configuración de Privacidad de administrador actualizada; por ejemplo, grupo de tamaño mínimo.|
|Datos de la organización cargados. <br/> |UploadedOrgData <br/> |Archivo de datos de la organización cargado por el administrador.|
|Explorar vista <br/> |ViewedExplore <br/> |El analista visualizó una o más pestañas de la página de exploración.|
||||

### <a name="microsoft-teams-activities"></a>Actividades de Microsoft Teams
  
En la siguiente tabla se enumeran las actividades de usuario y administrador en Microsoft Teams que se archivan en el registro de auditoría de Office 365. Microsoft Teams es un espacio de trabajo centrado en la charla en Office 365. Trae las conversaciones en Teams, las reuniones, los archivos y las notas de un equipo en un solo lugar. Para más información y vínculos con temas de ayuda, consulte:
  
- [Preguntas más frecuentes sobre Microsoft Teams: Ayuda para administradores](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Ayuda de Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Bot agregado al equipo  <br/> |BotAddedToTeam  <br/> |Un usuario agrega un bot a un equipo.  <br/> |
|Canal agregado  <br/> |ChannelAdded  <br/> |Un usuario agrega un canal a un equipo.  <br/> |
|Conector agregado  <br/> |ConnectorAdded  <br/> |Un usuario agrega un conector a un canal.  <br/> |
|Miembros agregados al equipo  <br/> |MemberAdded  <br/> |El propietario de un equipo agrega miembros a un equipo.  <br/> |
|Pestaña agregada  <br/> |TabAdded  <br/> |Un usuario agrega una pestaña a un canal.  <br/> |
|Configuración de canal cambiada  <br/> |ChannelSettingChanged  <br/> | La operación ChannelSettingChanged se registra cuando se realizan las siguientes actividades por un miembro del equipo. Para cada una de estas actividades, se muestra una descripción de la opción de configuración que se modificó (mostrada entre paréntesis a continuación) mostrada en la columna **Elemento**de los resultados de la búsqueda en el registro de auditoría.  <br/> <br/>- Cambiar el nombre de un canal de equipo (**nombre del canal**).  <br/>  <br/>- Cambiar la descripción de un canal de equipo (**descripción del canal**).  <br/> |
|Configuración de organización cambiada  <br/> |TeamsTenantSettingChanged  <br/> | La operación OrganizationSettingChanged se registra cuando un administrador global realiza las siguientes actividades (mediante el Centro de administración de Microsoft 365); Tenga en cuenta que estas actividades afectarán a la configuración de Microsoft Teams de toda la organización. Para obtener más información, consulte [Configuración de administrador de Microsoft Teams](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2).  <br/>  Para cada una de estas actividades, se muestra una descripción de la opción de configuración que se modificó (mostrada entre paréntesis a continuación) mostrada en la columna **Elemento**de los resultados de la búsqueda en el registro de auditoría.  <br/><br/>- Habilita o deshabilita Microsoft Teams para la organización(**Microsoft Teams**).  <br/><br/>- Habilita o deshabilita la interoperabilidad entre Microsoft Teams y Skype Empresarial para la organización (**interoperabilidad de Skype empresarial**).<br/><br/>- Habilitar o deshabilitar la vista de organigrama en los clientes de Microsoft Teams (vista de organigrama). <br/><br/>- Habilitar o deshabilitar la posibilidad que tienen los miembros del equipo para programar reuniones privadas(programación de reuniones privadas). - Habilitar o deshabilitar la posibilidad de que los miembros del equipo programen reuniones de canal(programación de reuniones de canal).   <br/><br/>- Habilitar o deshabilitar las llamadas de vídeo en las reuniones de Teams (vídeo para reuniones de Skype **). <br/><br/> - Habilitar o deshabilitar la pantalla compartida en las reuniones Microsoft Teams para la organización (** uso compartido de pantalla para reuniones de Skype **).  <br/><br/>- Habilitar o deshabilitar la posibilidad de agregar imágenes animadas (denominadas imágenes giphy) a las conversaciones de Teams (imágenes animadas**).   <br/><br/>Cambiar la configuración de la clasificación de contenido de la organización (**clasificación de contenido**). La clasificación de contenido restringe el tipo de imagen animada que se puede mostrar en las conversaciones.  <br/><br/>- Habilitar o deshabilitar la posibilidad de que los miembros del equipo agreguen imágenes personalizables (denominadas memes personalizados) de Internet a las conversaciones de Teams (imágenes personalizables de Internet). <br/><br/>- Habilitar o deshabilitar la posibilidad de que los miembros del equipo agreguen imágenes editables (denominadas adhesivos) a las conversaciones del equipo (** imágenes editables **). <br/><br/>- Habilita o deshabilita la posibilidad de que los miembros del equipo usen robots en chats de Microsoft Teams y canales (robots en toda la organización). <br/><br/>-Habilitar robots específicos para Microsoft Teams. Esto no incluye a T-Bot, que es el robot de ayuda de Microsoft Teams que está disponible cuando se habilitan los robots para la organización (**robots individuales**).  <br/><br/>- Habilitar o deshabilita la posibilidad de que los miembros del equipo agreguen extensiones o pestañas (**extensiones o pestañas**).  <br/><br/>- Habilitar o deshabilitar la instalación de prueba de los robots propiedad Microsoft Teams (**instalación de prueba de robots**).  <br/><br/>- Habilitar o deshabilitar la posibilidad de que los usuarios envíen mensajes de correo electrónico a un canal de Microsoft Teams (**correo electrónico del canal**).  <br/> |
|Rol cambiado de miembros del equipo  <br/> |MemberRoleChanged  <br/> |El propietario del equipo cambia el rol de los miembros del equipo. Los siguientes valores indican el tipo de rol asignado al usuario.  <br/><br/><br/> **1** - Indica el rol del propietario.<br/>**2** - Indica el rol del miembro. <br/>**3**- Indica el rol del invitado. <br/>La propiedad Miembros también incluye el nombre de su organización y la dirección de correo electrónico del miembro.  <br/> |
|Configuración de equipo cambiada  <br/> |TeamSettingChanged  <br/> | La operación TeamSettingChanged se registra cuando se realizan las siguientes actividades por el dueño del equipo. Para cada una de estas actividades, se muestra una descripción de la opción de configuración que se modificó (mostrada entre paréntesis a continuación) mostrada en la columna **Elemento**de los resultados de la búsqueda en el registro de auditoría.  <br/><br/>- Cambiar el tipo de acceso para un equipo. Los equipos se pueden establecer como privados o públicos (**Tipo de acceso de equipo**). Si un equipo es privado (valor predeterminado), los usuarios pueden acceder al equipo solo por invitación. Cuando un equipo es público, puede verlo cualquier persona.  <br/><br/>- Cambia la clasificación de la información de un equipo (**clasificación del equipo**).  <br/>  Por ejemplo, los datos de equipo se pueden clasificar como impacto empresarial alto, impacto empresarial medio o impacto empresarial bajo.<br/><br/>- Cambia el nombre de un equipo (**nombre del equipo**).  <br/><br/>-Cambia la descripción de un equipo (descripción del equipo**). <br/><br/>- Cambios realizados en cualquiera de las opciones de configuración del equipo. El propietario de un equipo puede obtener acceso a estas configuraciones en un cliente de Teams haciendo clic con el botón derecho en el equipo, **Administrar equipo**, y luego haciendo clic en la pestaña **Configuración**. Para estas actividades, se muestra el nombre de la opción de configuración que se modificó en la columna de **Elemento** de los resultados de la búsqueda en el registro de auditoría.  <br/> |
|Equipo creado  <br/> |TeamCreated  <br/> |El usuario crea un equipo.  <br/> |
|Canal eliminado  <br/> |ChannelDeleted  <br/> |Un usuario elimina un canal de un equipo.  <br/> |
|Equipo eliminado  <br/> |TeamDeleted  <br/> |Un propietario de equipo elimina un equipo.  <br/> |
|Bot quitado del equipo  <br/> |BotRemovedFromTeam  <br/> |Un usuario quita un bot de un equipo.  <br/> |
|Conector quitado  <br/> |ConnectorRemoved  <br/> |Un usuario quita un conector de un canal.  <br/> |
|Miembros quitados del equipo  <br/> |MemberRemoved  <br/> |El propietario de un equipo remueve miembros de un equipo.  <br/> |
|Pestaña removida  <br/> |TabRemoved  <br/> |Un usuario quita una pestaña de un canal.  <br/> |
|Conector actualizado  <br/> |ConnectorUpdated  <br/> |Un usuario ha modificado un conector en un canal.  <br/> |
|Pestaña actualizada  <br/> |TabUpdated  <br/> |Un usuario ha modificado una pestaña en un canal.  <br/> |
|Usuario que ha iniciado sesión en Equipos  <br/> |TeamsSessionStarted  <br/> |Un usuario inicia sesión como un cliente de Microsoft Teams.  <br/> |
||||

### <a name="yammer-activities"></a>Actividades de Yammer
  
En la siguiente tabla se enumeran las actividades de usuario y de administrador de Yammer, que se archivan en el registro de auditoría de Office 365. Para devolver las actividades relacionadas con Yammer del registro de auditoría de Office 365, deberá seleccionar **Mostrar resultados para todas las actividades** en la lista de**Actividades**. Use los cuadros de intervalo de fecha y la lista**Usuarios** para restringir los resultados de la búsqueda. 
  
|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Directiva de retención de datos cambiada  <br/> |SoftDeleteSettingsUpdated  <br/> |Un administrador superior actualizó la configuración de la directiva de retención de datos de la red a eliminación permanente o eliminación temporal. Solo los administradores superiores pueden realizar esta operación.  <br/> |
|Configuración de red cambiada  <br/> |NetworkConfigurationUpdated  <br/> |Un administrador superior o de red cambió la configuración de la red de Yammer. Esto incluye establecer el intervalo de exportación de datos y habilitar el chat.  <br/> |
|Configuración del perfil de red cambiada  <br/> |ProcessProfileFields  <br/> |Un administrador superior o de red cambia la información que aparece en los perfiles de usuario para los usuarios de su red.  <br/> |
|Modo de contenido privado cambiado  <br/> |SupervisorAdminToggled  <br/> |Un administrador superior activa o desactiva el *Modo de contenido privado*. Este modo permite a un administrador ver publicaciones de grupos privados y mensajes privados entre los usuarios (o grupos de usuarios). Solo los administradores superiores pueden realizar esta operación.  <br/> |
|Configuración de seguridad cambiada  <br/> |NetworkSecurityConfigurationUpdated  <br/> |Un administrador superior actualizó la configuración de seguridad de la red de Yammer. Esto incluye establecer las directivas de expiración de contraseña y las restricciones de las direcciones IP. Solo los administradores superiores pueden realizar esta operación.  <br/> |
|Archivo creado  <br/> |FileCreated  <br/> |El usuario cargó un archivo.  <br/> |
|Grupo creado  <br/> |GroupCreation  <br/> |El usuario crea un grupo.  <br/> |
|Grupo eliminado  <br/> |GroupDeletion  <br/> |Se eliminó un grupo de Yammer.  <br/> |
|Mensaje eliminado  <br/> |MessageDeleted  <br/> |El usuario eliminó un mensaje.  <br/> |
|Archivo descargado  <br/> |FileDownloaded  <br/> |El usuario descargó un archivo.  <br/> |
|Datos exportados  <br/> |DataExport  <br/> |Un administrador superior exportó datos de la red de Yammer. Solo los administradores superiores pueden realizar esta operación.  <br/> |
|Archivo compartido  <br/> |FileShared  <br/> |Un usuario compartió un archivo con otro usuario.  <br/> |
|Usuario de red suspendido  <br/> |NetworkUserSuspended  <br/> |Un administrador de red o superior suspendió (desactivó) un usuario de Yammer.  <br/> |
|Usuario suspendido  <br/> |UserSuspension  <br/> |Se suspendió una cuenta de usuario (se desactivó).  <br/> |
|Descripción del archivo actualizado  <br/> |FileUpdateDescription  <br/> |Un usuario cambió la descripción de un archivo.  <br/> |
|Nombre de archivo actualizado  <br/> |FileUpdateName  <br/> |Un usuario cambió el nombre de un archivo.  <br/> |
|Archivo visualizado  <br/> |FileVisited  <br/> |Un usuario visualizó un archivo.  <br/> |
||||
   
### <a name="microsoft-flow-activities"></a>Actividades de Microsoft Flow

Puede buscar el registro de auditoría actividades en Microsoft Flow. Entre estas actividades se incluyen la creación, edición y eliminación de flujos y cambios en los permisos de flujo. Para obtener información acerca de auditar las actividades de flujo, [Microsoft Flow Audit ahora disponibles en el centro de cumplimiento y seguridad ](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-powerapps"></a>Microsoft PowerApps

Puede buscar el registro de auditoría actividades relacionadas en PowerApps. Entre estas actividades se incluyen la creación, el lanzamiento y la publicación de una aplicación. La asignación de permisos a las aplicaciones también se audita. Para obtener una descripción de todas las actividades de PowerApps, consulte [ Registro de actividades para PowerApps](https://docs.microsoft.com/es-ES/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Actividades de Microsoft Stream
  
Puede buscar el registro de auditoría para actividades en Microsoft Stream. Entre estas actividades se incluyen las actividades de vídeo efectuadas por los usuarios, las actividades de canal de grupo y las actividades de administración, como la administración de usuarios, administración de la configuración de la organización y exportación de informes. Para obtener una descripción de estas actividades, consulte la sección "actividades iniciadas en Microsoft Stream " en[ registros de auditoría de Microsoft Stream](https://docs.microsoft.com/stream/audit-logs).

### <a name="exchange-admin-audit-log"></a>Registro de auditoría de administración de Exchange
  
El registro de auditoría de administrador de Exchange (que está habilitado de manera predeterminada en Office 365) registra un evento en el registro de auditoría de Office 365 cuando un administrador (o un usuario al que se le han asignado permisos administrativos) realiza un cambio en su organización de Exchange en línea. Los cambios que se han realizado mediante el Centro de administración de Exchange o mediante la ejecución de un cmdlet en PowerShell en Exchange en línea se registran en el registro de auditoría del administrador de Exchange. Los cmdlets que comienzan con el verbo **conseguir**, ** buscar**o **probar**, no se registran en el registro de auditoría de Office 365. Para obtener más información detallada sobre el registro de auditoría del administrador en Exchange, consulte [Registro de auditoría de administrador](https://go.microsoft.com/fwlink/p/?LinkID=619225).

> [!IMPORTANT]
> Algunos cmdlets de Exchange en línea que no se archivan en el registro de auditoría de administración de Exchange (o en el registro de auditoría de Office 365). Muchos de estos cmdlets se relacionan con el mantenimiento del servicio de Exchange en línea y los ejecuta el personal del centro de datos de Microsoft o las cuentas de servicio. Estos cmdlets no se registran porque darían un gran número de eventos de auditoría "ruidosos". Si hay un cmdlet de Exchange en línea que no se está auditando, envíe una sugerencia al foro de[ Office 365 Security & Compliance User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance)y solicite que está habilitado para la auditoría. También puede enviar una solicitud de cambio de diseño (DCR) al Soporte técnico de Microsoft.
  
Aquí se muestran algunas sugerencias para buscar actividades de administrador de Exchange al buscar en el registro de auditoría de Office 365:
  
- Para devolver las entradas del registro de auditoría de administrador Exchange, tiene que seleccionar **Mostrar resultados para todas las actividades**en la lista**Actividades**. Use los cuadros de intervalo de fecha y la lista de**Usuarios** para restringir los resultados de búsqueda para los cmdlets que se ejecutan mediante un administrador de Exchange específico dentro de un rango de fecha específico. 
    
- Para mostrar los eventos del registro de auditoría de administración de Exchange, filtre los resultados de búsqueda y escriba un**-** (guion) en el cuadro de filtro **Actividad**. Esto mostrará los nombres de los cmdlet, que se muestran en la columna**Actividad**de los eventos de administración de Exchange. Luego usted puede ordenar los nombres de cmdlet en orden alfabético. 
    
    ![Escriba un guión en el cuadro de actividades para filtrar los eventos de administración de Exchange](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- Para obtener información sobre qué cmdlet se ha ejecutado, qué parámetros y valores de parámetro se han usado y qué objetos se han visto afectados, tendrá que exportar los resultados de búsqueda y seleccionar la opción **Descargar todos los resultados**. Para más información, consulte[Exportar, configurar y ver registros de registro de auditoría](export-view-audit-log-records.md) 

- También puede usar el `Search-UnifiedAuditLog -RecordType ExchangeAdmin` comando de PowerShell Exchange en línea para devolver solo los registros de auditoría del registro de auditoría de administración de Exchange. Se pueden tardar hasta 30 minutos después de ejecutar el cmdlet de Exchange para que se devuelva la entrada del registro de auditoría correspondiente en los resultados de la búsqueda. Para obtener más información, consulte [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog). Para obtener información sobre cómo exportar los resultados de búsqueda devueltos por el cmdlet **Search-UnifiedAuditLoga un archivo CSV, consulte la sección "sugerencias para exportar y ver el registro de auditoría" exportar, configurar y ver el registro de auditoría registros.

- También puede ver los cambios que se han realizado mediante el Centro de administración de Exchange o mediante la ejecución de un **Search-AdminAuditLog** en PowerShell en Exchange en línea. Esta es una buena forma de buscar específicamente la actividad que realizan los administradores de Exchange Online. Para obtener instrucciones, consulte:
   
   - [Ver el registro de auditoría del administrador](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx) 
   
   -  [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)
   
   Tenga en cuenta que las mismas actividades de administración de Exchange se registran en el registro de auditoría de administración de Exchange y en el registro de auditoría de Office 365.
  
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Dónde puedo encontrar información acerca de las características que ofrece el servicio de auditoría en Office 365?**

Para obtener más información sobre las características de auditoría e informes disponibles en Office 365, consulte[auditoría e informes en Office 365](office-365-auditing-and-reporting-overview.md). 

**¿Cuáles son los distintos servicios de Office 365 que están actualmente auditados?**

Los servicios de Office 365 más usados como Exchange Online, SharePoint Online, OneDrive para la empresa, Azure Active Directory, Microsoft Teams, Dynamics 365, la protección contra amenazas avanzada y Power BI son auditados. Consulte el [principio de este artículo](search-the-audit-log-in-security-and-compliance.md) para obtener una lista de los servicios que se van a auditar.

**¿Qué actividades audita el servicio de auditoría en Office 365?**

Vea la sección[actividades auditadas](#audited-activities)de este artículo para obtener una lista y una descripción de las actividades que se auditan en Office 365.

**¿Cuánto tiempo tarda un registro de auditoría en disponible después de que se produzca un evento?**

Los datos más auditados están disponibles un máximo de 30 minutos pero puede tomar 24 horas después de que se produzca el evento para el registro de auditoría correspondiente para ser mostrado los resultados de búsqueda. Vea la tabla de la sección [antes de empezar](#before-you-begin)en este artículo, donde se muestra el tiempo que tarda para los eventos de los diferentes servicios de Office 365 para estar disponibles.

**¿Durante cuánto tiempo se conservan los registros de auditoría?**

Como se ha explicado anteriormente, el período de retención de los registros de auditoría depende de la suscripción a Office 365 de la organización.  

- **Office 365 E3:** Los registros de auditoría se conservan durante 90 días.

- **Office 365 E5:** Los registros de auditoría también se conservan durante 90 días. La retención mantenimiento de registros de auditoría para un año puede estar disponible en ocasiones para usuarios de E5 y usuarios con una licencia de E3 y una licencia de complemento a Cumplimiento avanzado de Office 365.

     > [!NOTE]
     > Como se explicó anteriormente, el programa de la versión preliminar privada para el período de retención de un año para los registros de auditoría de las organizaciones E5 (o para las organizaciones E3 que tienen licencias de complemento a Cumplimiento avanzado) está cerrado a la nueva inscripción. Este artículo se actualizará cuando el período de retención de un año se encuentre disponible en vista previa pública o se publique para la disponibilidad general.

Asimismo, tenga en cuenta que la duración del período de retención de los registros de auditoría se basa en las licencias por usuario. Por ejemplo, si a un usuario de su organización se le asigna una licencia de Office 365 E3 o E5, los registros de auditoría de las actividades que realiza el usuario se conservan durante 90 días.

**¿Puedo tener acceso a los datos de auditoría mediante programación?**

Sí. La API de Actividad de administración de Office 365 se usa para capturar los registros de auditoría mediante programación.  Para empezar, consulte [Empezar con el APÏ de Office 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**¿Hay otras formas de obtener registros de auditoría que no sean en el centro de seguridad y cumplimiento o con la API de Actividad de administración de Office 365?**

No. Éstas son las dos formas de obtener datos del servicio de auditoria de Office 365. 

**¿Necesito habilitar individualmente la auditoría en cada servicio en el que deseo capturar registros de auditoría?**

En la mayoría de los servicios 365 de Office, la auditoría está habilitada de forma predeterminada después de activar la auditoría de su organización de Office 365 (como se describe en la [sección antes de empezar ](#before-you-begin)en este artículo).

**¿El servicio de auditoría de Office 365 es compatible con la des duplicación de registros?**

No. La canalización del servicio de auditoría está casi en tiempo real, y por lo tanto no es compatible con la des duplicación.
 
**¿Office 365 audita el flujo de datos en todo el mundo?**

No. Actualmente, tenemos implementaciones de canaletas de auditoria en las regiones NA (Norteamérica), EMEA (Europa, Oriente Medio y África) y APAC (Asia del pacífico). Sin embargo, es posible que flujos los datos en estas zonas para equilibrar la carga y solo durante las cuestiones de sitio en directo. Cuando realizamos estas actividades, los datos en tránsito se encriptan.   
 
**¿Está la auditoría de datos encriptada?**

Los datos de auditoría se almacenan en buzones de Exchange (datos en reposo) en la misma región donde se implementa la canalización de auditoría. Estos datos no estan encriptados. Sin embargo, los datos en tránsito siempre están encriptados. 

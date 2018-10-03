---
title: Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365AC_AlternativeEmailAddress
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 'Usar la seguridad de Office 365 &amp; centro de cumplimiento para buscar el registro de auditoría unificado para ver la actividad de usuario y Administrador de la organización de Office 365. '
ms.openlocfilehash: 79aa544d7243a4f3a81aebea3ffce92e2ad057f8
ms.sourcegitcommit: 09d34bf058c0afce2c3800f207d64020ca984d57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "25363153"
---
# <a name="search-the-audit-log-in-the-office-365-security-amp-compliance-center"></a>Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365

¿Necesita encontrar si un usuario ve un documento específico o purga un elemento desde su buzón? Si, por lo tanto, puede usar la seguridad de Office 365 &amp; centro de cumplimiento para buscar el registro de auditoría unificado para ver la actividad de usuario y Administrador de la organización de Office 365. ¿Por qué se registra una auditoría unificada? Debido a que puede buscar los siguientes tipos de actividad de usuario y administración de Office 365:
  
- Actividad del usuario en SharePoint Online y OneDrive para la empresa
    
- Actividad del usuario en Exchange Online (registro de auditoría de buzón de Exchange)
    
    > [!IMPORTANT]
    > Auditoría de buzón de correo registro debe activarlo para cada buzón de usuario antes de que se registrarán la actividad del usuario en Exchange Online. Para obtener más información, vea [Habilitar la auditoría en Office 365 de buzón de correo](enable-mailbox-auditing.md).
  
- Actividad de administración en SharePoint Online
    
- Actividad de administración de Azure Active Directory (el servicio de directorio para Office 365)
    
- Actividad de administración de Exchange Online (registro de auditoría de administración de Exchange)
    
- Actividad de usuario y administración de balanceo
    
- actividades de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento
    
- Actividad de usuario y la administración en Power BI para Office 365
    
- Actividad de usuario y la administración en Microsoft Teams

- Actividad de usuario y administración de Dynamics 365
    
- Actividad de usuario y administración de Yammer
 
- Actividad de usuario y la administración in Microsoft Flow
    
- Actividad de usuario y la administración en Microsoft Stream
    
   
## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de leer el registro de auditoría de los siguientes elementos antes de iniciar la búsqueda de Office 365.
  
- Usted (u otro administrador) en primer lugar debe activar el registro de auditoría antes de empezar, puede buscar en el registro de auditoría de Office 365. Para activarla, haga clic en **iniciar la grabación de usuario y la actividad de administración** en la página de **búsqueda de registro de auditoría** en la seguridad &amp; centro de cumplimiento. (Si no ve este vínculo, auditoría ha ya se ha activado para la organización.) Después de activar, se muestra un mensaje que indica que se está preparando el registro de auditoría y que se puede ejecutar una búsqueda en un par de horas una vez finalizada la preparación. Solo tiene que hacer esto una vez. 
    
    > [!NOTE]
    > Estamos en el proceso de activación de la auditoría de forma predeterminada. Hasta entonces, puede desactivarla como se describió anteriormente. 
  
- Se debe asignar el rol registros de auditoría con permiso de vista o los registros de auditoría en Exchange Online para buscar el registro de auditoría de Office 365. De forma predeterminada, estas funciones se asignan a los grupos de funciones de administración de cumplimiento y administración de la organización en la página de **permisos** en el centro de administración de Exchange. Para conceder a un usuario la capacidad de buscar en el registro de auditoría de Office 365 con el nivel mínimo de privilegios, puede crear un grupo de roles personalizados en Exchange Online, agregar el rol registros de auditoría con permiso de vista o los registros de auditoría y, a continuación, agregar el usuario como un miembro del grupo de roles nueva. Para obtener más información, vea la [función de administrar grupos en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).
    
    > [!IMPORTANT]
    > Si se asigna a un usuario el rol registros de auditoría con permiso de vista o los registros de auditoría en la página de **permisos** en la seguridad &amp; centro de cumplimiento, no podrán buscar el registro de auditoría de Office 365. Se debe asignar los permisos en Exchange Online. Esto es debido a que el cmdlet subyacente que sirven para buscar el registro de auditoría es un cmdlet de Exchange Online. 
  
- Cuando se realiza una actividad auditada por un usuario o un administrador, un registro de auditoría se generado y se almacena en el registro de auditoría de Office 365 para su organización. El período de tiempo que un registro de auditoría se retenidas (y se pueden buscar en el registro de auditoría) depende de su suscripción de Office 365.

     - **Office 365 E3** - auditoría registros se conservan durante 90 días. Esto significa que puede buscar el registro de auditoría de las actividades que se realizaron en los últimos 90 días.

     - **Office 365 E5** - auditoría se retienen los registros de 365 días (un año). Esto significa que puede buscar el registro de auditoría de las actividades que se realizaron dentro del último año. Conservar registros de auditoría para un año también está disponible para las organizaciones que tienen una suscripción E3 y una suscripción de complemento de Office 365 avanzada cumplimiento.

        > [!NOTE]
        > El período de retención de un año para los registros de auditoría está actualmente disponible como parte de Office 365 Preview de programa y sólo está disponible para las organizaciones con una suscripción E5 que están inscritos en el programa de vista previa. Además, de auditoría de registros de las actividades que se realizaron antes de octubre de 2018 aún se conservan durante 90 días sólo. A partir de octubre de 2018, nuevos registros de auditoría se conservan durante un año para las organizaciones con una suscripción E5 o que tiene una suscripción E3 y una suscripción de complemento de cumplimiento avanzadas.

- Si desea desactivar la búsqueda de registro de auditoría en Office 365 para su organización, puede ejecutar el siguiente comando en PowerShell remoto conectado a la organización de Exchange Online:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Para activar búsqueda de auditoría, puede ejecutar el siguiente comando en Exchange Online PowerShell:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    Para obtener más información, vea [desactivar la búsqueda de registro de auditoría en Office 365](turn-audit-log-search-on-or-off.md).
    
- Como se ha indicado anteriormente, el cmdlet subyacente que sirven para buscar el registro de auditoría es un cmdlet de Exchange Online, que es **UnifiedAuditLog de búsqueda**. Esto significa que puede usar este cmdlet para buscar el registro de auditoría de Office 365 en lugar de desde la página de **búsqueda de registro de auditoría** de la seguridad &amp; centro de cumplimiento. Se debe ejecutar este cmdlet en PowerShell remoto conectado a la organización de Exchange Online. Para obtener más información, vea [UnifiedAuditLog de búsqueda](https://go.microsoft.com/fwlink/p/?linkid=834776).
    
- Si desea descargar mediante programación los datos desde el registro de auditoría de Office 365, se recomienda que utilice la API de actividad de administración de Office 365 en lugar de usar un script de PowerShell. La API de actividad de administración de Office 365 es un servicio web REST que puede usar para desarrollar soluciones de supervisión de cumplimiento para su organización, seguridad y operaciones. Para obtener más información, vea la [referencia de la API de actividad de administración de Office 365](https://go.microsoft.com/fwlink/?linkid=852309).
    
- Puede tardar hasta 30 minutos o copia de seguridad a 24 horas después de un evento se produce para que la entrada de registro de auditoría correspondientes que se mostrará en los resultados de búsqueda. En la siguiente tabla se muestra el tiempo necesario para los distintos servicios de Office 365.
    
|**Servicio de Office 365**|**30 minutos**|**24 horas**|
|:-----|:-----|:-----|
|Protección contra amenazas avanzadas y la información sobre amenazas  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
|Azure Active Directory (eventos de inicio de sesión de usuario)  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Azure Active Directory (administración eventos)  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
|Azure Active Directory (eventos de inicio de sesión de usuario)  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Prevención de pérdida de datos  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Dynamics 365 CRM <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|eDiscovery  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Exchange Online  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Microsoft Flow  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Forms  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Project  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Stream  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Microsoft Teams  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Power BI  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
|Seguridad &amp; centro de cumplimiento  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|SharePoint Online y OneDrive para la Empresa  <br/> |![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
|Sway  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|Yammer  <br/> ||![Marca de verificación](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (AD Azure) es el servicio de directorio para Office 365. El registro de auditoría unificadas contiene el usuario, grupo, aplicación, dominio y actividades de Active directory realizadas en el centro de administración de Office 365 o en el Azure en el portal de administración. Para obtener una lista completa de los eventos de Azure AD, vea [Eventos de informe de auditoría de Active Directory de Azure](https://go.microsoft.com/fwlink/p/?LinkID=616549).
    
- Registros de auditoría de Exchange Online constan de dos tipos de eventos: eventos de administración (acciones realizadas por los administradores) y eventos (acciones realizadas por los usuarios en los buzones de correo) de buzón de correo de Exchange. Tenga en cuenta que no está habilitada la auditoría de buzón de correo de forma predeterminada. Se debe habilitar para cada buzón de usuario antes de eventos de buzón de correo se pueden buscar en el registro de auditoría de Office 365. Para obtener más información acerca de la auditoría de buzón de correo y el buzón de auditoría de las acciones que se registran, vea [Habilitar la auditoría en Office 365 de buzón de correo](enable-mailbox-auditing.md).
    
- Registro de auditoría de Power BI no está habilitado de forma predeterminada. Para buscar actividades de Power BI en el registro de auditoría de Office 365, se debe habilitar la auditoría en el portal de administración de Power BI. Para obtener instrucciones, vea [Auditoría Power BI](https://docs.microsoft.com/power-bi/service-admin-auditing#enabling-auditing-functionality-in-the-power-bi-admin-portal).
    
    
## <a name="search-the-audit-log"></a>Buscar en el registro de auditoría

Aquí es el proceso para buscar en el registro de auditoría en Office 365.
  
[Paso 1: Ejecutar una búsqueda de registro de auditoría](#step-1-run-an-audit-log-search)
  
[Paso 2: Ver los resultados de búsqueda](#step-2-view-the-search-results)

[Paso 3: Filtrar los resultados de búsqueda](#step-3-filter-the-search-results)

[Paso 4: Exportar los resultados de búsqueda a un archivo](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>Paso 1: Ejecutar una búsqueda de registro de auditoría

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
    > [!TIP]
    > Usar una sesión de exploración privada (no una sesión normal) para tener acceso a la seguridad de Office 365 &amp; del centro de cumplimiento debido a que esto evitará que las credenciales que se encuentra actualmente con se usen. Para abrir una sesión de exploración de InPrivate en Internet Explorer o Microsoft Edge, presione CTRL + MAYÚS + P. Para abrir una sesión de exploración privada en Google Chrome (denominado una ventana incognito), presione CTRL + MAYÚS + N. 
  
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En el panel izquierdo de la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación**y, a continuación, haga clic en **búsqueda de registro de auditoría**.
    
    Se muestra la página de **búsqueda de registro de auditoría** . 
    
    ![Configurar los criterios y, a continuación, haga clic en Buscar para ejecutar informe](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > Se debe activar primero en el registro de auditoría antes de poder ejecutar una búsqueda de registro de auditoría. Si se muestra el vínculo **iniciar la grabación de usuario y la actividad de administración** , haga clic para activar la auditoría. Si no ve este vínculo, auditoría ya se ha activado para la organización. 
  
4. Configurar los criterios de búsqueda siguientes:
    
1. **Actividades** Haga clic en la lista desplegable para mostrar las actividades que puede buscar. Actividades de administrador y usuario están organizadas en grupos de actividades relacionadas. Puede seleccionar actividades específicas o puede hacer clic en el nombre del grupo de actividad para seleccionar todas las actividades en el grupo. También puede hacer clic en una actividad seleccionada para borrar la selección. Después de ejecutar la búsqueda, se muestran sólo las entradas de registro de auditoría de las actividades seleccionadas. Selección de **Mostrar los resultados de todas las actividades** mostrará los resultados para todas las actividades realizadas por el usuario seleccionado o el grupo de usuarios. 
    
    Más de 100 actividades de administrador y usuario se registran en el registro de auditoría de Office 365. Haga clic en la ficha **actividades auditada** en el tema de este artículo para ver las descripciones de cada actividad en cada uno de los distintos servicios de Office 365. 
    
2. **Fecha de inicio** y **fecha de finalización** de los últimos siete días están activadas de forma predeterminada. Seleccione un intervalo de fecha y hora para mostrar los eventos que se produjeron dentro de ese período. La fecha y hora se presentan en formato de hora Universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es de 90 días. Si el intervalo de fechas seleccionado es mayor que 90 días, se muestra un error. 
    
    > [!TIP]
    > Si se usa el intervalo de fechas máximo de 90 días, seleccione la hora actual de la **fecha de inicio**. De lo contrario, recibirá un error que indica que la fecha de inicio es anterior a la fecha de finalización. Si ha activado la auditoría en los últimos 90 días, no se puede iniciar el intervalo de fechas máximo antes de la fecha que se ha activado la auditoría. 
  
3. **Usuarios** Haga clic en este cuadro y, a continuación, seleccione uno o varios usuarios para mostrar los resultados de búsqueda para. Las entradas de registro de auditoría para la actividad seleccionada realizado por los usuarios que seleccione en este cuadro se muestran en la lista de resultados. Deje este cuadro en blanco para devolver las entradas para todos los usuarios (y las cuentas de servicio) en la organización. 
    
4. **Archivo o carpeta** Escriba algunos o todos los de un nombre de archivo o carpeta para buscar la actividad relacionada con el archivo de la carpeta que contiene la palabra clave especificada. También puede especificar una dirección URL de un archivo o carpeta. Si utiliza una dirección URL, asegúrese de que el tipo de la ruta de acceso de dirección URL completa o si sólo tiene que escribir una parte de la dirección URL, no incluya espacios ni caracteres especiales. 
    
    Deje este cuadro en blanco para devolver las entradas de todos los archivos y carpetas en la organización.
    
5. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
    Se cargan los resultados de búsqueda y, después de unos momentos se muestran en **los resultados**. Cuando finalice la búsqueda, se muestra el número de resultados que se encuentra. Tenga en cuenta que se mostrará un máximo de 5.000 eventos en el panel de **resultados** en incrementos de 150 eventos; Si más de 5.000 eventos cumplen los criterios de búsqueda, se muestran los eventos de 5.000 más recientes. 
    
    ![Se muestra el número de resultados una vez finalizada la búsqueda](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>Sugerencias para buscar el registro de auditoría

- Puede seleccionar actividades específicas para buscar haciendo clic en el nombre de la actividad. O bien, puede buscar todas las actividades de un grupo (por ejemplo, **las actividades de archivo y carpeta**) haciendo clic en el nombre del grupo. Si se selecciona una actividad, puede hacer clic en él para cancelar la selección. También puede usar el cuadro de búsqueda para mostrar las actividades que contienen la palabra clave que se escribe.
    
    ![Haga clic en el nombre del grupo de actividad para seleccionar todas las actividades](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- Se debe seleccionar **Mostrar los resultados de todas las actividades** en la lista de **actividades** para mostrar eventos desde el registro de auditoría de administración de Exchange. Eventos de este registro de auditoría de mostrar un nombre de cmdlet (por ejemplo, **Set-Mailbox** ) en la columna de la **actividad** en los resultados. Para obtener más información, haga clic en la ficha **actividades auditada** en este tema y, a continuación, haga clic en **las actividades de administración de Exchange**.
    
    De forma similar, hay algunas actividades de auditoría que no tengan un elemento correspondiente en la lista de **actividades** . Si conoce el nombre de la operación para estas actividades, puede buscar todas las actividades, a continuación, filtrar los resultados, escriba el nombre de la operación en el cuadro de la columna de **actividad** . Vea [paso 3: filtrar los resultados de búsqueda](#step-3-filter-the-search-results) para obtener más información acerca del filtrado de los resultados. 
    
- Haga clic en **Borrar** para borrar los criterios de búsqueda actual. Devuelve el intervalo de fechas en el valor predeterminado de los últimos siete días. También puede hacer clic en **Borrar todo para mostrar los resultados de todas las actividades** para cancelar todas las actividades seleccionadas. 
    
- Si se encuentran 5.000 resultados, puede suponer probablemente hay más de 5.000 eventos que cumplen los criterios de búsqueda. Puede refinar los criterios de búsqueda y vuelva a ejecutar la búsqueda para devolver resultados menos, o puede exportar todos los resultados de búsqueda mediante la selección de **exportar los resultados de** \> **Descargar todos los resultados**.

  
### <a name="step-2-view-the-search-results"></a>Paso 2: Ver los resultados de búsqueda

Los resultados de una búsqueda de registro de auditoría se muestran en **los resultados** en la página de **búsqueda de registro de auditoría** . Como se mencionó anteriormente un máximo de 5.000 eventos (más recientes) se muestran en incrementos de 150 eventos. Para mostrar más eventos puede utilizar la barra de desplazamiento en el panel de **resultados** o puede presionar **MAYÚS + fin** para mostrar los eventos de 150 a continuación. 
  
Los resultados contienen la siguiente información sobre cada evento devuelto por la búsqueda.
  
- **Fecha:** La fecha y la hora (en formato UTC) cuando se produjo el evento. 
    
- **Dirección IP:** La dirección IP del dispositivo que se usó cuando se registró la actividad. La dirección IP se muestra en formato de dirección de un IPv4 o IPv6. 
    
- **Usuario:** La cuenta de usuario (o servicio) que realizó la acción que desencadenó el evento. 
    
- **Actividad:** La actividad realizada por el usuario. Este valor corresponde a las actividades que ha seleccionado en la lista desplegable de **actividades** . Para un evento desde el registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange. 
    
- **Elemento:** El objeto que se creó o modificó como resultado de la actividad correspondiente. Por ejemplo, el archivo que se pueden ver ni modificar o la cuenta de usuario que se ha actualizado. No todas las actividades tienen un valor en esta columna. 
    
- **Detalle:** Detalles adicionales acerca de una actividad. Una vez más, no todas las actividades tendrá un valor. 
    
> [!TIP]
> Haga clic en un encabezado de columna en **los resultados** para ordenar los resultados. Puede ordenar los resultados de la A Z o Z a r. Haga clic en el encabezado de **fecha** para ordenar los resultados de la más antigua a más reciente a más antigua o más reciente. 
  
#### <a name="view-the-details-for-a-specific-event"></a>Ver los detalles de un evento específico

Puede ver más detalles acerca de un evento al hacer clic en el registro de eventos en la lista de resultados de búsqueda. Se muestra una página de **Detalles** que contiene las propiedades detalladas del registro de eventos. Las propiedades que se muestran dependen del servicio Office 365 en el que se produce el evento. Para mostrar estos detalles, haga clic en **obtener más información**. Para obtener descripciones, consulte el [registro de auditoría de propiedades detalladas en Office 365](detailed-properties-in-the-office-365-audit-log.md).
  
![Haga clic en obtener más información para ver las propiedades detalladas del registro de evento de registro de auditoría](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>Paso 3: Filtrar los resultados de búsqueda

Además de ordenación, también puede filtrar los resultados de una búsqueda de registro de auditoría. Esta es una característica excelente que puede ayudar a filtrar rápidamente los resultados para un usuario específico o una actividad. Puede crear inicialmente una búsqueda amplia y, a continuación, filtrar rápidamente los resultados para ver eventos específicos. A continuación, puede restringir los criterios de búsqueda y vuelva a ejecutar la búsqueda para devolver un conjunto más pequeño, más conciso de los resultados.
  
Para filtrar los resultados:
  
1. Ejecutar una búsqueda de registro de auditoría.
    
2. Cuando se muestran los resultados, haga clic en **filtrar los resultados**.
    
    Se muestran los cuadros de palabra clave en cada encabezado de columna.
    
3. Haga clic en uno de los cuadros en un encabezado de columna y escriba una palabra o frase, dependiendo de la columna que se va a filtrar. Los resultados se reajustar dinámicamente para mostrar los eventos que coinciden con el filtro.
    
    ![Escriba una palabra en filtro para mostrar los eventos que coinciden con el filtro](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. Para borrar un filtro, haga clic en la **X** en el cuadro filtro o simplemente haga clic en **Ocultar filtrado**.
    
> [!TIP]
> Para mostrar eventos desde el registro de auditoría de administración de Exchange, escriba un **-** (guión) en el cuadro de filtro de **actividad** . Esto mostrará los nombres de cmdlet, que se muestran en la columna de la **actividad** de eventos de administración de Exchange. A continuación, puede ordenar los nombres de cmdlet en orden alfabético. 

### <a name="step-4-export-the-search-results-to-a-file"></a>Paso 4: Exportar los resultados de búsqueda a un archivo

Puede exportar los resultados de una búsqueda de registro de auditoría a un archivo de (CSV) de valores separados por comas en el equipo local. Puede abrir este archivo en Microsoft Excel y usar características como la búsqueda, la ordenación, el filtrado y la división de una sola columna (que contiene las celdas de valor múltiple) en varias columnas.
  
1. Ejecutar una búsqueda de registro de auditoría y, a continuación, revise los criterios de búsqueda hasta que tenga los resultados deseados.
    
2. Haga clic en **exportar los resultados** y seleccione una de las siguientes opciones: 
    
  - **Guardar los resultados de la cargados** Elija esta opción para exportar sólo las entradas que se muestran en **los resultados** en la ** búsqueda de registro de auditoría ** página. El archivo CSV que se descarga contiene las mismas columnas (y datos) que se muestra en la página (fecha, usuario, actividad, elemento y obtener información detallada). Se incluye una columna adicional (denominada **más**) en el archivo CSV que contiene más información de la entrada de registro de auditoría. Debido a que se va a exportar los mismos resultados que se cargan (y visibles) en la página de **búsqueda de registro de auditoría** , se exportan un máximo de 5000 entradas. 
    
  - **Descargue todos los resultados** Elija esta opción para exportar todas las entradas del registro de auditoría de Office 365 que cumplen los criterios de búsqueda de. Para un amplio conjunto de resultados de la búsqueda, elija esta opción para descargar todas las entradas del registro de auditoría además de los resultados de 5.000 que se pueden mostrar en la página de **búsqueda de registro de auditoría** de. Esta opción descargará los datos sin procesar desde el registro de auditoría a un archivo CSV y contiene información adicional de la entrada de registro de auditoría en una columna denominada **AuditData**. Puede tardar más tiempo en descargar el archivo si elige esta opción de exportación debido a que el archivo puede ser mucho mayor que el que se descarga si elige la opción otra.
    
    > [!IMPORTANT]
    > Puede descargar un máximo de 50.000 entradas a un archivo CSV de una búsqueda de registro de auditoría único. Si se descargan 50.000 entradas en el archivo CSV, probablemente se puede suponer que hay más de 50.000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, intente usar un intervalo de fechas para reducir el número de entradas de registro de auditoría. Debe ejecutar varias búsquedas con más pequeños intervalos de fechas para exportar las entradas de más de 50.000. 
  
3. Después de seleccionar una opción de exportación, se muestra un mensaje en la parte inferior de la ventana que le pregunta si desea abrir el archivo CSV, guárdelo en la carpeta de descargas o guárdelo en una carpeta específica.

  
#### <a name="more-information-about-exporting-audit-log-search-results"></a>Para obtener más información acerca de cómo exportar los resultados de búsqueda de registro de auditoría

- La opción de **descargar los resultados de todas las** descargas de los datos sin procesar desde el registro de auditoría de Office 365 a un archivo CSV. Este archivo contiene los nombres de columna diferente (CreationDate, identificadores de usuario, operación, AuditData) que el archivo que se descarga si selecciona la opción de **Guardar los resultados de la cargados** . Los valores de los dos archivos CSV diferentes para la misma actividad también pueden ser diferentes. Por ejemplo, la actividad en la columna **acción** en el CSV de archivos y puede tener un valor diferente a la versión "fáciles de usar" que se muestra en la columna de la **actividad** en la página de **búsqueda de registro de auditoría** ; Por ejemplo, MailboxLogin frente a un usuario inició sesión en buzones de correo.
    
- Si descarga todos los resultados, el archivo CSV contiene una columna denominada **AuditData**, que contiene información adicional sobre cada evento. Como se señaló anteriormente, esta columna contiene una propiedad de varios valor para varias propiedades de la entrada del registro de auditoría. Cada uno de los pares de **valor de la propiedad:** en esta propiedad de varios valor están separados por una coma. Puede usar la consulta de alimentación en Excel para dividir esta columna en varias columnas para que cada propiedad tendrá su propia columna. Esto le permitirá ordenar y filtrar en una o varias de estas propiedades. Para obtener información sobre cómo hacerlo, vea la sección "Dividir una columna por delimitador" en [dividir una columna de texto (Power consulta)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662).
    
    Después de dividir la columna **AuditData** , puede filtrar en la columna de **operaciones** para mostrar las propiedades detalladas para un tipo específico de la actividad. 
    
- Hay un límite de caracteres 3,060 para los datos que se muestran en el campo **AuditData** para un registro de auditoría. Si se supera el límite de caracteres de 3,060, los datos en este campo se truncan. 
    
- Cuando se descarga todos los resultados de una consulta de búsqueda que contiene eventos desde distintos servicios de Office 365, la columna **AuditData** en el archivo CSV contiene distintas propiedades según el servicio de la acción se llevó a cabo en. Por ejemplo, las entradas de los registros de auditoría de Exchange y Azure AD incluyen una propiedad denominada **ResultStatus** que indica si la acción se realizó correctamente o no. Esta propiedad no se incluye para los eventos de SharePoint. De forma similar, eventos de SharePoint tienen una propiedad que identifica el sitio de actividades relacionadas con la dirección URL de archivo y carpeta. Para mitigar este comportamiento, considere el uso de búsquedas diferentes para exportar los resultados de las actividades de un solo servicio. 
    
    Para obtener una descripción de las propiedades que se enumeran en la columna **AuditData** en el archivo CSV cuando se descargan todos los resultados y el servicio de cada uno se aplica a, consulte el [registro de auditoría de propiedades detalladas en Office 365](detailed-properties-in-the-office-365-audit-log.md).

  
## <a name="audited-activities"></a>Actividades auditadas

Las tablas de esta sección describen las actividades que se auditan en Office 365. Puede buscar estos eventos buscando la auditoría de registro en la seguridad &amp; centro de cumplimiento. Haga clic en la ficha de **búsqueda del registro de auditoría** para obtener instrucciones paso a paso. 
  
Estas tablas agrupar actividades relacionadas o las actividades de un servicio específico de Office 365. Las tablas incluyen el nombre descriptivo que se muestra en la lista desplegable de **las actividades** y el nombre de la operación correspondiente que aparece en la información detallada de un registro de auditoría y en el archivo CSV al exportar los resultados de búsqueda. Para obtener descripciones de la información detallada, vea el [registro de auditoría de propiedades detalladas en Office 365](detailed-properties-in-the-office-365-audit-log.md).
  
Haga clic en uno de los siguientes vínculos para ir a una tabla específica.
  
||||
|:-----|:-----|:-----|
|[Actividades de archivo y página](#file-and-page-activities)<br/> |[Actividades de carpeta](#folder-activities)<br/> |[Actividades de solicitud de acceso y uso compartido](#sharing-and-access-request-activities)<br/> |
|[Actividades de sincronización](#synchronization-activities)<br/> |[Actividades de administración del sitio](#site-administration-activities)<br/> |[Actividades de buzón de correo de Exchange](#exchange-mailbox-activities)<br/> |
|[Influir hora de elegir las actividades](#sway-activities) <br/> |[Actividades de administración de usuario](#user-administration-activities) <br/> |[Actividades de administración de grupo de Azure AD](#azure-ad-group-administration-activities) <br/> |
|[Actividades de administración de aplicaciones](#application-administration-activities) <br/> |[Actividades de administración de roles](#role-administration-activities) <br/> |[Actividades de administración de Active Directory](#directory-administration-activities) <br/> |
|[actividades de exhibición de documentos electrónicos](#ediscovery-activities) <br/> |[Actividades de Power BI](#power-bi-activities) <br/> |[Actividades de Microsoft Teams](#microsoft-teams-activities) <br/> |
|[Actividades de yammer](#yammer-activities) <br/> |[Microsoft Flow](#microsoft-flow) <br/> |[Microsoft Stream](#microsoft-stream) <br/>|
|[Registro de auditoría de administración de Exchange](#exchange-admin-audit-log) <br/> |
   
  
### <a name="file-and-page-activities"></a>Actividades de archivo y página
  
En la siguiente tabla describe las actividades de archivo y la página en SharePoint Online y OneDrive para la empresa.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Archivo de acceso  <br/> |FileAccessed  <br/> |Cuenta de usuario o del sistema tiene acceso a un archivo.  <br/> |
|(ninguno)  <br/> |FileAccessedExtended  <br/> |Esto está relacionado con el "archivo de último acceso" actividad (FileAccessed). Se registra un evento FileAccessedExtended cuando la misma persona continuamente obtiene acceso a un archivo durante un largo período de tiempo (hasta 3 horas). El propósito del registro de eventos de FileAccessedExtended es reducir el número de eventos de FileAccessed que se registran cuando continuamente se accede a un archivo. Esto ayuda a reducir el ruido de varios registros de FileAccessed de lo que es esencialmente la misma actividad del usuario y le permite centrarse en el evento FileAccessed inicial (y más importante).  <br/> |
|Comprobados en el archivo  <br/> |FileCheckedIn  <br/> |El usuario protege un documento que ha desprotegido desde una biblioteca de documentos.  <br/> |
|Desprotege el archivo  <br/> |FileCheckedOut  <br/> |Usuario desprotege un documento que se encuentra en una biblioteca de documentos. Los usuarios pueden desproteger y realizar cambios en los documentos que se han compartido con ellos.  <br/> |
|Archivo copiado  <br/> |FileCopied  <br/> |Usuario copia un documento de un sitio. El archivo copiado puede guardarse en otra carpeta en el sitio.  <br/> |
|Archivo eliminado  <br/> |FileDeleted  <br/> |Usuario elimina un documento de un sitio.  <br/> |
|Archivo eliminado de la Papelera de reciclaje  <br/> |FileDeletedFirstStageRecycleBin  <br/> |Usuario elimina un archivo de la Papelera de reciclaje de un sitio.  <br/> |
|Archivo eliminado de la Papelera de reciclaje de segunda etapa  <br/> |FileDeletedSecondStageRecycleBin  <br/> |Usuario elimina un archivo de la Papelera de reciclaje de segunda etapa de un sitio.  <br/> |
|Se ha detectado malware en archivo  <br/> |FileMalwareDetected  <br/> |Motor de antivirus de SharePoint detecta malware en un archivo.  <br/> |
|Desprotección del archivo descartados  <br/> |FileCheckOutDiscarded  <br/> |El usuario descarta (o deshace) un archivo desprotegido, lo que significa que los cambios realizados en el archivo cuando estaba desprotegido se descartan y no se guardan en la versión del documento en la biblioteca de documentos.  <br/> |
|Archivo descargado  <br/> |FileDownloaded  <br/> |Usuario descarga un documento de un sitio.  <br/> |
|Archivo modificado  <br/> |FileModified  <br/> |Cuenta de usuario o del sistema modifica el contenido o las propiedades de un documento que se encuentra en un sitio.  <br/> |
|(ninguno)  <br/> |FileModifiedExtended  <br/> |Esto está relacionado con el "archivo modificado" actividad (FileModified). Se registra un evento FileModifiedExtended cuando la misma persona modifica continuamente un archivo durante un largo período de tiempo (hasta 3 horas). El propósito del registro de eventos de FileModifiedExtended es reducir el número de eventos de FileModified que se registran cuando un archivo se modifica de forma continua. Esto ayuda a reducir el ruido de varios registros de FileModified de lo que es esencialmente la misma actividad del usuario y le permite centrarse en el evento FileModified inicial (y más importante).  <br/> |
|Archivo que se ha movido  <br/> |FileMoved  <br/> |Usuario mueve un documento desde su ubicación actual en un sitio a una nueva ubicación.  <br/> |
|Recicla todas las versiones secundarias del archivo  <br/> |FileVersionsAllMinorsRecycled  <br/> |Usuario elimina todas las versiones secundarias del historial de versiones de un archivo. Las versiones eliminadas se mueven a la Papelera de reciclaje del sitio.  <br/> |
|Recicla todas las versiones de archivo  <br/> |FileVersionsAllRecycled  <br/> |Usuario elimina todas las versiones del historial de versiones de un archivo. Las versiones eliminadas se mueven a la Papelera de reciclaje del sitio.  <br/> |
|Versión de reciclado del archivo  <br/> |FileVersionRecycled  <br/> |Usuario elimina una versión del historial de versiones de un archivo. La versión eliminada se mueve a la Papelera de reciclaje del sitio.  <br/> |
|Ha cambiado el nombre de archivo  <br/> |FileRenamed  <br/> |Usuario cambia el nombre de un documento en un sitio.  <br/> |
|Archivo restaurado  <br/> |FileRestored  <br/> |Usuario restaura un documento desde la Papelera de reciclaje de un sitio.  <br/> |
|Archivo cargado  <br/> |FileUploaded  <br/> |Usuario carga un documento en una carpeta de un sitio.  <br/> |
|Página visitada  <br/> |PageViewed  <br/> |Usuario visualiza una página de un sitio. Esto no incluye el uso de un explorador Web para ver los archivos que se encuentra en una biblioteca de documentos.  <br/> |
|(ninguno)  <br/> |PageViewedExtended  <br/> |Esto está relacionado con el "se ve"página de actividad (PageViewed). Se registra un evento PageViewedExtended cuando la misma persona continuamente ve una página web durante un largo período de tiempo (hasta 3 horas). El propósito del registro de eventos de PageViewedExtended es reducir el número de eventos de PageViewed que se registran cuando una página se ve continuamente. Esto ayuda a reducir el ruido de varios registros de PageViewed de lo que es esencialmente la misma actividad del usuario y le permite centrarse en el evento PageViewed inicial (y más importante).  <br/> |
  
### <a name="folder-activities"></a>Actividades de carpeta
  
En la siguiente tabla describe las actividades de la carpeta en SharePoint Online y OneDrive para la empresa.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Carpeta copiada  <br/> |FolderCopied  <br/> |Usuario copia una carpeta de un sitio a otra ubicación en SharePoint o OneDrive para la empresa.  <br/> |
|Creación de la carpeta  <br/> |FolderCreated  <br/> |Usuario crea una carpeta en un sitio.  <br/> |
|Carpeta eliminada  <br/> |FolderDeleted  <br/> |Usuario elimina una carpeta de un sitio.  <br/> |
|Carpeta eliminada desde la Papelera de reciclaje  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |Usuario elimina una carpeta de la Papelera de reciclaje en un sitio.  <br/> |
|Carpeta eliminada desde la Papelera de reciclaje de segunda etapa  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |Usuario elimina una carpeta de la Papelera de reciclaje de segunda etapa en un sitio.  <br/> |
|Carpeta modificada  <br/> |FolderModified  <br/> |Usuario modifica una carpeta en un sitio. Esto incluye cambiar los metadatos de carpeta, como el cambio de etiquetas y propiedades.  <br/> |
|Carpeta que se ha movido  <br/> |FolderMoved  <br/> |Usuario mueve una carpeta a una ubicación diferente en un sitio.  <br/> |
|Ha cambiado el nombre de carpeta  <br/> |FolderRenamed  <br/> |Usuario cambia el nombre de una carpeta en un sitio.  <br/> |
|Carpeta restaurado  <br/> |FolderRestored  <br/> |Usuario restaura una carpeta eliminada de la Papelera de reciclaje en un sitio.  <br/> |
  
### <a name="sharing-and-access-request-activities"></a>Actividades de solicitud de acceso y uso compartido
  
En la siguiente tabla se describe las actividades de solicitud de uso compartido y el acceso de usuario en SharePoint Online y OneDrive para la empresa. Para eventos de uso compartido, la columna de **detalle** en **los resultados de** identifica el nombre del usuario o grupo que el elemento se ha compartido con y si dicho usuario o grupo es un miembro o invitado en su organización. Para obtener más información, vea [uso de uso compartido de auditoría en el registro de auditoría de Office 365](use-sharing-auditing.md).
  
> [!NOTE]
> Los usuarios pueden ser *miembros* o *invitados* en función de la propiedad UserType del objeto de usuario. Un miembro suele ser un empleado y un invitado normalmente es un colaborador fuera de la organización. Cuando un usuario acepta una invitación de uso compartido (y ya no forma parte de la organización), se crea una cuenta de invitado para ellos en Active directory de su organización. Una vez que el usuario invitado tiene una cuenta en el directorio, se pueden compartir recursos directamente con ellos (sin necesidad de una invitación). 
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Acepta solicitudes de acceso  <br/> |AccessRequestAccepted  <br/> |Se aceptó una solicitud de acceso a un sitio, una carpeta o un documento y el usuario solicitante se ha concedido acceso.  <br/> |
|Acepta la invitación de uso compartido  <br/> |SharingInvitationAccepted  <br/> |Usuario (miembro o invitado) acepta una invitación de uso compartido y se ha concedido acceso a un recurso. Este evento incluye información sobre el usuario invitado y la dirección de correo electrónico que se usó para aceptar la invitación (que podrían ser diferentes). Esta actividad a menudo va acompañada por un segundo evento que se describe cómo el usuario se ha concedido acceso al recurso, por ejemplo, agregar el usuario a un grupo que tenga acceso al recurso.  <br/> |
|Nivel de permisos se ha agregado a la colección de sitios  <br/> |PermissionLevelAdded  <br/> |Se agregó un nivel de permisos a una colección de sitios.  <br/> |
|Usuario ha añadido a vínculo seguro  <br/> |AddedToSecureLink  <br/> |Se agregó un usuario a la lista de entidades que puede usar este vínculo de uso compartido seguro.  <br/> |
|Bloquea la invitación de uso compartido  <br/> |SharingInvitationBlocked  <br/> | Una invitación para compartir enviada por un usuario de la organización está bloqueada debido a una directiva de uso compartido externa que permite o deniega el uso de compartido externo basado en el dominio del usuario de destino. En este caso, la invitación para compartir se bloqueó debido a que:<br/>  Dominio del usuario de destino no está incluido en la lista de dominios permitidos.  <br/>  O bien  <br/>  Dominio del usuario de destino se incluye en la lista de dominios bloqueados.  <br/>  Para obtener más información acerca de permitir o bloquear compartir externos basados en dominios, vea [dominios restringidos el uso compartido en SharePoint Online y OneDrive para la empresa](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9).  <br/> |
|Interrumpida por herencia de nivel de permisos  <br/> |PermissionLevelsInheritanceBroken  <br/> |Se modificó un elemento para que ya no herede los niveles de permisos de su elemento primario.  <br/> |
|Dañó el uso compartido de herencia  <br/> |SharingInheritanceBroken  <br/> |Se modificó un elemento para que ya no herede permisos de uso compartido de su elemento primario.  <br/> |
|Crea un vínculo que se pueden compartir de la compañía  <br/> |CompanyLinkCreated  <br/> |Un vínculo de toda la compañía a un recurso de creado por el usuario. sólo se pueden usar los vínculos de toda la compañía por los miembros de la organización. No pueden usarse los invitados.  <br/> |
|Crear solicitud de acceso  <br/> |AccessRequestCreated  <br/> |El usuario solicita acceso a un sitio, la carpeta o el documento no tienen permisos para tener acceso a.  <br/> |
|Crea un vínculo anónimo  <br/> |AnonymousLinkCreated  <br/> |Creado un vínculo anónimo a un recurso por el usuario. Cualquier usuario con este vínculo puede tener acceso al recurso sin tener que ser autenticados.  <br/> |
|Crea un vínculo seguro  <br/> |SecureLinkCreated  <br/> |Un vínculo de uso compartido seguro se creó para este elemento.  <br/> |
|Crear invitación de uso compartido  <br/> |SharingInvitationCreated  <br/> |Usuario comparte un recurso en SharePoint Online o OneDrive para la empresa con un usuario que no se encuentra en el directorio de la organización.  <br/> |
|Vínculo seguro eliminado  <br/> |SecureLinkDeleted  <br/> |Se eliminó un vínculo de uso compartido seguro.  <br/> |
|Denegado solicitudes de acceso  <br/> |AccessRequestDenied  <br/> |Se denegó una solicitud de acceso a un sitio, una carpeta o un documento.  <br/> |
|Nivel de permisos modificados en la colección de sitios  <br/> |PermissionLevelModified  <br/> |Se cambió un nivel de permisos en una colección de sitios.  <br/> |
|Quita un vínculo que se pueden compartir de la compañía  <br/> |CompanyLinkRemoved  <br/> |Usuario quita un vínculo de toda la compañía a un recurso. El vínculo ya no puede utilizarse para tener acceso al recurso.  <br/> |
|Quita un vínculo anónimo  <br/> |AnonymousLinkRemoved  <br/> |Usuario quita un vínculo anónimo a un recurso. El vínculo ya no puede utilizarse para tener acceso al recurso.  <br/> |
|Quita el nivel de permisos de colección de sitios  <br/> |PermissionLevelRemoved  <br/> |Se quitó un nivel de permisos de una colección de sitios.  <br/> |
|Restaura el uso compartido de herencia  <br/> |SharingInheritanceReset  <br/> |Se ha realizado un cambio para que un elemento hereda los permisos de uso compartido de su elemento primario.  <br/> |
|Archivo compartido, carpeta o sitio  <br/> |SharingSet  <br/> |Usuario (miembro o invitado) comparte un archivo, carpeta o sitio en SharePoint o OneDrive para la empresa con un usuario en Active directory de su organización. El valor de la columna de **detalle** para esta actividad identifica el nombre del usuario con que el recurso se ha compartido y si este usuario es un miembro o invitado. Esta actividad a menudo va acompañada por un segundo evento que se describe cómo el usuario se ha concedido acceso al recurso; Por ejemplo, agregar el usuario a un grupo que tenga acceso al recurso.<br/> |
|Solicitud de acceso actualizada  <br/> |AccessRequestUpdated  <br/> |Se actualizó una solicitud de acceso a un elemento.  <br/> |
|Se ha actualizado un vínculo anónimo  <br/> |AnonymousLinkUpdated  <br/> |Usuario se ha actualizado un vínculo anónimo a un recurso. El campo actualizado se incluye en la propiedad EventData al exportar los resultados de búsqueda.  <br/> |
|Se actualizó la invitación de uso compartido  <br/> |SharingInvitationUpdated  <br/> |Se actualizó una invitación de uso compartida externa.  <br/> |
|Utiliza un vínculo anónimo  <br/> |AnonymousLinkUsed  <br/> |Un usuario anónimo tener acceso a un recurso mediante el uso de un vínculo anónimo. Es posible que se desconoce la identidad del usuario, pero puede obtener otros detalles, como la dirección IP del usuario.  <br/> |
|Archivo no compartido, carpeta o sitio  <br/> |SharingRevoked  <br/> |Usuario (miembro o invitado) de compartir un archivo, carpeta o sitio que anteriormente se ha compartido con otro usuario.  <br/> |
|Utiliza un vínculo que se pueden compartir de la compañía  <br/> |CompanyLinkUsed  <br/> |Usuario tener acceso a un recurso mediante el uso de un vínculo de toda la compañía.  <br/> |
|Utiliza el vínculo seguro  <br/> |SecureLinkUsed  <br/> |Un usuario usa un vínculo seguro.  <br/> |
|Usuario ha añadido a vínculo seguro  <br/> |AddedToSecureLink  <br/> |Se agregó un usuario a la lista de entidades que puede usar un vínculo de uso compartido seguro.  <br/> |
|Usuario quitado de vínculo seguro  <br/> |RemovedFromSecureLink  <br/> |Un usuario se quitó de la lista de entidades que puede usar un vínculo de uso compartido seguro.  <br/> |
|Retiró invitación de uso compartido  <br/> |SharingInvitationRevoked  <br/> |Usuario retiró una invitación para compartir para un recurso.  <br/> |
  
### <a name="synchronization-activities"></a>Actividades de sincronización
  
En la siguiente tabla se enumera las actividades de sincronización del archivo en SharePoint Online y OneDrive para la empresa.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Permite el equipo para sincronizar los archivos  <br/> |ManagedSyncClientAllowed  <br/> |Usuario correctamente establece una relación de sincronización con un sitio. La relación de sincronización es correcta debido a que el equipo del usuario es un miembro de un dominio que se ha agregado a la lista de dominios (denominado la *lista de destinatarios seguros* ) que puede tener acceso a las bibliotecas de documentos en su organización.<br/> Para obtener más información acerca de esta característica, vea [Use Windows PowerShell cmdlets para habilitar la sincronización de OneDrive para dominios que se encuentran en la lista de destinatarios seguros](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|Bloquea el equipo de sincronización de archivos  <br/> |UnmanagedSyncClientBlocked  <br/> |Usuario intenta establecer una relación de sincronización con un sitio desde un equipo que no es un miembro del dominio de su organización o es un miembro de un dominio que no se ha agregado a la lista de dominios (denominado el *la lista de destinatarios seguros)* que puede tener acceso a documentos bibliotecas de la organización. No se permite la relación de sincronización, y el equipo del usuario se bloquea la sincronización, descargar o cargar archivos en una biblioteca de documentos.<br/> Para obtener información acerca de esta característica, vea [Use Windows PowerShell cmdlets para habilitar la sincronización de OneDrive para dominios que se encuentran en la lista de destinatarios seguros](https://go.microsoft.com/fwlink/p/?LinkID=534609).  <br/> |
|Archivos descargados en equipo  <br/> |FileSyncDownloadedFull  <br/> |Usuario establece una relación de sincronización y descarga correctamente archivos por primera vez en su equipo desde una biblioteca de documentos.  <br/> |
|Cambios de archivo descargado en el equipo  <br/> |FileSyncDownloadedPartial  <br/> |Usuario descarga correctamente los cambios a los archivos de una biblioteca de documentos. Esta actividad indica que los cambios que se han realizado en los archivos en la biblioteca de documentos se han descargado en el equipo del usuario. Sólo los cambios que se han descargado debido a que la biblioteca de documentos se ha descargado previamente por el usuario (tal como indica la actividad de **descargar los archivos en equipo** ).<br/> |
|Archivos cargados en biblioteca de documentos  <br/> |FileSyncUploadedFull  <br/> |Usuario establece una relación de sincronización y carga correctamente los archivos por primera vez desde su equipo a una biblioteca de documentos.  <br/> |
|Cambios de archivo cargado en la biblioteca de documentos  <br/> |FileSyncUploadedPartial  <br/> |Usuario carga correctamente los cambios en los archivos en una biblioteca de documentos. Este evento indica que los cambios realizados en la versión local de un archivo desde una biblioteca de documentos se cargan correctamente en la biblioteca de documentos. Sólo se descargan los cambios debido a que dichos archivos se han cargado previamente por el usuario (indicada por el ** a los archivos cargados en biblioteca de documentos ** actividad).  <br/> |
  
### <a name="site-administration-activities"></a>Actividades de administración del sitio
  
En la siguiente tabla se enumera los eventos que resultan de las tareas de administración de sitio en SharePoint Online.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Agente de usuario exentos se ha agregado  <br/> |ExemptUserAgentSet  <br/> |Un administrador global o SharePoint agrega a un agente de usuario a la lista de agentes de usuario exentos en el centro de administración de SharePoint.  <br/> |
|Administración de colección de sitios se ha agregado  <br/> |SiteCollectionAdminAdded  <br/> |Administrador de colección de sitios o propietario agrega a una persona como un administrador de colección de sitios para un sitio. Los administradores de colección de sitios tienen permisos de control total para la colección de sitios y todos los subsitios.  <br/> |
|Se ha agregado un usuario o grupo al grupo de SharePoint  <br/> |AddedToGroup  <br/> |Usuario agrega un miembro o invitado a un grupo de SharePoint. Esto es posible que han sido una acción intencionada o el resultado de otra actividad, como un evento de uso compartido.  <br/> |
|Permite al usuario crear grupos  <br/> |AllowGroupCreationSet  <br/> |Administrador de sitios o propietario agrega un nivel de permisos a un sitio que permite que a un usuario asignado ese permiso para crear un grupo para ese sitio.  <br/> |
|Mover sitios cancelado geo  <br/> |SiteGeoMoveCancelled  <br/> |Un administrador global o SharePoint correctamente cancela una SharePoint o OneDrive sitio ubican mover. La capacidad de Multi-ubican permite a una organización de Office 365 abarcan diversas geografías de centro de datos de Office 365, que se denominan zonas. Para obtener más información, vea [Funciones de Multi-ubican en OneDrive y SharePoint Online en Office 365](https://go.microsoft.com/fwlink/?linkid=860840).<br/> |
|Cambiar una directiva de uso compartido  <br/> |SharingPolicyChanged  <br/> |Un administrador global o SharePoint ha cambiado una SharePoint directiva de uso compartido mediante el portal de administración de Office 365, el portal de administración de SharePoint o el Shell de administración de SharePoint Online. Se registrará cualquier cambio en la configuración de la directiva de uso compartido de la organización. Se identifica la directiva que se ha cambiado en el campo **ModifiedProperties** en las propiedades detalladas del registro de eventos.<br/> |
|Cambiar la directiva de acceso de dispositivo  <br/> |DeviceAccessPolicyChanged  <br/> |Un administrador global o SharePoint ha cambiado la directiva de dispositivos no administrados para su organización. Esta directiva controla el acceso a SharePoint, OneDrive y Office 365 desde dispositivos que no se ha unido a la organización. Configura esta directiva, requiere una empresa movilidad + suscripción de seguridad. Para obtener más información, vea [controlar el acceso desde dispositivos no administrados](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622).<br/> |
|Agentes de usuario exentos modificado  <br/> |CustomizeExemptUsers  <br/> |Un administrador global o SharePoint puede personalizar la lista de agentes de usuario exentos en el centro de administración de SharePoint. Puede especificar a qué agentes de usuario que se excluyen del recibir una página web completa al índice. Esto significa que cuando un agente de usuario que ha especificado como exento encuentra un formulario de InfoPath, se devolverá el formulario como un archivo XML, en lugar de una página web completa. Esto hace que los formularios de InfoPath indización con mayor rapidez.  <br/> |
|Cambiar la directiva de acceso de red  <br/> |NetworkAccessPolicyChanged  <br/> |Un administrador global o SharePoint ha cambiado la directiva de acceso basados en ubicación (también denominada un límite de red de confianza) en el centro de administración de SharePoint o mediante el uso de PowerShell en SharePoint Online. Este tipo de directiva controla quién puede tener acceso a los recursos de SharePoint y OneDrive en la organización en función de intervalos de direcciones IP autorizados que especifique. Para obtener más información, vea [controlar el acceso a SharePoint Online y datos de OneDrive en función de la ubicación de red](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f).<br/> |
|Mover de sitio completados geo  <br/> |SiteGeoMoveCompleted  <br/> |Un movimiento de geo de sitio que se ha programado por un administrador global de la organización se ha completado correctamente. La capacidad de Multi-ubican permite a una organización de Office 365 abarcan diversas geografías de centro de datos de Office 365, que se denominan zonas. Para obtener más información, vea [Funciones de Multi-ubican en OneDrive y SharePoint Online en Office 365](https://go.microsoft.com/fwlink/?linkid=860840).<br/> |
|Grupo creado  <br/> |GroupAdded  <br/> |Administrador del sitio o propietario crea un grupo para un sitio o realiza una tarea que da como resultado un grupo que se está creando. Por ejemplo, la primera vez que un usuario crea un vínculo para compartir un archivo, un grupo de sistema se agrega a OneDrive del usuario para el sitio de negocio. Este evento también puede ser un resultado de un usuario que crea un vínculo con editar los permisos en un archivo compartido.  <br/> |
|Conexión creada enviado a  <br/> |SendToConnectionAdded  <br/> |Un administrador global o SharePoint crea una nueva conexión de enviar a en la página de administración de registros en el centro de administración de SharePoint. Una conexión de enviar a especifica la configuración de un repositorio de documentos o un centro de registros. Cuando se crea una conexión de enviar a, un organizador de contenido pueden enviar documentos a la ubicación especificada.  <br/> |
|Colección de sitios creada  <br/> |SiteCollectionCreated  <br/> |Un administrador global o SharePoint crea una nueva colección de sitios en la organización de SharePoint Online o un usuario proporcione su OneDrive para el sitio de negocio.  <br/> |
|Grupo eliminado  <br/> |GroupRemoved  <br/> |Usuario elimina un grupo de un sitio.  <br/> |
|Conexión eliminada enviado a  <br/> |SendToConnectionRemoved  <br/> |Un administrador global o SharePoint elimina una conexión de enviar a en la página de administración de registros en el centro de administración de SharePoint.  <br/> |
|Sitio eliminado  <br/> |SiteDeleted  <br/> |Administrador de sitios elimina un sitio.  <br/> |
|Habilitado para la vista previa del documento  <br/> |PreviewModeEnabledSet  <br/> |Administrador del sitio permite la vista previa del documento para un sitio.  <br/> |
|Habilitado para flujo de trabajo heredado  <br/> |LegacyWorkflowEnabledSet  <br/> |El administrador o el propietario del sitio agregan el tipo de contenido Tarea de flujo de trabajo de SharePoint 2013 al sitio. Los administradores globales también pueden habilitar flujos de trabajo para toda la organización en el centro de administración de SharePoint.  <br/> |
|Enabled Office a petición  <br/> |OfficeOnDemandSet  <br/> |Administrador del sitio permite Office a petición, lo que permite a los usuarios tener acceso a la versión más reciente de aplicaciones de escritorio de Office. Office a petición está habilitada en el centro de administración de SharePoint y requiere una suscripción a Office 365 que incluye las aplicaciones de Office instaladas, completas.  <br/> |
|Fuentes RSS habilitadas  <br/> |NewsFeedEnabledSet  <br/> |Administrador de sitios o propietario permite fuentes RSS para un sitio. Los administradores globales pueden habilitar fuentes RSS para toda la organización en el centro de administración de SharePoint.  <br/> |
|Configuración de solicitud de acceso modificados  <br/> |WebRequestAccessModified  <br/> |La configuración de solicitud de acceso se modificaron en un sitio.  <br/> |
|Configuración de los miembros pueden compartir modificada  <br/> |WebMembersCanShareModified  <br/> |Se modificó la configuración de **Los miembros pueden compartir** en un sitio.  <br/> |
|Permisos de sitio modificado  <br/> |SitePermissionsModified  <br/> |Administrador del sitio o propietario (o la cuenta del sistema) cambia el nivel de permisos que se asignan a un grupo en un sitio. Esta actividad también se registra si se quitan todos los permisos de un grupo.<br/> > [!NOTE]> Esta operación ha quedado obsoleto en SharePoint Online. Para buscar eventos relacionados, se puede buscar en otras actividades relacionadas con el permiso como **administración de colección de sitios se ha agregado**, **se agregó un usuario o grupo al grupo de SharePoint**, **usuario permitido para crear grupos**, **grupo creado**y **Deleted grupo.**         |
|Quitar usuario o grupo de grupo de SharePoint  <br/> |RemovedFromGroup  <br/> |Usuario quita un miembro o invitado de un grupo de SharePoint. Esto es posible que han sido una acción intencionada o el resultado de otra actividad, como un evento de dejar de compartir.  <br/> |
|Ha cambiado el nombre de sitio  <br/> |SiteRenamed  <br/> |Administrador de sitios o propietario cambia el nombre de un sitio  <br/> |
|Permisos de administrador de sitio solicitado  <br/> |SiteAdminChangeRequest  <br/> |Solicitudes de usuario que se agregará como un administrador de colección de sitios para una colección de sitios. Los administradores de colección de sitios tienen permisos de control total para la colección de sitios y todos los subsitios.  <br/> |
|Mover ubican programado del sitio  <br/> |SiteGeoMoveScheduled  <br/> |Un administrador global o SharePoint correctamente programaciones de SharePoint o OneDrive sitio ubican mover. La capacidad de Multi-ubican permite a una organización de Office 365 abarcan diversas geografías de centro de datos de Office 365, que se denominan zonas. Para obtener más información, vea [Funciones de Multi-ubican en OneDrive y SharePoint Online en Office 365](https://go.microsoft.com/fwlink/?linkid=860840).<br/> |
|Sitio de host de conjunto  <br/> |HostSiteSet  <br/> |Un administrador global o SharePoint cambia el sitio designado para hospedar personal o OneDrive para los sitios de negocio.  <br/> |
|Grupo actualizado  <br/> |GroupUpdated  <br/> |Administrador de sitios o propietario cambia la configuración de un grupo para un sitio. Esto puede incluir cambiar el nombre del grupo, que puede ver o editar la pertenencia al grupo, y cómo se controlan las solicitudes de participación.  <br/> |
  
### <a name="exchange-mailbox-activities"></a>Actividades de buzón de correo de Exchange
  
En la siguiente tabla se enumera las actividades que se pueden registrar por buzón de registro de auditoría. Se registran las actividades de buzón de correo realizadas por el propietario del buzón, un usuario delegado o un administrador. De forma predeterminada, la auditoría de buzón de correo en Office 365 no está activada. Auditoría de buzón de correo registro debe activarlo para cada buzón de correo antes de que se registrarán la actividad de buzón de correo. Para obtener más información, vea [Habilitar la auditoría en Office 365 de buzón de correo](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Se ha agregado un delegado permisos de buzón de correo  <br/> |Agregar permiso de buzón  <br/> |Un administrador asigna contar con permiso de buzón de correo a un usuario (conocido como delegado) al buzón de otra persona. Contar con permiso permite al delegado abrir el buzón de la otra persona y leer y administrar el contenido del buzón.  <br/> |
|Mensajes copiados a otra carpeta  <br/> |Copiar  <br/> |Un mensaje se copió en otra carpeta.  <br/> |
|Elemento de buzón de correo creada  <br/> |Crear  <br/> |Se crea un elemento en la carpeta Calendario, contactos, notas o tareas en el buzón de correo; Por ejemplo, se crea una nueva convocatoria de reunión. Tenga en cuenta que no se audita crear, enviar o recibir un mensaje. Además, no se audita la creación de una carpeta de buzón de correo.  <br/> |
|Mensajes eliminados de la carpeta Elementos eliminados  <br/> |SoftDelete  <br/> |Un mensaje fue eliminado o se elimina de la carpeta Elementos eliminados permanentemente. Estos elementos se mueven a la carpeta elementos recuperables. Los mensajes también se mueven a la carpeta elementos recuperables cuando un usuario selecciona y presiona la **Tecla MAYÚS + SUPR**.<br/> |
|Mover mensajes a otra carpeta  <br/> |Mover  <br/> |Un mensaje se movió a otra carpeta.  <br/> |
|Mover mensajes a la carpeta Elementos eliminados  <br/> |MoveToDeletedItems  <br/> |Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.  <br/> |
|Permisos de carpeta modificada  <br/> |UpdateFolderPermissions  <br/> |Se ha cambiado un permiso de la carpeta. Control de los permisos de carpeta qué usuarios de la organización pueden tener acceso a las carpetas de buzón de correo y los mensajes en la carpeta.  <br/> |
|Mensajes purgados desde el buzón de correo  <br/> |HardDelete  <br/> |Se ha purgado un mensaje desde la carpeta elementos recuperables (eliminada de manera permanente el buzón de correo).  <br/> |
|Permisos de buzón de correo delegado quitado  <br/> |Remove-MailboxPermission  <br/> |Un administrador ha quitado contar con permiso (que se asignó a un delegado) de un buzón de la persona. Después de que se ha quitado el contar con permiso, el delegado no se puede abrir el buzón de la otra persona o tener acceso a cualquier contenido en ella.  <br/> |
|Envía el mensaje con permisos Enviar como  <br/> |SendAs  <br/> |Un mensaje se envió mediante el permiso SendAs. Esto significa que otro usuario envió el mensaje como si procediera del propietario del buzón.  <br/> |
|Envía el mensaje con los permisos Enviar en nombre  <br/> |SendOnBehalf  <br/> |Un mensaje se envió mediante el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje en nombre del propietario del buzón. El mensaje indica el destinatario en nombre de quien se envió el mensaje y quién lo envió realmente.  <br/> |
|Acceso delegado actualizado a la carpeta Calendario  <br/> |UpdateCalendarDelegation  <br/> |Una delegación de calendario se asignó a un buzón de correo. Delegación de calendario proporciona a otra persona en los mismos permisos de organización para administrar el calendario del propietario del buzón.  <br/> |
|Mensaje actualizado  <br/> |Update  <br/> |Se cambió un mensaje o sus propiedades.  <br/> |
|Usuario que ha iniciado sesión en el buzón de correo  <br/> |MailboxLogin  <br/> |El usuario inició sesión en su buzón.  <br/> |
|(ninguno)  <br/> |UpdateInboxRules  <br/> |Se han agregado, eliminada o cambiado una regla de bandeja de entrada. Las reglas de bandeja de entrada se usan para procesar los mensajes en la Bandeja de entrada del usuario en función de las condiciones especificadas y realizar acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o la eliminación de un mensaje.<br/> Para devolver las entradas para las actividades de regla de bandeja de entrada, tendrá que seleccionar **Mostrar los resultados de todas las actividades** en la lista de **actividades** . Utilice los cuadros intervalo de fechas y la lista de **usuarios** para restringir los resultados de búsqueda.<br/> |
  
### <a name="sway-activities"></a>Influir hora de elegir las actividades
  
En la siguiente tabla enumera las actividades de usuario y administración de balanceo. Balanceo es una aplicación de Office 365 que ayuda a los usuarios recopilar, dar formato y compartir ideas, casos y presentaciones en un lienzo interactiva, basada en web. Para obtener más información, consulte [preguntas frecuentes sobre balanceo - ayuda de administración](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075).
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Nivel de recurso compartido de balanceo modificada  <br/> |SwayChangeShareLevel  <br/> |Usuario cambia el nivel de recurso compartido de un balanceo. Este evento captura al usuario cambie el ámbito de uso compartido asociado con un balanceo; Por ejemplo, pública frente a dentro de la organización.  <br/> |
|Balanceo creada  <br/> |SwayCreate  <br/> |El usuario crea un balanceo.  <br/> |
|Balanceo eliminado  <br/> |SwayDelete  <br/> |Usuario elimina un balanceo.  <br/> |
|Duplicación de balanceo deshabilitado  <br/> |SwayDisableDuplication  <br/> |Usuario deshabilita la duplicación de un balanceo.  <br/> |
|Balanceo duplicada  <br/> |SwayDuplicate  <br/> |Usuario duplica un balanceo.  <br/> |
|Balanceo editado  <br/> |SwayEdit  <br/> |Usuario edita un balanceo.  <br/> |
|Duplicación de balanceo habilitado  <br/> |EnableDuplication  <br/> |Usuario habilita la duplicación de un balanceo; la capacidad de un usuario habilitar la duplicación de un balanceo está habilitada de forma predeterminada.  <br/> |
|Uso compartido de balanceo revocado  <br/> |SwayRevokeShare  <br/> |Usuario deja de compartir un balanceo por revocar el acceso a ella. Revocar el acceso cambia los vínculos asociados con un balanceo.  <br/> |
|Balanceo compartida  <br/> |SwayShare  <br/> |Usuario que se va a compartir un balanceo. Este evento captura la acción del usuario de hacer clic en un destino de recurso compartido específico en el menú Compartir de balanceo. El evento no indica si el usuario finalizó la acción de recurso compartido.  <br/> |
|Desactivar uso compartido externo de balanceo  <br/> |SwayExternalSharingOff  <br/> |Administrador deshabilita balanceo uso compartido externo para toda la organización mediante el centro de administración de Office 365.  <br/> |
|Activado el uso compartido externo de balanceo  <br/> |SwayExternalSharingOn  <br/> |Administrador habilita balanceo uso compartido externo para toda la organización mediante el centro de administración de Office 365.  <br/> |
|Desactivar el servicio de balanceo  <br/> |SwayServiceOff  <br/> |Administrador deshabilita balanceo para toda la organización mediante el centro de administración de Office 365.  <br/> |
|Activado el servicio de balanceo  <br/> |SwayServiceOn  <br/> |Administrador habilita balanceo para toda la organización mediante el centro de administración de Office 365 (balanceo servicio está habilitado de forma predeterminada).  <br/> |
|Balanceo visualizado  <br/> |SwayView  <br/> |Usuario visualiza un balanceo.  <br/> |

  
### <a name="user-administration-activities"></a>Actividades de administración de usuario
  
En la siguiente tabla se enumera las actividades de administración de usuario que se registran cuando un administrador agrega o cambia una cuenta de usuario mediante el centro de administración de Office 365 o el portal de administración de Azure.
  
|**Actividad**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Se ha agregado un usuario  <br/> |Agregar usuario  <br/> |Se ha creado una cuenta de usuario de Office 365.  <br/> |
|Licencia de usuario modificado  <br/> |Licencia de usuario de cambio  <br/> |La licencia asignada a un usuario, lo que ha cambiado. Para ver qué licencias fueron los cambios, vea la actividad de **usuario se ha actualizado** correspondiente.<br/> |
|Contraseña de usuario modificado  <br/> |Cambiar la contraseña de usuario  <br/> |Administrador de cambia la contraseña la contraseña de un usuario.  <br/> |
|Usuario eliminado  <br/> |Eliminación de usuario  <br/> |Se eliminó una cuenta de usuario de Office 365.  <br/> |
|Restablecer la contraseña de usuario  <br/> |Restablecer la contraseña de usuario  <br/> |Administrador de restablecer la contraseña de un usuario.  <br/> |
|Establece la propiedad que obliga al usuario cambiar la contraseña  <br/> |Conjunto force cambiar contraseña de usuario  <br/> |Administrador establecer la propiedad que obliga a un usuario para cambiar su contraseña la próxima vez que el usuario iniciar sesión en Office 365.  <br/> |
|Establecer propiedades de licencia  <br/> |Establecer propiedades de licencia  <br/> |Administrador modifica las propiedades de una licencia asignada a un usuario.  <br/> |
|Usuario actualizada  <br/> |Usuario de actualización  <br/> |Administrador cambia las propiedades de uno o más de una cuenta de usuario. Para obtener una lista de las propiedades de usuario que se pueden actualizar, vea la sección "Actualizar los atributos de usuario" en [Eventos de informe de auditoría de Active Directory de Azure](https://go.microsoft.com/fwlink/p/?LinkID=616549).<br/> |
  
### <a name="azure-ad-group-administration-activities"></a>Actividades de administración de grupo de Azure AD
  
En la siguiente tabla se enumera las actividades de administración de grupo que se registran cuando un administrador o un usuario crea o cambia un grupo de Office 365 o cuando un administrador crea un grupo de seguridad mediante el centro de administración de Office 365 o el portal de administración de Azure. Para obtener más información acerca de los grupos en Office 365, vea [Ver, crear y eliminar grupos en el centro de administración de Office 365](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7).
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Se ha agregado un grupo  <br/> |Agregar grupo  <br/> |Ha creado un grupo.  <br/> |
|Se ha agregado un miembro al grupo  <br/> |Agregar a miembros al grupo  <br/> |Se ha agregado un miembro a un grupo.  <br/> |
|Grupo eliminado  <br/> |Eliminar grupo  <br/> |Se eliminó un grupo.  <br/> |
|Se ha quitado miembro de grupo  <br/> |Quitar a miembros de grupo  <br/> |Se ha quitado un miembro de un grupo.  <br/> |
|Grupo actualizado  <br/> |Grupo de actualización  <br/> |Se ha cambiado una propiedad de un grupo.  <br/> |
   
### <a name="application-administration-activities"></a>Actividades de administración de aplicaciones
  
En la siguiente tabla se enumera las actividades de administración de aplicaciones que se registran cuando un administrador agrega o cambia una aplicación que está registrada en Azure AD. Cualquier aplicación que se basa en Azure AD para la autenticación se debe registrar en el directorio.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Entrada de delegación se ha agregado  <br/> |Agregar entrada de delegación  <br/> |Un permiso de autenticación fue creado/concedidos a una aplicación en Azure AD.  <br/> |
|Se ha agregado un servicio principal  <br/> |Agregar la entidad de seguridad de servicio  <br/> |Una aplicación se ha registrado en Azure AD. Una aplicación está representada por una entidad de seguridad de servicio en el directorio.  <br/> |
|Credenciales se ha agregado a una entidad de seguridad de servicio  <br/> |Agregar credenciales del servicio de entidad de seguridad  <br/> |Las credenciales se han agregado a un servicio de entidad de seguridad en Azure AD. Un principio de servicio representa una aplicación en el directorio.  <br/> |
|Entrada de delegación se han quitado  <br/> |Quitar entrada de delegación  <br/> |Se ha quitado un permiso de autenticación desde una aplicación en Azure AD.  <br/> |
|Quita una entidad de seguridad del servicio del directorio  <br/> |Quitar entidad de seguridad de servicio  <br/> |Una aplicación fue eliminado o elimina del registro de Azure AD. Una aplicación está representada por una entidad de seguridad de servicio en el directorio.  <br/> |
|Se han quitado las credenciales de una entidad de seguridad de servicio  <br/> |Quitar las credenciales del servicio de entidad de seguridad  <br/> |Se han eliminado las credenciales de un servicio de entidad de seguridad en Azure AD. Un principio de servicio representa una aplicación en el directorio.  <br/> |
|Entrada de conjunto de delegación  <br/> |Entrada de conjunto de delegación  <br/> |Se ha actualizado un permiso de autenticación para una aplicación en Azure AD.  <br/> |

### <a name="role-administration-activities"></a>Actividades de administración de roles
  
En la siguiente tabla se enumera las actividades de administración de roles Azure AD que se registran cuando un administrador que administra los roles de administrador en el centro de administración de Office 365 o en el portal de administración de Azure.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Agregar a miembro a función  <br/> |Agregar a miembro de la función a función  <br/> |Agrega un usuario a un rol de administración de Office 365.  <br/> |
|Quita un usuario de una función de Active directory  <br/> |Quitar a miembro de la función de función  <br/> |Quitar a un usuario de una función de administración de Office 365.  <br/> |
|Establecer información de contacto de la compañía  <br/> |Establecer información de contacto de la compañía  <br/> |Se ha actualizado las preferencias de contacto de nivel de empresa para su organización de Office 365. Esto incluye las direcciones de correo electrónico para relacionadas con la suscripción el correo electrónico enviado por Office 365, así como las notificaciones de técnicas acerca de los servicios de Office 365.  <br/> |
   
### <a name="directory-administration-activities"></a>Actividades de administración de Active Directory
  
La siguiente tabla se recogen AD Azure Active directory y dominio relacionadas con las actividades que se registran cuando un administrador administra su organización de Office 365 en el centro de administración de Office 365 o en el portal de administración de Azure.
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Se ha agregado un dominio a la compañía  <br/> |Agregar dominio a la compañía  <br/> |Agregar un dominio a su organización de Office 365.  <br/> |
|Agrega a un socio en el directorio  <br/> |Adición de un socio a la compañía  <br/> |Agrega a un socio (administrador delegado) a la organización de Office 365.  <br/> |
|Dominio se ha quitado de la empresa  <br/> |Quitar el dominio de la empresa  <br/> |Quita un dominio de la organización de Office 365.  <br/> |
|Quita a un socio del directorio  <br/> |Quitar el socio de empresa  <br/> |Quita a un socio (administrador delegado) de la organización de Office 365.  <br/> |
|Conjunto de información de la compañía  <br/> |Conjunto de información de la compañía  <br/> |Se actualizó la información de la compañía para la organización de Office 365. Esto incluye las direcciones de correo electrónico para relacionadas con la suscripción el correo electrónico enviado por Office 365, así como las notificaciones de técnicas acerca de los servicios de Office 365.  <br/> |
|Configurar la autenticación de dominio  <br/> |Configurar la autenticación de dominio  <br/> |Puede cambiar la configuración de autenticación de dominio para la organización de Office 365.  <br/> |
|Se actualizó la configuración de federación para un dominio  <br/> |Establecer configuración de federación en dominio  <br/> |Puede cambiar la configuración de federación (compartir externo) para la organización de Office 365.  <br/> |
|Directiva de contraseñas de conjunto  <br/> |Directiva de contraseñas de conjunto  <br/> |Puede cambiar las restricciones de carácter y longitud de las contraseñas de usuario en la organización de Office 365.  <br/> |
|Activa la sincronización de Azure AD  <br/> |Establecer marca de DirSyncEnabled en la empresa  <br/> |Establezca la propiedad que permite a un directorio para la sincronización de AD de Azure.  <br/> |
|Dominio actualizado  <br/> |Actualizar dominio  <br/> |Se actualizó la configuración de un dominio de la organización de Office 365.  <br/> |
|Dominio comprobado  <br/> |Comprobar el dominio  <br/> |Comprobar que la organización es el propietario de un dominio.  <br/> |
|Dominio de correo electrónico comprobada verificado  <br/> |Comprobar el dominio verificado de correo electrónico  <br/> |Comprobación de correo electrónico se usa para comprobar que la organización es el propietario de un dominio.  <br/> |
   
### <a name="ediscovery-activities"></a>actividades de exhibición de documentos electrónicos
  
Contenido de búsqueda y las actividades relacionadas con la exhibición de documentos electrónicos que se realizan en Office 365 seguridad &amp; centro de cumplimiento o mediante la ejecución de la correspondiente Windows PowerShell cmdlets se registran en el registro de auditoría de Office 365. Esto incluye las siguientes actividades:
  
- Creación y administración de casos de exhibición de documentos electrónicos
    
- Crear, iniciar y edición de las búsquedas de contenido
    
- Realizar acciones de búsqueda de contenido, como obtener una vista previa, los resultados de búsqueda de exportación y al eliminar
    
- Configuración de permisos de filtrado para la búsqueda de contenido
    
- Administración de la función de administrador de exhibición de documentos electrónicos
    
Para una lista y una descripción detallada de las actividades de exhibición de documentos electrónicos que se registran, consulte [Buscar actividades de exhibición de documentos electrónicos en Office 365 registro de auditoría](search-for-ediscovery-activities-in-the-audit-log.md).
  
> [!NOTE]
> Se tardan hasta 30 minutos para los eventos que resultan de las actividades enumeradas en **las actividades de exhibición de documentos electrónicos** en la lista desplegable de **actividades** que se mostrará en los resultados de búsqueda. Por el contrario, se tardan hasta 24 horas para los eventos correspondientes de exhibición de documentos electrónicos actividades de cmdlet que aparezca en los resultados de búsqueda. 
  
### <a name="power-bi-activities"></a>Actividades de Power BI
  
En la siguiente tabla se enumera usuarios y las actividades de administración en Power BI que se registran en el registro de auditoría de Office 365.
  
 **Importante:** Registro de auditoría de Power BI no está habilitado de forma predeterminada. Para buscar actividades de Power BI en el registro de auditoría de Office 365, se debe habilitar la auditoría en el portal de administración de Power BI. Para obtener instrucciones, vea [Auditoría Power BI](https://docs.microsoft.com/power-bi/service-admin-auditing#enabling-auditing-functionality-in-the-power-bi-admin-portal).
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Se ha agregado los miembros del grupo de Power BI  <br/> |AddGroupMembers  <br/> |Se agrega un miembro a un área de trabajo de grupo de Power BI.  <br/> |
|Conjunto de datos de Power BI analizado  <br/> |AnalyzedByExternalApplication  <br/> |Un conjunto de datos se analiza por una aplicación externa.  <br/> |
|Panel de Power BI creado  <br/> |CreateDashboard  <br/> |Se crea un nuevo panel.  <br/> |
|Grupo de Power BI creado  <br/> |CreateGroup  <br/> |Se crea un grupo.  <br/> |
|Crear paquete de contenido de Power BI organizativa  <br/> |CreateOrgApp  <br/> |Se crea un paquete de contenido de organización.  <br/> |
|Panel de Power BI eliminado  <br/> |DeleteDashboard  <br/> |Se elimina un panel.  <br/> |
|Conjunto de datos de Power BI eliminado  <br/> |DeleteDataset  <br/> |Se elimina un conjunto de datos.  <br/> |
|Informe de Power BI eliminados  <br/> |DeleteReport  <br/> |Se elimina un informe.  <br/> |
|Informe de Power BI descargado  <br/> |DownloadReport  <br/> |Un usuario descarga un informe de Power BI desde el servicio en su equipo.  <br/> |
|Panel de Power BI editado  <br/> |Editar panel  <br/> |Cambiar el nombre de un panel.  <br/> |
|Datos de informe visual Power BI exportados  <br/> |ExportReport  <br/> |Se exportan los datos de un mosaico de informe.  <br/> |
|Datos exportados de mosaico de Power BI  <br/> |ExportTile  <br/> |Se exportan los datos desde un icono de panel.  <br/> |
|Panel de Power BI impresa  <br/> |PrintDashboard  <br/> |Se imprime un panel.  <br/> |
|Página de informe de Power BI impresa  <br/> |PrintReport  <br/> |Se imprime un informe.  <br/> |
|Publicar el informe de Power BI en web  <br/> |PublishToWebReport  <br/> |Un informe se publica en el web.  <br/> |
|Panel de Power BI compartida  <br/> |ShareDashboard  <br/> |Se comparte un panel.  <br/> |
|Versión de evaluación de Power BI iniciado  <br/> |OptInForProTrial  <br/> |Un usuario inicia una suscripción de prueba Power BI Pro.  <br/> |
|Configuración de la organización actualizados de Power BI  <br/> |UpdatedAdminFeatureSwitch  <br/> |Un administrador ha cambiado un valor de organización en el portal de administración de Power BI.  <br/> |
|Panel de Power BI visualizado  <br/> |ViewDashboard  <br/> |Se ve un panel.  <br/> |
|Informe de Power BI visualizado  <br/> |ViewReport  <br/> |Se ve un informe.  <br/> |
  
### <a name="microsoft-teams-activities"></a>Actividades de Microsoft Teams
  
En la siguiente tabla se enumera el usuario y el registro de auditoría de las actividades de administración en Microsoft Teams que se registran en Office 365. Microsoft Teams es un área de trabajo centrado en el chat en Office 365. Reúne las conversaciones, reuniones, archivos y notas de un equipo en un solo lugar. Para que obtener más información y vínculos a temas de ayuda, vea:
  
- [Preguntas más frecuentes sobre Microsoft Teams - ayuda de administración](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Ayuda de Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Se ha agregado un bot al equipo  <br/> |BotAddedToTeam  <br/> |Un usuario agrega un componente a un equipo.  <br/> |
|Se ha agregado un canal  <br/> |ChannelAdded  <br/> |Un usuario agrega un canal a un equipo.  <br/> |
|Se ha agregado un conector  <br/> |ConnectorAdded  <br/> |Un usuario agrega un conector a un canal.  <br/> |
|Se ha agregado los miembros del equipo  <br/> |MemberAdded  <br/> |El propietario de un equipo agrega miembros a un equipo.  <br/> |
|Ficha agregada  <br/> |TabAdded  <br/> |Un usuario agrega una ficha a un canal.  <br/> |
|Cambiar la configuración de canal  <br/> |ChannelSettingChanged  <br/> | La operación de ChannelSettingChanged se registra cuando se llevan a cabo las siguientes actividades por un miembro del equipo. Para cada una de estas actividades, una descripción de la configuración que se ha cambiado (que se muestra entre paréntesis que aparece a continuación) se muestra en la columna de **elemento** en los resultados de búsqueda de registro de auditoría.<br/> <br/>-Cambia el nombre de un canal de equipo ( **nombre del canal**).  <br/>  <br/>-Cambia la descripción de un canal de equipo ( **Descripción del canal**).  <br/> |
|Cambiar la configuración de la organización  <br/> |TeamsTenantSettingChanged  <br/> | La operación de TeamsTenantSettingChanged se registra cuando se llevan a cabo las siguientes actividades por un administrador global (mediante el centro de administración de Office 365); Tenga en cuenta que estas actividades afectan a la configuración de Microsoft Teams de toda la organización. Para obtener más información, vea [configuración de administrador de equipos de Microsoft](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2).<br/>  Para cada una de estas actividades, una descripción de la configuración que se ha cambiado (que se muestra entre paréntesis que aparece a continuación) se muestra en la columna de **elemento** en los resultados de búsqueda de registro de auditoría.  <br/><br/>-Habilita o deshabilita Microsoft Teams para la organización ( **Equipos de Microsoft**).  <br/><br/>-Habilita o deshabilita la interoperabilidad entre Microsoft Teams y Skype para la empresa para la organización ( **Skype para la interoperabilidad de negocio**).<br/><br/>-Habilita o deshabilita la vista Gráfico de la organización en los clientes de Microsoft Teams ( **Org vista del gráfico**).  <br/><br/>-Habilita o deshabilita la capacidad de los miembros del equipo programar reuniones privadas ( **Programar reunión privada**).  <br/><br/>-Habilita o deshabilita la capacidad de los miembros del equipo programar reuniones de canal ( **programación de reuniones de canal**).  <br/><br/>-Habilita o deshabilita el vídeo de llamada en los equipos de las reuniones ( **vídeo para las reuniones de Skype**).  <br/><br/>-Habilita o deshabilita el uso compartido en Microsoft Teams meetups para la organización ( **uso compartido de pantalla para las reuniones de Skype**) de pantalla.  <br/><br/>-Habilita o deshabilita la capacidad de agregar imágenes animadas (denominadas Giphys) a las conversaciones de los equipos ( **animado imágenes**).  <br/><br/>-Cambia la configuración para la organización ( **clasificación de contenido**) de clasificación de contenido. La clasificación del contenido restringe el tipo de imagen animada que se puede mostrar en las conversaciones.<br/><br/>-Habilita o deshabilita la posibilidad de que los integrantes del grupo agregar imágenes personalizables (denominadas memes personalizados) desde Internet a las conversaciones de equipo ( **personalizables imágenes desde Internet**).  <br/><br/>-Habilita o deshabilita la posibilidad de que los integrantes del grupo agregar imágenes modificables (denominadas pegatinas) a las conversaciones de equipo ( **modificables imágenes**).<br/><br/>-Habilita o deshabilita la capacidad de los miembros del equipo usar bots en Microsoft Teams chats y canales ( **bots de toda la organización**).<br/><br/>-Permite bots específicos para Microsoft Teams; Esto no incluye el robot T, que es el componente de Ayuda de los equipos que está disponible cuando bots están habilitados para la organización ( **bots individuales**).  <br/><br/>-Habilita o deshabilita la posibilidad de agregar pestañas ( **extensiones o fichas**) o las extensiones de los integrantes del grupo.  <br/><br/>-Habilita o deshabilita la carga de lado de su propiedad Bots para Microsoft Teams ( **carga de lado de Bots**).  <br/><br/>-Habilita o deshabilita la capacidad de los usuarios enviar mensajes de correo electrónico a un canal de Microsoft Teams ( **correo electrónico de canal**).  <br/> |
|Función modificada de miembros de equipo  <br/> |MemberRoleChanged  <br/> |El propietario de un equipo cambie la función de miembros en un equipo. Los siguientes valores indican el tipo de función asignado al usuario.<br/><br/><br/> **1** - indica la función de propietario.<br/>**2** - indica la función de miembro. <br/>**3** - indica la función de invitado. <br/>La propiedad Members también incluye el nombre de la organización y dirección de correo electrónico del miembro.  <br/> |
|Cambiar la configuración de equipo  <br/> |TeamSettingChanged  <br/> | La operación de TeamSettingChanged se registra cuando se llevan a cabo las siguientes actividades por el propietario de un equipo. Para cada una de estas actividades, una descripción de la configuración que se ha cambiado (que se muestra entre paréntesis que aparece a continuación) se muestra en la columna de **elemento** en los resultados de búsqueda de registro de auditoría.<br/><br/>-Cambia el tipo de acceso de un equipo. Los equipos pueden establecer como privado o público ( **tipo de acceso de equipo**). Cuando un equipo es privado (valor predeterminado), los usuarios pueden acceder el equipo sólo por invitación. Cuando un equipo es público, es reconocible por cualquier usuario.<br/><br/>-Cambia la clasificación de la información de un equipo ( **clasificación de equipo**).  <br/>  Por ejemplo, datos de equipo se pueden clasificar como impacto en el negocio alta, el impacto de medianas empresas o bajo impacto empresarial.<br/><br/>-Cambia el nombre de un equipo ( **nombre de equipo**).  <br/><br/>-Cambia la descripción del equipo ( **Descripción del equipo**). <br/><br/>-Los cambios realizados en cualquiera de las configuraciones de equipo. El propietario de un equipo puede tener acceso a esta configuración en un cliente de los equipos bien un equipo, haciendo clic en **Administrar equipo**y, a continuación, haga clic en la ficha **configuración** . Para estas actividades, se muestra el nombre de la configuración que se ha cambiado en la columna de **elemento** en los resultados de búsqueda de registro de auditoría.<br/> |
|Equipo creado  <br/> |TeamCreated  <br/> |Un usuario crea un nuevo equipo.  <br/> |
|Canal eliminado  <br/> |ChannelDeleted  <br/> |Un usuario elimina un canal de un equipo.  <br/> |
|Equipo eliminado  <br/> |Eliminado del equipo  <br/> |El propietario de un equipo elimina un equipo.  <br/> |
|Se ha quitado bot de equipo  <br/> |BotRemovedFromTeam  <br/> |Un usuario quita un componente de un equipo.  <br/> |
|Se ha quitado de conector  <br/> |ConnectorRemoved  <br/> |Un usuario quita conector de un canal.  <br/> |
|Se han quitado los miembros del equipo de  <br/> |MemberRemoved  <br/> |El propietario de un equipo quita miembros de un equipo.  <br/> |
|Ficha se han quitado  <br/> |TabRemoved  <br/> |Un usuario quita una ficha de un canal.  <br/> |
|Versión actualizada del conector  <br/> |ConnectorUpdated  <br/> |Un usuario puede modificar un conector en un canal.  <br/> |
|Ficha actualizada  <br/> |TabUpdated  <br/> |Un usuario puede modificar una ficha en un canal.  <br/> |
|Usuario que ha iniciado sesión en los equipos  <br/> |TeamsSessionStarted  <br/> |Un usuario inicia sesión en un cliente de Microsoft Teams.  <br/> |

### <a name="yammer-activities"></a>Actividades de yammer
  
En la siguiente tabla se enumera el usuario y el registro de auditoría de las actividades de administración de Yammer que se registran en Office 365. Para devolver el registro de auditoría de actividades relacionadas con el Yammer de Office 365, tendrá que seleccionar **Mostrar los resultados de todas las actividades** en la lista de **actividades** . Utilice los cuadros intervalo de fechas y la lista de **usuarios** para restringir los resultados de búsqueda. 
  
|**Nombre descriptivo**|**Operation**|**Descripción**|
|:-----|:-----|:-----|
|Directiva de retención de datos que han cambiado  <br/> |SoftDeleteSettingsUpdated  <br/> |Administración comprobada actualiza la configuración de la directiva de retención de datos de red eliminar disco duro o eliminar suave. Sólo los administradores comprobados pueden realizar esta operación.  <br/> |
|Configuración de red modificada  <br/> |NetworkConfigurationUpdated  <br/> |Red o un administrador de comprobada cambia la configuración de la red Yammer. Esto incluye la configuración del intervalo de exportación de datos y la habilitación de chat.  <br/> |
|Configuración de perfiles de red modificadas  <br/> |ProcessProfileFields  <br/> |Red o un administrador de comprobada cambia la información que aparece en perfiles de usuario para la red de los usuarios de red.  <br/> |
|Cambiar el modo de contenido privado  <br/> |SupervisorAdminToggled  <br/> |Administración comprobada activa o desactiva la *El modo de contenido privado* . Este modo permite una vista de administración se expone en grupos privados y ver los mensajes privados entre los usuarios individuales (o grupos de usuarios). Sólo los administradores comprobados solo pueden realizar esta operación.<br/> |
|Configuración de seguridad modificado  <br/> |NetworkSecurityConfigurationUpdated  <br/> |Administración comprobada actualiza la configuración de seguridad de la red Yammer. Esto incluye la configuración de directivas de caducidad de contraseña y restricciones de direcciones IP. Sólo los administradores comprobados pueden realizar esta operación.  <br/> |
|Archivo creado  <br/> |FileCreated  <br/> |Usuario carga un archivo.  <br/> |
|Grupo creado  <br/> |GroupCreation  <br/> |Usuario crea un nuevo grupo.  <br/> |
|Grupo eliminado  <br/> |GroupDeletion  <br/> |Se elimina un grupo de Yammer.  <br/> |
|Mensaje eliminado  <br/> |MessageDeleted  <br/> |Usuario elimina un mensaje.  <br/> |
|Archivo descargado  <br/> |FileDownloaded  <br/> |Usuario descarga un archivo.  <br/> |
|Datos exportados  <br/> |DataExport  <br/> |Administración comprobada exporta datos de la red Yammer. Sólo los administradores comprobados pueden realizar esta operación.  <br/> |
|Archivo compartido  <br/> |FileShared  <br/> |Usuario comparte un archivo con otro usuario.  <br/> |
|Usuario de la red suspendido  <br/> |NetworkUserSuspended  <br/> |Suspende la red o un administrador de comprobada (desactivará) un usuario de Yammer.  <br/> |
|Usuario suspendido  <br/> |UserSuspension  <br/> |Cuenta de usuario se ha suspendido (desactivado).  <br/> |
|Descripción del archivo actualizado  <br/> |FileUpdateDescription  <br/> |Usuario cambia la descripción de un archivo.  <br/> |
|Nombre del archivo actualizado  <br/> |FileUpdateName  <br/> |Usuario cambia el nombre de un archivo.  <br/> |
|Archivo visualizado  <br/> |FileVisited  <br/> |Usuario ve un archivo.  <br/> |
   
### <a name="microsoft-flow"></a>Microsoft Flow

Puede buscar el registro de auditoría para actividades in Microsoft Flow. Estas actividades incluyen la creación, edición y eliminación de flujos y cambiar los permisos de flujo. Para obtener información acerca de la auditoría para actividades de flujo de, consulte el blog del [Flujo de Microsoft de auditoría de eventos ahora está disponibles en el centro de cumplimiento y seguridad de Office 365](https://flow.microsoft.com/blog/security-and-compliance-center).


### <a name="microsoft-stream"></a>Microsoft Stream
  
Puede buscar el registro de auditoría para actividades en Microsoft Stream. Estas actividades incluyen actividades vídeo realizadas por los usuarios, las actividades de canal de grupo y las actividades de administración como administración de usuarios, administración de la configuración de la organización y exportación de informes. Para obtener una descripción de estas actividades, vea la sección "Registran las actividades en Microsoft Stream" en [Los registros de auditoría en secuencia de Microsoft](https://docs.microsoft.com/stream/audit-logs).
  
### <a name="exchange-admin-audit-log"></a>Registro de auditoría de administración de Exchange
  
Registro de auditoría de administrador de Exchange, que está habilitada de forma predeterminada en Office 365: registra un evento en el registro de auditoría de Office 365 cuando un administrador (o un usuario que se ha asignado permisos administrativos) realiza un cambio en la organización de Exchange Online. Los cambios realizados mediante el centro de administración de Exchange o mediante la ejecución de un cmdlet de Windows PowerShell se registran en el registro de auditoría de administración de Exchange. Para obtener información más detallada acerca de la administración de auditoría de registros en Exchange, vea [el registro de auditoría del administrador](https://go.microsoft.com/fwlink/p/?LinkID=619225).
  
Estas son algunas sugerencias para la búsqueda de actividad en el registro de auditoría de administración de Exchange:
  
- Para devolver las entradas desde el registro de auditoría de administración de Exchange, se debe seleccionar **Mostrar los resultados de todas las actividades** en la lista de **actividades** . Utilice los cuadros intervalo de fechas y la lista de **usuarios** para restringir los resultados de búsqueda para los cmdlets ejecutados por un administrador de Exchange específico dentro de un intervalo de fechas específico. 
    
- Para mostrar eventos desde el registro de auditoría de administración de Exchange, filtrar los resultados de la búsqueda y el tipo de un **-** (guión) en el cuadro de filtro de **actividad** . Esto mostrará los nombres de cmdlet, que se muestran en la columna de la **actividad** de eventos de administración de Exchange. A continuación, puede ordenar los nombres de cmdlet en orden alfabético. 
    
    ![Escriba un guión en el cuadro de actividades a filtrar los eventos de administración de Exchange](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- Para obtener información acerca de qué cmdlet se ejecutó, se usaron los parámetros y los valores de parámetro y qué objetos afectados, debe exportar los resultados de búsqueda y seleccione la opción de **Descargar todos los resultados** . 
    
- También puede ver eventos en el registro de auditoría de administración de Exchange mediante el centro de administración de Exchange. Para obtener instrucciones, vea [Ver el Administrador de registro de auditoría](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx).
  
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Dónde puedo encontrar acerca de las características que ofrece el servicio de auditoría en Office 365?**

Para obtener más información acerca de las características de auditoría y creación de informes disponibles en Office 365, vea [auditoría e informes en Office 365](office-365-auditing-and-reporting-overview.md). 

**¿Cuáles son los distintos servicios de Office 365 que actualmente se auditan?**

Los servicios de Office 365 más usados, como Exchange Online, SharePoint, OneDrive, Azure Active Directory, Microsoft Teams, CRM, protección avanzada de amenaza y prevención de pérdida de datos que se auditan. Vea la sección de [Introducción](#search-the-audit-log-in-the-office-365-security-amp-compliance-center) de este artículo para obtener una lista completa.

**¿Qué actividades se auditan mediante la auditoría de servicio en Office 365?**

Vea la sección [actividades auditada](#audited-activities) en este artículo para una lista y una descripción de las actividades que se auditan en Office 365.

**¿Cuánto tiempo tarda para que un registro de auditoría a estar disponible después de que se ha producido un evento?**

La mayoría de datos de auditoría están disponibles dentro de 30 minutos, pero puede tardar hasta 24 horas después de que se produce un evento de la entrada de registro de auditoría correspondientes que se mostrará en los resultados de búsqueda. Vea la tabla en la sección [antes de empezar](#before-you-begin) de este artículo que se muestra el tiempo que tarda eventos en los distintos servicios de Office 365 esté disponible.

**¿Durante cuánto tiempo se conservan los registros de auditoría para?**

Tal y como se ha explicado anteriormente, el período de retención para los registros de auditoría depende de suscripción de Office 365 de su organización.  

- **Office 365 E3** - auditoría registros se conservan durante 90 días.

- **Office 365 E5** - auditoría se retienen los registros de 365 días (un año). Conservar registros de auditoría para un año también está disponible para las organizaciones que tienen una suscripción E3 y una suscripción de complemento de Office 365 avanzada cumplimiento.

     > [!NOTE]
     > El período de retención de un año para los registros de auditoría actualmente sólo está disponible para las organizaciones que están inscritos en el programa de vista previa de Office 365.

**¿Tener acceso a los datos de auditoría mediante programación?**

Sí. La API de actividad de administración de Office 365 se usa para recuperar los registros de auditoría mediante programación.  Para empezar, vea [Introducción a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**¿Hay otras maneras de obtener auditoría de registros que no sean suing la seguridad de Office 365 & Centro de cumplimiento o la API de actividad de administración de Office 365?**

No. Estos son las sólo dos maneras de obtener datos desde el servicio de auditoría de Office 365. 

**¿Es necesario habilitar individualmente la auditoría en cada servicio que va a capturar los registros de auditoría para?**

En la mayoría de los servicios de Office 365, la auditoría está habilitada de forma predeterminada después de activar inicialmente de auditoría para la organización de Office 365 (tal como se describe en la sección [antes de comenzar](#before-you-begin) en este artículo). Sin embargo, se debe habilitar la auditoría en Exchange Online para cada buzón de correo que se va a auditar el buzón de correo.   Estamos trabajando en habilitar la auditoría de buzón de correo de forma predeterminada para todos los buzones en una organización de Office 365. Para obtener más información, consulte "auditoría de buzón de correo de Exchange estará habilitada de forma predeterminada" en el [blog de seguridad de Microsoft, privacidad y cumplimiento de normas](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Exchange-Mailbox-Auditing-will-be-enabled-by-default/ba-p/215171).

**¿La compatibilidad de servicio de auditoría de Office 365 la desduplicación de registros?**

No. La canalización del servicio de auditoría es casi en tiempo real y, por lo tanto, no es compatible con la desduplicación.
 
**¿Flujo de datos de auditoría de Office 365 en todo el mundo?**

No. Actualmente disponemos de auditoría de las implementaciones de canalización en NA (Norteamérica), EMEA (Europa, Oriente medio y África) y regiones APAC (Asia Pacífico). Sin embargo, nos podremos flujo de los datos entre estas regiones para equilibrio de carga y sólo durante los problemas del sitio de Live Meeting. Cuando se lleva a cabo estas actividades, se cifran los datos en tránsito.   
 
**¿Es la auditoría datos cifrados?**

Auditoría de datos se almacena en los buzones de Exchange (datos en reposo) en la misma región donde se implementa la canalización de auditoría. Estos datos no se cifran. Sin embargo, siempre se cifran los datos en tránsito. 













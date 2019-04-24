---
title: RGPD para SharePoint Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos del RGPD en un entorno local de SharePoint Server.
ms.openlocfilehash: 84692799222be595d69f7a33a31b0ec3fe767c3d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253898"
---
# <a name="gdpr-for-sharepoint-server"></a>RGPD para SharePoint Server

Como parte de la protección de información personal, le recomendamos lo siguiente:

-   Clasifique sus datos con Azure Information Protection.

-   Ejecute SharePoint Server con una configuración de privilegios mínimos. Para obtener más información, vea [Planear la administración de privilegios mínimos en SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) y [Seguridad para SharePoint Server](https://docs.microsoft.com/es-ES/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).

-   [Habilite el cifrado de BitLocker en sus servidores](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).

## <a name="user-generated-content"></a>Contenido generado por el usuario

El método recomendado básico para contenido generado por usuarios contenido en bibliotecas y sitios de SharePoint Server es este:

-   Use Azure Information Protection para etiquetar la información confidencial.

-   Use la [búsqueda de SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) e [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) para recuperar información confidencial.

El método recomendado para recursos compartidos de archivos y bibliotecas y sitios de SharePoint está compuesto por estos pasos:

1.  **[Instale y configure el escáner de Azure Information Protection.](https://docs.microsoft.com/es-ES/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**

    -   Decida qué tipos de información confidencial quiere usar.

    -   Especifique qué sitios de SharePoint quiere usar.

2.  **Complete un ciclo de detección.**

    -   Ejecute el escáner en el modo de detección y valide los resultados.

    -   Si es necesario, optimice las condiciones y los tipos de información confidencial.

    -   Evalúe el impacto esperado de aplicar etiquetas automáticamente.

3.  **Ejecute el analizador de Azure Information Protection para aplicar etiquetas a los documentos necesarios**.

4.  **Para obtener protección:**

    a. Configure las reglas de prevención de pérdida de datos de Exchange para proteger los documentos con la etiqueta que prefiera.

    b. Asegúrese de usar permisos para limitar quién puede obtener acceso a los archivos.

    c. Para SharePoint, use la protección de IRM para bibliotecas.

5.  **Para supervisar, integre los registros de Windows Server con una herramienta SIEM.**

    a. Para buscar datos personales de solicitudes del titular de los datos, use el Centro de búsqueda o eDiscovery.

Al aplicar etiquetas a información confidencial, asegúrese de usar una etiqueta no configurada con protección. En la protección, se incluye el cifrado, que impide que los servicios puedan detectar información confidencial en los archivos.

Para obtener más información sobre cómo usar el escáner de Azure Information Protection para buscar y etiquetar datos personales, vea el [Kit de herramientas de detección de datos de RGPD de Microsoft](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).

Para obtener información sobre cómo configurar el escáner para buscar condiciones y usar los tipos de información confidencial de prevención de pérdida de datos (DLP) de Office 365, vea [Configurar las condiciones para la clasificación automática y recomendada en Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Tenga en cuenta que los nuevos tipos de información confidencial de Office 365 no estarán disponibles inmediatamente para su uso con el escáner y que los tipos de información confidencial personalizados no pueden usarse con el escáner.

## <a name="removing-personal-information-from-office-files"></a>Quitar información personal de archivos de Office

El proceso para quitar información personal (como metadatos o comentarios en un documento de Word) de archivos de Office almacenados en una biblioteca de documentos de SharePoint tiene que realizarse de forma manual. Siga estos pasos:

1.  Descargue una copia del documento desde SharePoint Server en el disco local.

2.  Elimine el documento de la biblioteca de documentos de SharePoint.

3.  Siga los pasos que se indican en [Quitar datos ocultos e información personal al inspeccionar documentos](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).

4.  Vuelva a cargar el documento en la biblioteca de documentos de SharePoint.

## <a name="telemetry-and-log-files"></a>Telemetría y archivos de registro

### <a name="uls-logs"></a>Registros de ULS

El Servicio de registro unificado (ULS) y el Registro de uso en SharePoint Server realizan un seguimiento de una amplia variedad de funciones del sistema y pueden contener información de usuario. Los registros de ULS y los registros de uso son archivos de texto y permiten realizar búsquedas con distintas herramientas de búsqueda. El [cmdlet de PowerShell Merge-SPLogFile](https://docs.microsoft.com/es-ES/powershell/module/sharepoint-server/merge-splogfile) proporciona un método para devolver entradas de registro desde los registros de ULS en varios servidores de una granja de servidores.

Puede configurar las directivas de retención de registros con el valor mínimo necesario para sus fines empresariales. Para obtener información sobre cómo configurar el registro en SharePoint Server, vea [Configuración del registro de diagnóstico en SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

Tenga en cuenta que algunos eventos del sistema también se registran en el Registro de eventos de Windows.

### <a name="usage-database"></a>Base de datos de uso

La base de datos de uso de SharePoint Server (nombre predeterminado WSS_Logging) contiene un subconjunto de la información que se encuentra en los registros de ULS. El período máximo de retención de datos en esta base de datos es de 30 días. Le recomendamos que lo configure para la duración mínima permitida según sus necesidades empresariales. Para obtener más información, vea [Configurar el registro de diagnóstico en SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

## <a name="personal-information-and-search"></a>Información personal y búsqueda

El historial de consultas de búsqueda y los registros de uso contienen referencias a nombres de usuario.

### <a name="query-history-and-favorite-queries"></a>Historial de consultas y consultas favoritas

En SharePoint Server, los historiales de consultas y las consultas “favoritas” expiran automáticamente después de 365 días. Si un usuario abandona su organización, puede seguir los pasos siguientes para eliminar las referencias a un nombre de usuario del historial de consultas.

Las siguientes consultas SQL son válidas para SharePoint Server y permiten lo siguiente:

-   Exportar el historial de consultas o las consultas favoritas de un usuario

-   Quitar referencias a nombres de usuario en el historial de consultas

#### <a name="export-a-users-queries-since-a-specific-date"></a>Exportar las consultas de un usuario desde una fecha específica 

Siga este procedimiento para exportar las consultas desde las tablas del registro de consultas del Almacén de vínculos realizadas por @UserName desde @StartTime.

```sql
[In dbo].[LinkStore_<ID>]:
CREATE PROCEDURE proc_MSS_GetQueryTermsForUser 
( 
    @UserName nvarchar(256), 
    @StartTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT searchTime, queryString 
    FROM 
        dbo.MSSQLogPageImpressionQuery 
    WITH 
        (NOLOCK) 
    WHERE 
        userName = @UserName AND 
        searchTime > @StartTime 
END 
GO 
```

#### <a name="export-a-users-queries-from-the-past-100-days"></a>Exportar las consultas de un usuario de los últimos 100 días

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a>Exportar las consultas favoritas de un usuario

Siga este procedimiento para exportar las consultas favoritas de un usuario desde las tablas de resultados personales de la base de datos del administrador de búsquedas realizadas por @UserName desde <DateTime>.

```sql
In [dbo].[Search_<ID>]:
CREATE PROCEDURE proc_MSS_GetPersonalFavoriteQueries 
( 
    @UserName nvarchar(256), 
    @SearchTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT max(queries.SearchTime) as SearchTime, 
           max(queries.querystring) as queryString, 
           max(url.url) as URL 
    FROM MSSQLogOwner owners WITH(NOLOCK) 
    JOIN MSSQLogPersonalResults results WITH(NOLOCK) on owners.OwnerId = results.OwnerId 
    JOIN MSSQLogUrl url WITH(NOLOCK) on results.ClickedUrlId = url.urlId 
    JOIN MSSQLogPersonalQueries queries WITH(NOLOCK) on results.OwnerId = queries.OwnerId 
    WHERE queries.SearchTime > @SearchTime 
        AND queries.UserName = @UserName 
        GROUP BY queries.QueryString,url.url 
END 
GO 
```

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a>Exportar las consultas favoritas de un usuario de los últimos 100 días 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a>Quitar referencias a nombres de usuario que tengan más de X días

Siga este procedimiento para quitar referencias a *todos* los nombres de usuario que tengan más de @Days de las tablas del registro de consultas del Almacén de vínculos. El procedimiento solo quita referencias pasadas hasta que alcanza @LastCleanupTime.

```sql
In [dbo].[LinksStore_<ID>]:  
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a>Quitar referencias a un nombre de usuario específico que tenga más de X días

Siga este procedimiento para quitar las referencias a un nombre de usuario *específico* de las tablas del registro de consultas del almacén de vínculos, donde las referencias tienen más de @Days. El procedimiento solo quita referencias pasadas hasta que alcanza @LastCleanupTime.

```sql
In [dbo].[LinksStore_<ID>]:
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @UserName nvarchar(256),
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a>Quitar referencias a todos los nombres de usuario en el historial de consultas desde una fecha y hasta los 30 días anteriores

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a>Eliminar registros de uso

SharePoint Server elimina automáticamente registros de uso después de tres años. Puede eliminar de forma manual esos registros siguiendo este procedimiento:

Para eliminar todos los registros de uso asociados con los documentos eliminados: 

1.  Asegúrese de que tiene instalada la actualización de SharePoint más reciente. 

2.  Inicie un Shell de administración de SharePoint.

3.  Detenga y borre el último análisis realizado con Análisis de uso: 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  Espere hasta que vuelva a iniciarse el análisis (este proceso podría tardar hasta 24 horas). 

5.  La próxima vez que se ejecute el análisis, creará un volcado de todos los registros de la base de datos de informes de análisis. Este volcado completo puede tardar bastante tiempo en completarse para una base de datos de gran tamaño con muchas entradas.

6.  Espere 10 días. El análisis se ejecuta todos los días, los registros asociados con los documentos eliminados se quitarán después de ejecutarse diez veces. Esta ejecución puede tardar más tiempo del habitual si es necesario eliminar un gran número de registros. 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a>Información personal y búsqueda en SharePoint Server 2010

#### <a name="fast-search-server-2010-for-sharepoint"></a>FAST Search Server 2010 for SharePoint 

Además de almacenar archivos en el índice, el complemento FAST Search Server 2010 también almacena archivos en un formato intermedio denominado FIXML. Los archivos FIXML se compactan periódicamente (de forma predeterminada, entre las 3:00 y las 5:00 cada noche). La compactación quita automáticamente los archivos eliminados de los archivos FIXML. Para asegurarse de quitar de forma puntual la información que pertenece a los usuarios o documentos eliminados, asegúrese de que la compactación siempre esté habilitada.

### <a name="hybrid-search"></a>Búsqueda híbrida 

Las acciones recomendadas para las soluciones de búsqueda híbrida son las mismas que para la búsqueda en SharePoint Server o SharePoint Online. Hay dos soluciones de búsqueda híbrida:

**Solución de búsqueda híbrida en la nube**: con la solución de búsqueda híbrida la nube para SharePoint, indexará todo el contenido rastreado, incluido el contenido local, en el índice de búsqueda de Office 365. Cuando los usuarios consultan el índice de búsqueda de Office 365, obtienen resultados de la búsqueda tanto del contenido local como del contenido de Office 365. Al eliminar documentos del entorno de SharePoint Server, también se eliminan del índice de búsqueda en Office 365. [Obtenga más información sobre la solución de búsqueda híbrida en la nube](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) y [cómo interactúan los componentes de búsqueda y las bases de datos en la búsqueda híbrida en la nube](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) para comprender mejor cómo afecta el RGPD al entorno híbrido.

**Solución de búsqueda federada híbrida**: con la solución de búsqueda federada híbrida, usará tanto el índice de SharePoint Server como el índice de Office 365. Tanto los servicios de SharePoint Server como los servicios de búsqueda de SharePoint Online pueden consultar el índice de búsqueda del otro entorno y devolver resultados federados. Cuando los usuarios buscan desde un Centro de búsqueda, los resultados de la búsqueda provienen tanto del índice de búsqueda en SharePoint Server como del índice de búsqueda en Office 365. [Obtenga más información sobre la solución de búsqueda federada híbrida](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) para comprender mejor cómo afecta el RGPD al entorno híbrido.

## <a name="on-prem-to-cloud-migrations"></a>Migración de un entorno local a la nube

Al migrar datos desde SharePoint Server a SharePoint Online, pueden existir datos duplicados en dos ubicaciones durante un tiempo. Si tiene datos que es necesario eliminar y que se encuentran en mitad de una migración, le recomendamos que primero complete la migración y, después, elimine los datos de ambas ubicaciones. Puede consultar datos para exportarlos desde una ubicación.

## <a name="user-profile-data"></a>Datos de perfiles de usuario

El servicio de perfiles de usuario le permite importar datos de perfiles de una amplia variedad de orígenes externos. Las consultas y actualizaciones de esos datos de perfiles de usuario tienen que procesarse en los sistemas que contienen los datos maestros. Si realiza actualizaciones en el sistema externo, asegúrese de volver a sincronizar los perfiles de usuario en SharePoint Server.

Siga estos pasos básicos para quitar la información personal de un usuario de su perfil de usuario de SharePoint Server:

1.  Quite la información de usuario de cualquier sistema externo que inserte información en el perfil de usuario de SharePoint Server. Si usa la sincronización de directorios, es necesario quitar al usuario del entorno de Active Directory local.

2.  Ejecute una [sincronización de perfiles](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) en SharePoint Server.

3.  Elimine el perfil de SharePoint Server. Cuando complete esto, SharePoint Server eliminará por completo el perfil de la base de datos de perfiles de usuario en un plazo de 30 días. Se eliminarán el sitio personal y la página de perfil del usuario.

Después de eliminar un perfil de usuario, es posible que información limitada (como el identificador de usuario) aún quede registrada en las colecciones de sitios que visitó el usuario. Para eliminar estos datos de una colección de sitios específica, puede usar CSOM. Este es un script de ejemplo:

```powershell
$username = "<admin@company.sharepoint.com>"
$password = "password"
$url = "<https://site.sharepoint.com>"
$securePassword = ConvertTo-SecureString $Password -AsPlainText -Force

# the path here may need to change if you used e.g. C:Lib.
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.dll"
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.Runtime.dll"

# connect/authenticate to SharePoint Online and get ClientContext object.
$clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($username, $securePassword)
$clientContext.Credentials = $credentials
if (!$clientContext.ServerObjectIsNull.Value)
{
    Write-Host "Connected to SharePoint Online site: '$Url'" -ForegroundColor Green
}

# Get user
$user = $clientContext.Web.SiteUsers.GetByLoginName("i:0#.f|membership|user@company.sharepoint.com")

# Redact user
$user.Email = "Redacted"
$user.Title = "Redacted"
$user.Update()
$clientContext.Load($user)
$clientContext.ExecuteQuery()

# Get users
$users = $clientContext.Web.SiteUsers

# Remove user from site
$users.RemoveById($user.Id)
$clientContext.Load($users)
$clientContext.ExecuteQuery()
```

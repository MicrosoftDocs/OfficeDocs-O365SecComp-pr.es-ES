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
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221120"
---
# <a name="gdpr-for-sharepoint-server"></a><span data-ttu-id="98e22-103">RGPD para SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="98e22-103">GDPR for SharePoint Server</span></span>

<span data-ttu-id="98e22-104">Como parte de la protección de información personal, le recomendamos lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98e22-104">As part of safeguarding personal information, we recommend the following:</span></span>

-   <span data-ttu-id="98e22-105">Clasifique sus datos con Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="98e22-105">Classify your data, using Azure Information Protection.</span></span>

-   <span data-ttu-id="98e22-p101">Ejecute SharePoint Server con una configuración de privilegios mínimos. Para obtener más información, vea [Planear la administración de privilegios mínimos en SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) y [Seguridad para SharePoint Server](https://docs.microsoft.com/es-ES/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).</span><span class="sxs-lookup"><span data-stu-id="98e22-p101">Run SharePoint Server in a least-privileged configuration. See [Plan for least-privileged administration in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) and [Security for SharePoint Server](https://docs.microsoft.com/es-ES/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) for more information.</span></span>

-   <span data-ttu-id="98e22-108">[Habilite el cifrado de BitLocker en sus servidores](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="98e22-108">[Enable BitLocker encryption on your servers](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span></span>

## <a name="user-generated-content"></a><span data-ttu-id="98e22-109">Contenido generado por el usuario</span><span class="sxs-lookup"><span data-stu-id="98e22-109">User Generated content</span></span>

<span data-ttu-id="98e22-110">El método recomendado básico para contenido generado por usuarios contenido en bibliotecas y sitios de SharePoint Server es este:</span><span class="sxs-lookup"><span data-stu-id="98e22-110">The basic recommended approach for user generated content contained in SharePoint Server sites and libraries is:</span></span>

-   <span data-ttu-id="98e22-111">Use Azure Information Protection para etiquetar la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="98e22-111">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="98e22-112">Use la [búsqueda de SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) e [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) para recuperar información confidencial.</span><span class="sxs-lookup"><span data-stu-id="98e22-112">Use [SharePoint Server search](https://docs.microsoft.com/SharePoint/search/search) and [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) to retrieve sensitive data.</span></span>

<span data-ttu-id="98e22-113">El método recomendado para recursos compartidos de archivos y bibliotecas y sitios de SharePoint está compuesto por estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98e22-113">The recommended approach for files shares and SharePoint sites and libraries includes these steps:</span></span>

1.  <span data-ttu-id="98e22-114">**[Instale y configure el escáner de Azure Information Protection.](https://docs.microsoft.com/es-ES/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span><span class="sxs-lookup"><span data-stu-id="98e22-114">**[Install and configure Azure Information Protection scanner.](https://docs.microsoft.com/es-ES/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span></span>

    -   <span data-ttu-id="98e22-115">Decida qué tipos de información confidencial quiere usar.</span><span class="sxs-lookup"><span data-stu-id="98e22-115">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="98e22-116">Especifique qué sitios de SharePoint quiere usar.</span><span class="sxs-lookup"><span data-stu-id="98e22-116">Specify which SharePoint sites to use.</span></span>

2.  <span data-ttu-id="98e22-117">**Complete un ciclo de detección.**</span><span class="sxs-lookup"><span data-stu-id="98e22-117">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="98e22-118">Ejecute el escáner en el modo de detección y valide los resultados.</span><span class="sxs-lookup"><span data-stu-id="98e22-118">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="98e22-119">Si es necesario, optimice las condiciones y los tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="98e22-119">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="98e22-120">Evalúe el impacto esperado de aplicar etiquetas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="98e22-120">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="98e22-121">**Ejecute el analizador de Azure Information Protection para aplicar etiquetas a los documentos necesarios**.</span><span class="sxs-lookup"><span data-stu-id="98e22-121">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="98e22-122">**Para obtener protección:**</span><span class="sxs-lookup"><span data-stu-id="98e22-122">**For protection:**</span></span>

    <span data-ttu-id="98e22-p102">a. Configure las reglas de prevención de pérdida de datos de Exchange para proteger los documentos con la etiqueta que prefiera.</span><span class="sxs-lookup"><span data-stu-id="98e22-p102">a.  Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    <span data-ttu-id="98e22-p103">b. Asegúrese de usar permisos para limitar quién puede obtener acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="98e22-p103">b.  Be sure permissions to limit who can access files.</span></span>

    <span data-ttu-id="98e22-p104">c. Para SharePoint, use la protección de IRM para bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="98e22-p104">c.  For SharePoint, use IRM-protection for libraries.</span></span>

5.  <span data-ttu-id="98e22-129">**Para supervisar, integre los registros de Windows Server con una herramienta SIEM.**</span><span class="sxs-lookup"><span data-stu-id="98e22-129">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    <span data-ttu-id="98e22-p105">a. Para buscar datos personales de solicitudes del titular de los datos, use el Centro de búsqueda o eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="98e22-p105">a.  To find personal data for data subject requests, use Search Center or eDiscovery.</span></span>

<span data-ttu-id="98e22-p106">Al aplicar etiquetas a información confidencial, asegúrese de usar una etiqueta no configurada con protección. En la protección, se incluye el cifrado, que impide que los servicios puedan detectar información confidencial en los archivos.</span><span class="sxs-lookup"><span data-stu-id="98e22-p106">When applying labels to sensitive data, be sure to use a label that is not configured with protection. Protection includes encryption which prevents services from detecting sensitive data in the files.</span></span>

<span data-ttu-id="98e22-134">Para obtener más información sobre cómo usar el escáner de Azure Information Protection para buscar y etiquetar datos personales, vea el [Kit de herramientas de detección de datos de RGPD de Microsoft](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).</span><span class="sxs-lookup"><span data-stu-id="98e22-134">For more information on using Azure Information Protection scanner to find and label personal data, see the [Microsoft GDPR Data Discovery Toolkit](http://aka.ms/gdprpartners) (http://aka.ms/gdprpartners).</span></span>

<span data-ttu-id="98e22-p107">Para obtener información sobre cómo configurar el escáner para buscar condiciones y usar los tipos de información confidencial de prevención de pérdida de datos (DLP) de Office 365, vea [Configurar las condiciones para la clasificación automática y recomendada en Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Tenga en cuenta que los nuevos tipos de información confidencial de Office 365 no estarán disponibles inmediatamente para su uso con el escáner y que los tipos de información confidencial personalizados no pueden usarse con el escáner.</span><span class="sxs-lookup"><span data-stu-id="98e22-p107">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>

## <a name="removing-personal-information-from-office-files"></a><span data-ttu-id="98e22-137">Quitar información personal de archivos de Office</span><span class="sxs-lookup"><span data-stu-id="98e22-137">Removing personal information from Office files</span></span>

<span data-ttu-id="98e22-p108">El proceso para quitar información personal (como metadatos o comentarios en un documento de Word) de archivos de Office almacenados en una biblioteca de documentos de SharePoint tiene que realizarse de forma manual. Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="98e22-p108">Removing personal information (such as metadata or comments in a Word document) from Office files that are stored in a SharePoint document library must be done manually. Follow these steps:</span></span>

1.  <span data-ttu-id="98e22-140">Descargue una copia del documento desde SharePoint Server en el disco local.</span><span class="sxs-lookup"><span data-stu-id="98e22-140">Download a copy of the document from SharePoint Server to your local disk.</span></span>

2.  <span data-ttu-id="98e22-141">Elimine el documento de la biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98e22-141">Delete the document from the SharePoint document library.</span></span>

3.  <span data-ttu-id="98e22-142">Siga los pasos que se indican en [Quitar datos ocultos e información personal al inspeccionar documentos](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span><span class="sxs-lookup"><span data-stu-id="98e22-142">Follow the steps in [Remove hidden data and personal information by inspecting documents](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span></span>

4.  <span data-ttu-id="98e22-143">Vuelva a cargar el documento en la biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98e22-143">Upload the document back to the SharePoint document library.</span></span>

## <a name="telemetry-and-log-files"></a><span data-ttu-id="98e22-144">Telemetría y archivos de registro</span><span class="sxs-lookup"><span data-stu-id="98e22-144">Telemetry and log files</span></span>

### <a name="uls-logs"></a><span data-ttu-id="98e22-145">Registros de ULS</span><span class="sxs-lookup"><span data-stu-id="98e22-145">ULS Logs</span></span>

<span data-ttu-id="98e22-p109">El Servicio de registro unificado (ULS) y el Registro de uso en SharePoint Server realizan un seguimiento de una amplia variedad de funciones del sistema y pueden contener información de usuario. Los registros de ULS y los registros de uso son archivos de texto y permiten realizar búsquedas con distintas herramientas de búsqueda. El [cmdlet de PowerShell Merge-SPLogFile](https://docs.microsoft.com/es-ES/powershell/module/sharepoint-server/merge-splogfile) proporciona un método para devolver entradas de registro desde los registros de ULS en varios servidores de una granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="98e22-p109">Unified Logging Service (ULS) and Usage logging in SharePoint Server track a variety of system functions and can contain user information. ULS logs and usage logs are text files and can be searched using a variety of searching tools. The [Merge-SPLogFile PowerShell cmdlet](https://docs.microsoft.com/es-ES/powershell/module/sharepoint-server/merge-splogfile) provides a way to return records from the ULS logs on multiple servers in a farm.</span></span>

<span data-ttu-id="98e22-p110">Puede configurar las directivas de retención de registros con el valor mínimo necesario para sus fines empresariales. Para obtener información sobre cómo configurar el registro en SharePoint Server, vea [Configuración del registro de diagnóstico en SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="98e22-p110">Consider setting log retention policies to the minimum value needed for your business purposes. For information about configuring logging in SharePoint Server, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

<span data-ttu-id="98e22-151">Tenga en cuenta que algunos eventos del sistema también se registran en el Registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="98e22-151">Note that some system events are also logged to the Windows Event Log.</span></span>

### <a name="usage-database"></a><span data-ttu-id="98e22-152">Base de datos de uso</span><span class="sxs-lookup"><span data-stu-id="98e22-152">Usage Database</span></span>

<span data-ttu-id="98e22-p111">La base de datos de uso de SharePoint Server (nombre predeterminado WSS_Logging) contiene un subconjunto de la información que se encuentra en los registros de ULS. El período máximo de retención de datos en esta base de datos es de 30 días. Le recomendamos que lo configure para la duración mínima permitida según sus necesidades empresariales. Para obtener más información, vea [Configurar el registro de diagnóstico en SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="98e22-p111">The SharePoint Server Usage database (default name WSS_Logging) contains a subset of the information found in the ULS logs. The maximum retention of data in this database is 30 days. We recommend that you configure it for the shortest duration allowable by your business needs. For more information, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

## <a name="personal-information-and-search"></a><span data-ttu-id="98e22-157">Información personal y búsqueda</span><span class="sxs-lookup"><span data-stu-id="98e22-157">Personal information and search</span></span>

<span data-ttu-id="98e22-158">El historial de consultas de búsqueda y los registros de uso contienen referencias a nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="98e22-158">The search query history and usage records contain references to user names.</span></span>

### <a name="query-history-and-favorite-queries"></a><span data-ttu-id="98e22-159">Historial de consultas y consultas favoritas</span><span class="sxs-lookup"><span data-stu-id="98e22-159">Query history and favorite queries</span></span>

<span data-ttu-id="98e22-p112">En SharePoint Server, los historiales de consultas y las consultas “favoritas” expiran automáticamente después de 365 días. Si un usuario abandona su organización, puede seguir los pasos siguientes para eliminar las referencias a un nombre de usuario del historial de consultas.</span><span class="sxs-lookup"><span data-stu-id="98e22-p112">In SharePoint Server, query histories and ‘favorite’ queries automatically expire after 365 days. If a user leaves your organization, it is possible to remove references to a user's name from the query history using the steps below.</span></span>

<span data-ttu-id="98e22-162">Las siguientes consultas SQL son válidas para SharePoint Server y permiten lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98e22-162">The following SQL queries apply to SharePoint Server and make it possible to:</span></span>

-   <span data-ttu-id="98e22-163">Exportar el historial de consultas o las consultas favoritas de un usuario</span><span class="sxs-lookup"><span data-stu-id="98e22-163">Export a user’s query history or favorite queries</span></span>

-   <span data-ttu-id="98e22-164">Quitar referencias a nombres de usuario en el historial de consultas</span><span class="sxs-lookup"><span data-stu-id="98e22-164">Remove references to user names in the query history</span></span>

#### <a name="export-a-users-queries-since-a-specific-date"></a><span data-ttu-id="98e22-165">Exportar las consultas de un usuario desde una fecha específica</span><span class="sxs-lookup"><span data-stu-id="98e22-165">Export a user’s queries since a specific date</span></span> 

<span data-ttu-id="98e22-166">Siga este procedimiento para exportar las consultas desde las tablas del registro de consultas del Almacén de vínculos realizadas por @UserName desde @StartTime.</span><span class="sxs-lookup"><span data-stu-id="98e22-166">Use the following procedure to export queries from the Link Store query log tables, performed by @UserName since @StartTime.</span></span>

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

#### <a name="export-a-users-queries-from-the-past-100-days"></a><span data-ttu-id="98e22-167">Exportar las consultas de un usuario de los últimos 100 días</span><span class="sxs-lookup"><span data-stu-id="98e22-167">Export a user’s queries from the past 100 days</span></span>

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a><span data-ttu-id="98e22-168">Exportar las consultas favoritas de un usuario</span><span class="sxs-lookup"><span data-stu-id="98e22-168">Export a user’s favorite queries</span></span>

<span data-ttu-id="98e22-169">Siga este procedimiento para exportar las consultas favoritas de un usuario desde las tablas de resultados personales de la base de datos del administrador de búsquedas realizadas por @UserName desde <DateTime>.</span><span class="sxs-lookup"><span data-stu-id="98e22-169">Use the following procedure to export a user's favorite queries from the Search Admin DB personal result tables, performed by @UserName, since <DateTime>.</span></span>

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

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a><span data-ttu-id="98e22-170">Exportar las consultas favoritas de un usuario de los últimos 100 días</span><span class="sxs-lookup"><span data-stu-id="98e22-170">Export a user’s favorite queries from the past 100 days</span></span> 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a><span data-ttu-id="98e22-171">Quitar referencias a nombres de usuario que tengan más de X días</span><span class="sxs-lookup"><span data-stu-id="98e22-171">Remove references to user names that are more than X days old</span></span>

<span data-ttu-id="98e22-p113">Siga este procedimiento para quitar referencias a *todos* los nombres de usuario que tengan más de @Days de las tablas del registro de consultas del Almacén de vínculos. El procedimiento solo quita referencias pasadas hasta que alcanza @LastCleanupTime.</span><span class="sxs-lookup"><span data-stu-id="98e22-p113">Use the following procedure to remove references to *all* user names that are more than @Days old, from the Links Store query log tables. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a><span data-ttu-id="98e22-174">Quitar referencias a un nombre de usuario específico que tenga más de X días</span><span class="sxs-lookup"><span data-stu-id="98e22-174">Remove references to a specific user name that’s more than X days old</span></span>

<span data-ttu-id="98e22-p114">Siga este procedimiento para quitar las referencias a un nombre de usuario *específico* de las tablas del registro de consultas del almacén de vínculos, donde las referencias tienen más de @Days. El procedimiento solo quita referencias pasadas hasta que alcanza @LastCleanupTime.</span><span class="sxs-lookup"><span data-stu-id="98e22-p114">Use the following procedure to remove references to a *specific* user name from the Links Store query log tables, where the references are more than @Days old. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a><span data-ttu-id="98e22-177">Quitar referencias a todos los nombres de usuario en el historial de consultas desde una fecha y hasta los 30 días anteriores</span><span class="sxs-lookup"><span data-stu-id="98e22-177">Remove references to all user names in the query history from a date and up to the past 30 days</span></span>

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a><span data-ttu-id="98e22-178">Eliminar registros de uso</span><span class="sxs-lookup"><span data-stu-id="98e22-178">Delete usage records</span></span>

<span data-ttu-id="98e22-p115">SharePoint Server elimina automáticamente registros de uso después de tres años. Puede eliminar de forma manual esos registros siguiendo este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="98e22-p115">SharePoint Server automatically deletes usage records after 3 years. You can manually delete such records using the procedure below:</span></span>

<span data-ttu-id="98e22-181">Para eliminar todos los registros de uso asociados con los documentos eliminados:</span><span class="sxs-lookup"><span data-stu-id="98e22-181">To delete all usage records associated with deleted documents:</span></span> 

1.  <span data-ttu-id="98e22-182">Asegúrese de que tiene instalada la actualización de SharePoint más reciente.</span><span class="sxs-lookup"><span data-stu-id="98e22-182">Ensure that you have the latest SharePoint update installed.</span></span> 

2.  <span data-ttu-id="98e22-183">Inicie un Shell de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98e22-183">Start a SharePoint Management shell.</span></span>

3.  <span data-ttu-id="98e22-184">Detenga y borre el último análisis realizado con Análisis de uso:</span><span class="sxs-lookup"><span data-stu-id="98e22-184">Stop and Clear the Usage Analytics analysis:</span></span> 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  <span data-ttu-id="98e22-185">Espere hasta que vuelva a iniciarse el análisis (este proceso podría tardar hasta 24 horas).</span><span class="sxs-lookup"><span data-stu-id="98e22-185">Wait for the analysis to start again (might take up to 24 hours).</span></span> 

5.  <span data-ttu-id="98e22-p116">La próxima vez que se ejecute el análisis, creará un volcado de todos los registros de la base de datos de informes de análisis. Este volcado completo puede tardar bastante tiempo en completarse para una base de datos de gran tamaño con muchas entradas.</span><span class="sxs-lookup"><span data-stu-id="98e22-p116">On the next run of the analysis, it will dump all records from the Analytics Reporting database. This full dump may take a while for a large database with many entries.</span></span>

6.  <span data-ttu-id="98e22-p117">Espere 10 días. El análisis se ejecuta todos los días, los registros asociados con los documentos eliminados se quitarán después de ejecutarse diez veces. Esta ejecución puede tardar más tiempo del habitual si es necesario eliminar un gran número de registros.</span><span class="sxs-lookup"><span data-stu-id="98e22-p117">Wait for 10 days. The analysis runs daily, and records associated with deleted documents will be removed after the 10^th^ run. This run may take longer than normal if many records need to be deleted.</span></span> 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a><span data-ttu-id="98e22-191">Información personal y búsqueda en SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="98e22-191">Personal information and search in SharePoint Server 2010</span></span>

#### <a name="fast-search-server-2010-for-sharepoint"></a><span data-ttu-id="98e22-192">FAST Search Server 2010 for SharePoint</span><span class="sxs-lookup"><span data-stu-id="98e22-192">FAST Search Server 2010 for SharePoint</span></span> 

<span data-ttu-id="98e22-p118">Además de almacenar archivos en el índice, el complemento FAST Search Server 2010 también almacena archivos en un formato intermedio denominado FIXML. Los archivos FIXML se compactan periódicamente (de forma predeterminada, entre las 3:00 y las 5:00 cada noche). La compactación quita automáticamente los archivos eliminados de los archivos FIXML. Para asegurarse de quitar de forma puntual la información que pertenece a los usuarios o documentos eliminados, asegúrese de que la compactación siempre esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="98e22-p118">In addition to storing files in the index, the FAST Search Server 2010 Add-On also stores files in an intermediate format called FixML. FiXML files are compacted regularly, by default between 3 am and 5 am every night. Compaction removes deleted files from the FiXML files automatically. To ensure timely removal of information belonging to deleted users or documents, ensure that compaction is always enabled.</span></span>

### <a name="hybrid-search"></a><span data-ttu-id="98e22-197">Búsqueda híbrida</span><span class="sxs-lookup"><span data-stu-id="98e22-197">Hybrid Search</span></span> 

<span data-ttu-id="98e22-p119">Las acciones recomendadas para las soluciones de búsqueda híbrida son las mismas que para la búsqueda en SharePoint Server o SharePoint Online. Hay dos soluciones de búsqueda híbrida:</span><span class="sxs-lookup"><span data-stu-id="98e22-p119">The recommended actions for hybrid search solutions are the same as for search in SharePoint Server or SharePoint Online. There are two hybrid search solutions:</span></span>

<span data-ttu-id="98e22-p120">**Solución de búsqueda híbrida en la nube**: con la solución de búsqueda híbrida la nube para SharePoint, indexará todo el contenido rastreado, incluido el contenido local, en el índice de búsqueda de Office 365. Cuando los usuarios consultan el índice de búsqueda de Office 365, obtienen resultados de la búsqueda tanto del contenido local como del contenido de Office 365. Al eliminar documentos del entorno de SharePoint Server, también se eliminan del índice de búsqueda en Office 365. [Obtenga más información sobre la solución de búsqueda híbrida en la nube](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) y [cómo interactúan los componentes de búsqueda y las bases de datos en la búsqueda híbrida en la nube](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) para comprender mejor cómo afecta el RGPD al entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="98e22-p120">**The cloud hybrid search solution -** With the cloud hybrid search solution for SharePoint, you index all your crawled content, including on-premises content, in your search index in Office 365. When users query your search index in Office 365, they get search results from both on-premises and Office 365 content. When documents are deleted from the SharePoint Server environment, they are also deleted from the search index in Office 365. [Read more about the cloud hybrid search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) and [how search components and databases interact in cloud hybrid search](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

<span data-ttu-id="98e22-p121">**Solución de búsqueda federada híbrida**: con la solución de búsqueda federada híbrida, usará tanto el índice de SharePoint Server como el índice de Office 365. Tanto los servicios de SharePoint Server como los servicios de búsqueda de SharePoint Online pueden consultar el índice de búsqueda del otro entorno y devolver resultados federados. Cuando los usuarios buscan desde un Centro de búsqueda, los resultados de la búsqueda provienen tanto del índice de búsqueda en SharePoint Server como del índice de búsqueda en Office 365. [Obtenga más información sobre la solución de búsqueda federada híbrida](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) para comprender mejor cómo afecta el RGPD al entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="98e22-p121">**The hybrid federated search solution -** With the hybrid federated search solution, you use both your index in SharePoint Server and your index in Office 365. Both SharePoint Server and SharePoint Online Search services can query the search index in the other environment and return federated results. When users search from a Search Center, the search results come from both your search index in SharePoint Server and your search index in Office 365. [Read more about the hybrid federated search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

## <a name="on-prem-to-cloud-migrations"></a><span data-ttu-id="98e22-208">Migración de un entorno local a la nube</span><span class="sxs-lookup"><span data-stu-id="98e22-208">On Prem to Cloud Migrations</span></span>

<span data-ttu-id="98e22-p122">Al migrar datos desde SharePoint Server a SharePoint Online, pueden existir datos duplicados en dos ubicaciones durante un tiempo. Si tiene datos que es necesario eliminar y que se encuentran en mitad de una migración, le recomendamos que primero complete la migración y, después, elimine los datos de ambas ubicaciones. Puede consultar datos para exportarlos desde una ubicación.</span><span class="sxs-lookup"><span data-stu-id="98e22-p122">While migrating data from SharePoint Server to SharePoint Online, duplicate data may exist in both locations for a time. If you have data that you need to delete that is in mid-migration, we recommend that you complete the migration first, and then delete the data from both locations. You can query data for export from either location.</span></span>

## <a name="user-profile-data"></a><span data-ttu-id="98e22-212">Datos de perfiles de usuario</span><span class="sxs-lookup"><span data-stu-id="98e22-212">User Profile data</span></span>

<span data-ttu-id="98e22-p123">El servicio de perfiles de usuario le permite importar datos de perfiles de una amplia variedad de orígenes externos. Las consultas y actualizaciones de esos datos de perfiles de usuario tienen que procesarse en los sistemas que contienen los datos maestros. Si realiza actualizaciones en el sistema externo, asegúrese de volver a sincronizar los perfiles de usuario en SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="98e22-p123">The User Profile Service allows for import of profile data from a variety of external sources. Queries for and update of such user profile data should be handled in the systems in which the data is mastered. If you make updates to the external system, be sure to synchronize the user profiles in SharePoint Server again.</span></span>

<span data-ttu-id="98e22-216">Siga estos pasos básicos para quitar la información personal de un usuario de su perfil de usuario de SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="98e22-216">Follow these basic steps to remove a user’s personal information from their SharePoint Server user profile:</span></span>

1.  <span data-ttu-id="98e22-p124">Quite la información de usuario de cualquier sistema externo que inserte información en el perfil de usuario de SharePoint Server. Si usa la sincronización de directorios, es necesario quitar al usuario del entorno de Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="98e22-p124">Remove the user information from any external systems that feed into the SharePoint Server user profile. If you are using directory synchronization, the user must be removed from the on-premises Active Directory environment.</span></span>

2.  <span data-ttu-id="98e22-219">Ejecute una [sincronización de perfiles](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) en SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="98e22-219">Run a [profile synchronization](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) on SharePoint Server.</span></span>

3.  <span data-ttu-id="98e22-p125">Elimine el perfil de SharePoint Server. Cuando complete esto, SharePoint Server eliminará por completo el perfil de la base de datos de perfiles de usuario en un plazo de 30 días. Se eliminarán el sitio personal y la página de perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="98e22-p125">Delete the profile from SharePoint Server. Once this is done, SharePoint Server will fully remove the profile from the User Profile Database in 30 days. The user’s profile page and personal site will be deleted.</span></span>

<span data-ttu-id="98e22-p126">Después de eliminar un perfil de usuario, es posible que información limitada (como el identificador de usuario) aún quede registrada en las colecciones de sitios que visitó el usuario. Para eliminar estos datos de una colección de sitios específica, puede usar CSOM. Este es un script de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="98e22-p126">After deleting a user’s profile, some limited information (such as user ID) may still be recorded in site collections that the user has visited. If you choose to delete this data from a given site collection, this can be done using CSOM. A sample script is provided below:</span></span>

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

---
title: Aumentar la velocidad de descarga al exportar resultados de búsqueda de exhibición de documentos electrónicos de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Aprenda a configurar el registro de Windows para aumentar el rendimiento de los datos al descargar los resultados de búsqueda y los datos de &amp; búsqueda del centro de seguridad y cumplimiento de Office 365 y eDiscovery avanzado.
ms.openlocfilehash: bafe9eda98b411472098770e4178748eb84f8afd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216250"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="1cfac-103">Aumentar la velocidad de descarga al exportar resultados de búsqueda de exhibición de documentos electrónicos de Office 365</span><span class="sxs-lookup"><span data-stu-id="1cfac-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="1cfac-p101">Cuando usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para descargar los resultados de una búsqueda de &amp; contenido en el centro de seguridad de cumplimiento de Office 365 o descargar datos desde Office 365 Advanced eDiscovery, la herramienta inicia un determinado número de exportaciones simultáneas. operaciones para descargar los datos en el equipo local. De forma predeterminada, el número de operaciones simultáneas se establece en 8 veces el número de núcleos en el equipo que está usando para descargar los datos. Por ejemplo, si tiene un equipo con dos núcleos (es decir, dos unidades de procesamiento central en un chip), el número predeterminado de operaciones de exportación simultáneas es 16. Para aumentar el rendimiento de la transferencia de datos y acelerar el proceso de descarga, puede aumentar el número de operaciones simultáneas configurando una configuración del registro de Windows en el equipo que use para descargar los resultados de la búsqueda. Para acelerar el proceso de descarga, se recomienda comenzar con una configuración de 24 operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="1cfac-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="1cfac-p102">Si descarga los resultados de la búsqueda en una red de ancho de banda bajo, aumentar esta configuración puede tener un impacto negativo. Como alternativa, es posible que pueda aumentar la configuración a más de 24 operaciones simultáneas en una red de ancho de banda alto (el número máximo de operaciones simultáneas es 512). Después de configurar este valor del registro, es posible que tenga que cambiarlo para encontrar el número óptimo de operaciones simultáneas para su entorno.</span><span class="sxs-lookup"><span data-stu-id="1cfac-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="1cfac-112">Crear una configuración del registro para cambiar el número de operaciones simultáneas al exportar datos</span><span class="sxs-lookup"><span data-stu-id="1cfac-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="1cfac-113">Lleve a cabo el siguiente procedimiento en el equipo que va a usar para descargar los resultados de &amp; la búsqueda del centro de seguridad y cumplimiento o de los datos de la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1cfac-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="1cfac-114">Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta.</span><span class="sxs-lookup"><span data-stu-id="1cfac-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="1cfac-115">Guarde el siguiente texto en un archivo de registro de la ventana mediante un sufijo de nombre de archivo. reg; por ejemplo, ConcurrentOperations. reg.</span><span class="sxs-lookup"><span data-stu-id="1cfac-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="1cfac-116">Como se ha explicado anteriormente, se recomienda comenzar con 24 operaciones simultáneas y, a continuación, cambiar esta configuración según corresponda.</span><span class="sxs-lookup"><span data-stu-id="1cfac-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="1cfac-117">En el explorador de Windows, haga clic o doble clic en el archivo. reg que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="1cfac-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="1cfac-118">En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="1cfac-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="1cfac-119">Cuando se le pregunte si desea continuar, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="1cfac-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="1cfac-120">El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.</span><span class="sxs-lookup"><span data-stu-id="1cfac-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="1cfac-121">Puede repetir los pasos 2-5 para cambiar el valor de la `DownloadConcurrency` configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="1cfac-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="1cfac-p103">Una vez que haya creado o `DownloadConcurrency` cambiado la configuración del registro, asegúrese de crear un nuevo trabajo de exportación o reiniciar un trabajo de exportación existente para los resultados de búsqueda o los datos que desea descargar. Consulte la sección [More Information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1cfac-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="1cfac-124">Más información</span><span class="sxs-lookup"><span data-stu-id="1cfac-124">More information</span></span>

- <span data-ttu-id="1cfac-p104">La primera vez que ejecute el archivo. reg que creó en este procedimiento, se creará una nueva clave del registro. A continuación `DownloadConcurrency` , la configuración del registro se edita cada vez que cambia y vuelve a ejecutar el archivo de edición. reg.</span><span class="sxs-lookup"><span data-stu-id="1cfac-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="1cfac-p105">La herramienta de exportación de exhibición de documentos electrónicos de Office 365 usa la [utilidad de Azure AzCopy](https://go.microsoft.com/fwlink/?linkid=849949) para descargar los datos de búsqueda del centro de seguridad &amp; y cumplimiento o de la exhibición avanzada de documentos electrónicos. La configuración `DownloadConcurrency` del registro es similar a usar el parámetro **/NC** al ejecutar la utilidad AzCopy. Por lo tanto, la `"DownloadConcurrency=24"` configuración del registro de tendría el mismo efecto que usar el `/NC:24` valor del parámetro de con la utilidad AzCopy.</span><span class="sxs-lookup"><span data-stu-id="1cfac-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="1cfac-p106">Si detiene una descarga de exportación que está actualmente en curso y la reinicia (intentando descargar los resultados de la búsqueda de nuevo), la herramienta de exportación de exhibición de documentos electrónicos de Office 365 intentará reanudar la misma descarga. Por lo tanto, si inicia una descarga, la detiene y, a continuación `DownloadConcurrency` , cambia la configuración del registro, es probable que se produzca un error en la descarga si la reinicia (al hacer clic en **Descargar resultados**exportados). Esto se debe a que la herramienta de exportación intentará reanudar la descarga anterior con una configuración que no es válida porque ha cambiado la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="1cfac-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="1cfac-p107">Por lo tanto, después de `DownloadConcurrency` cambiar la configuración del registro, asegúrese de reiniciar el trabajo de exportación (haciendo clic en **reiniciar exportación**) en el centro de seguridad &amp; y cumplimiento. A continuación, puede descargar los resultados exportados. Para obtener más información sobre la exportación de resultados de búsqueda y datos, vea:</span><span class="sxs-lookup"><span data-stu-id="1cfac-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="1cfac-136">Exportar resultados de búsqueda de contenido desde el centro &amp; de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="1cfac-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="1cfac-137">Exportar resultados en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="1cfac-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    

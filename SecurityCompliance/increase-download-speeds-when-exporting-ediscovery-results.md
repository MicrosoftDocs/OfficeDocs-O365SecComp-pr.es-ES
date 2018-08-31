---
title: Aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Obtenga información sobre cómo configurar el registro de Windows para aumentar el rendimiento de los datos al descargar los resultados de búsqueda y búsqueda de datos de la seguridad de Office 365 &amp; centro de cumplimiento y Office 365 avanzada de exhibición de documentos electrónicos.
ms.openlocfilehash: 3f456f5ee0312d4d4d7b95f868520e6756a90fd1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536855"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="33ec1-103">Aumentar la velocidad de descarga al exportar los resultados de búsqueda de exhibición de documentos electrónicos de Office 365</span><span class="sxs-lookup"><span data-stu-id="33ec1-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="33ec1-p101">Cuando use la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para descargar los resultados de una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento o descarga de datos de Office 365 avanzada exhibición de documentos electrónicos, la herramienta inician un cierto número de exportación simultánea operaciones para descargar los datos en el equipo local. De forma predeterminada, se establece el número de operaciones simultáneas a 8 veces el número de núcleos en el equipo que está utilizando para descargar los datos. Por ejemplo, si tiene un equipo de doble núcleo (lo que significa dos unidades centrales de procesamiento en uno chip), el número predeterminado de las operaciones de exportación de usuarios simultáneos es de 16. Para aumentar el rendimiento de transferencia de datos y el proceso de descarga de velocidad, puede aumentar el número de operaciones simultáneas mediante la configuración de una configuración del registro de Windows en el equipo que se utiliza para descargar los resultados de búsqueda. Para el proceso de descarga de la velocidad, se recomienda que comience con una configuración de 24 operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="33ec1-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="33ec1-p102">Si descarga los resultados de búsqueda a través de una red de ancho de banda bajo, el aumento de esta configuración podría tener un impacto negativo. Como alternativa, es posible que pueda aumentar la configuración de más de 24 operaciones simultáneas en una red de gran ancho de banda (el número máximo de operaciones simultáneas es 512). Después de configurar este valor del registro, debe cambiar para buscar el número óptimo de las operaciones de usuarios simultáneos para su entorno.</span><span class="sxs-lookup"><span data-stu-id="33ec1-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="33ec1-112">Crear una configuración para cambiar el número de operaciones simultáneas al exportar datos del registro</span><span class="sxs-lookup"><span data-stu-id="33ec1-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="33ec1-113">Realice el siguiente procedimiento en el equipo que se usará para descargar los resultados de búsqueda de la seguridad &amp; centro de cumplimiento o datos de exhibición de documentos electrónicos avanzada.</span><span class="sxs-lookup"><span data-stu-id="33ec1-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="33ec1-114">Si está abierta, cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="33ec1-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="33ec1-115">Guarde el siguiente texto en un archivo de registro de la ventana mediante el uso de un sufijo de nombre de archivo de. reg; Por ejemplo, ConcurrentOperations.reg.</span><span class="sxs-lookup"><span data-stu-id="33ec1-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="33ec1-116">Como anterior se explica, se recomienda que empiece por 24 operaciones simultáneas y, a continuación, cambie esta opción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="33ec1-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="33ec1-117">En el Explorador de Windows, haga clic en o haga doble clic en el archivo .reg que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="33ec1-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="33ec1-118">En la ventana de Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del registro de realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="33ec1-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="33ec1-119">Cuando se le solicite para continuar, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="33ec1-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="33ec1-120">El Editor del registro, se muestra un mensaje que indica que la configuración se ha agregado correctamente en el registro.</span><span class="sxs-lookup"><span data-stu-id="33ec1-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="33ec1-121">Repita los pasos del 2 al 5 para cambiar el valor para el `DownloadConcurrency` configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="33ec1-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="33ec1-p103">Después de crear o cambiar la `DownloadConcurrency` , la configuración del registro asegúrese de crear un nuevo trabajo de exportación o reiniciar un trabajo de exportación existente para los resultados de búsqueda o los datos que desea descargar. Vea la sección [obtener más información](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="33ec1-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="33ec1-124">Más información</span><span class="sxs-lookup"><span data-stu-id="33ec1-124">More information</span></span>

- <span data-ttu-id="33ec1-p104">Una nueva clave de registro se crea la primera vez que ejecute el archivo .reg que creó en este procedimiento. Entonces el `DownloadConcurrency` configuración del registro se edita cada vez que cambie y vuelva a ejecuta el archivo de edición. reg.</span><span class="sxs-lookup"><span data-stu-id="33ec1-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="33ec1-p105">La herramienta de exportación de exhibición de documentos electrónicos de Office 365 usa la [utilidad AzCopy de Azure](https://go.microsoft.com/fwlink/?linkid=849949) para descargar los datos de búsqueda de la seguridad &amp; centro de cumplimiento de normas o de exhibición de documentos electrónicos avanzada. Configuración de la `DownloadConcurrency` configuración del registro es similar a utilizar el **parámetro/NC** cuando ejecute la utilidad AzCopy. Por lo que la configuración del registro de `"DownloadConcurrency=24"` tendría el mismo efecto que utilizar el valor del parámetro de `/NC:24` con la utilidad AzCopy.</span><span class="sxs-lookup"><span data-stu-id="33ec1-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="33ec1-p106">Si detiene una descarga de exportación que está actualmente en curso y, a continuación, reinícielo (al tratar de volver a descargar los resultados de búsqueda), la herramienta de exportación de exhibición de documentos electrónicos de Office 365 intentará reanudar la descarga del misma. Por lo tanto, si inicia una descarga, deténgalo y, a continuación, cambie la `DownloadConcurrency` registro de configuración, la descarga se probablemente producirá un error si reinicia (haciendo clic en **descarga exporta resultados**). Esto es debido a que la herramienta de exportación intentará reanudar la descarga anterior con la configuración que no es válida debido a que ha cambiado la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="33ec1-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="33ec1-p107">Por lo tanto, después de cambiar la `DownloadConcurrency` no olvide reiniciar el trabajo de exportación (haciendo clic en **reiniciar exportación**) de la seguridad, la configuración del registro &amp; centro de cumplimiento. A continuación, puede descargar los resultados exportados. Para obtener más información acerca de cómo exportar los resultados de búsqueda y datos, vea:</span><span class="sxs-lookup"><span data-stu-id="33ec1-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="33ec1-136">Exportar los resultados de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="33ec1-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="33ec1-137">Exportar resultados en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="33ec1-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    

---
title: Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Puede cambiar el tamaño predeterminado de los archivos PST que se descargan en el equipo al exportar los resultados de búsqueda de exhibición de documentos electrónicos.
ms.openlocfilehash: c01f05a02fd94941eb2eb7a05b4c84ffecec9b39
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522251"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="50792-103">Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="50792-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="50792-p101">Cuando se usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para exportar los resultados de correo electrónico de una búsqueda de exhibición de documentos electrónicos de las distintas herramientas de exhibición de documentos electrónicos de Microsoft, el tamaño predeterminado de un archivo PST que se puede exportar es 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el registro de Windows en el equipo que utilice para exportar los resultados de búsqueda. Una razón para hacer esto es para que un archivo PST puede quepan en medios extraíbles, como un DVD, un CD o una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="50792-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="50792-107">La herramienta de exportación de exhibición de documentos electrónicos de Office 365 se usa para exportar los resultados de búsqueda cuando se usa la búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento, en lugar de exhibición de documentos electrónicos en Exchange Online y el centro de exhibición de documentos electrónicos en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="50792-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="50792-108">Crear una configuración del registro para cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="50792-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="50792-109">Realice el procedimiento siguiente en el equipo que se usará para exportar los resultados de una búsqueda de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="50792-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="50792-110">Si está abierta, cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="50792-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="50792-111">Guarde el siguiente texto en un archivo de registro de la ventana mediante el uso de un sufijo de nombre de archivo de. reg; Por ejemplo, PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="50792-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="50792-p102">En el ejemplo anterior, el `PstSizeLimitInBytes` valor está establecido en 1.073.741.824 bytes o aproximadamente 1 GB. A continuación presentamos algunos otros valores de ejemplo para la `PstSizeLimitInBytes` configuración.</span><span class="sxs-lookup"><span data-stu-id="50792-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="50792-114">**Cambio de tamaño en GB (aproximadamente)**</span><span class="sxs-lookup"><span data-stu-id="50792-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="50792-115">**Tamaño en bytes**</span><span class="sxs-lookup"><span data-stu-id="50792-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="50792-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="50792-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="50792-117">751619277</span><span class="sxs-lookup"><span data-stu-id="50792-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="50792-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="50792-118">2 GB</span></span>  <br/> |<span data-ttu-id="50792-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="50792-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="50792-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="50792-120">4 GB</span></span>  <br/> |<span data-ttu-id="50792-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="50792-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="50792-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="50792-122">8 GB</span></span>  <br/> |<span data-ttu-id="50792-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="50792-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="50792-124">Cambiar el `PstSizeLimitInBytes` valor para el tamaño máximo que desee de un archivo PST al exportar los resultados de búsqueda y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="50792-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="50792-125">En el Explorador de Windows, haga clic en o haga doble clic en el archivo .reg que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="50792-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="50792-126">En la ventana de Control de acceso de usuario, haga clic en **Sí** para permitir que el Editor del registro de realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="50792-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="50792-127">Cuando se le solicite para continuar, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="50792-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="50792-128">El Editor del registro, se muestra un mensaje que indica que la configuración se ha agregado correctamente en el registro.</span><span class="sxs-lookup"><span data-stu-id="50792-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="50792-129">Repita los pasos del 3 al 6 para cambiar el valor para el `PstSizeLimitInBytes` configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="50792-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="50792-130">Preguntas más frecuentes acerca de cómo cambiar el tamaño predeterminado de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="50792-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="50792-131">**¿Por qué es el valor predeterminado de tamaño 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="50792-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="50792-132">El tamaño predeterminado de 10 GB se ha basado en los comentarios del cliente; 10 GB es un buen equilibrio entre la cantidad óptima de contenido en un archivo PST único y con un mínimo de posibilidades de daños en el archivo.</span><span class="sxs-lookup"><span data-stu-id="50792-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="50792-133">**¿Debo aumentar o disminuir el tamaño predeterminado de los archivos PST?**</span><span class="sxs-lookup"><span data-stu-id="50792-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="50792-p103">Los clientes tienden a reducir el límite de tamaño para que quepan los resultados de búsqueda en medios extraíbles que puede enviar físicamente otras ubicaciones en su organización. No se recomienda aumentar el tamaño predeterminado porque PST archivos mayor que 10 GB podría tener problemas de daños.</span><span class="sxs-lookup"><span data-stu-id="50792-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="50792-136">**¿Qué equipo es necesario hacer esto en?**</span><span class="sxs-lookup"><span data-stu-id="50792-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="50792-137">Debe cambiar la configuración del registro en cualquier equipo local que ejecute la herramienta de exportación de exhibición de documentos electrónicos de Office 365 en.</span><span class="sxs-lookup"><span data-stu-id="50792-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="50792-138">**¿Después de cambiar esta configuración, tengo que reiniciar el equipo?**</span><span class="sxs-lookup"><span data-stu-id="50792-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="50792-p104">No, no es necesario reiniciar el equipo. Pero, si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos de Office 365, tendrá que cerrarlo y el reinicio después de cambiar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="50792-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="50792-141">**¿Obtener editada una clave del registro existente o se crea una nueva clave?**</span><span class="sxs-lookup"><span data-stu-id="50792-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="50792-p105">Una nueva clave de registro se crea la primera vez que ejecute el archivo .reg que creó en este procedimiento. A continuación, la configuración se edita cada vez que cambie y vuelva a ejecuta el archivo de edición. reg.</span><span class="sxs-lookup"><span data-stu-id="50792-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>

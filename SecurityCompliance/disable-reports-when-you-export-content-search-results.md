---
title: Deshabilitar informes al exportar los resultados de búsqueda de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Edite el registro de Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido desde el centro de seguridad & cumplimiento en Office 365. La deshabilitación de estos informes puede acelerar el tiempo de descarga y ahorrar espacio en disco.
ms.openlocfilehash: f6abcf8afe70bc6ce04f0f9343e28879f7fed885
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154832"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="e04fc-104">Deshabilitar informes al exportar los resultados de búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="e04fc-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="e04fc-105">Cuando usa la herramienta de exportación de exhibición de documentos electrónicos de Office 365 para exportar los resultados de una búsqueda de contenido en el centro de seguridad & cumplimiento, la herramienta crea y exporta automáticamente dos informes que contienen información adicional acerca del contenido exportado.</span><span class="sxs-lookup"><span data-stu-id="e04fc-105">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="e04fc-106">Estos informes son el archivo Results. csv y el archivo manifest. XML (consulte la sección [preguntas más frecuentes sobre cómo deshabilitar los informes de exportación](#frequently-asked-questions-about-disabling-export-reports) de este tema para obtener descripciones detalladas de estos informes).</span><span class="sxs-lookup"><span data-stu-id="e04fc-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="e04fc-107">Como estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco al impedir que se exporten estos archivos.</span><span class="sxs-lookup"><span data-stu-id="e04fc-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="e04fc-108">Para ello, puede cambiar el registro de Windows en el equipo que usa para exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e04fc-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="e04fc-109">Si desea incluir los informes más adelante, puede editar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="e04fc-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="e04fc-110">Crear una configuración del registro para deshabilitar los informes de exportación</span><span class="sxs-lookup"><span data-stu-id="e04fc-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="e04fc-111">Lleve a cabo el siguiente procedimiento en el equipo que va a usar para exportar los resultados de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="e04fc-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="e04fc-112">Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta.</span><span class="sxs-lookup"><span data-stu-id="e04fc-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="e04fc-113">Realice uno o ambos de los pasos siguientes, según el informe de exportación que quiera deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="e04fc-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="e04fc-114">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="e04fc-114">**Results.csv**</span></span>
    
      <span data-ttu-id="e04fc-115">Guarde el siguiente texto en un archivo de registro de Windows mediante un sufijo de nombre de archivo. reg; por ejemplo, DisableResultsCsv. reg.</span><span class="sxs-lookup"><span data-stu-id="e04fc-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="e04fc-116">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="e04fc-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="e04fc-117">Guarde el siguiente texto en un archivo de registro de Windows mediante un sufijo de nombre de archivo. reg; por ejemplo, DisableManifestXml. reg.</span><span class="sxs-lookup"><span data-stu-id="e04fc-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="e04fc-118">En el explorador de Windows, haga clic o doble clic en el archivo. reg que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="e04fc-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="e04fc-119">En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="e04fc-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="e04fc-120">Cuando se le pregunte si desea continuar, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="e04fc-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="e04fc-121">El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.</span><span class="sxs-lookup"><span data-stu-id="e04fc-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="e04fc-122">Editar la configuración del registro para volver a habilitar los informes de exportación</span><span class="sxs-lookup"><span data-stu-id="e04fc-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="e04fc-123">Si ha deshabilitado los informes Results. csv y manifest. XML creando los archivos. reg en el procedimiento anterior, puede editar esos archivos para volver a habilitar un informe de manera que se exporte con los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e04fc-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="e04fc-124">De nuevo, realice el siguiente procedimiento en el equipo que va a usar para exportar los resultados de una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="e04fc-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="e04fc-125">Cierre la herramienta de exportación de exhibición de documentos electrónicos de Office 365 si está abierta.</span><span class="sxs-lookup"><span data-stu-id="e04fc-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="e04fc-126">Edite uno o ambos de los archivos. reg Edit que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="e04fc-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="e04fc-127">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="e04fc-127">**Results.csv**</span></span>
    
        <span data-ttu-id="e04fc-128">Abra el archivo DisableResultsCsv. reg en el Bloc de notas, `False` cambie `True`el valor a y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="e04fc-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="e04fc-129">Por ejemplo, después de editar el archivo, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e04fc-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="e04fc-130">**Manifest. XML**</span><span class="sxs-lookup"><span data-stu-id="e04fc-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="e04fc-131">Abra el archivo DisableManifestXml. reg en el Bloc de notas, `False` cambie `True`el valor a y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="e04fc-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="e04fc-132">Por ejemplo, después de editar el archivo, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e04fc-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="e04fc-133">En el explorador de Windows, haga clic o doble clic en un archivo. reg que modificó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="e04fc-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="e04fc-134">En la ventana control de acceso de usuario, haga clic en **sí** para permitir que el editor del registro realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="e04fc-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="e04fc-135">Cuando se le pregunte si desea continuar, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="e04fc-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="e04fc-136">El editor del registro muestra un mensaje que indica que la configuración se agregó correctamente al registro.</span><span class="sxs-lookup"><span data-stu-id="e04fc-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="e04fc-137">Preguntas más frecuentes sobre la deshabilitación de informes de exportación</span><span class="sxs-lookup"><span data-stu-id="e04fc-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="e04fc-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e04fc-138"></span></span>

 <span data-ttu-id="e04fc-139">**¿Cuáles son los informes Results. csv y manifest. XML?**</span><span class="sxs-lookup"><span data-stu-id="e04fc-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="e04fc-140">Los archivos Results. csv y manifest. XML contienen información adicional acerca del contenido que se exportó.</span><span class="sxs-lookup"><span data-stu-id="e04fc-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="e04fc-141">**Results. csv** un documento de Excel que contiene información acerca de cada elemento que se descarga como resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e04fc-141">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="e04fc-142">Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:</span><span class="sxs-lookup"><span data-stu-id="e04fc-142">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="e04fc-143">La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).</span><span class="sxs-lookup"><span data-stu-id="e04fc-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="e04fc-144">La fecha en que se envió o se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e04fc-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="e04fc-145">La línea Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e04fc-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="e04fc-146">El remitente y los destinatarios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e04fc-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="e04fc-147">Si el mensaje es un mensaje duplicado si ha habilitado la desduplicación al exportar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e04fc-147">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="e04fc-148">Los mensajes duplicados tendrán un valor en la columna **principal de Itemid** que identifica el mensaje como duplicado.</span><span class="sxs-lookup"><span data-stu-id="e04fc-148">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="e04fc-149">El valor de la columna **principal de Itemid** es el mismo que el valor de la columna DocumentId del **elemento** del mensaje que se exportó.</span><span class="sxs-lookup"><span data-stu-id="e04fc-149">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="e04fc-150">Para los documentos de los sitios de SharePoint y OneDrive para la empresa, el registro de resultados contiene información sobre cada documento, incluidos:</span><span class="sxs-lookup"><span data-stu-id="e04fc-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="e04fc-151">La dirección URL del documento.</span><span class="sxs-lookup"><span data-stu-id="e04fc-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="e04fc-152">La dirección URL de la colección de sitio donde se ubica el documento.</span><span class="sxs-lookup"><span data-stu-id="e04fc-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="e04fc-153">La fecha en la que el documento se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="e04fc-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="e04fc-154">El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).</span><span class="sxs-lookup"><span data-stu-id="e04fc-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="e04fc-155">**Manifest. XML** un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e04fc-155">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="e04fc-156">La información de este informe es la misma que la del informe Results. csv, pero está en el formato especificado por el modelo de referencia de detección electrónica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="e04fc-156">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="e04fc-157">Para obtener más información acerca de EDRM, [https://www.edrm.net](https://www.edrm.net)vaya a.</span><span class="sxs-lookup"><span data-stu-id="e04fc-157">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="e04fc-158">**¿Cuándo debo deshabilitar la exportación de estos informes?**</span><span class="sxs-lookup"><span data-stu-id="e04fc-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="e04fc-159">Depende de sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="e04fc-159">It depends on your specific needs.</span></span> <span data-ttu-id="e04fc-160">Muchas organizaciones no necesitan más información sobre los resultados de la búsqueda y no necesitan estos informes.</span><span class="sxs-lookup"><span data-stu-id="e04fc-160">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="e04fc-161">**¿En qué equipo tengo que hacerlo?**</span><span class="sxs-lookup"><span data-stu-id="e04fc-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="e04fc-162">Tiene que cambiar la configuración del registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e04fc-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="e04fc-163">**Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**</span><span class="sxs-lookup"><span data-stu-id="e04fc-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="e04fc-164">No, no es necesario reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="e04fc-164">No, you don't have to restart the computer.</span></span> <span data-ttu-id="e04fc-165">Pero si se está ejecutando la herramienta de exportación de exhibición de documentos electrónicos de Office 365, debe cerrarla y reiniciarla después de cambiar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="e04fc-165">But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="e04fc-166">**¿Se modifica una clave del registro existente o se crea una nueva clave?**</span><span class="sxs-lookup"><span data-stu-id="e04fc-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="e04fc-167">La primera vez que ejecute el archivo. reg que creó en el procedimiento de este tema, se creará una nueva clave del registro.</span><span class="sxs-lookup"><span data-stu-id="e04fc-167">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="e04fc-168">A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición. reg.</span><span class="sxs-lookup"><span data-stu-id="e04fc-168">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>

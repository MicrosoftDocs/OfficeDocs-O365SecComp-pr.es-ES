---
title: Corrección de errores al procesar los datos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c9c2660929037430535c9b612218563c51b1f056
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490797"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="5d683-102">Corrección de errores al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="5d683-102">Error remediation when processing data</span></span>

<span data-ttu-id="5d683-103">La corrección de errores permite que los administradores de eDiscovery puedan rectificar problemas de datos que impiden que eDiscovery avanzado procese correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="5d683-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="5d683-104">Por ejemplo, no se pueden procesar archivos protegidos con contraseña, ya que los archivos están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="5d683-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="5d683-105">Mediante la corrección de errores, los administradores de eDiscovery pueden descargar archivos con estos errores, quitar la protección con contraseña y, a continuación, cargar los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="5d683-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="5d683-106">Use el siguiente flujo de trabajo para corregir los archivos con errores en casos de exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5d683-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="5d683-107">Crear una sesión de corrección de errores para corregir los archivos con errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="5d683-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="5d683-108">Si el Asistente para la corrección de errores se cierra en cualquier momento durante el siguiente procedimiento, puede volver a la sesión de corrección de errores desde \*\*\*\* la pestaña procesando; para ello, seleccione **corrección de errores** en el menú desplegable **Ver** .</span><span class="sxs-lookup"><span data-stu-id="5d683-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="5d683-109">En la pestaña **procesamiento** en un caso de exhibición avanzada de documentos electrónicos, seleccione **errores** en el menú desplegable **Ver** .</span><span class="sxs-lookup"><span data-stu-id="5d683-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop-down menu.</span></span>

2. <span data-ttu-id="5d683-110">Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto a tipo de error o tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="5d683-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="5d683-111">En el siguiente ejemplo, estamos corrigiendo un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="5d683-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="5d683-112">Haga clic en **nueva corrección de errores**.</span><span class="sxs-lookup"><span data-stu-id="5d683-112">Click **New error remediation**.</span></span>

    ![Corrección de errores](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="5d683-114">La sesión de corrección de errores se inicia con una etapa de preparación en la que los archivos con errores se copian en una ubicación de almacenamiento de Azure proporcionada por Microsoft para que pueda descargarlos en el equipo local para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="5d683-114">The error remediation session starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Preparación de la corrección de errores](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="5d683-116">Una vez completada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.</span><span class="sxs-lookup"><span data-stu-id="5d683-116">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="5d683-118">Para descargar archivos, especifique la **ruta de destino de la descarga**.</span><span class="sxs-lookup"><span data-stu-id="5d683-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="5d683-119">Se trata de una ruta de acceso en el equipo local en la que se ha descargado el archivo.</span><span class="sxs-lookup"><span data-stu-id="5d683-119">This is a path on your local computer where the file is downloaded.</span></span>  <span data-ttu-id="5d683-120">La ruta de acceso predeterminada,%USERPROFILE%\Downloads\errors, apunta a la carpeta descargas del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="5d683-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="5d683-121">Puede cambiar esta ruta de acceso si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5d683-121">You can change this path if necessary.</span></span> <span data-ttu-id="5d683-122">Si lo cambia, le recomendamos que use una ruta de acceso de archivo local para obtener el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5d683-122">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="5d683-123">No use una ruta de acceso de red remota.</span><span class="sxs-lookup"><span data-stu-id="5d683-123">Don't use a remote network path.</span></span>

6. <span data-ttu-id="5d683-124">Copie el comando predefinido; para ello, haga clic en **copiar al**portapapeles.</span><span class="sxs-lookup"><span data-stu-id="5d683-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="5d683-125">Inicie un símbolo del sistema de Windows, pegue el comando y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="5d683-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="5d683-126">Los archivos se descargan.</span><span class="sxs-lookup"><span data-stu-id="5d683-126">The files are downloaded.</span></span>

    ![Preparar la corrección de errores](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="5d683-128">Debe usar AzCopy v 8.1 para usar correctamente el comando que se proporciona en la página **descargar archivos** .</span><span class="sxs-lookup"><span data-stu-id="5d683-128">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="5d683-129">También debe usar AzCopy v 8.1 para cargar los archivos en el paso 10 siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d683-129">You also must use AzCopy v8.1 to upload the files in step 10 below.</span></span> <span data-ttu-id="5d683-130">Para instalar esta versión de AzCopy, consulte [transferir datos con AzCopy v 8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="5d683-130">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="5d683-131">Si el comando AzCopy proporcionado no se produce, consulte [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="5d683-131">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="5d683-132">Después de descargar los archivos, puede corregirlos con una herramienta adecuada.</span><span class="sxs-lookup"><span data-stu-id="5d683-132">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="5d683-133">Para archivos protegidos con contraseña, hay varias herramientas de averiguación de contraseñas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="5d683-133">For password-protected files, there several password cracking tools you can use.</span></span> <span data-ttu-id="5d683-134">Si conoce las contraseñas de los archivos, puede abrirlas y quitar la protección con contraseña.</span><span class="sxs-lookup"><span data-stu-id="5d683-134">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="5d683-135">Es importante que conserve la estructura de directorios y los nombres de archivo de los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="5d683-135">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="5d683-136">Los nombres de ruta de acceso de los archivos y carpetas descargados hacen posible asociar los archivos corregidos con los archivos originales.</span><span class="sxs-lookup"><span data-stu-id="5d683-136">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="5d683-137">Si se cambian la estructura de directorios o los nombres de archivo, recibirá el siguiente `Cannot apply Error Remediation to the current Workingset`error:.</span><span class="sxs-lookup"><span data-stu-id="5d683-137">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span>

8. <span data-ttu-id="5d683-138">Ahora, vuelva a eDiscovery avanzado y haga clic en **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="5d683-138">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="5d683-139">Se desplazará al siguiente paso en el que ahora puede cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="5d683-139">This will move to the next step where you can now upload the files.</span></span>

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="5d683-141">Especifique la ubicación de los archivos corregidos en el cuadro **de texto Ruta de acceso a la ubicación del archivo** y, a continuación, haga clic en **copiar al**portapapeles.</span><span class="sxs-lookup"><span data-stu-id="5d683-141">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="5d683-142">Pegue el comando en un símbolo del sistema de Windows y presione **entrar** para cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="5d683-142">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="5d683-144">Vuelva a eDiscovery avanzado y haga clic en **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="5d683-144">Return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="5d683-145">Cuando se complete el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5d683-145">When processing is complete.</span></span> <span data-ttu-id="5d683-146">Puede volver al conjunto de revisiones y ver el archivo corregido.</span><span class="sxs-lookup"><span data-stu-id="5d683-146">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="5d683-147">Qué sucede cuando se corrigen los archivos</span><span class="sxs-lookup"><span data-stu-id="5d683-147">What happens when files are remediated</span></span>

<span data-ttu-id="5d683-148">Cuando se cargan los archivos corregidos, se conservan los metadatos originales excepto los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d683-148">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="5d683-149">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="5d683-149">ExtractedTextSize</span></span>
- <span data-ttu-id="5d683-150">HasText</span><span class="sxs-lookup"><span data-stu-id="5d683-150">HasText</span></span>
- <span data-ttu-id="5d683-151">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="5d683-151">IsErrorRemediate</span></span>
- <span data-ttu-id="5d683-152">LoadId</span><span class="sxs-lookup"><span data-stu-id="5d683-152">LoadId</span></span>
- <span data-ttu-id="5d683-153">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="5d683-153">ProcessingErrorMessage</span></span>
- <span data-ttu-id="5d683-154">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="5d683-154">ProcessingStatus</span></span>
- <span data-ttu-id="5d683-155">Texto</span><span class="sxs-lookup"><span data-stu-id="5d683-155">Text</span></span>
- <span data-ttu-id="5d683-156">WordCount</span><span class="sxs-lookup"><span data-stu-id="5d683-156">WordCount</span></span>
- <span data-ttu-id="5d683-157">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="5d683-157">WorkingsetId</span></span>

<span data-ttu-id="5d683-158">Para obtener una definición de todos los campos de metadatos en eDiscovery avanzado, consulte campos de metadatos del [documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="5d683-158">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>

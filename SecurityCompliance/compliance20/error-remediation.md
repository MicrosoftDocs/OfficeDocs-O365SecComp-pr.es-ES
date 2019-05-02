---
title: Corrección de errores al procesar los datos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d54f5ffa5a2dd253a478a758ac0616025a79f118
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33516498"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="963a4-102">Corrección de errores al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="963a4-102">Error remediation when processing data</span></span>

<span data-ttu-id="963a4-103">La corrección de errores permite que los administradores de eDiscovery puedan rectificar problemas de datos que impiden que eDiscovery avanzado procese correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="963a4-103">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="963a4-104">Por ejemplo, no se pueden procesar archivos protegidos con contraseña, ya que los archivos están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="963a4-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="963a4-105">Mediante la corrección de errores, los administradores de eDiscovery pueden descargar archivos con estos errores, quitar la protección con contraseña y cargar los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="963a4-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="963a4-106">Use el siguiente flujo de trabajo para corregir los archivos con errores en casos de exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="963a4-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="963a4-107">Crear una sesión de corrección de errores para corregir los archivos con errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="963a4-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="963a4-108">Si el Asistente para la corrección de errores se cierra en cualquier momento durante el siguiente procedimiento, puede volver a la sesión de corrección de errores desde \*\*\*\* la pestaña procesando; para ello, seleccione **corrección de errores** en el menú desplegable **Ver** .</span><span class="sxs-lookup"><span data-stu-id="963a4-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="963a4-109">En la pestaña **procesamiento** en un caso de exhibición avanzada de documentos electrónicos, seleccione **errores** en el menú desplegable **Ver** .</span><span class="sxs-lookup"><span data-stu-id="963a4-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="963a4-110">Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto a tipo de error o tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="963a4-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="963a4-111">En el siguiente ejemplo, estamos corrigiendo un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="963a4-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="963a4-112">Haga clic en **+ nuevo error de corrección**.</span><span class="sxs-lookup"><span data-stu-id="963a4-112">Click **+ New error remediation**.</span></span>

    ![Corrección de errores](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="963a4-114">La sesión de corrección de errores comenzará a partir de una etapa de preparación en la que los archivos con errores se moverán a una ubicación segura de Azure que se descargará.</span><span class="sxs-lookup"><span data-stu-id="963a4-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![Preparación de la corrección de errores](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="963a4-116">Una vez completada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.</span><span class="sxs-lookup"><span data-stu-id="963a4-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="963a4-118">Para descargar archivos, especifique la **ruta de destino de la descarga**; se trata de una ruta de acceso en el equipo local en la que se debe descargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="963a4-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="963a4-119">La ruta de acceso predeterminada,%USERPROFILE%\Downloads\errors, apunta a la carpeta descargas del usuario que ha iniciado sesión; Esto se puede cambiar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="963a4-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="963a4-120">Le recomendamos que use una ruta de acceso de archivo local en lugar de una ruta de acceso de red remota para obtener un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="963a4-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="963a4-121">Si no ha instalado AzCopy, puede instalarlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="963a4-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="963a4-122">Copie el comando predefinido; para ello, haga clic en **copiar al**portapapeles.</span><span class="sxs-lookup"><span data-stu-id="963a4-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="963a4-123">Inicie un símbolo del sistema de Windows, pegue el comando y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="963a4-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="963a4-124">Los archivos se descargarán.</span><span class="sxs-lookup"><span data-stu-id="963a4-124">The files will be downloaded.</span></span>

    ![Preparación de la corrección de errores](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="963a4-126">Si se produce un error en el comando AzCopy proporcionado, vea para [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md) .</span><span class="sxs-lookup"><span data-stu-id="963a4-126">If the supplied AzCopy command fails, see to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

7. <span data-ttu-id="963a4-127">Después de descargar los archivos, puede corregirlos con una herramienta adecuada.</span><span class="sxs-lookup"><span data-stu-id="963a4-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="963a4-128">Para los archivos protegidos con contraseña, hay varias herramientas de averiguación de contraseñas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="963a4-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="963a4-129">Si conoce las contraseñas de los archivos, puede abrirlas y quitar la protección con contraseña.</span><span class="sxs-lookup"><span data-stu-id="963a4-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="963a4-130">Es importante que mantenga intactos la estructura de directorios y los nombres de archivo de los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="963a4-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="963a4-131">Todas las convenciones de nomenclatura usadas en los archivos y carpetas descargados hacen posible asociar los archivos de remdiated con el original.</span><span class="sxs-lookup"><span data-stu-id="963a4-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="963a4-132">Ahora, vuelva a eDiscovery avanzado y haga clic en **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="963a4-132">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="963a4-133">Se desplazará al siguiente paso en el que ahora puede cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="963a4-133">This will move to the next step where you can now upload the files.</span></span>

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="963a4-135">Especifique la ubicación de los archivos corregidos en el cuadro **de texto Ruta de acceso a la ubicación del archivo** y, a continuación, haga clic en **copiar a clibpboard**.</span><span class="sxs-lookup"><span data-stu-id="963a4-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="963a4-136">Pegue el comando en un símbolo del sistema de Windows y presione **entrar** para cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="963a4-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="963a4-138">Por último, regrese a la exhibición avanzada de documentos electrónicos y haga clic en **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="963a4-138">Finally, return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="963a4-139">Cuando se complete el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="963a4-139">When processing is complete.</span></span>  <span data-ttu-id="963a4-140">Puede volver al conjunto de revisiones y ver el archivo corregido.</span><span class="sxs-lookup"><span data-stu-id="963a4-140">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="963a4-141">Qué sucede cuando se corrigen los archivos</span><span class="sxs-lookup"><span data-stu-id="963a4-141">What happens when files are remediated</span></span>

<span data-ttu-id="963a4-142">Cuando se cargan los archivos corregidos, se conservan los metadatos originales, con la excepción de los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="963a4-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="963a4-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="963a4-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="963a4-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="963a4-144">ExtractedTextSize</span></span>
- <span data-ttu-id="963a4-145">HasText</span><span class="sxs-lookup"><span data-stu-id="963a4-145">HasText</span></span>
- <span data-ttu-id="963a4-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="963a4-146">IsErrorRemediate</span></span>
- <span data-ttu-id="963a4-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="963a4-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="963a4-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="963a4-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="963a4-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="963a4-149">LoadId</span></span>
- <span data-ttu-id="963a4-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="963a4-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="963a4-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="963a4-151">ProcessingStatus</span></span>
- <span data-ttu-id="963a4-152">Text</span><span class="sxs-lookup"><span data-stu-id="963a4-152">Text</span></span>
- <span data-ttu-id="963a4-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="963a4-153">WordCount</span></span>
- <span data-ttu-id="963a4-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="963a4-154">WorkingsetId</span></span>

<span data-ttu-id="963a4-155">Para obtener una definición de todos los campos de metadatos del documento en eDiscovery avanzado, consulte campos de metadatos del [documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="963a4-155">For a definition of all document metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
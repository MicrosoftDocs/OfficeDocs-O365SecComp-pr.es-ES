---
title: Corrección de errores al procesar datos para una investigación
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
ms.openlocfilehash: bca6967fd99696ffb4b610105e448011b9837be4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150862"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="7393a-102">Corrección de errores al procesar datos para una investigación</span><span class="sxs-lookup"><span data-stu-id="7393a-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="7393a-103">La corrección de errores permite que los investigadores puedan rectificar los problemas de datos que impiden que las investigaciones de datos (vista previa) procesen correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="7393a-103">Error remediation allows investigators the ability to rectify data issues which prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="7393a-104">Por ejemplo, no se pueden procesar archivos protegidos con contraseña, ya que los archivos están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="7393a-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="7393a-105">Mediante la corrección de errores, los investigadores pueden descargar archivos con estos errores, quitar la protección con contraseña y cargar los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="7393a-105">Using error remediation, investigators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="7393a-106">Use el siguiente flujo de trabajo para corregir los archivos con errores en los casos de investigación de datos (vista previa).</span><span class="sxs-lookup"><span data-stu-id="7393a-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="7393a-107">Crear una sesión de corrección de errores para corregir los archivos con errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="7393a-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="7393a-108">Si el Asistente para la corrección de errores se cierra en cualquier momento durante el siguiente procedimiento, puede volver a la sesión de corrección de errores desde \*\*\*\* la pestaña procesando; para ello, seleccione **corrección de errores** en el menú desplegable **Ver** .</span><span class="sxs-lookup"><span data-stu-id="7393a-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="7393a-109">En la pestaña **procesamiento** en un caso de investigación de datos (vista previa), seleccione **errores** en el menú desplegable **vista** .</span><span class="sxs-lookup"><span data-stu-id="7393a-109">On the **Processing** tab in an Data Investigations (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="7393a-110">Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto a tipo de error o tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="7393a-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="7393a-111">En el siguiente ejemplo, estamos corrigiendo un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="7393a-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="7393a-112">Haga clic en **+ nuevo error de corrección**.</span><span class="sxs-lookup"><span data-stu-id="7393a-112">Click **+ New error remediation**.</span></span>

    ![Corrección de errores](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="7393a-114">La sesión de corrección de errores comenzará a partir de una etapa de preparación en la que los archivos con errores se moverán a una ubicación segura de Azure que se descargará.</span><span class="sxs-lookup"><span data-stu-id="7393a-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![Preparación de la corrección de errores](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="7393a-116">Una vez completada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.</span><span class="sxs-lookup"><span data-stu-id="7393a-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="7393a-118">Para descargar archivos, especifique la **ruta de destino de la descarga**; se trata de una ruta de acceso en el equipo local en la que se debe descargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="7393a-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="7393a-119">La ruta de acceso predeterminada,%USERPROFILE%\Downloads\errors, apunta a la carpeta descargas del usuario que ha iniciado sesión; Esto se puede cambiar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="7393a-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7393a-120">Le recomendamos que use una ruta de acceso de archivo local en lugar de una ruta de acceso de red remota para obtener un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="7393a-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7393a-121">Si no ha instalado AzCopy, puede instalarlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="7393a-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="7393a-122">Copie el comando predefinido; para ello, haga clic en **copiar al**portapapeles.</span><span class="sxs-lookup"><span data-stu-id="7393a-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="7393a-123">Inicie un símbolo del sistema de Windows, pegue el comando y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="7393a-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="7393a-124">Los archivos se descargarán.</span><span class="sxs-lookup"><span data-stu-id="7393a-124">The files will be downloaded.</span></span>

    ![Preparación de la corrección de errores](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="7393a-126">Si tiene problemas al ejecutar este comando, consulte https://go.microsoft.com/fwlink/?linkid=2038117 para obtener sugerencias para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="7393a-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="7393a-127">Después de descargar los archivos, puede corregirlos con una herramienta adecuada.</span><span class="sxs-lookup"><span data-stu-id="7393a-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="7393a-128">Para los archivos protegidos con contraseña, hay varias herramientas de averiguación de contraseñas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="7393a-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="7393a-129">Si conoce las contraseñas de los archivos, puede abrirlas y quitar la protección con contraseña.</span><span class="sxs-lookup"><span data-stu-id="7393a-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7393a-130">Es importante que mantenga intactos la estructura de directorios y los nombres de archivo de los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="7393a-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="7393a-131">Todas las convenciones de nomenclatura usadas en los archivos y carpetas descargados hacen posible asociar los archivos de remdiated con el original.</span><span class="sxs-lookup"><span data-stu-id="7393a-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="7393a-132">Ahora, vuelva a investigaciones de datos (versión preliminar) y haga clic en **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="7393a-132">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="7393a-133">Se desplazará al siguiente paso en el que ahora puede cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="7393a-133">This will move to the next step where you can now upload the files.</span></span>

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="7393a-135">Especifique la ubicación de los archivos corregidos en el cuadro **de texto Ruta de acceso a la ubicación del archivo** y, a continuación, haga clic en **copiar a clibpboard**.</span><span class="sxs-lookup"><span data-stu-id="7393a-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="7393a-136">Pegue el comando en un símbolo del sistema de Windows y presione **entrar** para cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="7393a-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="7393a-138">Por último, vuelva a investigaciones de datos (versión preliminar) y haga clic en **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="7393a-138">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="7393a-139">Cuando se complete el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7393a-139">When processing is complete.</span></span>  <span data-ttu-id="7393a-140">Puede volver al conjunto de trabajo y ver el archivo corregido.</span><span class="sxs-lookup"><span data-stu-id="7393a-140">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="7393a-141">Qué sucede cuando se corrigen los archivos</span><span class="sxs-lookup"><span data-stu-id="7393a-141">What happens when files are remediated</span></span>

<span data-ttu-id="7393a-142">Cuando se cargan los archivos corregidos, se conservan los metadatos originales, con la excepción de los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7393a-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="7393a-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="7393a-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="7393a-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="7393a-144">ExtractedTextSize</span></span>
- <span data-ttu-id="7393a-145">HasText</span><span class="sxs-lookup"><span data-stu-id="7393a-145">HasText</span></span>
- <span data-ttu-id="7393a-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="7393a-146">IsErrorRemediate</span></span>
- <span data-ttu-id="7393a-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="7393a-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="7393a-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="7393a-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="7393a-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="7393a-149">LoadId</span></span>
- <span data-ttu-id="7393a-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="7393a-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="7393a-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="7393a-151">ProcessingStatus</span></span>
- <span data-ttu-id="7393a-152">Texto</span><span class="sxs-lookup"><span data-stu-id="7393a-152">Text</span></span>
- <span data-ttu-id="7393a-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="7393a-153">WordCount</span></span>
- <span data-ttu-id="7393a-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="7393a-154">WorkingsetId</span></span>

<span data-ttu-id="7393a-155">Para obtener una definición de todos los campos de metadatos de documentos en las investigaciones de datos (versión preliminar), vea [Document Metadata Fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="7393a-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
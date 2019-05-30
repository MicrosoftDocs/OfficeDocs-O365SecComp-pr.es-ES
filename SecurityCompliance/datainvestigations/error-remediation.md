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
ms.openlocfilehash: f8e253a3d38f0f4846485e3b88ea09914d9978ce
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547955"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="ffe3b-102">Corrección de errores al procesar datos para una investigación</span><span class="sxs-lookup"><span data-stu-id="ffe3b-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="ffe3b-103">La corrección de errores permite que los investigadores puedan rectificar los problemas de datos que impiden que las investigaciones de datos (vista previa) procesen correctamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-103">Error remediation allows investigators the ability to rectify data issues which prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="ffe3b-104">Por ejemplo, no se pueden procesar archivos protegidos con contraseña, ya que los archivos están bloqueados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="ffe3b-105">Mediante la corrección de errores, los investigadores pueden descargar archivos con estos errores, quitar la protección con contraseña y cargar los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-105">Using error remediation, investigators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="ffe3b-106">Use el siguiente flujo de trabajo para corregir los archivos con errores en los casos de investigación de datos (vista previa).</span><span class="sxs-lookup"><span data-stu-id="ffe3b-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="ffe3b-107">Crear una sesión de corrección de errores para corregir los archivos con errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="ffe3b-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="ffe3b-108">Si el Asistente para la corrección de errores se cierra en cualquier momento durante el siguiente procedimiento, puede volver a la sesión de corrección de errores desde \*\*\*\* la pestaña procesando; para ello, seleccione **corrección de errores** en el menú desplegable **Ver** .</span><span class="sxs-lookup"><span data-stu-id="ffe3b-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="ffe3b-109">En la pestaña **procesamiento** en un caso de investigación de datos (vista previa), seleccione **errores** en el menú desplegable **vista** .</span><span class="sxs-lookup"><span data-stu-id="ffe3b-109">On the **Processing** tab in an Data Investigations (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="ffe3b-110">Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto a tipo de error o tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="ffe3b-111">En el siguiente ejemplo, estamos corrigiendo un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="ffe3b-112">Haga clic en **+ nuevo error de corrección**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-112">Click **+ New error remediation**.</span></span>

    ![Corrección de errores](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="ffe3b-114">La sesión de corrección de errores comenzará, a partir de una fase de preparación, en la que los archivos con errores se copian en una ubicación segura de Azure para que se puedan descargar.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-114">The error remediation session will begin, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![Preparación de la corrección de errores](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="ffe3b-116">Una vez completada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="ffe3b-118">Para descargar archivos, especifique la **ruta de destino de la descarga**; se trata de una ruta de acceso en el equipo local en la que se debe descargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="ffe3b-119">La ruta de acceso predeterminada,%USERPROFILE%\Downloads\errors, apunta a la carpeta descargas del usuario que ha iniciado sesión; Esto se puede cambiar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ffe3b-120">Le recomendamos que use una ruta de acceso de archivo local en lugar de una ruta de acceso de red remota para obtener un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ffe3b-121">Si no ha instalado AzCopy, puede instalarlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="ffe3b-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="ffe3b-122">Copie el comando predefinido; para ello, haga clic en **copiar al**portapapeles.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="ffe3b-123">Inicie un símbolo del sistema de Windows, pegue el comando y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="ffe3b-124">Los archivos se descargarán.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-124">The files will be downloaded.</span></span>

    ![Preparación de la corrección de errores](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="ffe3b-126">Si tiene problemas al ejecutar este comando, consulte [solucionar problemas de AzCopy en EDiscovery avanzado](../compliance20/troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="ffe3b-126">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](../compliance20/troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="ffe3b-127">Después de descargar los archivos, puede corregirlos con una herramienta adecuada.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="ffe3b-128">Para los archivos protegidos con contraseña, hay varias herramientas de averiguación de contraseñas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="ffe3b-129">Si conoce las contraseñas de los archivos, puede abrirlas y quitar la protección con contraseña.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="ffe3b-130">Es importante que mantenga intactos la estructura de directorios y los nombres de archivo de los archivos corregidos.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-130">It's important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="ffe3b-131">Todas las convenciones de nomenclatura usadas en los archivos y carpetas descargados hacen posible asociar los archivos de remdiated con el original.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="ffe3b-132">Ahora, vuelva a investigaciones de datos (versión preliminar) y haga clic en **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-132">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="ffe3b-133">Se desplazará al siguiente paso en el que ahora puede cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-133">This will move to the next step where you can now upload the files.</span></span>

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="ffe3b-135">Especifique la ubicación de los archivos corregidos en el cuadro **de texto Ruta de acceso a la ubicación del archivo** y, a continuación, haga clic en **copiar al**portapapeles.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-135">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="ffe3b-136">Pegue el comando en un símbolo del sistema de Windows y presione **entrar** para cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="ffe3b-138">Por último, vuelva a investigaciones de datos (versión preliminar) y haga clic en **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-138">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="ffe3b-139">Cuando se complete el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-139">When processing is complete.</span></span>  <span data-ttu-id="ffe3b-140">Puede volver al conjunto de trabajo y ver el archivo corregido.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-140">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="ffe3b-141">Qué sucede cuando se corrigen los archivos</span><span class="sxs-lookup"><span data-stu-id="ffe3b-141">What happens when files are remediated</span></span>

<span data-ttu-id="ffe3b-142">Cuando se cargan los archivos corregidos, se conservan los metadatos originales, con la excepción de los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="ffe3b-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="ffe3b-143">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="ffe3b-143">ExtractedTextSize</span></span>
- <span data-ttu-id="ffe3b-144">HasText</span><span class="sxs-lookup"><span data-stu-id="ffe3b-144">HasText</span></span>
- <span data-ttu-id="ffe3b-145">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="ffe3b-145">IsErrorRemediate</span></span>
- <span data-ttu-id="ffe3b-146">LoadId</span><span class="sxs-lookup"><span data-stu-id="ffe3b-146">LoadId</span></span>
- <span data-ttu-id="ffe3b-147">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="ffe3b-147">ProcessingErrorMessage</span></span>
- <span data-ttu-id="ffe3b-148">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="ffe3b-148">ProcessingStatus</span></span>
- <span data-ttu-id="ffe3b-149">Texto</span><span class="sxs-lookup"><span data-stu-id="ffe3b-149">Text</span></span>
- <span data-ttu-id="ffe3b-150">WordCount</span><span class="sxs-lookup"><span data-stu-id="ffe3b-150">WordCount</span></span>
- <span data-ttu-id="ffe3b-151">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="ffe3b-151">WorkingsetId</span></span>

<span data-ttu-id="ffe3b-152">Para obtener una definición de todos los campos de metadatos de documentos en las investigaciones de datos (versión preliminar), vea [Document Metadata Fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="ffe3b-152">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
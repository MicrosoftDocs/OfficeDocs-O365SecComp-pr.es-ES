---
title: Corrección de error al procesar los datos
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 82e6d44ded64d586611f429f9b3eebe4f47e9898
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608402"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="7db58-102">Corrección de error al procesar los datos</span><span class="sxs-lookup"><span data-stu-id="7db58-102">Error remediation when processing data</span></span>

<span data-ttu-id="7db58-p101">Corrección de error permite a los administradores de la exhibición de documentos electrónicos la posibilidad de corregir los problemas de datos que impiden que procesar correctamente el contenido de exhibición de documentos electrónicos avanzada (vista previa). Por ejemplo, los archivos que están protegidos con contraseña no se puede procesar ya que los archivos estén bloqueados o se cifran. Con corrección de error, los administradores de exhibición de documentos electrónicos pueden descargar archivos con estos errores, quitar la protección con contraseña y cargar los archivos corregidos con pruebas.</span><span class="sxs-lookup"><span data-stu-id="7db58-p101">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content. For example, files that are password protected cannot be processed since the files are locked or encrypted. Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="7db58-106">Use el siguiente flujo de trabajo para corregir los archivos con errores en los casos de exhibición de documentos electrónicos avanzada (vista previa).</span><span class="sxs-lookup"><span data-stu-id="7db58-106">Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="7db58-107">Creación de una sesión de corrección de error para corregir los archivos con errores de procesamiento</span><span class="sxs-lookup"><span data-stu-id="7db58-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="7db58-108">Si el en cualquier momento durante el procedimiento siguiente, se cierra el Asistente para la corrección de error, puede volver a la sesión de corrección de error desde la ficha **procesamiento** mediante la selección de **correcciones de Error** en el menú desplegable **vista** .</span><span class="sxs-lookup"><span data-stu-id="7db58-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="7db58-109">En la ficha **de procesamiento** en un caso de exhibición de documentos electrónicos avanzada (vista previa), seleccione **errores** en el menú desplegable **vista** .</span><span class="sxs-lookup"><span data-stu-id="7db58-109">On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="7db58-p102">Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto al tipo de error o el tipo de archivo.  En el siguiente ejemplo, nos estamos solucionar relativos a un archivo protegido con contraseña.</span><span class="sxs-lookup"><span data-stu-id="7db58-p102">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.  In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="7db58-112">Haga clic en **+ nuevo corrección de error**.</span><span class="sxs-lookup"><span data-stu-id="7db58-112">Click **+ New error remediation**.</span></span>

    ![Corrección de error](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="7db58-114">La sesión de corrección de error comenzará, empezando por una fase de preparación, donde los archivos con errores que se mueven a una ubicación segura de Azure para ser descargado.</span><span class="sxs-lookup"><span data-stu-id="7db58-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![Preparación de la corrección de error](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="7db58-116">Una vez finalizada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.</span><span class="sxs-lookup"><span data-stu-id="7db58-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="7db58-p103">Para descargar los archivos, especifique la **ruta de acceso de destino para su descarga**; Esto es una ruta de acceso en el equipo local donde se debe descargar el archivo.  La ruta de acceso predeterminada, % USERPROFILE%\Downloads\errors, señala a la carpeta de descargas del usuario que ha iniciado sesión; Esto se puede cambiar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7db58-p103">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.  The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7db58-120">Se recomienda usar una ruta de acceso de archivo local en lugar de una ruta de acceso de red remoto para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="7db58-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7db58-121">Si no ha instalado AzCopy, se pueden instalar desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="7db58-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="7db58-p104">Copie el comando predefinido, haga clic en **Copiar al Portapapeles**. Inicie un símbolo del sistema de windows, pegue el comando y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="7db58-p104">Copy the predefined command by clicking **Copy to clipboard**. Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="7db58-124">Los archivos se descargarán.</span><span class="sxs-lookup"><span data-stu-id="7db58-124">The files will be downloaded.</span></span>

    ![Preparación de la corrección de error](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="7db58-126">Si tiene problemas al ejecutar este comando, vea https://go.microsoft.com/fwlink/?linkid=2038117 sugerencias para resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="7db58-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="7db58-p105">Después de descargar los archivos, puede corregir con una herramienta apropiada. Para archivos protegidos con contraseña, hay un número de contraseñas de herramientas que puede utilizar. Si conoce las contraseñas de los archivos, puede abrirlos y quitar la protección con contraseña.</span><span class="sxs-lookup"><span data-stu-id="7db58-p105">After downloading the files, you can remediate them with an appropriate tool. For password protected files, there are a number of password cracking tools you can use. If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7db58-p106">TI es importante que mantenga los nombres de archivo y la estructura de directorio de los archivos corregidos con pruebas permanecen.  Convenciones de nomenclatura de todos los que se usan en los archivos descargados y carpetas hacen posible asociar los archivos de remdiated al original.</span><span class="sxs-lookup"><span data-stu-id="7db58-p106">IT is important that you retain the directory structure and file names of the remediated files in tact.  All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="7db58-p107">Ahora, vuelva a la exhibición de documentos electrónicos avanzada (vista previa) y haga clic en **siguiente: cargar archivos**.  Se moverán con el paso siguiente donde puede cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="7db58-p107">Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.  This will move to the next step where you can now upload the files.</span></span>

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="7db58-135">Especifique la ubicación de los archivos corregidos con pruebas en el cuadro de texto **ruta de acceso a la ubicación de archivos** , a continuación, haga clic en **Copiar a clibpboard**.</span><span class="sxs-lookup"><span data-stu-id="7db58-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="7db58-136">Pegue el comando en un símbolo del sistema de Windows y presione **ENTRAR** para cargar los archivos.</span><span class="sxs-lookup"><span data-stu-id="7db58-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="7db58-138">Por último, volver a la exhibición de documentos electrónicos avanzada (vista previa) y haga clic en **siguiente: procesar archivos**.</span><span class="sxs-lookup"><span data-stu-id="7db58-138">Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="7db58-p108">Cuando el procesamiento se complete.  Puede devolver el conjunto de trabajo y ver el archivo corregidos con pruebas.</span><span class="sxs-lookup"><span data-stu-id="7db58-p108">When processing is complete.  You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="7db58-141">¿Qué sucede cuando se modifiquen los archivos</span><span class="sxs-lookup"><span data-stu-id="7db58-141">What happens when files are remediated</span></span>

<span data-ttu-id="7db58-142">Cuando se cargan archivos corregidos con pruebas, los metadatos originales se conservan con la excepción de los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7db58-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="7db58-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="7db58-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="7db58-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="7db58-144">ExtractedTextSize</span></span>
- <span data-ttu-id="7db58-145">HasText</span><span class="sxs-lookup"><span data-stu-id="7db58-145">HasText</span></span>
- <span data-ttu-id="7db58-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="7db58-146">IsErrorRemediate</span></span>
- <span data-ttu-id="7db58-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="7db58-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="7db58-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="7db58-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="7db58-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="7db58-149">LoadId</span></span>
- <span data-ttu-id="7db58-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="7db58-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="7db58-151">Procesamiento</span><span class="sxs-lookup"><span data-stu-id="7db58-151">ProcessingStatus</span></span>
- <span data-ttu-id="7db58-152">Text</span><span class="sxs-lookup"><span data-stu-id="7db58-152">Text</span></span>
- <span data-ttu-id="7db58-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="7db58-153">WordCount</span></span>
- <span data-ttu-id="7db58-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="7db58-154">WorkingsetId</span></span>

<span data-ttu-id="7db58-155">Para una definición de todos los campos de metadatos de documento de exhibición de documentos electrónicos avanzada (vista previa), vea [los campos de metadatos del documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="7db58-155">For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
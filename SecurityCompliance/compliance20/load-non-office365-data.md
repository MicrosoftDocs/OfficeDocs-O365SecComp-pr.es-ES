---
title: Cargar datos que no son de Office 365 a un conjunto de revisión
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
description: Importar datos que no son de Office 365 a un conjunto de revisión en un caso de exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: d7609c774e7c8a42e24b22a87fbed271a12a97f5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048112"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="b4595-103">Cargar datos que no son de Office 365 a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="b4595-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="b4595-104">No todos los documentos que debe analizar en la exhibición avanzada de documentos electrónicos se encuentran en Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4595-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="b4595-105">Con la característica de importación de datos no de Office 365 en eDiscovery avanzado, puede cargar documentos que no se encuentran en Office 365 a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b4595-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="b4595-106">En este artículo se muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.</span><span class="sxs-lookup"><span data-stu-id="b4595-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="b4595-107">EDiscovery avanzado requiere una suscripción a Microsoft 365 o a Office 365 E5 para su organización o una suscripción a E3 con la suscripción de complemento de cumplimiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="b4595-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="b4595-108">Si no tiene ese plan y desea probar la exhibición avanzada de documentos electrónicos, puede registrarse para obtener una versión de prueba de Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="b4595-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b4595-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="b4595-109">Before you begin</span></span>

<span data-ttu-id="b4595-110">El uso de la característica de carga que no es de Office 365 que se describe en este artículo requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4595-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="b4595-111">Todos los custodios que desee asociar a contenido que no pertenece a Office 365 deben tener asignada una licencia E5 o una licencia E3 con una licencia de complemento de cumplimiento avanzada.</span><span class="sxs-lookup"><span data-stu-id="b4595-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="b4595-112">Un caso de exhibición avanzada de documentos electrónicos existente.</span><span class="sxs-lookup"><span data-stu-id="b4595-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="b4595-113">Los custodios deben agregarse al caso antes de que pueda cargar y asociar los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4595-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="b4595-114">Los datos que no son de Office 365 deben ser un tipo de archivo compatible con la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="b4595-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="b4595-115">Para obtener más información, consulte [tipos de archivo admitidos en EDiscovery avanzado](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="b4595-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="b4595-116">Todos los archivos que se cargan en un conjunto de revisión deben estar ubicados en carpetas, donde cada carpeta está asociada a un custodio específico.</span><span class="sxs-lookup"><span data-stu-id="b4595-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="b4595-117">Los nombres de estas carpetas deben usar el siguiente formato de nombre: *alias @ domainname*.</span><span class="sxs-lookup"><span data-stu-id="b4595-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="b4595-118">El alias @ domainname debe ser el alias y el dominio de Office 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="b4595-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="b4595-119">Puede recopilar todas las carpetas alias @ domainname en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="b4595-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="b4595-120">La carpeta raíz solo puede contener las carpetas alias @ domainname.</span><span class="sxs-lookup"><span data-stu-id="b4595-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="b4595-121">No se admiten los archivos separados en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="b4595-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="b4595-122">La estructura de carpetas para los datos que no son de Office 365 que desea cargar sería similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4595-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="b4595-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4595-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="b4595-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4595-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="b4595-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b4595-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="b4595-126">Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.</span><span class="sxs-lookup"><span data-stu-id="b4595-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Estructura de carpetas de carga de datos no de Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="b4595-128">Una cuenta asignada al grupo de roles eDiscovery Manager (y agregada como administrador de exhibición de documentos electrónicos).</span><span class="sxs-lookup"><span data-stu-id="b4595-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="b4595-129">La herramienta AzCopy v 8.1 instalada en un equipo que tiene acceso a la estructura de carpetas de contenido no perteneciente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4595-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="b4595-130">Para instalar AzCopy, consulte [transferir datos con azcopy v 8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="b4595-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="b4595-131">Asegúrese de instalar AzCopy en la ubicación predeterminada, que es **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="b4595-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="b4595-132">Debe usar AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="b4595-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="b4595-133">Es posible que otras versiones de AzCopy no funcionen al cargar datos que no son de Office 365 en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="b4595-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="b4595-134">Cargar contenido no de Office 365 en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="b4595-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="b4595-135">Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y, a continuación, el caso en el que se cargarán los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4595-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="b4595-136">Haga clic en **revisar conjuntos**y, a continuación, seleccione el conjunto de revisiones para cargar los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4595-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="b4595-137">Si no tiene un conjunto de revisión, puede crear uno.</span><span class="sxs-lookup"><span data-stu-id="b4595-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="b4595-138">En el conjunto de revisiones, haga clic en **administrar conjunto de revisiones**y, a continuación, haga clic en **Ver cargas** en el mosaico de **datos que no son de Office 365** .</span><span class="sxs-lookup"><span data-stu-id="b4595-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="b4595-139">Haga clic en **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4595-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="b4595-141">El primer paso del asistente prepara una ubicación de almacenamiento de Azure segura proporcionada por Microsoft para cargar los archivos en.</span><span class="sxs-lookup"><span data-stu-id="b4595-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="b4595-142">Una vez completada la preparación, el botón **cargar archivos** se activa.</span><span class="sxs-lookup"><span data-stu-id="b4595-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importación no de Office 365: preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="b4595-144">Haga clic en **siguiente: cargar archivos**.</span><span class="sxs-lookup"><span data-stu-id="b4595-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="b4595-145">En la página **cargar archivos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4595-145">On the **Upload files** page, do the following:</span></span>

   ![No Office 365 Import: upload files](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="b4595-147">a.</span><span class="sxs-lookup"><span data-stu-id="b4595-147">a.</span></span> <span data-ttu-id="b4595-148">En el cuadro **ruta de acceso a la ubicación de los archivos** , compruebe o escriba la ubicación de la carpeta raíz donde almacenó los datos que no son de Office 365 que desea cargar.</span><span class="sxs-lookup"><span data-stu-id="b4595-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="b4595-149">Por ejemplo, para la ubicación de los archivos de ejemplo que se muestran en la **sección antes de comenzar**, debe escribir **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="b4595-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="b4595-150">Si se proporciona la ubicación correcta, se asegurará de que el comando AzCopy que se muestra en Box en la ruta se haya actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4595-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="b4595-151">b.</span><span class="sxs-lookup"><span data-stu-id="b4595-151">b.</span></span> <span data-ttu-id="b4595-152">Haga clic en **copiar al** portapapeles para copiar el comando que se muestra en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="b4595-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="b4595-153">Inicie un símbolo del sistema de Windows, pegue el comando que copió en el paso anterior y, a continuación, presione **entrar** para iniciar el comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="b4595-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="b4595-154">Después de iniciar el comando, los archivos que no son de Office 365 se cargarán en la ubicación de almacenamiento de Azure que se preparó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="b4595-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importación no de Office 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="b4595-156">Como se indicó anteriormente, debe usar AzCopy v 8.1 para usar correctamente el comando que se proporciona en la página **cargar archivos** .</span><span class="sxs-lookup"><span data-stu-id="b4595-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="b4595-157">Si el comando AzCopy proporcionado no se produce, consulte [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="b4595-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="b4595-158">Vuelva al centro de cumplimiento de & de seguridad y haga clic en **siguiente: procesar archivos** en el asistente.</span><span class="sxs-lookup"><span data-stu-id="b4595-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="b4595-159">Esto inicia el procesamiento, la extracción de texto y la indización de los archivos que no son de Office 365 que se cargaron en la ubicación de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="b4595-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="b4595-160">Realice un seguimiento del progreso del procesamiento de los archivos que no son de Office 365 en la página **procesar archivos** o en la ficha **trabajos** mediante la visualización de un trabajo denominado **adición de datos que no son de Office 365 a un conjunto de revisión**.</span><span class="sxs-lookup"><span data-stu-id="b4595-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="b4595-161">Una vez finalizado el trabajo, los nuevos archivos estarán disponibles en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="b4595-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importación no de Office 365: procesar archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="b4595-163">Una vez finalizado el procesamiento, puede cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="b4595-163">After the processing is finished, you can close the wizard.</span></span>
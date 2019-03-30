---
title: Importar contenido no de Office 365 para el análisis avanzado de eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Pasos para importar contenido que no está almacenado en O365 en un BLOB de Azure para que se pueda analizar con AeD
ms.openlocfilehash: 7b7694754b26951aa02930fd101631ba9060bc17
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001173"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="ca49d-103">Importar contenido no de Office 365 para el análisis avanzado de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ca49d-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="ca49d-104">No todos los documentos que puede que necesite analizar con Office 365 Advanced eDiscovery residirán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca49d-104">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="ca49d-105">Con la característica de importación de contenido no de Office 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Office 365 (excepto los archivos PST) en un caso vinculado al BLOB de almacenamiento de Azure y analizarlo con la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ca49d-105">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="ca49d-106">Este procedimiento muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.</span><span class="sxs-lookup"><span data-stu-id="ca49d-106">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca49d-p102">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ca49d-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ca49d-109">Puede adquirir una suscripción de complemento de almacenamiento de datos de eDiscovery avanzado de Office 365 para el contenido que no es de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca49d-109">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content.</span></span> <span data-ttu-id="ca49d-110">Esto está disponible exclusivamente para el contenido que se va a analizar con la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ca49d-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="ca49d-111">Siga los pasos descritos en [Buy or Edit and Add-in for office 365 for Business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) y compre el complemento de almacenamiento avanzado de exhibición de documentos electrónicos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca49d-111">Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ca49d-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ca49d-112">Before you begin</span></span>

<span data-ttu-id="ca49d-113">El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:</span><span class="sxs-lookup"><span data-stu-id="ca49d-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="ca49d-114">Un complemento de Office 365 E3 con Advanced Compliance o de la suscripción a E5</span><span class="sxs-lookup"><span data-stu-id="ca49d-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="ca49d-115">Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargarán deben tener E3 con las licencias del complemento de cumplimiento avanzado o E5.</span><span class="sxs-lookup"><span data-stu-id="ca49d-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="ca49d-116">Un caso de eDiscovery existente</span><span class="sxs-lookup"><span data-stu-id="ca49d-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="ca49d-117">Todos los archivos que se van a cargar se recopilan en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentra en el formato de *alias @ nombredominio* .</span><span class="sxs-lookup"><span data-stu-id="ca49d-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="ca49d-118">El *alias @ domainname* debe ser users Office 365 alias y dominio.</span><span class="sxs-lookup"><span data-stu-id="ca49d-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="ca49d-119">Puede recopilar todas las carpetas *alias @ domainname* en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="ca49d-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="ca49d-120">La carpeta raíz solo puede contener las carpetas *alias @ domainname* , no debe haber archivos sueltos en la carpeta raíz</span><span class="sxs-lookup"><span data-stu-id="ca49d-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="ca49d-121">Una cuenta que sea administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="ca49d-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="ca49d-122">[Herramientas de almacenamiento de Microsoft Azure](https://aka.ms/downloadazcopy) instaladas en un equipo que tiene acceso a la estructura de carpetas de contenido no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca49d-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="ca49d-123">Cargar contenido no de Office 365 en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="ca49d-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="ca49d-124">Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, Abra **eDiscovery**y abra el caso en el que se cargarán los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca49d-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="ca49d-125">Si necesita crear un caso, consulte [administrar casos de eDiscovery en el centro de seguridad &amp; y cumplimiento de Office 365](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="ca49d-125">If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="ca49d-126">Haga clic en **cambiar a exhibición avanzada de** documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="ca49d-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="ca49d-127">En **tipo de origen** , seleccione **datos que no son de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="ca49d-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="ca49d-128">Haga clic en **Agregar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="ca49d-128">Click **Add container**.</span></span> <span data-ttu-id="ca49d-129">Asigne un nombre al contenedor y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="ca49d-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="ca49d-130">Seleccione el contenedor recién agregado de la lista de contenedores y copie la dirección URL que aparece en el panel de detalles del contenedor y, a continuación, cierre el panel.</span><span class="sxs-lookup"><span data-stu-id="ca49d-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="ca49d-131">Abra un símbolo del sistema como administrador y cambie el directorio a la carpeta donde está instalado AzCopy.</span><span class="sxs-lookup"><span data-stu-id="ca49d-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="ca49d-132">Construya la línea de comandos de AzCopy para cargar los archivos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ca49d-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="ca49d-133">AzCopy/Source: " *ruta de acceso completa a la carpeta raíz en el equipo local* "/dest: " *dirección URL del contenedor hasta el? o sin incluir el?*</span><span class="sxs-lookup"><span data-stu-id="ca49d-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="ca49d-134">"/DestSAS:" *resto de la dirección URL del contenedor del? al final* "/S.</span><span class="sxs-lookup"><span data-stu-id="ca49d-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="ca49d-135">Por ejemplo, con estos valores:</span><span class="sxs-lookup"><span data-stu-id="ca49d-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="ca49d-136">carpeta raíz: datos de C:\Collected</span><span class="sxs-lookup"><span data-stu-id="ca49d-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="ca49d-137">Dirección URL del https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&ampcontenedor-; Sr&amp;= c si = NonOfficeData15&amp;% 7C0 SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D</span><span class="sxs-lookup"><span data-stu-id="ca49d-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="ca49d-138">la sintaxis de la línea de comandos de AzCopy sería:</span><span class="sxs-lookup"><span data-stu-id="ca49d-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="ca49d-139">Para obtener más información sobre la sintaxis de Azcopy, consulte [transferir datos con Azcopy en Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span><span class="sxs-lookup"><span data-stu-id="ca49d-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ca49d-140">Debe haber una carpeta raíz por usuario y el nombre de la carpeta debe tener el formato *alias @ nombreDeDominio* .</span><span class="sxs-lookup"><span data-stu-id="ca49d-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="ca49d-141">Una vez que las carpetas terminen de cargarse, vuelva a la exhibición avanzada de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ca49d-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="ca49d-142">El contenido de las carpetas que cargó ya está listo para su procesamiento en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="ca49d-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="ca49d-143">Seleccione el contenedor y haga clic en el botón procesar.</span><span class="sxs-lookup"><span data-stu-id="ca49d-143">Select the container and click the Process button.</span></span> <span data-ttu-id="ca49d-144">Para obtener más información sobre el procesamiento avanzado de eDiscovery, vea [ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="ca49d-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ca49d-145">Una vez que el contenedor se procesa correctamente en eDiscovery avanzado, ya no podrá agregar nuevo contenido al almacenamiento SAS en Azure.</span><span class="sxs-lookup"><span data-stu-id="ca49d-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="ca49d-146">Si recopila contenido adicional y desea agregarlo al análisis de eDiscovery avanzado, debe crear un nuevo contenedor de **datos distinto de Office 365** y repetir este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ca49d-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ca49d-147">Si el contenedor *no se procesa correctamente debido a problemas de nombres de carpeta* y, a continuación, soluciona los problemas, deberá crear un nuevo contenedor y volver a conectar y cargar de nuevo con los procedimientos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ca49d-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  


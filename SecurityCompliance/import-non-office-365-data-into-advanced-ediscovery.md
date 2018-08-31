---
title: Importar contenido que no sea de Office 365 para el análisis de eDiscovery avanzado
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Cómo a pasos para importar el contenido que no se almacena en O365 en un Azure blob para que se puede analizar con donde
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536860"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="2ec06-103">Importar contenido que no sea de Office 365 para el análisis de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="2ec06-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="2ec06-p101">No todos los documentos que necesita analizar con Office 365 avanzada eDiscovery residirá en Office 365. Con el contenido que no son Office 365 importar característica de exhibición de documentos electrónicos avanzada que puede cargar documentos que no Live Meeting en Office 365 (excepto los archivos PST) a un blob de almacenamiento vinculado, Azure mayúsculas y análisis de ellos con avanzadas exhibición de documentos electrónicos. Este procedimiento muestra cómo incorporar los documentos que no sean Office 365 en la exhibición de documentos electrónicos avanzada para el análisis.</span><span class="sxs-lookup"><span data-stu-id="2ec06-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ec06-p102">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2ec06-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2ec06-p103">Puede adquirir una suscripción de Office 365 avanzada de exhibición de documentos electrónicos datos almacenamiento complementario para el contenido que no sean Office 365. Esto está disponible exclusivamente para el contenido que va a analizarse con avanzadas exhibición de documentos electrónicos. Siga los pasos descritos en [comprar o editar y complemento de Office 365 para profesionales](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) y el complemento Office 365 avanzada de almacenamiento de exhibición de documentos electrónicos de compra.</span><span class="sxs-lookup"><span data-stu-id="2ec06-p103">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content. This is exclusively available for content that is to be analyzed with Advanced eDiscovery. Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2ec06-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2ec06-112">Before you begin</span></span>

<span data-ttu-id="2ec06-113">Uso de la característica de carga no Office 365 tal como se describe en este procedimiento requiere que tenga:</span><span class="sxs-lookup"><span data-stu-id="2ec06-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="2ec06-114">Un equipo con Office 365 E3 con complemento de cumplimiento avanzadas o suscripción E5</span><span class="sxs-lookup"><span data-stu-id="2ec06-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="2ec06-115">Todos los Custodios cuyo contenido que no sean Office 365 se cargará deben tener E3 con complemento de cumplimiento avanzadas o licencias E5</span><span class="sxs-lookup"><span data-stu-id="2ec06-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="2ec06-116">Un caso de exhibición de documentos electrónicos existentes</span><span class="sxs-lookup"><span data-stu-id="2ec06-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="2ec06-p104">Todos los archivos para cargar se recopilan en carpetas donde hay una carpeta por custodia y es el nombre de las carpetas en este formato *alias@domainname* . El *alias@domainname* debe ser dominio y alias de los usuarios de Office 365. Puede recopilar todas las carpetas de *alias@domainname* en una carpeta raíz. La carpeta raíz sólo puede contener las carpetas *alias@domainname* , no debe haber ningún archivos separados en la carpeta raíz</span><span class="sxs-lookup"><span data-stu-id="2ec06-p104">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  . The  *alias@domainname*  must be users Office 365 alias and domain. You can collect all the  *alias@domainname*  folders into a root folder. The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="2ec06-121">Una cuenta que sea una exhibición de documentos electrónicos Manager o la exhibición de documentos electrónicos administrador</span><span class="sxs-lookup"><span data-stu-id="2ec06-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="2ec06-122">[Herramientas de almacenamiento de información de Microsoft Azure](https://aka.ms/downloadazcopy) instalado en un equipo que tenga acceso a la estructura de la carpeta de contenido que no sean Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ec06-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="2ec06-123">Cargar contenido que no sean Office 365 en la exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="2ec06-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="2ec06-p105">Como una exhibición de documentos electrónicos Manager o la exhibición de documentos electrónicos administrador, abra la **exhibición de documentos electrónicos**y abrir el caso de que los datos que no sean Office 365 se cargará en. Si necesita crear un caso, vea [administrar casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="2ec06-p105">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to. If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="2ec06-126">Haga clic en **cambiar para exhibición de documentos electrónicos avanzada**</span><span class="sxs-lookup"><span data-stu-id="2ec06-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="2ec06-127">En **tipo de origen** , seleccione **datos no Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2ec06-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="2ec06-p106">Haga clic en **Agregar contenedor**. Nombre del contenedor y agregar una descripción.</span><span class="sxs-lookup"><span data-stu-id="2ec06-p106">Click **Add container**. Name the container and add a description.</span></span>
    
5. <span data-ttu-id="2ec06-130">Seleccione el contenedor recién agregado en la lista de contenedor y copie la dirección URL que aparece en el panel de detalles del contenedor y, a continuación, cierre el panel</span><span class="sxs-lookup"><span data-stu-id="2ec06-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="2ec06-131">Abra un símbolo del sistema como administrador y cambie el directorio a la carpeta donde ha instalado el AzCopy..</span><span class="sxs-lookup"><span data-stu-id="2ec06-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="2ec06-132">Construir la línea de comandos AzCopy para cargar los archivos como este:</span><span class="sxs-lookup"><span data-stu-id="2ec06-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="2ec06-p107">¿AzCopy /Source: " *ruta de acceso completa a la carpeta raíz en el equipo local* " / dest: " *dirección URL de contenedor hasta, pero sin incluir el?* " /DestSAS: " *resto de la dirección url de contenedor de la? al final* "/ S.</span><span class="sxs-lookup"><span data-stu-id="2ec06-p107">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*  " /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="2ec06-135">Por ejemplo, con estos valores:</span><span class="sxs-lookup"><span data-stu-id="2ec06-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="2ec06-136">carpeta raíz - C:\Collected datos</span><span class="sxs-lookup"><span data-stu-id="2ec06-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="2ec06-137">dirección url de contenedor - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA % 3D</span><span class="sxs-lookup"><span data-stu-id="2ec06-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="2ec06-138">la sintaxis de línea de comandos de AzCopy sería el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ec06-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="2ec06-139">Para obtener más información sobre Azcopy sintaxis, consulte [transferir datos con el AzCopy en Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span><span class="sxs-lookup"><span data-stu-id="2ec06-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2ec06-140">Debe haber una carpeta raíz por usuario y el nombre de la carpeta debe tener el formato *alias@domainname* .</span><span class="sxs-lookup"><span data-stu-id="2ec06-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="2ec06-p108">Una vez han terminado las carpetas cargar, volver a la exhibición de documentos electrónicos avanzada. El contenido de las carpetas que ha cargado ahora está listo para ser procesado en la exhibición de documentos electrónicos avanzada. Seleccione el contenedor y haga clic en el botón de proceso. Para obtener más detalles sobre la exhibición de documentos electrónicos avanzada vea procesamiento, [ejecute el módulo de proceso y carga de datos en la exhibición de documentos electrónicos avanzada de Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="2ec06-p108">Once the folders have finished uploading, switch back to Advanced eDiscovery. The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery. Select the container and click the Process button. For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2ec06-p109">Una vez que el contenedor se procesa correctamente en la exhibición de documentos electrónicos avanzada, ya no podrá agregar nuevo contenido al almacenamiento SAS en Azure. Si recopilar contenido adicional y que desee agregar el caso para el análisis de exhibición de documentos electrónicos avanzada, debe crear un nuevo contenedor de **datos que no son de Office 365** y repita este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2ec06-p109">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure. If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="2ec06-147">Si el contenedor *no procesa correctamente debido a problemas de nomenclatura de carpeta* y, a continuación, solucionar los problemas, debe seguir crear un nuevo contenedor y volver a conectar y cargar nuevo mediante los procedimientos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="2ec06-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  


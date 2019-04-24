---
title: Cargar datos que no son de Office 365 en pruebas
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
ms.openlocfilehash: f5478d89d71db22e710b5d5fcab397ae8d6aee56
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259568"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="17217-102">Cargar datos que no son de Office 365 en pruebas</span><span class="sxs-lookup"><span data-stu-id="17217-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="17217-103">No todos los documentos que puede que necesite analizar con Office 365 Advanced eDiscovery residirán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="17217-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="17217-104">Con la característica de importación de contenido no de Office 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Office 365 en un conjunto de trabajo para que se analice con eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="17217-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="17217-105">Este procedimiento muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.</span><span class="sxs-lookup"><span data-stu-id="17217-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="17217-106">EDiscovery avanzado requiere un Office 365 E3 con el complemento Advanced Compliance o una suscripción a e5 para su organización.</span><span class="sxs-lookup"><span data-stu-id="17217-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="17217-107">Si no tiene ese plan y desea probar la exhibición avanzada de documentos electrónicos, puede registrarse para obtener una versión de prueba de Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="17217-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="17217-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="17217-108">Before you begin</span></span>
<span data-ttu-id="17217-109">El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:</span><span class="sxs-lookup"><span data-stu-id="17217-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="17217-110">Una suscripción a Office 365 E3 con Advanced Compliance Add-on o E5.</span><span class="sxs-lookup"><span data-stu-id="17217-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="17217-111">Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargarán deben tener E3 con las licencias del complemento de cumplimiento avanzado o E5.</span><span class="sxs-lookup"><span data-stu-id="17217-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="17217-112">Un caso de eDiscovery existente.</span><span class="sxs-lookup"><span data-stu-id="17217-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="17217-113">Todos los archivos que se van a cargar se recopilan en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentra en el formato de *alias @ nombredominio* .</span><span class="sxs-lookup"><span data-stu-id="17217-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="17217-114">El *alias @ domainname* debe ser users Office 365 alias y dominio.</span><span class="sxs-lookup"><span data-stu-id="17217-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="17217-115">Puede recopilar todas las carpetas *alias @ domainname* en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="17217-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="17217-116">La carpeta raíz solo puede contener las carpetas *alias @ domainname* , no debe haber archivos sueltos en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="17217-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="17217-117">Una cuenta que sea un administrador de eDiscovery o un administrador de exhibición de documentos electrónicos herramientas de almacenamiento de Microsoft Azure instaladas en un equipo que tenga acceso a la estructura de carpetas de contenido no Office 365.</span><span class="sxs-lookup"><span data-stu-id="17217-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="17217-118">Instale AzCopy, que puede hacer desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="17217-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="17217-119">Cargar contenido no de Office 365 en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="17217-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="17217-120">Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y, a continuación, el caso en el que se cargarán los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="17217-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="17217-121">Haga clic en la ficha **conjuntos de trabajo** y, a continuación, seleccione el conjunto de trabajo en el que desea cargar los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="17217-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="17217-122">Si todavía no ha creado un conjunto de trabajo, puede hacerlo ahora.</span><span class="sxs-lookup"><span data-stu-id="17217-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="17217-123">Por último, haga clic en **administrar el conjunto de trabajo** y, a continuación, **Ver cargas** en la sección de datos que no son de Office 365</span><span class="sxs-lookup"><span data-stu-id="17217-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="17217-124">Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="17217-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="17217-126">El primer paso del asistente simplemente prepara un BLOB seguro de Azure para los archivos que se van a cargar.</span><span class="sxs-lookup"><span data-stu-id="17217-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="17217-127">Una vez que se compelted la preparación, haga clic en el botón **cargar archivos** .</span><span class="sxs-lookup"><span data-stu-id="17217-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Importación no de Office 365-preparación](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="17217-129">En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de los archivos**, aquí es donde se ubican los datos que no son de Office 365 que tiene previsto importar.</span><span class="sxs-lookup"><span data-stu-id="17217-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="17217-130">La configuración de la ubicación correcta asegura que el comando AzCopy se haya actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="17217-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="17217-131">Si todavía no ha instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="17217-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="17217-132">Copie el comando predefinido haciendo clic en el vínculo **copiar al** portapapeles.</span><span class="sxs-lookup"><span data-stu-id="17217-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="17217-133">Inicie un símbolo del sistema de Windows, pegue el comando y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="17217-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="17217-134">Los archivos se cargarán en el almacenamiento de blobs seguro de Azure para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="17217-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Importación no de Office 365: cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![No Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="17217-137">Por último, vuelva al cumplimiento de & de seguridad y haga clic en el botón **siguiente: procesar archivos** .</span><span class="sxs-lookup"><span data-stu-id="17217-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="17217-138">Se iniciará el procesamiento, la extracción de texto y la indización de los archivos cargados.</span><span class="sxs-lookup"><span data-stu-id="17217-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="17217-139">Puede realizar un seguimiento del progreso del procesamiento aquí o en la pestaña **trabajos** .  Una vez completados, los nuevos archivos estarán disponibles en el conjunto de trabajo.</span><span class="sxs-lookup"><span data-stu-id="17217-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="17217-140">Una vez que se haya completado el procesamiento, puede descartar el asistente.</span><span class="sxs-lookup"><span data-stu-id="17217-140">Once processing is complete, you can dismiss the wizard.</span></span>

![Archivos que no son de Office 365 importación-proceso](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


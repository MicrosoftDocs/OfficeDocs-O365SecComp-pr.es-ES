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
description: ''
ms.openlocfilehash: 86d858994f95176ea4d415405c4043f7e7c5308e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155012"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="28940-102">Cargar datos que no son de Office 365 a un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="28940-102">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="28940-103">No todos los documentos que puede que necesite analizar con Office 365 Advanced eDiscovery residirán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="28940-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="28940-104">Con la característica de importación de contenido no de Office 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Office 365 en un conjunto de revisión para que se analice con eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="28940-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a review set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="28940-105">Este procedimiento muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.</span><span class="sxs-lookup"><span data-stu-id="28940-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="28940-106">EDiscovery avanzado requiere un Office 365 E3 con el complemento Advanced Compliance o una suscripción a e5 para su organización.</span><span class="sxs-lookup"><span data-stu-id="28940-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="28940-107">Si no tiene ese plan y desea probar la exhibición avanzada de documentos electrónicos, puede registrarse para obtener una versión de prueba de Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="28940-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28940-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="28940-108">Before you begin</span></span>

<span data-ttu-id="28940-109">El uso de la característica cargar no de Office 365 tal y como se describe en este artículo requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28940-109">Using the upload Non-Office 365 feature as described in this article requires that you have the following:</span></span>

- <span data-ttu-id="28940-110">Una suscripción de Office 365 o Microsoft 365 E5 o una suscripción a E3 con la suscripción de complemento de cumplimiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="28940-110">An Office 365 or Microsoft 365 E5 subscription or an E3 subscription with the Advanced Compliance add-on subscription.</span></span>

- <span data-ttu-id="28940-111">Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargará deben tener una licencia E3 con una licencia de complemento de cumplimiento avanzado o tener una licencia E5.</span><span class="sxs-lookup"><span data-stu-id="28940-111">All custodians whose non-Office 365 content will be uploaded must have E3 license with an Advanced Compliance add-on license or have an E5 license.</span></span>

- <span data-ttu-id="28940-112">Un caso de exhibición avanzada de documentos electrónicos existente.</span><span class="sxs-lookup"><span data-stu-id="28940-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="28940-113">Se deben agregar custodios al caso antes de cargar los datos que no son de Office 365 asociados a ellos.</span><span class="sxs-lookup"><span data-stu-id="28940-113">Custodians must be added to the case before you upload the non-Office 365 data that's associated to them.</span></span>

- <span data-ttu-id="28940-114">Todos los archivos que se cargarán deben encontrarse en carpetas, donde cada carpeta está asociada a un custodio específico.</span><span class="sxs-lookup"><span data-stu-id="28940-114">All files that will be uploaded must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="28940-115">Los nombres de estas carpetas deben usar el siguiente formato de nombre: *alias @ domainname*.</span><span class="sxs-lookup"><span data-stu-id="28940-115">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="28940-116">El *alias @ domainname* debe ser el alias y el dominio de Office 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="28940-116">The *alias@domainname* must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="28940-117">Puede recopilar todas las carpetas *alias @ domainname* en una carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="28940-117">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="28940-118">La carpeta raíz solo puede contener las carpetas *alias @ domainname* ; los archivos sueltos no se permiten en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="28940-118">The root folder can only contain the *alias@domainname* folders; loose files aren't allowed in the root folder.</span></span>

   <span data-ttu-id="28940-119">Por ejemplo, la estructura de carpetas para los datos que no son de Office 365 que desea cargar sería similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="28940-119">For example, the folder structure for the non-Office 365 data that you want to upload would be similar to the following:</span></span>

   - <span data-ttu-id="28940-120">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="28940-120">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="28940-121">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="28940-121">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="28940-122">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="28940-122">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="28940-123">Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.</span><span class="sxs-lookup"><span data-stu-id="28940-123">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Estructura de carpetas de carga de datos no de Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="28940-125">Una cuenta que sea administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="28940-125">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>

- <span data-ttu-id="28940-126">Herramientas de almacenamiento de Microsoft Azure instaladas en un equipo que tiene acceso a la estructura de carpetas de contenido no Office 365.</span><span class="sxs-lookup"><span data-stu-id="28940-126">Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="28940-127">Instale AzCopy, que puede hacer desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="28940-127">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="28940-128">Cargar contenido no de Office 365 en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="28940-128">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="28940-129">Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y, a continuación, el caso en el que se cargarán los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="28940-129">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="28940-130">Haga clic en la pestaña **Review sets** y, a continuación, seleccione el conjunto de revisión en el que desea cargar los datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="28940-130">Click the **review sets** tab, then select the review set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="28940-131">Si aún no ha creado un conjunto de revisiones, puede hacerlo ahora.</span><span class="sxs-lookup"><span data-stu-id="28940-131">If you have not already created a review set, you can do so now.</span></span>  <span data-ttu-id="28940-132">Por último, haga clic en **administrar conjunto de revisiones** y, a continuación, haga clic en **Ver cargas** en el mosaico de datos \* \* que no es de Office 365.</span><span class="sxs-lookup"><span data-stu-id="28940-132">Finally, click **Manage review set** and then click **View uploads** in the \*\*Non-Office 365 data tile.</span></span>

2. <span data-ttu-id="28940-133">Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.</span><span class="sxs-lookup"><span data-stu-id="28940-133">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="28940-135">El primer paso del asistente simplemente prepara un BLOB seguro de Azure para los archivos que se van a cargar.</span><span class="sxs-lookup"><span data-stu-id="28940-135">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="28940-136">Una vez completada la preparación, haga clic en el botón **cargar archivos** .</span><span class="sxs-lookup"><span data-stu-id="28940-136">Once preparation is completed, click the **Next: Upload files** button.</span></span>

   ![Importación no de Office 365-preparación](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="28940-138">En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de los archivos**, aquí es donde se ubican los datos que no son de Office 365 que tiene previsto importar.</span><span class="sxs-lookup"><span data-stu-id="28940-138">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="28940-139">La configuración de la ubicación correcta asegura que el comando AzCopy se haya actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="28940-139">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

   > [!NOTE]
   > <span data-ttu-id="28940-140">Si todavía no ha instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="28940-140">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="28940-141">Copie el comando predefinido haciendo clic en el vínculo **copiar al** portapapeles.</span><span class="sxs-lookup"><span data-stu-id="28940-141">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="28940-142">Inicie un símbolo del sistema de Windows, pegue el comando y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="28940-142">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="28940-143">Los archivos se cargarán en el almacenamiento de blobs seguro de Azure para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="28940-143">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

   ![Importación no de Office 365: cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![No Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="28940-146">Si se produce un error en el comando AzCopy proporcionado, consulte [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md) .</span><span class="sxs-lookup"><span data-stu-id="28940-146">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

6. <span data-ttu-id="28940-147">Por último, vuelva al cumplimiento de & de seguridad y haga clic en el botón **siguiente: procesar archivos** .</span><span class="sxs-lookup"><span data-stu-id="28940-147">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="28940-148">Se iniciará el procesamiento, la extracción de texto y la indización de los archivos cargados.</span><span class="sxs-lookup"><span data-stu-id="28940-148">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="28940-149">Puede realizar un seguimiento del progreso del procesamiento aquí o en la pestaña **trabajos** .  Una vez completados, los nuevos archivos estarán disponibles en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="28940-149">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the review set.</span></span>  <span data-ttu-id="28940-150">Una vez que se haya completado el procesamiento, puede descartar el asistente.</span><span class="sxs-lookup"><span data-stu-id="28940-150">Once processing is complete, you can dismiss the wizard.</span></span>

   ![Archivos que no son de Office 365 importación-proceso](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


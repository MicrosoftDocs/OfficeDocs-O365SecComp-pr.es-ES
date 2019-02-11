---
title: Cargar datos que no son de Office 365 a un conjunto de trabajo
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
ms.openlocfilehash: 1dad52075303450673e7f48b87e2952e35629a5e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706091"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="9060f-102">Cargar datos que no son de Office 365 a un conjunto de trabajo</span><span class="sxs-lookup"><span data-stu-id="9060f-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="9060f-p101">No todos los documentos que necesita analizar con Office 365 avanzada eDiscovery residirá en Office 365. Con el contenido que no son Office 365 importar característica de exhibición de documentos electrónicos avanzada que puede cargar documentos que no live en Office 365 en un conjunto de trabajo, por lo que se analiza con avanzadas exhibición de documentos electrónicos. Este procedimiento muestra cómo incorporar los documentos que no sean Office 365 en la exhibición de documentos electrónicos avanzada para el análisis.</span><span class="sxs-lookup"><span data-stu-id="9060f-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="9060f-p102">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede registrarse para una prueba de Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="9060f-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9060f-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="9060f-108">Before you begin</span></span>
<span data-ttu-id="9060f-109">Uso de la característica de carga no Office 365 tal como se describe en este procedimiento requiere que tenga:</span><span class="sxs-lookup"><span data-stu-id="9060f-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="9060f-110">Un Office 365 E3 con complemento de cumplimiento avanzadas o suscripción E5.</span><span class="sxs-lookup"><span data-stu-id="9060f-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="9060f-111">Todos los Custodios cuyo contenido que no sean Office 365 se cargará deben tener E3 con complemento de cumplimiento avanzadas o licencias E5.</span><span class="sxs-lookup"><span data-stu-id="9060f-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="9060f-112">Un caso de exhibición de documentos electrónicos existentes.</span><span class="sxs-lookup"><span data-stu-id="9060f-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="9060f-p103">Todos los archivos para cargar se recopilan en carpetas donde hay una carpeta por custodia y es el nombre de las carpetas en este formato *alias@domainname* . El *alias@domainname* debe ser dominio y alias de los usuarios de Office 365. Puede recopilar todas las carpetas de *alias@domainname* en una carpeta raíz. La carpeta raíz sólo puede contener las carpetas *alias@domainname* , no debe haber ningún archivos separados en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="9060f-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="9060f-117">Una cuenta que es un administrador de exhibición de documentos electrónicos o exhibición de documentos electrónicos Administrador Microsoft Azure almacenamiento herramientas instalado en un equipo que tenga acceso a la estructura de la carpeta de contenido que no sean Office 365.</span><span class="sxs-lookup"><span data-stu-id="9060f-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="9060f-118">Instalar AzCopy, que se puede realizar desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="9060f-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="9060f-119">Cargar contenido que no sean Office 365 en la exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="9060f-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="9060f-p104">Como una exhibición de documentos electrónicos Manager o la exhibición de documentos electrónicos administrador, abra la exhibición de documentos electrónicos avanzada, a continuación, en el caso de que los datos que no sean Office 365 se cargará en.  Haga clic en la ficha **conjuntos de trabajo** y, a continuación, seleccione el conjunto de trabajo que desea cargar los datos que no son de Office 365 para.  Si aún no ha creado un conjunto de trabajo, puede hacerlo ahora.  Por último, haga clic en **establece el funcionamiento de administrar** **cargas de vista** en la sección de datos que no son de Office 365</span><span class="sxs-lookup"><span data-stu-id="9060f-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="9060f-124">Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos que no son de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9060f-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="9060f-p105">El primer paso en el Asistente para simplemente prepara un blob de Azure seguro para los archivos que se va a cargar.  Una vez que la preparación del es compelted, haga clic en el **siguiente: cargar archivos** botón.</span><span class="sxs-lookup"><span data-stu-id="9060f-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![No son de Office 365-importar: preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="9060f-p106">En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de archivos**, esto es donde se encuentran los datos no Office 365 que piensa acerca de la importación.  Establecer la ubicación correcta, asegura la AzCopy comando se actualiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="9060f-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="9060f-131">Si no tiene instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="9060f-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="9060f-p107">Copie el comando predefinido, haga clic en el vínculo **Copiar al Portapapeles** . Inicie un símbolo del sistema de windows, pegue el comando y presione ENTRAR.  Los archivos se cargarán en el almacenamiento de blobs de Azure seguro para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="9060f-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Importación de no-Office 365 - cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Importación de no son de Office 365 - AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="9060f-p108">Por último, volver a la & cumplimiento de seguridad y haga clic en el **siguiente: procesar archivos** botón.  Se iniciará el procesamiento, extracción de texto e indización de los archivos cargados.  Puede realizar un seguimiento del progreso de procesamiento aquí o en la ficha **trabajos** .  Una vez completado, los nuevos archivos estará disponibles en el conjunto de trabajo.  Una vez finalizado el procesamiento, puede pasar por alto al asistente.</span><span class="sxs-lookup"><span data-stu-id="9060f-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![Importación de no-Office 365 - proceso de archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


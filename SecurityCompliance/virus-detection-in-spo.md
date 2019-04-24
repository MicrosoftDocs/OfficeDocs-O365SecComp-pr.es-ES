---
title: Detección de virus en SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/14/2019
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online. Los archivos se examinan en busca de virus una vez cargados. Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.
ms.openlocfilehash: d4f18c84935d9c6e1d3f135bbda6c40737956ae7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266834"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="fdfa3-105">Detección de virus en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fdfa3-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="fdfa3-106">Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="fdfa3-107">Los archivos se examinan en busca de virus una vez cargados.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-107">Files are scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="fdfa3-108">Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fdfa3-109">Estas capacidades antivirus de SharePoint Online son una forma de contener virus.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="fdfa3-110">No pretenden ser un punto único de defensa contra el malware en su entorno.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="fdfa3-111">Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="fdfa3-112">Para obtener más información acerca de las estrategias y los procedimientos recomendados, vea [procedimientos recomendados de seguridad para Office 365](security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="fdfa3-112">For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="fdfa3-113">¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="fdfa3-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="fdfa3-114">Office 365 usa un motor de detección de virus común.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="fdfa3-115">El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina los archivos después de que se cargan.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-115">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="fdfa3-116">Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-116">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="fdfa3-117">En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-117">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="fdfa3-118">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="fdfa3-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="fdfa3-119">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="fdfa3-120">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="fdfa3-121">Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="fdfa3-122">¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?</span><span class="sxs-lookup"><span data-stu-id="fdfa3-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="fdfa3-123">Si un archivo está infectado con un virus, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="fdfa3-124">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="fdfa3-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="fdfa3-125">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="fdfa3-126">Al usuario se le advierte de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="fdfa3-127">Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-127">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="fdfa3-128">Puede usar el cmdlet Set-SPOTenant con el parámetro **DisallowInfectedFileDownload** para no permitir que los usuarios descarguen un archivo detectado, incluso en la ventana de advertencia de antivirus.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-128">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="fdfa3-129">Consulte [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="fdfa3-129">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="fdfa3-130">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="fdfa3-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="fdfa3-131">Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive. exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove. exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="fdfa3-132">El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="fdfa3-132">The sync client will display a notification that the file can't be synced.</span></span>
  


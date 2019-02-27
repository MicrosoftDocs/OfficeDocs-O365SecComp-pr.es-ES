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
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276240"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="20e94-105">Detección de virus en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="20e94-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="20e94-p102">Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online. Los archivos se examinan en busca de virus una vez cargados. Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="20e94-p102">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online. Files are scanned for viruses after they are uploaded. If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="20e94-p103">Estas capacidades antivirus de SharePoint Online son una forma de contener virus. No pretenden ser un punto único de defensa contra el malware en su entorno. Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa. Para obtener más información acerca de las estrategias y los procedimientos recomendados, vea [procedimientos recomendados de seguridad para Office 365](security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="20e94-p103">These antivirus capabilities in SharePoint Online are a way to contain viruses. They aren't intended as a single point of defense against malware for your environment. We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure. For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="20e94-113">¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="20e94-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="20e94-p104">Office 365 usa un motor de detección de virus común. El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina los archivos después de que se cargan. Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo. En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="20e94-p104">Office 365 uses a common virus detection engine. The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded. When a file is found to contain a virus, it's flagged so that it can't be downloaded again. In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="20e94-118">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="20e94-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="20e94-119">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="20e94-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="20e94-120">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="20e94-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="20e94-121">Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="20e94-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="20e94-122">¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?</span><span class="sxs-lookup"><span data-stu-id="20e94-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="20e94-123">Si un archivo está infectado con un virus, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.</span><span class="sxs-lookup"><span data-stu-id="20e94-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="20e94-124">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="20e94-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="20e94-125">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="20e94-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="20e94-p105">Al usuario se le advierte de que se ha detectado un virus. Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="20e94-p105">The user is given a warning that a virus has been detected. The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="20e94-p106">Puede usar el cmdlet Set-SPOTenant con el parámetro **DisallowInfectedFileDownload** para no permitir que los usuarios descarguen un archivo detectado, incluso en la ventana de advertencia de antivirus. Consulte [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="20e94-p106">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window. See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="20e94-130">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="20e94-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="20e94-p107">Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive. exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove. exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="20e94-p107">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  


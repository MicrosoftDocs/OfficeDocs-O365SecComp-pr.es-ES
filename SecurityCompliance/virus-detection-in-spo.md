---
title: Detección de virus en SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
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
ms.openlocfilehash: 8b15ac8e82082c2c6d940986d2018fa559835146
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598346"
---
# <a name="virus-detection-in-sharepoint-online"></a>Detección de virus en SharePoint Online

Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online. Los archivos se examinan en busca de virus una vez cargados. Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.
  
> [!IMPORTANT]
> Estas capacidades antivirus de SharePoint Online son una forma de contener virus. No pretenden ser un punto único de defensa contra el malware en su entorno. Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa. Para obtener más información acerca de las estrategias y los procedimientos recomendados, vea [procedimientos recomendados de seguridad para Office 365](security-best-practices.md). 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?

Office 365 usa un motor de detección de virus común. El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina los archivos después de que se cargan. Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo. En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.
  
Esto es lo que sucede:
  
1. Un usuario carga un archivo en SharePoint Online.
    
2. El motor de detección de virus examina el archivo.
    
3. Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?

Si un archivo está infectado con un virus, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.
  
Esto es lo que sucede:
  
1. Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.
    
2. Al usuario se le advierte de que se ha detectado un virus. Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.

> [!NOTE]
> Puede usar el cmdlet Set-SPOTenant con el parámetro **DisallowInfectedFileDownload** para no permitir que los usuarios descarguen un archivo detectado, incluso en la ventana de advertencia de antivirus. Consulte [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive. exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove. exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.
  


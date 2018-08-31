---
title: Detección de virus en SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 puede ayudar a proteger su entorno de malware mediante la detección de virus en los archivos que los usuarios cargar en SharePoint Online. Los archivos se examinan en busca de virus después de que se cargan. Si se encuentra un archivo infectado, se establece una propiedad para que los usuarios no se pueden descargar o sincronizar el archivo.
ms.openlocfilehash: 22e983d35283ff96e1469fdf913e25b8d1d1c485
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536452"
---
# <a name="virus-detection-in-sharepoint-online"></a>Detección de virus en SharePoint Online

Office 365 puede ayudar a proteger su entorno de malware mediante la detección de virus en los archivos que los usuarios cargar en SharePoint Online. Los archivos se examinan en busca de virus después de que se cargan. Si se encuentra un archivo infectado, se establece una propiedad para que los usuarios no se pueden descargar o sincronizar el archivo.
  
> [!IMPORTANT]
> Estas capacidades antivirus en SharePoint Online son una forma de contener virus. Que no están destinados como un único punto de defensa contra malware para su entorno. Le animamos a todos los clientes a evaluar e implementan la protección antimalware en distintas capas y aplique los procedimientos recomendados para proteger la infraestructura de enterprise. Para obtener más información acerca de las estrategias y procedimientos recomendados, vea [procedimientos recomendados de seguridad para Office 365](security-best-practices.md). 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué sucede cuando un archivo infectado se carga a SharePoint Online?

Office 365 usa un motor de detección de virus comunes. El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina los archivos después de cargarlas. Cuando se encuentra un archivo que contenga un virus, se marca para que no se puede descargar de nuevo. En abril de 2018, hemos eliminado el límite de 25 MB para archivos analizados.
  
Esto es lo que sucede:
  
1. Un usuario carga un archivo en SharePoint Online.
    
2. El motor de detección de virus examina el archivo.
    
3. Si se encuentra un virus, el motor de virus establece una propiedad en el archivo que indica que está infectado.
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado mediante el explorador?

Si un archivo está infectado con un virus, los usuarios no pueden descargar el archivo desde SharePoint Online mediante el explorador.
  
Esto es lo que sucede:
  
1. Un usuario abre un explorador web y se intenta descargar un archivo infectado desde SharePoint Online.
    
2. El usuario recibe una advertencia de que un virus ha detectado y se le ofrecerá la opción para descargar el archivo e intentar limpiar utilizando su propio software antivirus.
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Si los usuarios sincronización los archivos con el nuevo cliente de sincronización de OneDrive (OneDrive.exe) o la anterior OneDrive para el cliente de sincronización de negocio (Groove.exe), si un archivo contiene un virus, el cliente de sincronización no descargarla. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.
  


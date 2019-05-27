---
title: Office 365 ATP para SharePoint, OneDrive y Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: Amplíe la protección contra amenazas avanzada de Office 365 a los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams para permitir una colaboración más segura para su organización.
ms.openlocfilehash: a73f978ca40571e33864061cfe9538033579b3c7
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408265"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP para SharePoint, OneDrive y Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Información general sobre Office 365 ATP para SharePoint, OneDrive y Microsoft Teams

Los usuarios comparten archivos de forma regular y colaboran con SharePoint, OneDrive y Microsoft Teams. Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), su organización puede colaborar de forma más segura. ATP ayuda a detectar y bloquear archivos identificados como malintencionados en los sitios de grupo y las bibliotecas de documentos.  
  
## <a name="how-it-works"></a>Cómo funciona

Cuando un archivo en SharePoint Online, OneDrive para la empresa y Microsoft Teams se ha identificado como malintencionado, ATP se integra directamente con los almacenes de archivos para bloquear el archivo. La imagen siguiente muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.
  
[![Archivos en OneDrive para la empresa con uno detectado como malintencionado](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Aunque el archivo bloqueado todavía aparece en la biblioteca de documentos y en las aplicaciones Web, móviles o de escritorio, el archivo bloqueado no se puede abrir, copiar, mover o compartir. Sin embargo, los usuarios pueden eliminar un archivo bloqueado. Este es un ejemplo de lo que parece en el dispositivo móvil de un usuario:
  
[![Eliminación de un archivo bloqueado de OneDrive para la empresa desde la aplicación móvil de OneDrive](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
En función de cómo se configure Office 365, es posible que los usuarios no puedan descargar un archivo bloqueado. Esto es lo que parece descargar un archivo bloqueado en el dispositivo móvil de un usuario:
  
[![Descargar un archivo bloqueado en OneDrive para la empresa](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Para obtener más información, consulte [activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
  
## <a name="keep-these-points-in-mind"></a>Tenga en cuenta estos puntos

- ATP no examinará cada archivo único en SharePoint Online, OneDrive para la empresa o Microsoft Teams. Esto ocurre por motivos de diseño. Los archivos se examinan de forma asincrónica, a través de un proceso que usa eventos de actividad de uso compartido e invitados junto con heurística inteligente y señales de amenazas para identificar archivos malintencionados.

- Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Cuando un archivo se identifica como malintencionado y bloqueado, los usuarios pueden ver que se ha producido en la experiencia moderna, pero no en la vista clásica. La protección ATP se aplica si se usa la experiencia moderna o la vista clásica; sin embargo, los indicadores visuales que un archivo está bloqueado solo están presentes en la experiencia moderna.
    
- Los archivos que se identifican como malintencionados en SharePoint Online, OneDrive para la empresa o Microsoft Teams se mostrarán en [informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md) y en [el explorador (y las detecciones en tiempo real)](threat-explorer.md).
    
- ATP forma parte de la estrategia de protección contra amenazas global de su organización, que incluye protección contra correo electrónico no deseado y antimalware, así como vínculos seguros y datos adjuntos seguros. Para obtener más información, consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
    
- Un administrador de SharePoint Online puede determinar si se va a permitir que los usuarios descarguen archivos que se detectan como malintencionados. Para ello, ejecute el cmdlet de PowerShell Set-SPOTenant con un parámetro DisallowInfectedFileDownload (consulte [activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Poner en cuarentena ATP para SharePoint Online, OneDrive para la empresa y Microsoft Teams

 Desde tarde Mayo 2018, las capacidades de [cuarentena](quarantine-email-messages.md) del centro &amp; de seguridad y cumplimiento se amplían a ATP para SharePoint Online, OneDrive para la empresa y Microsoft Teams.
  
Cuando un archivo en SharePoint Online, OneDrive para la empresa o Microsoft Teams se identifica como malintencionado, además de que ATP bloquee que el archivo se abra o se comparta, el archivo se incluirá en una lista de elementos en cuarentena. (En el centro &amp; de seguridad y cumplimiento, vaya a **Threat Management** \> **Review** \> **Quarantine** and Filter for **Content**). 
  
Si forma parte del equipo de seguridad de Office 365 de su organización y tiene los [permisos necesarios asignados en el centro &amp; de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md), puede descargar, liberar, informar y eliminar archivos detectados como malintencionados por ATP de la cuarentena.
  
- La **liberación y la generación de informes** de un archivo quita el bloque ATP del archivo en el sitio de equipo o la biblioteca de documentos respectivos para SharePoint, OneDrive o Microsoft Teams. A continuación, los usuarios pueden abrir, compartir y descargar el archivo. Y, cuando se selecciona la opción **Enviar informe a Microsoft** , el archivo se notifica como falso positivo para Microsoft. 
    
- Al **eliminar un archivo** , se quita el archivo de la cuarentena; sin embargo, el archivo sigue bloqueado y no se puede abrir ni compartir. El archivo también debe eliminarse en su biblioteca de documentos o sitio de grupo respectivo (SharePoint Online, OneDrive para la empresa o Microsoft Teams). 
    
- La **descarga de un archivo** permite descargar y analizar el archivo en busca de falsos positivos. 
    
## <a name="next-steps"></a>Siguientes pasos

1. [Activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
    

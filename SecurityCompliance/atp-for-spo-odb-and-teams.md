---
title: ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams.
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 11/08/2018
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: Ampliar la protección de amenaza avanzada de Office 365 a los archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams permitir la colaboración más seguro para su organización.
ms.openlocfilehash: bf2285ac8c78d8a652861b5c635f5764677f0915
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995251"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams.

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Información general de Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft

Recurso compartido de archivos de personas con regularidad y colaborar mediante SharePoint, OneDrive y Microsoft Teams. Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede colaborar de manera más segura. ATP ayuda a detectar y bloquear archivos que haya identificado como malintencionados en sitios de grupo y las bibliotecas de documentos.  
  
## <a name="how-it-works"></a>Funcionamiento

Cuando un archivo en SharePoint Online, OneDrive para la empresa y Teams Microsoft ha identificado como malintencionados, ATP se integra directamente con los almacenes de archivos para bloquear ese archivo. En la siguiente imagen se muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.
  
[![Archivos de OneDrive para la empresa con uno detectado como malintencionado](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Aunque los archivos bloqueados sigue apareciendo en la biblioteca de documentos y web, aplicaciones móviles o de escritorio, los archivos bloqueados no se abre, copiado, movido o compartidos. Personas sin embargo, pueden eliminar un archivo bloqueado. Aquí un ejemplo del aspecto que tiene el aspecto al igual que en el dispositivo móvil de un usuario:
  
[![Eliminación de un archivo bloqueado de OneDrive para la empresa desde la aplicación móvil OneDrive](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Dependiendo de cómo se configura Office 365, personas podrían o no se puede tener la capacidad para descargar un archivo bloqueado. Aquí está descargando un archivo bloqueado aspecto en el dispositivo móvil de un usuario:
  
[![Descarga de un archivo bloqueado en OneDrive para la empresa](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Para obtener más información, vea [activar Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](turn-on-atp-for-spo-odb-and-teams.md).
  
## <a name="keep-these-points-in-mind"></a>Tenga en cuenta estos puntos

- ATP no va a analizar cada archivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams. Esto es por diseño. Los archivos se analizan de forma asincrónica, a través de un proceso que utiliza los eventos de actividad de uso compartido e invitado junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.

- Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Cuando un archivo se identifica como personas malintencionadas y bloqueadas, pueden ver que esto se ha producido en la experiencia de moderna, pero no en la vista clásica. Protección de ATP se aplica si se usa la experiencia moderna o en la vista clásica; Sin embargo, indicadores visuales que se bloquea un archivo están presentes sólo en la experiencia de moderna.
    
- Los archivos que se identifican como malintencionado en SharePoint Online, OneDrive para el negocio o Microsoft Teams se mostrará en los [informes de protección de amenaza avanzada de Office 365](view-reports-for-atp.md) y en el Explorador de amenaza (parte de la [Información sobre amenazas de Office 365](office-365-ti.md)).
    
- ATP es parte de estrategia general de amenaza protección su organización, que incluye contra correo no deseado y la protección contra malware, así como vínculos seguros y los datos adjuntos seguros. Para obtener más información, vea [proteger contra las amenazas en Office 365](protect-against-threats.md).
    
- Un administrador de SharePoint Online puede determinar si se permiten a las personas descargar los archivos que se detectan como malintencionados. Esto se realiza mediante la ejecución del cmdlet Set-SPOTenant PowerShell con un parámetro de DisallowInfectedFileDownload (vea [activar Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](turn-on-atp-for-spo-odb-and-teams.md)).
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Cuarentena de ATP para SharePoint Online, OneDrive para la empresa y los equipos de Microsoft

 A partir de las últimas mayo de 2018, capacidades de [cuarentena](quarantine-email-messages.md) en la seguridad &amp; centro de cumplimiento se están extendiendo a ATP para SharePoint Online, OneDrive para la empresa y Microsoft Teams.
  
Cuando un archivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams se identifica como malintencionado, además de ATP bloqueo del archivo se abran o compartido, ese archivo se incluye en una lista de elementos en cuarentena. (En la seguridad &amp; centro de cumplimiento, vaya a **administración de amenazas** \> **revisión** \> **cuarentena** y filtro de **contenido**.) 
  
Si es parte del equipo de seguridad de Office 365 de su organización y tener el requisito [permisos asignados en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md), puede descargar, versión, notificar y eliminar los archivos que se detectan como malintencionados por ATP desde la cuarentena.
  
- **Informes y lanzamiento de** un archivo quita el bloque de ATP en el archivo en la biblioteca de documentos o sitio de equipo respectivos para SharePoint, OneDrive o Microsoft Teams. Los usuarios, a continuación, son capaces de abrir, compartir y descargue el archivo. Y, cuando se selecciona la opción **Enviar informe a Microsoft** , el archivo se notifica como un falso positivo a Microsoft. 
    
- **Eliminación de un archivo** , se quita el archivo de cuarentena; Sin embargo, el archivo aún esté bloqueado desde que se va a abrir o compartidos. También se debe eliminar el archivo en su sitio de biblioteca o equipo de documento respectivos (SharePoint Online, OneDrive para el negocio o Microsoft Teams). 
    
- **Descargar un archivo** le permite descargar y analizar el archivo para los falsos positivos. 
    
## <a name="next-steps"></a>Pasos siguientes

1. [Activar Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
    

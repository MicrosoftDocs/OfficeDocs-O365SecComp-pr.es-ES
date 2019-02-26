---
title: Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Obtenga información sobre dónde ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Teams, y cómo tomar medidas en esos archivos.
ms.openlocfilehash: f5304f78ddec884748dd7d1090e2a7895044d045
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241902"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams

[Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) protege a su organización de archivos malintencionados en las bibliotecas de documentos y sitios de grupo. Cuando se detecta un archivo malintencionado, se bloquea el archivo para que nadie lo pueda abrir, copiar, mover ni compartir hasta que el equipo de seguridad de la organización haya realizado otras acciones. Lea este artículo para obtener información sobre cómo ver información sobre los archivos detectados y qué acciones llevar a cabo. 

Para realizar las tareas descritas en este artículo, debe tener los [permisos necesarios para el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Ver informes con información sobre los archivos detectados

Para ver información detallada y de estado sobre los archivos detectados por Office 365 ATP, puede usar el informe de estado de protección contra amenazas.
  
1. en el [centro de seguridad &amp; y cumplimiento de Office 365](https://protection.office.com), elija **informes** \> de **estado de protección contra amenazas**del **panel** \> .
    
2. En la esquina superior derecha del informe, elija **ver tabla de detalles**.
    
3. Ver la lista de los archivos que se han detectado en el informe.
    
4. Seleccione un elemento de la lista para ver información detallada, incluidas las acciones realizadas, el nombre de archivo, la ruta de acceso al archivo, etc.
    
5. Elija la pestaña **análisis avanzado** para ver la información, como el comportamiento observado y los detalles de análisis. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Ver y emprender acciones en los archivos en cuarentena

1. en el centro de seguridad &amp; y cumplimiento de Office 365, seleccione Quarantine **management** \> **review** \> **Quarantine**.
    
2. En la esquina superior izquierda, cambie el filtro de **correo electrónico** a **contenido**.
    
3. Seleccione un elemento de la lista para ver información detallada, incluida la dirección URL del archivo.
    
4. Elija una acción disponible.
    
  - Elija **Informe &amp; de versión** para desbloquear el archivo. 
    
    Seleccione **Enviar informe a Microsoft** para informar del archivo como falso positivo a Microsoft. 
    
  - Elija **Descargar archivo** para investigar más el archivo. 
    
  - Elija **eliminar** para quitar el archivo de la lista de elementos en cuarentena. Si elige esta opción, también debe eliminar el archivo de su biblioteca correspondiente en SharePoint Online, OneDrive para la empresa o Microsoft Teams. Esta opción no bloquea la apertura o el uso compartido de un archivo. 
    
5. Elija **cerrar** para cerrar los detalles de un elemento seleccionado. 
  
  


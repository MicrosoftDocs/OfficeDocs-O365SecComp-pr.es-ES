---
title: Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: Obtenga información sobre dónde ir para ver la información acerca de los archivos malintencionados detectado en SharePoint, OneDrive o equipos y cómo tomar medidas en esos archivos.
ms.openlocfilehash: e9a68c1cee1f2f3fb7fba148365449f0136fe637
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536179"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams

[Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) protege su organización desde archivos malintencionados en bibliotecas de documentos y sitios de grupo. Cuando se detecta un archivo malintencionado, ese archivo se bloquea para que nadie puede abrir, copiar, mover o compártalo hasta que se toman más acciones por el equipo de seguridad de la organización. Lea este artículo para obtener información sobre cómo ver información acerca de los archivos detectados y qué acciones que se realizarán. 
  
> [!TIP]
> A fin de realizar las tareas descritas en este artículo, debe tener el requisito [permisos asignados en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visualización de informes con información acerca de los archivos detectados

Para ver el estado y obtener información detallada acerca de los archivos que se han detectado por Office 365 ATP, puede usar el informe de estado de protección de amenaza.
  
1. En la seguridad de Office 365 &amp; centro de cumplimiento, seleccione **informes** \> **panel** \> **estado de protección de amenaza**.
    
2. En la esquina superior derecha del informe, elija **tabla de detalles de la vista**.
    
3. Ver la lista de archivos que se han detectado en el informe.
    
4. Seleccione un elemento en la lista para ver información detallada, incluidas las acciones llevadas a cabo, el nombre de archivo, la ruta de acceso y mucho más.
    
5. Elija la pestaña de **Análisis avanzadas** para ver la información, como los detalles de análisis y comportamiento observados. 
    
> [!TIP]
> Para obtener más información acerca de los informes disponibles, vea [Ver informes de protección de amenaza avanzada de Office 365](view-reports-for-atp.md). 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Ver y realizar acciones en los archivos en cuarentena

1. En la seguridad de Office 365 &amp; centro de cumplimiento, elija **administración de amenaza** \> **revisión** \> **cuarentena**.
    
2. En la esquina superior izquierda, cambie el filtro de **correo electrónico** a **contenido**.
    
3. Seleccione un elemento de la lista para ver información detallada, incluida la URL del archivo.
    
4. Elija una acción disponible.
    
  - Elija **versión &amp; informe** para desbloquear el archivo. 
    
    Seleccione **Enviar informe a Microsoft** para notificar el archivo como un falso positivo a Microsoft. 
    
  - Elija **descargar el archivo** para investigar más el archivo. 
    
  - Elija **Eliminar** para quitar el archivo de la lista de elementos en cuarentena. Si elige esta opción, también debe eliminar el archivo desde su biblioteca respectivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams. Esta opción no desbloquear un archivo desde el que se va a abrir o compartidos. 
    
5. Elija **Cerrar** para cerrar los detalles de un elemento seleccionado. 
    
> [!TIP]
> Para obtener más información acerca de cómo administrar los archivos en cuarentena, consulte [administrar en cuarentena mensajes y archivos como administrador en Office 365](manage-quarantined-messages-and-files.md). 
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Ver los informes de protección de amenaza avanzada de Office 365](view-reports-for-atp.md)
  
[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  


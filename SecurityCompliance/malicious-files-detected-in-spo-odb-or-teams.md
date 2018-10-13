---
title: Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: Obtenga información sobre dónde ir para ver la información acerca de los archivos malintencionados detectado en SharePoint, OneDrive o equipos y cómo tomar medidas en esos archivos.
ms.openlocfilehash: 37cd721c9ec2608ddcd74f9ae1ed6991b5f0cea7
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552388"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="84208-103">Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84208-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="84208-p101">[Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) protege su organización desde archivos malintencionados en bibliotecas de documentos y sitios de grupo. Cuando se detecta un archivo malintencionado, ese archivo se bloquea para que nadie puede abrir, copiar, mover o compártalo hasta que se toman más acciones por el equipo de seguridad de la organización. Lea este artículo para obtener información sobre cómo ver información acerca de los archivos detectados y qué acciones que se realizarán.</span><span class="sxs-lookup"><span data-stu-id="84208-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="84208-107">A fin de realizar las tareas descritas en este artículo, debe tener el requisito [permisos asignados en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="84208-107">In order to perform the tasks described in this article, you must have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="84208-108">Visualización de informes con información acerca de los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="84208-108">View reports with information about detected files</span></span>

<span data-ttu-id="84208-109">Para ver el estado y obtener información detallada acerca de los archivos que se han detectado por Office 365 ATP, puede usar el informe de estado de protección de amenaza.</span><span class="sxs-lookup"><span data-stu-id="84208-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="84208-110">En la seguridad de Office 365 &amp; centro de cumplimiento, seleccione **informes** \> **panel** \> **Estado de protección de amenaza**.</span><span class="sxs-lookup"><span data-stu-id="84208-110">In the Office 365 Security &amp; Compliance Center, choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="84208-111">En la esquina superior derecha del informe, elija **tabla de detalles de la vista**.</span><span class="sxs-lookup"><span data-stu-id="84208-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="84208-112">Ver la lista de archivos que se han detectado en el informe.</span><span class="sxs-lookup"><span data-stu-id="84208-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="84208-113">Seleccione un elemento en la lista para ver información detallada, incluidas las acciones llevadas a cabo, el nombre de archivo, la ruta de acceso y mucho más.</span><span class="sxs-lookup"><span data-stu-id="84208-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="84208-114">Elija la pestaña de **Análisis avanzadas** para ver la información, como los detalles de análisis y comportamiento observados.</span><span class="sxs-lookup"><span data-stu-id="84208-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="84208-115">Ver y realizar acciones en los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="84208-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="84208-116">En la seguridad de Office 365 &amp; centro de cumplimiento, elija **administración de amenaza** \> **revisión** \> **cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="84208-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="84208-117">En la esquina superior izquierda, cambie el filtro de **correo electrónico** a **contenido**.</span><span class="sxs-lookup"><span data-stu-id="84208-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="84208-118">Seleccione un elemento de la lista para ver información detallada, incluida la URL del archivo.</span><span class="sxs-lookup"><span data-stu-id="84208-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="84208-119">Elija una acción disponible.</span><span class="sxs-lookup"><span data-stu-id="84208-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="84208-120">Elija **versión &amp; informe** para desbloquear el archivo.</span><span class="sxs-lookup"><span data-stu-id="84208-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="84208-121">Seleccione **Enviar informe a Microsoft** para notificar el archivo como un falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84208-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="84208-122">Elija **descargar el archivo** para investigar más el archivo.</span><span class="sxs-lookup"><span data-stu-id="84208-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="84208-p102">Elija **Eliminar** para quitar el archivo de la lista de elementos en cuarentena. Si elige esta opción, también debe eliminar el archivo desde su biblioteca respectivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams. Esta opción no desbloquear un archivo desde el que se va a abrir o compartidos.</span><span class="sxs-lookup"><span data-stu-id="84208-p102">Choose **Delete** to remove the file from the list of quarantined items. If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams. This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="84208-126">Elija **Cerrar** para cerrar los detalles de un elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="84208-126">Choose **Close** to close the details for a selected item.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="84208-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="84208-127">Related topics</span></span>

[<span data-ttu-id="84208-128">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="84208-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="84208-129">Ver los informes de protección de amenaza avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="84208-129">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="84208-130">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="84208-130">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="84208-131">Administrar mensajes en cuarentena y los archivos como un administrador en Office 365</span><span class="sxs-lookup"><span data-stu-id="84208-131">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
  


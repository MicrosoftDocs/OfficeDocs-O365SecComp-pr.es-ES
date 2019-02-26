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
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="ea1e3-103">Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea1e3-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="ea1e3-p101">[Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) protege a su organización de archivos malintencionados en las bibliotecas de documentos y sitios de grupo. Cuando se detecta un archivo malintencionado, se bloquea el archivo para que nadie lo pueda abrir, copiar, mover ni compartir hasta que el equipo de seguridad de la organización haya realizado otras acciones. Lea este artículo para obtener información sobre cómo ver información sobre los archivos detectados y qué acciones llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="ea1e3-107">Para realizar las tareas descritas en este artículo, debe tener los [permisos necesarios para el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ea1e3-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="ea1e3-108">Ver informes con información sobre los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="ea1e3-108">View reports with information about detected files</span></span>

<span data-ttu-id="ea1e3-109">Para ver información detallada y de estado sobre los archivos detectados por Office 365 ATP, puede usar el informe de estado de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="ea1e3-110">en el [centro de seguridad &amp; y cumplimiento de Office 365](https://protection.office.com), elija **informes** \> de **estado de protección contra amenazas**del **panel** \> .</span><span class="sxs-lookup"><span data-stu-id="ea1e3-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="ea1e3-111">En la esquina superior derecha del informe, elija **ver tabla de detalles**.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="ea1e3-112">Ver la lista de los archivos que se han detectado en el informe.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="ea1e3-113">Seleccione un elemento de la lista para ver información detallada, incluidas las acciones realizadas, el nombre de archivo, la ruta de acceso al archivo, etc.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="ea1e3-114">Elija la pestaña **análisis avanzado** para ver la información, como el comportamiento observado y los detalles de análisis.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="ea1e3-115">Ver y emprender acciones en los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="ea1e3-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="ea1e3-116">en el centro de seguridad &amp; y cumplimiento de Office 365, seleccione Quarantine **management** \> **review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="ea1e3-117">En la esquina superior izquierda, cambie el filtro de **correo electrónico** a **contenido**.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="ea1e3-118">Seleccione un elemento de la lista para ver información detallada, incluida la dirección URL del archivo.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="ea1e3-119">Elija una acción disponible.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="ea1e3-120">Elija **Informe &amp; de versión** para desbloquear el archivo.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="ea1e3-121">Seleccione **Enviar informe a Microsoft** para informar del archivo como falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="ea1e3-122">Elija **Descargar archivo** para investigar más el archivo.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="ea1e3-p102">Elija **eliminar** para quitar el archivo de la lista de elementos en cuarentena. Si elige esta opción, también debe eliminar el archivo de su biblioteca correspondiente en SharePoint Online, OneDrive para la empresa o Microsoft Teams. Esta opción no bloquea la apertura o el uso compartido de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-p102">Choose **Delete** to remove the file from the list of quarantined items. If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams. This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="ea1e3-126">Elija **cerrar** para cerrar los detalles de un elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ea1e3-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  


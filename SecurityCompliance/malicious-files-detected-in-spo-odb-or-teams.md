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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259838"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="5c1d4-103">Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5c1d4-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="5c1d4-104">[Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) protege a su organización de archivos malintencionados en las bibliotecas de documentos y sitios de grupo.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="5c1d4-105">Cuando se detecta un archivo malintencionado, se bloquea el archivo para que nadie lo pueda abrir, copiar, mover ni compartir hasta que el equipo de seguridad de la organización haya realizado otras acciones.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="5c1d4-106">Lea este artículo para obtener información sobre cómo ver información sobre los archivos detectados y qué acciones llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="5c1d4-107">Para realizar las tareas descritas en este artículo, debe tener los [permisos necesarios para el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5c1d4-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="5c1d4-108">Ver informes con información sobre los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="5c1d4-108">View reports with information about detected files</span></span>

<span data-ttu-id="5c1d4-109">Para ver información detallada y de estado sobre los archivos detectados por Office 365 ATP, puede usar el informe de estado de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="5c1d4-110">en el [centro de seguridad &amp; y cumplimiento de Office 365](https://protection.office.com), elija **informes** \> de **estado de protección contra amenazas**del **panel** \> .</span><span class="sxs-lookup"><span data-stu-id="5c1d4-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="5c1d4-111">En la esquina superior derecha del informe, elija **ver tabla de detalles**.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="5c1d4-112">Ver la lista de los archivos que se han detectado en el informe.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="5c1d4-113">Seleccione un elemento de la lista para ver información detallada, incluidas las acciones realizadas, el nombre de archivo, la ruta de acceso al archivo, etc.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="5c1d4-114">Elija la pestaña **análisis avanzado** para ver la información, como el comportamiento observado y los detalles de análisis.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="5c1d4-115">Ver y emprender acciones en los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="5c1d4-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="5c1d4-116">en el centro de seguridad &amp; y cumplimiento de Office 365, seleccione Quarantine **management** \> **review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="5c1d4-117">En la esquina superior izquierda, cambie el filtro de **correo electrónico** a **contenido**.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="5c1d4-118">Seleccione un elemento de la lista para ver información detallada, incluida la dirección URL del archivo.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="5c1d4-119">Elija una acción disponible.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="5c1d4-120">Elija **Informe &amp; de versión** para desbloquear el archivo.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="5c1d4-121">Seleccione **Enviar informe a Microsoft** para informar del archivo como falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="5c1d4-122">Elija **Descargar archivo** para investigar más el archivo.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="5c1d4-123">Elija **eliminar** para quitar el archivo de la lista de elementos en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-123">Choose **Delete** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="5c1d4-124">Si elige esta opción, también debe eliminar el archivo de su biblioteca correspondiente en SharePoint Online, OneDrive para la empresa o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-124">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="5c1d4-125">Esta opción no bloquea la apertura o el uso compartido de un archivo.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-125">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="5c1d4-126">Elija **cerrar** para cerrar los detalles de un elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  


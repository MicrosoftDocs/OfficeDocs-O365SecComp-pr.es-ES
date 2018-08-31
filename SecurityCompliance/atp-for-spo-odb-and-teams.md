---
title: ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams.
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: Ampliar la protección de amenaza avanzada de Office 365 a los archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams permitir la colaboración más seguro para su organización.
ms.openlocfilehash: ea1c77273be70ce27f60bfaeae3544d605553a32
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536619"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="bc27b-103">ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc27b-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="bc27b-p101">Recurso compartido de archivos de personas con regularidad y colaborar mediante SharePoint, OneDrive y Microsoft Teams. Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede colaborar de manera más segura. ATP ayuda a detectar y bloquear archivos que haya identificado como malintencionados en sitios de grupo y las bibliotecas de documentos. Lea este artículo para obtener una visión general de ATP para SharePoint Online, OneDrive para la empresa y Microsoft Teams y, a continuación, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="bc27b-p101">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams. With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner. ATP helps detect and block files that are identified as malicious in team sites and document libraries. Read this article to get an overview of ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams, and then take your next steps.</span></span> 
  
> [!TIP]
> <span data-ttu-id="bc27b-p102">Para realizar las tareas descritas en este artículo, debe ser un administrador global de Office 365 o un administrador de seguridad. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bc27b-p102">In order to perform the tasks described in this article, you must be an Office 365 global administrator or a security administrator. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-it-works"></a><span data-ttu-id="bc27b-110">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="bc27b-110">How it works</span></span>

<span data-ttu-id="bc27b-p103">Cuando un archivo en SharePoint Online, OneDrive para la empresa y Teams Microsoft ha identificado como malintencionados, ATP se integra directamente con los almacenes de archivos para bloquear ese archivo. En la siguiente imagen se muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bc27b-p103">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file. The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="bc27b-113">[![Captura de pantalla de los archivos en OneDrive para la empresa con uno detectado como malintencionado](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="bc27b-113">[![Screenshot of files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="bc27b-p104">Aunque los archivos bloqueados sigue apareciendo en la biblioteca de documentos y web, aplicaciones móviles o de escritorio, los archivos bloqueados no se abre, copiado, movido o compartidos. Personas sin embargo, pueden eliminar un archivo bloqueado. Aquí un ejemplo del aspecto que tiene el aspecto al igual que en el dispositivo móvil de un usuario:</span><span class="sxs-lookup"><span data-stu-id="bc27b-p104">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared. People can, however, delete a blocked file. Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="bc27b-117">[![Captura de pantalla de eliminación de un archivo bloqueado de OneDrive para la empresa desde la aplicación móvil OneDrive](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="bc27b-117">[![Screenshot of deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="bc27b-p105">Dependiendo de cómo se configura Office 365, personas podrían o no se puede tener la capacidad para descargar un archivo bloqueado. Aquí está descargando un archivo bloqueado aspecto en el dispositivo móvil de un usuario:</span><span class="sxs-lookup"><span data-stu-id="bc27b-p105">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file. Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="bc27b-120">[![Captura de pantalla de descarga de un archivo bloqueado en OneDrive para la empresa](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="bc27b-120">[![Screenshot of downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="bc27b-121">Para obtener más información, vea [activar Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bc27b-121">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
### <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="bc27b-122">Tenga en cuenta los siguientes puntos</span><span class="sxs-lookup"><span data-stu-id="bc27b-122">Keep the following points in mind</span></span>

- <span data-ttu-id="bc27b-p106">ATP no va a analizar cada archivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams. Esto es por diseño. Los archivos se analizan de forma asincrónica, a través de un proceso que utiliza los eventos de actividad de uso compartido e invitado junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="bc27b-p106">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams. This is by design. Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>
    
- <span data-ttu-id="bc27b-126">Los archivos que se identifican como malintencionado en SharePoint Online, OneDrive para el negocio o Microsoft Teams se mostrará en los [informes de protección de amenaza avanzada de Office 365](view-reports-for-atp.md) y en el Explorador de amenaza (parte de la [Información sobre amenazas de Office 365](office-365-ti.md)).</span><span class="sxs-lookup"><span data-stu-id="bc27b-126">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in Threat Explorer (part of [Office 365 Threat Intelligence](office-365-ti.md)).</span></span>
    
- <span data-ttu-id="bc27b-p107">ATP es parte de estrategia general de amenaza protección su organización, que incluye contra correo no deseado y la protección contra malware, así como vínculos seguros y los datos adjuntos seguros. Para obtener más información, vea [proteger contra las amenazas en Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="bc27b-p107">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments. To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="bc27b-p108">Un administrador de SharePoint Online puede determinar si se permiten a las personas descargar los archivos que se detectan como malintencionados. Esto se realiza mediante la ejecución del cmdlet Set-SPOTenant PowerShell con un parámetro de DisallowInfectedFileDownload (vea [activar Office 365 ATP para SharePoint, OneDrive y los equipos de Microsoft](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="bc27b-p108">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious. This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="new-quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="bc27b-131">(Nuevo)! Cuarentena de ATP para SharePoint Online, OneDrive para la empresa y los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc27b-131">(New!) Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="bc27b-132">** A partir de las últimas mayo de 2018, capacidades de [cuarentena](quarantine-email-messages.md) en la seguridad &amp; centro de cumplimiento se están extendiendo a ATP para SharePoint Online, OneDrive para la empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bc27b-132">**Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> **
  
<span data-ttu-id="bc27b-p109">Cuando un archivo en SharePoint Online, OneDrive para el negocio o Microsoft Teams se identifica como malintencionado, además de ATP bloqueo del archivo se abran o compartido, ese archivo se incluye en una lista de elementos en cuarentena. (En la seguridad &amp; centro de cumplimiento, vaya a **administración de amenazas** \> **revisión** \> **cuarentena** y filtro de contenido.)</span><span class="sxs-lookup"><span data-stu-id="bc27b-p109">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items. (In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for Content.)</span></span> 
  
<span data-ttu-id="bc27b-135">Si es parte del equipo de seguridad de Office 365 de su organización y tener el requisito [permisos asignados en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md), puede descargar, versión, notificar y eliminar los archivos que se detectan como malintencionados por ATP desde la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="bc27b-135">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="bc27b-p110">**Informes y lanzamiento de** un archivo quita el bloque de ATP en el archivo en la biblioteca de documentos o sitio de equipo respectivos para SharePoint, OneDrive o Microsoft Teams. Los usuarios, a continuación, son capaces de abrir, compartir y descargue el archivo. Y, cuando se selecciona la opción **Enviar informe a Microsoft** , el archivo se notifica como un falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc27b-p110">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams. Users are then able to open, share, and download the file. And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="bc27b-p111">**Eliminación de un archivo** , se quita el archivo de cuarentena; Sin embargo, el archivo aún esté bloqueado desde que se va a abrir o compartidos. También se debe eliminar el archivo en su sitio de biblioteca o equipo de documento respectivos (SharePoint Online, OneDrive para el negocio o Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="bc27b-p111">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared. The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="bc27b-141">**Descargar un archivo** le permite descargar y analizar el archivo para los falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="bc27b-141">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="bc27b-142">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bc27b-142">Next steps</span></span>

- [<span data-ttu-id="bc27b-143">Activar Office 365 ATP para SharePoint, OneDrive y equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc27b-143">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
- [<span data-ttu-id="bc27b-144">Ver información sobre archivos malintencionados detectada en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc27b-144">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
## <a name="related-topics"></a><span data-ttu-id="bc27b-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bc27b-145">Related topics</span></span>

[<span data-ttu-id="bc27b-146">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="bc27b-146">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="bc27b-147">Ver los informes de protección de amenaza avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="bc27b-147">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="bc27b-148">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bc27b-148">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


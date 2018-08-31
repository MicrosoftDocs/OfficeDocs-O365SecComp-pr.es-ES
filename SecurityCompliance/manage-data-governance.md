---
title: Administrar el control de datos en Office 365
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: Gobierno de datos es todos los detalles sobre mantener los datos de alrededor de cuando lo necesite y obtención de suprimirlo cuando no lo hace. Con el control de datos en Office 365, puede administrar el ciclo de vida de contenido completo, de importación y almacenamiento de datos al principio, a la creación de directivas que conservarán y, a continuación, se eliminación permanentemente el contenido al final.
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536714"
---
# <a name="manage-data-governance-in-office-365"></a><span data-ttu-id="053ab-104">Administrar el control de datos en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-104">Manage data governance in Office 365</span></span>

<span data-ttu-id="053ab-p102">Gobierno de datos es todos los detalles sobre mantener los datos de alrededor de cuando lo necesite y obtención de suprimirlo cuando no lo hace. Con el control de datos en Office 365, puede administrar el ciclo de vida de contenido completo, de importación y almacenamiento de datos al principio, a la creación de directivas que conservarán y, a continuación, se eliminación permanentemente el contenido al final.</span><span class="sxs-lookup"><span data-stu-id="053ab-p102">Data governance is all about keeping your data around when you need it and getting rid of it when you don't. With data governance in Office 365, you can manage the full content lifecycle, from importing and storing data at the beginning, to creating policies that retain and then permanently delete content at the end.</span></span>
  
## <a name="import"></a><span data-ttu-id="053ab-107">Importar</span><span class="sxs-lookup"><span data-stu-id="053ab-107">Import</span></span>

<span data-ttu-id="053ab-p103">Algunos de los datos pueden almacenarse en lugares fuera de la nube, al igual que los servidores locales o en aplicaciones de terceros. El servicio de importación facilita Traer su mensajería, SharePoint y OneDrive para los datos profesionales en Office 365, ya sea por cargar directamente a través de la red o de envío de una unidad cifrada para nosotros. También puede usar la característica de importación inteligente en el servicio de importación para filtrar los elementos en los archivos PST que realmente obtengan importa a los buzones de correo de destino.</span><span class="sxs-lookup"><span data-stu-id="053ab-p103">Some of your data might be stored in places outside the cloud, like on-premises servers or in third-party apps. The Import service makes it easy to bring your messaging, SharePoint, and OneDrive for Business data into Office 365, either by uploading it directly over the network or shipping an encrypted drive to us. You can also use the Intelligent Import feature in the Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> 
  
- [<span data-ttu-id="053ab-111">Información general de importación de archivos PST en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-111">Overview of importing PST files to Office 365</span></span>](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [<span data-ttu-id="053ab-112">Usar la carga en la red para importar archivos PST en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-112">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
- [<span data-ttu-id="053ab-113">Usar el envío de unidades para importar los archivos PST a Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-113">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [<span data-ttu-id="053ab-114">Use la herramienta de recopilación de PST para buscar, copiar y eliminar los archivos PST en su organización</span><span class="sxs-lookup"><span data-stu-id="053ab-114">Use the PST Collection Tool to find, copy, and delete PST files in your organization</span></span>](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [<span data-ttu-id="053ab-115">Filtrar datos al importar archivos PST a Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-115">Filter data when importing PST files to Office 365</span></span>](filter-data-when-importing-pst-files.md)
    
- [<span data-ttu-id="053ab-116">Cargar contenido local en SharePoint Online con los cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="053ab-116">Upload on-premises content to SharePoint Online using PowerShell cmdlets</span></span>](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a><span data-ttu-id="053ab-117">Controlar los datos del almacén de I:</span><span class="sxs-lookup"><span data-stu-id="053ab-117">Govern I: Store data</span></span>

<span data-ttu-id="053ab-p104">Después de importar datos, es posible que necesite aumentar la capacidad de almacenamiento. La característica de archivado ilimitada en Office 365 (llamado ampliación automática archivado) proporciona una cantidad ilimitada de almacenamiento en buzones de archivo.</span><span class="sxs-lookup"><span data-stu-id="053ab-p104">After you import data, you might need to increase your storage. The unlimited archiving feature in Office 365 (called auto-expanding archiving) provides an unlimited amount of storage in archive mailboxes.</span></span>
  
- [<span data-ttu-id="053ab-120">Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="053ab-120">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>](enable-archive-mailboxes.md)

- [<span data-ttu-id="053ab-121">Información general sobre el archivo ilimitado en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-121">Overview of unlimited archiving in Office 365</span></span>](unlimited-archiving.md)
    
- [<span data-ttu-id="053ab-122">Habilitar el archivado ilimitado en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-122">Enable unlimited archiving in Office 365</span></span>](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a><span data-ttu-id="053ab-123">Controlar II: Crear directivas y etiquetas para conservar el contenido</span><span class="sxs-lookup"><span data-stu-id="053ab-123">Govern II: Create policies and labels to retain content</span></span>

<span data-ttu-id="053ab-p105">Una directiva de retención le ayudará a cumplir de forma proactiva con las normativas del sector y políticas internas asegurándose de que mantenga siempre que, pero ya no es necesario que el contenido. Una sola directiva de retención puede cubrir toda la organización. Además, puede utilizar etiquetas para implementar un plan de archivos mediante la clasificación de datos en toda la organización de gobierno y, a continuación, aplicar reglas de retención basadas en dicha clasificación.</span><span class="sxs-lookup"><span data-stu-id="053ab-p105">A retention policy helps you to comply proactively with industry regulations and internal policies by ensuring that you retain content as long as required but no longer than that. A single retention policy can cover your entire organization. In addition, you can use labels to implement a file plan by classifying data across your organization for governance, and then enforcing retention rules based on that classification.</span></span>
  
- [<span data-ttu-id="053ab-127">Introducción a las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="053ab-127">Overview of retention policies</span></span>](retention-policies.md)
    
- [<span data-ttu-id="053ab-128">Introducción a las etiquetas</span><span class="sxs-lookup"><span data-stu-id="053ab-128">Overview of labels</span></span>](labels.md)
    
- [<span data-ttu-id="053ab-129">Masiva creación y publicación de etiquetas mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="053ab-129">Bulk create and publish labels by using PowerShell</span></span>](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [<span data-ttu-id="053ab-130">Introducción a las revisiones de disposición</span><span class="sxs-lookup"><span data-stu-id="053ab-130">Overview of disposition reviews</span></span>](disposition-reviews.md)
    
- [<span data-ttu-id="053ab-131">Introducción a la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="053ab-131">Overview of event-driven retention</span></span>](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a><span data-ttu-id="053ab-132">Controlar III: Conservar el correo electrónico de antiguos empleados</span><span class="sxs-lookup"><span data-stu-id="053ab-132">Govern III: Retain the email of former employees</span></span>

<span data-ttu-id="053ab-p106">Cuando una persona abandona la organización, puede conservar su correo electrónico mediante la creación de un buzón de correo inactivo. Un buzón de correo se convierte en inactivo cuando un juicio, directiva de retención de Office 365, o se le aplica otro tipo de espera y, a continuación, se elimina la cuenta de usuario de Office 365 correspondiente. Se conservan los elementos de un buzón inactivo para la duración de la directiva de retención o suspensión que se realizó en el buzón de correo antes de que se ha realizado como inactiva.</span><span class="sxs-lookup"><span data-stu-id="053ab-p106">When a person leaves your organization, you can retain their email by creating an inactive mailbox. A mailbox becomes inactive when a Litigation Hold, Office 365 retention policy, or other type of hold is applied to it, and then the corresponding Office 365 user account is deleted. Items in an inactive mailbox are retained for the duration of the hold or retention policy that was placed on the mailbox before it was made inactive.</span></span>
  
- [<span data-ttu-id="053ab-136">Información general de buzones inactivos en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-136">Overview of inactive mailboxes in Office 365</span></span>](inactive-mailboxes-in-office-365.md)
    
- [<span data-ttu-id="053ab-137">Crear y administrar buzones inactivos en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-137">Create and manage inactive mailboxes in Office 365</span></span>](create-and-manage-inactive-mailboxes.md)

- [<span data-ttu-id="053ab-138">Cambiar la duración de retención para un buzón inactivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-138">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [<span data-ttu-id="053ab-139">Recuperar un buzón inactivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-139">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
 
- [<span data-ttu-id="053ab-140">Restaurar un buzón inactivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-140">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)

- [<span data-ttu-id="053ab-141">Eliminar un buzón inactivo en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-141">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

## <a name="monitor"></a><span data-ttu-id="053ab-142">Supervisar</span><span class="sxs-lookup"><span data-stu-id="053ab-142">Monitor</span></span>

<span data-ttu-id="053ab-p107">Supervisión le permite definir directivas que capturan correo electrónico y las comunicaciones 3rd terceros en su organización, por lo que se puede examinar por revisores internos o externos. Los revisores, a continuación, pueden clasificar estos communications, asegúrese de que son compatibles con las directivas de su organización y pasar material dudoso si es necesario.</span><span class="sxs-lookup"><span data-stu-id="053ab-p107">Supervision lets you define policies that capture email and 3rd-party communications in your organization so they can be examined by internal or external reviewers. Reviewers can then classify these communications, make sure they're compliant with your organization's policies, and escalate questionable material if necessary.</span></span>
  
<span data-ttu-id="053ab-145">También puede usar los informes de gobierno de datos y el Explorador de actividad de etiqueta para supervisar que las etiquetas se aplican a contenido según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="053ab-145">You can also use the data governance reports and the Label Activity Explorer to monitor that your labels are being applied to content as you intended.</span></span>
  
- [<span data-ttu-id="053ab-146">Configurar directivas de supervisión para su organización</span><span class="sxs-lookup"><span data-stu-id="053ab-146">Configure supervision policies for your organization</span></span>](configure-supervision-policies.md)
    
- [<span data-ttu-id="053ab-147">Informes de supervisión</span><span class="sxs-lookup"><span data-stu-id="053ab-147">Supervision reports</span></span>](supervision-reports.md)
    
- [<span data-ttu-id="053ab-148">Ver la actividad de etiquetas de documentos</span><span class="sxs-lookup"><span data-stu-id="053ab-148">View label activity for documents</span></span>](view-label-activity-for-documents.md)
    
- [<span data-ttu-id="053ab-149">Ver los informes de gobierno de datos</span><span class="sxs-lookup"><span data-stu-id="053ab-149">View the data governance reports</span></span>](view-the-data-governance-reports.md)
    
## <a name="more-information"></a><span data-ttu-id="053ab-150">Más información</span><span class="sxs-lookup"><span data-stu-id="053ab-150">More information</span></span>

- [<span data-ttu-id="053ab-151">Ver vídeos del equipo de gobierno de datos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="053ab-151">Watch videos from the Microsoft Data Governance team</span></span>](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [<span data-ttu-id="053ab-152">Vea una visión general de gobierno de datos en Office 365</span><span class="sxs-lookup"><span data-stu-id="053ab-152">Watch an overview of data governance in Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [<span data-ttu-id="053ab-153">Seguridad de Office 365 &amp; cmdlets de centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="053ab-153">Office 365 Security &amp; Compliance Center cmdlets</span></span>](https://go.microsoft.com/fwlink/?linkid=852310)
    


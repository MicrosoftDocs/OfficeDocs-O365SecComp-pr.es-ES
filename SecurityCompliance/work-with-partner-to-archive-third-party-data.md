---
title: Trabajar con un partner para archivar datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Su organización puede trabajar con un socio de Microsoft para configurar un conector personalizado para importar datos de terceros desde orígenes de datos como Salesforce chatter, Yahoo Messenger o Yammer. Esto le permite archivar datos de orígenes de datos de terceros en Office 365 para poder usar las características de cumplimiento de Office 365, como directivas de retención, búsqueda de contenido y retención legal para administrar el gobierno de los datos de terceros de la organización.
ms.openlocfilehash: dce015438c9764f66e98936df9454cba73fd8472
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308268"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="ae21e-104">Trabajar con un partner para archivar datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="ae21e-105">Puede trabajar con un socio de Microsoft para importar y archivar datos desde un origen de datos de terceros a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="ae21e-106">Un asociado puede proporcionarle un conector personalizado que está configurado para extraer elementos del origen de datos de terceros (de forma periódica) y, a continuación, importar dichos elementos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-106">A partner can provide you with an custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="ae21e-107">El conector de asociados convierte el contenido de un elemento del origen de datos en un formato de mensaje de correo electrónico y, a continuación, almacena los elementos en los buzones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="ae21e-108">Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Office 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría y las directivas de retención de Office 365, a estos datos.</span><span class="sxs-lookup"><span data-stu-id="ae21e-108">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data.</span></span>
  
<span data-ttu-id="ae21e-109">A continuación, se presenta una introducción al proceso y los pasos necesarios para trabajar con un socio de Microsoft para importar datos de terceros a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="ae21e-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="ae21e-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="ae21e-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="ae21e-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="ae21e-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="ae21e-113">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="ae21e-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="ae21e-114">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ae21e-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="ae21e-115">Cómo funciona el proceso de importación de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="ae21e-115">How the third-party data import process works</span></span>

<span data-ttu-id="ae21e-116">En la siguiente ilustración y descripción se explica cómo funciona el proceso de importación de datos de terceros al trabajar con un partner.</span><span class="sxs-lookup"><span data-stu-id="ae21e-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Cómo funciona el proceso de importación de datos de terceros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="ae21e-118">El cliente trabaja con su compañero de elección para configurar un conector que extraerá elementos del origen de datos de terceros y, a continuación, importará dichos elementos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="ae21e-119">El conector del asociado se conecta a orígenes de datos de terceros a través de una API de terceros (en una base programada o configurada) y extrae elementos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ae21e-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="ae21e-120">El conector asociado convierte el contenido de un elemento en un formato de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ae21e-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="ae21e-121">Consulte la sección [More information](#more-information) para obtener una descripción del esquema de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae21e-121">See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="ae21e-122">El conector del asociado se conecta al servicio de Azure en Office 365 mediante el servicio Web Exchange (EWS) a través de un punto final conocido.</span><span class="sxs-lookup"><span data-stu-id="ae21e-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="ae21e-p104">Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae21e-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="ae21e-125">a.</span><span class="sxs-lookup"><span data-stu-id="ae21e-125">a.</span></span> <span data-ttu-id="ae21e-126">**Elementos que tienen un identificador de usuario que se corresponde con una cuenta de usuario de Office 365** : Si el conector del asociado puede asignar el identificador de usuario del elemento del origen de datos de terceros a un identificador de usuario específico en Office 365, el \*\*\*\* elemento se copia en la carpeta purgas del REC del usuario. carpeta de elementos que se van a retener.</span><span class="sxs-lookup"><span data-stu-id="ae21e-126">**Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="ae21e-127">Los usuarios no pueden acceder a los elementos de esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="ae21e-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="ae21e-128">Sin embargo, puede usar las herramientas de Office 365 eDiscovery para buscar elementos en la carpeta dePuraciones.</span><span class="sxs-lookup"><span data-stu-id="ae21e-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="ae21e-129">b.</span><span class="sxs-lookup"><span data-stu-id="ae21e-129">b.</span></span> <span data-ttu-id="ae21e-130">**Elementos que no tienen un identificador de usuario correspondiente a una cuenta de usuario de office 365** : Si el conector del asociado no puede asignar el identificador de usuario de un elemento a un identificador de usuario específico en Office 365, el elemento se copia en la carpeta **bandeja de entrada** del buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-130">**Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="ae21e-131">La importación de elementos a la Bandeja de entrada permite que usted u otra persona de la organización inicie sesión en el buzón de correo de terceros para ver y administrar estos elementos, y ver si es necesario realizar ajustes en la configuración del conector asociado.</span><span class="sxs-lookup"><span data-stu-id="ae21e-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="ae21e-132">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="ae21e-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="ae21e-133">Un componente clave para archivar datos de terceros en Office 365 es encontrar y trabajar con un socio de Microsoft que se especializa en capturar datos de un origen de datos de terceros e importarlos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="ae21e-134">Una vez importados los datos, se pueden archivar y conservar junto con los otros datos de Microsoft de la organización, como el correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="ae21e-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="ae21e-135">Un asociado crea un conector que extrae datos de los orígenes de datos de terceros de la organización (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa los datos a una API de Office 365 que importa elementos a buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ae21e-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="ae21e-136">En las secciones siguientes se enumeran los socios de Microsoft (y los orígenes de datos de terceros que admiten) que participan en el programa para archivar datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-136">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="ae21e-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="ae21e-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="ae21e-138">ACTI</span><span class="sxs-lookup"><span data-stu-id="ae21e-138">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="ae21e-139">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="ae21e-139">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="ae21e-140">Globanet</span><span class="sxs-lookup"><span data-stu-id="ae21e-140">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="ae21e-141">OpenText</span><span class="sxs-lookup"><span data-stu-id="ae21e-141">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="ae21e-142">Verboa</span><span class="sxs-lookup"><span data-stu-id="ae21e-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="ae21e-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="ae21e-143">17a-4 LLC</span></span>

<span data-ttu-id="ae21e-144">17a-4 LLC admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-144">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="ae21e-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="ae21e-145">BlackBerry</span></span>
    
- <span data-ttu-id="ae21e-146">Secuencias de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ae21e-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="ae21e-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="ae21e-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="ae21e-148">FactSet</span><span class="sxs-lookup"><span data-stu-id="ae21e-148">FactSet</span></span>
    
- <span data-ttu-id="ae21e-149">HipChat</span><span class="sxs-lookup"><span data-stu-id="ae21e-149">HipChat</span></span>
    
- <span data-ttu-id="ae21e-150">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="ae21e-150">InvestEdge</span></span>
    
- <span data-ttu-id="ae21e-151">LivePerson</span><span class="sxs-lookup"><span data-stu-id="ae21e-151">LivePerson</span></span>
    
- <span data-ttu-id="ae21e-152">Secuencias de datos de MessageLabs</span><span class="sxs-lookup"><span data-stu-id="ae21e-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="ae21e-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="ae21e-153">OpenText</span></span>
    
- <span data-ttu-id="ae21e-154">Ayuda de Hacer clic para llamar de Oracle/ATG Live</span><span class="sxs-lookup"><span data-stu-id="ae21e-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="ae21e-155">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="ae21e-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="ae21e-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae21e-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="ae21e-157">MindAlign</span><span class="sxs-lookup"><span data-stu-id="ae21e-157">MindAlign</span></span>
    
- <span data-ttu-id="ae21e-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="ae21e-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="ae21e-159">Skype Empresarial (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="ae21e-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="ae21e-160">Skype Empresarial Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="ae21e-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="ae21e-161">Bases de datos SQL</span><span class="sxs-lookup"><span data-stu-id="ae21e-161">SQL Databases</span></span>
    
- <span data-ttu-id="ae21e-162">Squawker</span><span class="sxs-lookup"><span data-stu-id="ae21e-162">Squawker</span></span>
    
- <span data-ttu-id="ae21e-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="ae21e-163">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="ae21e-164">ACTI</span><span class="sxs-lookup"><span data-stu-id="ae21e-164">Actiance</span></span>

<span data-ttu-id="ae21e-165">La [acti](https://www.actiance.com) ? a admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-165">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ae21e-166">APUNTA</span><span class="sxs-lookup"><span data-stu-id="ae21e-166">AIM</span></span>
    
- <span data-ttu-id="ae21e-167">American Idol</span><span class="sxs-lookup"><span data-stu-id="ae21e-167">American Idol</span></span>
    
- <span data-ttu-id="ae21e-168">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="ae21e-168">Apple Juice</span></span>
    
- <span data-ttu-id="ae21e-169">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="ae21e-169">AOL with Pivot client</span></span>
    
- <span data-ttu-id="ae21e-170">Áreas</span><span class="sxs-lookup"><span data-stu-id="ae21e-170">Ares</span></span>
    
- <span data-ttu-id="ae21e-171">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-171">Bazaar Voice</span></span>
    
- <span data-ttu-id="ae21e-172">Bear Share</span><span class="sxs-lookup"><span data-stu-id="ae21e-172">Bear Share</span></span>
    
- <span data-ttu-id="ae21e-173">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="ae21e-173">Bit Torrent</span></span>
    
- <span data-ttu-id="ae21e-174">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-175">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-176">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-177">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-178">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="ae21e-178">Bloomberg Mail</span></span>
    
- <span data-ttu-id="ae21e-179">CellTrust</span><span class="sxs-lookup"><span data-stu-id="ae21e-179">CellTrust</span></span>
    
- <span data-ttu-id="ae21e-180">Importación de chat</span><span class="sxs-lookup"><span data-stu-id="ae21e-180">Chat Import</span></span>
    
- <span data-ttu-id="ae21e-181">Directiva y registro en tiempo real de chat</span><span class="sxs-lookup"><span data-stu-id="ae21e-181">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="ae21e-182">Flanco</span><span class="sxs-lookup"><span data-stu-id="ae21e-182">Chatter</span></span>
    
- <span data-ttu-id="ae21e-183">Servidor de &amp; presencia de mensajería instantánea de Cisco (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="ae21e-183">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="ae21e-184">Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="ae21e-184">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="ae21e-185">Importación de colaboración</span><span class="sxs-lookup"><span data-stu-id="ae21e-185">Collaboration Import</span></span>
    
- <span data-ttu-id="ae21e-186">Registro de colaboración en tiempo real</span><span class="sxs-lookup"><span data-stu-id="ae21e-186">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="ae21e-187">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="ae21e-187">Direct Connect</span></span>
    
- <span data-ttu-id="ae21e-188">Facebook</span><span class="sxs-lookup"><span data-stu-id="ae21e-188">Facebook</span></span>
    
- <span data-ttu-id="ae21e-189">FactSet</span><span class="sxs-lookup"><span data-stu-id="ae21e-189">FactSet</span></span>
    
- <span data-ttu-id="ae21e-190">FastTrack</span><span class="sxs-lookup"><span data-stu-id="ae21e-190">FastTrack</span></span>
    
- <span data-ttu-id="ae21e-191">Gnutella</span><span class="sxs-lookup"><span data-stu-id="ae21e-191">Gnutella</span></span>
    
- <span data-ttu-id="ae21e-192">Google +</span><span class="sxs-lookup"><span data-stu-id="ae21e-192">Google+</span></span>
    
- <span data-ttu-id="ae21e-193">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="ae21e-193">GoToMyPC</span></span>
    
- <span data-ttu-id="ae21e-194">Hopster</span><span class="sxs-lookup"><span data-stu-id="ae21e-194">Hopster</span></span>
    
- <span data-ttu-id="ae21e-195">HubConnex</span><span class="sxs-lookup"><span data-stu-id="ae21e-195">HubConnex</span></span>
    
- <span data-ttu-id="ae21e-196">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="ae21e-196">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="ae21e-197">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="ae21e-197">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="ae21e-198">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="ae21e-198">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="ae21e-199">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="ae21e-199">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="ae21e-200">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="ae21e-200">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="ae21e-201">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="ae21e-201">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="ae21e-202">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="ae21e-202">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="ae21e-203">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="ae21e-203">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="ae21e-204">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="ae21e-204">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="ae21e-205">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="ae21e-205">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="ae21e-206">Importación de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="ae21e-206">IM Import</span></span>
    
- <span data-ttu-id="ae21e-207">Directiva y registro de mensajería instantánea en tiempo real</span><span class="sxs-lookup"><span data-stu-id="ae21e-207">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="ae21e-208">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="ae21e-208">Indii Messenger</span></span>
    
- <span data-ttu-id="ae21e-209">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ae21e-209">Instant Bloomberg</span></span>
    
- <span data-ttu-id="ae21e-210">IRC</span><span class="sxs-lookup"><span data-stu-id="ae21e-210">IRC</span></span>
    
- <span data-ttu-id="ae21e-211">Jive</span><span class="sxs-lookup"><span data-stu-id="ae21e-211">Jive</span></span>
    
- <span data-ttu-id="ae21e-212">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="ae21e-212">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="ae21e-213">Jive Import</span><span class="sxs-lookup"><span data-stu-id="ae21e-213">Jive Import</span></span>
    
- <span data-ttu-id="ae21e-214">JXTA</span><span class="sxs-lookup"><span data-stu-id="ae21e-214">JXTA</span></span>
    
- <span data-ttu-id="ae21e-215">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ae21e-215">LinkedIn</span></span>
    
- <span data-ttu-id="ae21e-216">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="ae21e-216">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="ae21e-217">MFTP</span><span class="sxs-lookup"><span data-stu-id="ae21e-217">MFTP</span></span>
    
- <span data-ttu-id="ae21e-218">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-218">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="ae21e-219">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="ae21e-219">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="ae21e-220">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ae21e-220">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="ae21e-221">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="ae21e-221">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="ae21e-222">MindAlign</span><span class="sxs-lookup"><span data-stu-id="ae21e-222">MindAlign</span></span>
    
- <span data-ttu-id="ae21e-223">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="ae21e-223">Mobile Guard</span></span>
    
- <span data-ttu-id="ae21e-224">Fotos</span><span class="sxs-lookup"><span data-stu-id="ae21e-224">MSN</span></span>
    
- <span data-ttu-id="ae21e-225">My Space</span><span class="sxs-lookup"><span data-stu-id="ae21e-225">My Space</span></span>
    
- <span data-ttu-id="ae21e-226">Subred</span><span class="sxs-lookup"><span data-stu-id="ae21e-226">NEONetwork</span></span>
    
- <span data-ttu-id="ae21e-227">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="ae21e-227">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="ae21e-228">Mensajería instantánea compartida de Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-228">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="ae21e-229">Pinterest</span><span class="sxs-lookup"><span data-stu-id="ae21e-229">Pinterest</span></span>
    
- <span data-ttu-id="ae21e-230">Pivot</span><span class="sxs-lookup"><span data-stu-id="ae21e-230">Pivot</span></span>
    
- <span data-ttu-id="ae21e-231">QQ</span><span class="sxs-lookup"><span data-stu-id="ae21e-231">QQ</span></span>
    
- <span data-ttu-id="ae21e-232">Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="ae21e-232">Skype for Business 2015</span></span>
    
- <span data-ttu-id="ae21e-233">SoftEther</span><span class="sxs-lookup"><span data-stu-id="ae21e-233">SoftEther</span></span>
    
- <span data-ttu-id="ae21e-234">Symphony</span><span class="sxs-lookup"><span data-stu-id="ae21e-234">Symphony</span></span>
    
- <span data-ttu-id="ae21e-235">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="ae21e-235">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="ae21e-236">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="ae21e-236">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="ae21e-237">Términos</span><span class="sxs-lookup"><span data-stu-id="ae21e-237">Tor</span></span>
    
- <span data-ttu-id="ae21e-238">TTT</span><span class="sxs-lookup"><span data-stu-id="ae21e-238">TTT</span></span>
    
- <span data-ttu-id="ae21e-239">Twitter</span><span class="sxs-lookup"><span data-stu-id="ae21e-239">Twitter</span></span>
    
- <span data-ttu-id="ae21e-240">WinMX</span><span class="sxs-lookup"><span data-stu-id="ae21e-240">WinMX</span></span>
    
- <span data-ttu-id="ae21e-241">Winny</span><span class="sxs-lookup"><span data-stu-id="ae21e-241">Winny</span></span>
    
- <span data-ttu-id="ae21e-242">Toolbar</span><span class="sxs-lookup"><span data-stu-id="ae21e-242">Yahoo</span></span>
    
- <span data-ttu-id="ae21e-243">Yammer</span><span class="sxs-lookup"><span data-stu-id="ae21e-243">Yammer</span></span>
    
- <span data-ttu-id="ae21e-244">YouTube</span><span class="sxs-lookup"><span data-stu-id="ae21e-244">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="ae21e-245">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="ae21e-245">ArchiveSocial</span></span>

<span data-ttu-id="ae21e-246">[ArchiveSocial](https://www.archivesocial.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-246">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ae21e-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="ae21e-247">Facebook</span></span>
    
- <span data-ttu-id="ae21e-248">Flickr</span><span class="sxs-lookup"><span data-stu-id="ae21e-248">Flickr</span></span>
    
- <span data-ttu-id="ae21e-249">Instagram</span><span class="sxs-lookup"><span data-stu-id="ae21e-249">Instagram</span></span>
    
- <span data-ttu-id="ae21e-250">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ae21e-250">LinkedIn</span></span>
    
- <span data-ttu-id="ae21e-251">Pinterest</span><span class="sxs-lookup"><span data-stu-id="ae21e-251">Pinterest</span></span>
    
- <span data-ttu-id="ae21e-252">Twitter</span><span class="sxs-lookup"><span data-stu-id="ae21e-252">Twitter</span></span>
    
- <span data-ttu-id="ae21e-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="ae21e-253">YouTube</span></span>
    
- <span data-ttu-id="ae21e-254">Vimeo</span><span class="sxs-lookup"><span data-stu-id="ae21e-254">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="ae21e-255">Globanet</span><span class="sxs-lookup"><span data-stu-id="ae21e-255">Globanet</span></span>

<span data-ttu-id="ae21e-256">[Globanet](https://www.globanet.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-256">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ae21e-257">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="ae21e-257">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="ae21e-258">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-258">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-259">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-259">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-260">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-260">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-261">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ae21e-261">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ae21e-262">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="ae21e-262">Bloomberg Chat</span></span>
    
- <span data-ttu-id="ae21e-263">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="ae21e-263">Bloomberg Mail</span></span>
    
- <span data-ttu-id="ae21e-264">Cuadro</span><span class="sxs-lookup"><span data-stu-id="ae21e-264">Box</span></span>
    
- <span data-ttu-id="ae21e-265">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="ae21e-265">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="ae21e-266">Servidor de &amp; presencia de mensajería instantánea de Cisco (V10, v 10.5.1 SU1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="ae21e-266">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="ae21e-267">Equipos Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="ae21e-267">Cisco Webex Teams</span></span>

- <span data-ttu-id="ae21e-268">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="ae21e-268">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="ae21e-269">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="ae21e-269">CrowdCompass</span></span>

- <span data-ttu-id="ae21e-270">Archivos de texto delimitados por tabulaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="ae21e-270">Custom delimited text files</span></span>
    
- <span data-ttu-id="ae21e-271">Archivos XML personalizados</span><span class="sxs-lookup"><span data-stu-id="ae21e-271">Custom XML files</span></span>
    
- <span data-ttu-id="ae21e-272">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="ae21e-272">Facebook (Pages)</span></span>
    
- <span data-ttu-id="ae21e-273">FactSet</span><span class="sxs-lookup"><span data-stu-id="ae21e-273">Factset</span></span>
    
- <span data-ttu-id="ae21e-274">FXConnect</span><span class="sxs-lookup"><span data-stu-id="ae21e-274">FXConnect</span></span>
    
- <span data-ttu-id="ae21e-275">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="ae21e-275">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="ae21e-276">Jive</span><span class="sxs-lookup"><span data-stu-id="ae21e-276">Jive</span></span>
    
- <span data-ttu-id="ae21e-277">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="ae21e-277">Macgregor XIP</span></span>

- <span data-ttu-id="ae21e-278">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ae21e-278">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="ae21e-279">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="ae21e-279">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="ae21e-280">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae21e-280">Microsoft Teams</span></span>
       
- <span data-ttu-id="ae21e-281">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="ae21e-281">Microsoft Yammer</span></span>
    
- <span data-ttu-id="ae21e-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="ae21e-282">Mobile Guard</span></span>
    
- <span data-ttu-id="ae21e-283">Pivot</span><span class="sxs-lookup"><span data-stu-id="ae21e-283">Pivot</span></span>
    
- <span data-ttu-id="ae21e-284">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="ae21e-284">Salesforce Chatter</span></span>

- <span data-ttu-id="ae21e-285">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ae21e-285">Skype for Business Online</span></span>
    
- <span data-ttu-id="ae21e-286">Skype Empresarial, versiones 2007 R2 - 2016 (local)</span><span class="sxs-lookup"><span data-stu-id="ae21e-286">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="ae21e-287">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="ae21e-287">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="ae21e-288">Symphony</span><span class="sxs-lookup"><span data-stu-id="ae21e-288">Symphony</span></span>
    
- <span data-ttu-id="ae21e-289">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="ae21e-289">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="ae21e-290">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="ae21e-290">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="ae21e-291">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="ae21e-291">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="ae21e-292">Twitter</span><span class="sxs-lookup"><span data-stu-id="ae21e-292">Twitter</span></span>
    
- <span data-ttu-id="ae21e-293">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="ae21e-293">UBS Chat</span></span>
    
- <span data-ttu-id="ae21e-294">YouTube</span><span class="sxs-lookup"><span data-stu-id="ae21e-294">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="ae21e-295">OpenText</span><span class="sxs-lookup"><span data-stu-id="ae21e-295">OpenText</span></span>

<span data-ttu-id="ae21e-296">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-296">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ae21e-297">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="ae21e-297">Axs Encrypted</span></span>
    
- <span data-ttu-id="ae21e-298">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="ae21e-298">Axs Exchange</span></span>
    
- <span data-ttu-id="ae21e-299">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="ae21e-299">Axs Local Archive</span></span>
    
- <span data-ttu-id="ae21e-300">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="ae21e-300">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="ae21e-301">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="ae21e-301">Axs Signed</span></span>
    
- <span data-ttu-id="ae21e-302">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ae21e-302">Bloomberg</span></span>
    
- <span data-ttu-id="ae21e-303">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="ae21e-303">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="ae21e-304">Verboa</span><span class="sxs-lookup"><span data-stu-id="ae21e-304">Verba</span></span>

<span data-ttu-id="ae21e-305">[Verboa](https://www.verba.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ae21e-306">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="ae21e-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="ae21e-307">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="ae21e-308">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="ae21e-308">Avtec Radio</span></span>
    
- <span data-ttu-id="ae21e-309">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="ae21e-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="ae21e-310">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="ae21e-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="ae21e-311">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="ae21e-312">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-312">Centile Voice</span></span>
    
- <span data-ttu-id="ae21e-313">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="ae21e-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="ae21e-314">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="ae21e-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="ae21e-315">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="ae21e-316">Vídeo de Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="ae21e-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="ae21e-317">Cisco UCCX/UCCE de voz</span><span class="sxs-lookup"><span data-stu-id="ae21e-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="ae21e-318">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="ae21e-318">ESChat Radio</span></span>
    
- <span data-ttu-id="ae21e-319">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="ae21e-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="ae21e-320">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="ae21e-321">Centro de contacto de Luware LUCS</span><span class="sxs-lookup"><span data-stu-id="ae21e-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="ae21e-322">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="ae21e-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="ae21e-323">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="ae21e-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="ae21e-324">Vídeo de controlador de borde de sesión de paquete Oracle/Acme</span><span class="sxs-lookup"><span data-stu-id="ae21e-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="ae21e-325">Voz de controlador de borde de sesión de paquete Oracle/Acme</span><span class="sxs-lookup"><span data-stu-id="ae21e-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="ae21e-326">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="ae21e-327">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="ae21e-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="ae21e-328">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="ae21e-329">Skype Empresarial/MI de Lync</span><span class="sxs-lookup"><span data-stu-id="ae21e-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="ae21e-330">Skype Empresarial/Vídeo de Lync</span><span class="sxs-lookup"><span data-stu-id="ae21e-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="ae21e-331">Skype Empresarial/Voz de Lync</span><span class="sxs-lookup"><span data-stu-id="ae21e-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="ae21e-332">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="ae21e-333">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="ae21e-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="ae21e-334">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="ae21e-335">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="ae21e-335">Truphone Voice</span></span>
    
- <span data-ttu-id="ae21e-336">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="ae21e-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="ae21e-337">Pantalla de equipo de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="ae21e-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="ae21e-338">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="ae21e-339">Estos son los pasos para crear y configurar un buzón de datos de terceros para importar datos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="ae21e-340">Como se explicó anteriormente, los elementos se importan a este buzón si el conector del asociado no puede asignar el identificador de usuario del elemento a una cuenta de usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="ae21e-341">**Complete estas tareas en el centro de administración de 365 de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="ae21e-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="ae21e-342">Cree una nueva cuenta de usuario en Office 365 y asígnela una licencia de Exchange Online (plan 2). vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="ae21e-342">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="ae21e-343">Se necesita una licencia de plan 2 para poner el buzón en retención por juicio o habilitar un buzón de archivo que tenga una cuota de almacenamiento ilimitada.</span><span class="sxs-lookup"><span data-stu-id="ae21e-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="ae21e-344">Agregue la cuenta de usuario para el buzón de datos de terceros a la función de administrador de **Administrador de Exchange** en Office 365; consulte [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="ae21e-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ae21e-345">Escriba las credenciales para esta cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="ae21e-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="ae21e-346">Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="ae21e-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="ae21e-347">**Completar estas tareas en el centro de administración de Exchange**</span><span class="sxs-lookup"><span data-stu-id="ae21e-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="ae21e-348">Ocultar el buzón de datos de terceros de la libreta de direcciones y de otras listas de direcciones de la organización; consulte [Manage User mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="ae21e-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="ae21e-349">Como alternativa, puede ejecutar el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae21e-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="ae21e-350">Asignar el permiso **FullAccess** al buzón de datos de terceros para que los administradores o responsables de cumplimiento puedan abrir el buzón de datos de terceros en el cliente de escritorio de Outlook; consulte [administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="ae21e-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="ae21e-351">Habilite las siguientes características de Office 365 relacionadas con el cumplimiento para el buzón de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="ae21e-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="ae21e-352">Habilitar el buzón de archivo; consulte [Habilitar](enable-archive-mailboxes.md) el archivado de buzones de archivo y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ae21e-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="ae21e-353">Esto le permitirá liberar espacio de almacenamiento en el buzón de correo principal mediante la configuración de una directiva de archivo que mueva los elementos de datos de terceros al buzón de archivo.</span><span class="sxs-lookup"><span data-stu-id="ae21e-353">This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="ae21e-354">Así, dispondrá de almacenamiento ilimitado para los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-354">This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="ae21e-355">Coloque el buzón de datos de la tercera persona en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="ae21e-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="ae21e-356">También puede aplicar una directiva de retención de Office 365 en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae21e-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="ae21e-357">Colocar este buzón en retención conservará elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evitará que se purguen del buzón.</span><span class="sxs-lookup"><span data-stu-id="ae21e-357">Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="ae21e-358">Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="ae21e-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="ae21e-359">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="ae21e-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="ae21e-360">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="ae21e-361">Habilite el registro de auditoría del buzón para el acceso como propietario, delegado y administrador al buzón de datos de terceros; consulte [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="ae21e-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="ae21e-362">Esto le permitirá auditar todas las actividades realizadas por cualquier usuario que tenga acceso al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-362">This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="ae21e-363">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="ae21e-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="ae21e-364">El paso siguiente es configurar los buzones de usuario para que admitan los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="ae21e-365">Complete estas tareas con el centro de administración de Exchange o con los cmdlets de Windows PowerShell correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ae21e-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="ae21e-366">Habilitar el buzón de archivo para cada usuario; consulte [Habilitar](enable-archive-mailboxes.md) el archivado de buzones de archivo y [Habilitar el archivado ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ae21e-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="ae21e-367">Coloque los buzones de usuario en retención por juicio o aplique una directiva de retención de Office 365; Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="ae21e-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="ae21e-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="ae21e-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="ae21e-369">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="ae21e-370">Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="ae21e-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="ae21e-371">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="ae21e-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="ae21e-372">El último paso es proporcionar a su asociado la información siguiente para que pueda configurar el conector y conectarse a su organización de Office 365 con el fin de importar datos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="ae21e-373">El extremo que se usa para conectarse al servicio de Azure en Office 365:</span><span class="sxs-lookup"><span data-stu-id="ae21e-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="ae21e-374">Las credenciales de inicio de sesión (identificador de usuario y contraseña de Office 365) del buzón de datos de terceros que ha creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ae21e-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="ae21e-375">Estas credenciales son necesarias para que el conector asociado pueda tener acceso e importar elementos a los buzones de usuario y al buzón de datos de un tercero.</span><span class="sxs-lookup"><span data-stu-id="ae21e-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="ae21e-376">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ae21e-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="ae21e-377">A partir del 30 de septiembre de 2018, el servicio de Azure en Office 365 empezará a usar la autenticación moderna en Exchange Online para autenticar conectores de datos de terceros que intenten conectarse a su organización de Office 365 para importar datos.</span><span class="sxs-lookup"><span data-stu-id="ae21e-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="ae21e-378">El motivo de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se basaba en conectores de terceros de la lista blanca que usan el punto de conexión descrito anteriormente para conectarse al servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="ae21e-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="ae21e-379">Para permitir que un conector de datos de terceros se conecte a Office 365 mediante el nuevo método de autenticación moderna, un administrador de la organización de Office 365 debe dar su consentimiento para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae21e-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="ae21e-380">Esto se realiza al aceptar una solicitud de permisos para permitir que el conector tenga acceso a los datos de la organización en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae21e-380">This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="ae21e-381">Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa a Azure Active Directory y se representa como una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="ae21e-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="ae21e-382">Para obtener más información sobre el proceso de consentimiento, consulte [consentimiento de administrador](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ae21e-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="ae21e-383">Estos son los pasos para acceder y aceptar la solicitud para registrar el conector:</span><span class="sxs-lookup"><span data-stu-id="ae21e-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="ae21e-384">Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e inicie sesión con las credenciales de un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="ae21e-385">Se muestra el siguiente cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae21e-385">The following dialog box is displayed.</span></span> <span data-ttu-id="ae21e-386">Puede expandir los Cares para revisar los permisos que se asignarán al conector.</span><span class="sxs-lookup"><span data-stu-id="ae21e-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="ae21e-387">![Se muestra el cuadro de diálogo de solicitud de permisos](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="ae21e-387">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="ae21e-388">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae21e-388">Click **Accept**.</span></span>

<span data-ttu-id="ae21e-389">Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="ae21e-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="ae21e-390">Para ver la lista de aplicaciones de su organización, haga clic en**aplicaciones empresariales**de **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="ae21e-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="ae21e-391">El conector de datos de terceros de Office 365 aparece en la hoja **aplicaciones empresariales** .</span><span class="sxs-lookup"><span data-stu-id="ae21e-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae21e-392">Después del 30 de septiembre de 2018, los datos de terceros ya no se importarán en los buzones de la organización si no registra un conector de datos de terceros en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae21e-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="ae21e-393">Nota los conectores de datos de terceros existentes (los creados antes del 30 de septiembre de 2018) también deben registrarse en Azure Active Directory siguiendo el procedimiento que se indica en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="ae21e-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="ae21e-394">Revocar el consentimiento de un conector de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="ae21e-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="ae21e-395">Una vez que la organización ha Condado permiso a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar ese consentimiento en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ae21e-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="ae21e-396">Sin embargo, si se revoca el consentimiento de un conector, los datos del origen de datos de terceros ya no se importarán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-396">However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="ae21e-397">Para revocar el consentimiento de un conector de datos de terceros, puede eliminar la aplicación (eliminando la entidad de servicio correspondiente) de Azure Active Directory mediante la hoja **aplicaciones empresariales** en el portal de Azure o mediante el [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) en PowerShell de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="ae21e-398">También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) en PowerShell de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae21e-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="ae21e-399">Más información</span><span class="sxs-lookup"><span data-stu-id="ae21e-399">More information</span></span>

- <span data-ttu-id="ae21e-400">Tal como se ha explicado, los elementos de orígenes de datos de terceros se importan a los buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ae21e-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="ae21e-401">El conector del asociado importa el elemento mediante un esquema requerido por la API 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="ae21e-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="ae21e-402">En la tabla siguiente se describen las propiedades del mensaje de un elemento de un origen de datos de terceros después de que este se importe a un buzón de Exchange como un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ae21e-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="ae21e-403">La tabla también indica si la propiedad del mensaje es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="ae21e-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="ae21e-404">Las propiedades obligatorias deben rellenarse.</span><span class="sxs-lookup"><span data-stu-id="ae21e-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="ae21e-405">Si a un elemento le falta una propiedad obligatoria, no se importará a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="ae21e-406">El proceso de importación mostrará un mensaje de error que explica por qué un elemento no se importó y qué propiedad falta.</span><span class="sxs-lookup"><span data-stu-id="ae21e-406">The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="ae21e-407">**Propiedad del mensaje**</span><span class="sxs-lookup"><span data-stu-id="ae21e-407">**Message property**</span></span>|<span data-ttu-id="ae21e-408">**¿Es obligatoria?**</span><span class="sxs-lookup"><span data-stu-id="ae21e-408">**Mandatory?**</span></span>|<span data-ttu-id="ae21e-409">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ae21e-409">**Description**</span></span>|<span data-ttu-id="ae21e-410">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="ae21e-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae21e-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="ae21e-411">**FROM**</span></span> <br/> |<span data-ttu-id="ae21e-412">Sí</span><span class="sxs-lookup"><span data-stu-id="ae21e-412">Yes</span></span>  <br/> |<span data-ttu-id="ae21e-413">El usuario que originalmente ha creado o enviado el elemento en el origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="ae21e-414">El conector del asociado intentará asignar el identificador de usuario del elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario de Office 365 para todos los participantes (usuarios de los campos de y a).</span><span class="sxs-lookup"><span data-stu-id="ae21e-414">The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="ae21e-415">Una copia del mensaje se importará al buzón de cada participante.</span><span class="sxs-lookup"><span data-stu-id="ae21e-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="ae21e-416">Si ninguno de los participantes del elemento se puede asignar a una cuenta de usuario de Office 365, el elemento se importará al buzón de archivado de otro fabricante en Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae21e-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="ae21e-417">El participante que se identifica como remitente del elemento debe tener un buzón activo en la organización de Office 365 a la que se va a importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="ae21e-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="ae21e-418">Si el remitente no tiene un buzón activo, se devolverá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="ae21e-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="ae21e-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="ae21e-419">**TO**</span></span> <br/> |<span data-ttu-id="ae21e-420">Sí</span><span class="sxs-lookup"><span data-stu-id="ae21e-420">Yes</span></span>  <br/> |<span data-ttu-id="ae21e-421">El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ae21e-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="ae21e-422">**TITULAR**</span><span class="sxs-lookup"><span data-stu-id="ae21e-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="ae21e-423">No</span><span class="sxs-lookup"><span data-stu-id="ae21e-423">No</span></span>  <br/> |<span data-ttu-id="ae21e-424">El asunto del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="ae21e-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="ae21e-425">**OBSOLET**</span><span class="sxs-lookup"><span data-stu-id="ae21e-425">**DATE**</span></span> <br/> |<span data-ttu-id="ae21e-426">Sí</span><span class="sxs-lookup"><span data-stu-id="ae21e-426">Yes</span></span>  <br/> |<span data-ttu-id="ae21e-427">La fecha en la que el elemento originalmente se ha creado o publicado en el origen de datos del cliente; por ejemplo, la fecha en la que se ha publicado un mensaje en Twitter.</span><span class="sxs-lookup"><span data-stu-id="ae21e-427">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="ae21e-428">**CUERPO**</span><span class="sxs-lookup"><span data-stu-id="ae21e-428">**BODY**</span></span> <br/> |<span data-ttu-id="ae21e-429">No</span><span class="sxs-lookup"><span data-stu-id="ae21e-429">No</span></span>  <br/> |<span data-ttu-id="ae21e-430">El contenido del mensaje o la publicación.</span><span class="sxs-lookup"><span data-stu-id="ae21e-430">The contents of the message or post.</span></span> <span data-ttu-id="ae21e-431">En el caso de algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="ae21e-431">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="ae21e-432">Durante el proceso de importación, el conector asociado intentará mantener en la medida de lo posible la fidelidad total desde el origen de contenido.</span><span class="sxs-lookup"><span data-stu-id="ae21e-432">During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="ae21e-433">Si es posible, los archivos, los gráficos u otro contenido del cuerpo del elemento de origen se incluyen en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="ae21e-433">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="ae21e-434">Si no es así, el contenido del elemento de origen se incluye en la propiedad **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="ae21e-434">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="ae21e-435">El contenido de esta propiedad dependerá del conector del asociado y de la capacidad de la plataforma de origen.</span><span class="sxs-lookup"><span data-stu-id="ae21e-435">The contents of this property will depend on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="ae21e-436">**DATOS adjuntos**</span><span class="sxs-lookup"><span data-stu-id="ae21e-436">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="ae21e-437">No</span><span class="sxs-lookup"><span data-stu-id="ae21e-437">No</span></span>  <br/> |<span data-ttu-id="ae21e-438">Si un elemento del origen de datos (como un Tweet en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluye imágenes, la conexión del asociado intentará primero incluir datos adjuntos en la propiedad **Body** .</span><span class="sxs-lookup"><span data-stu-id="ae21e-438">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="ae21e-439">Si esto no es posible, se agrega a la propiedad \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="ae21e-439">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="ae21e-440">Otros ejemplos de datos adjuntos son los "Me gusta" de Facebook, los metadatos del origen del contenido y las respuestas a un mensaje o una publicación.</span><span class="sxs-lookup"><span data-stu-id="ae21e-440">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="ae21e-441">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="ae21e-441">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="ae21e-442">Sí</span><span class="sxs-lookup"><span data-stu-id="ae21e-442">Yes</span></span>  <br/> | <span data-ttu-id="ae21e-443">Se trata de una propiedad de varios valores, que se crea y rellena con el conector de asociado.</span><span class="sxs-lookup"><span data-stu-id="ae21e-443">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="ae21e-444">El formato de esta propiedad es `IPM.NOTE.Source.Event`.</span><span class="sxs-lookup"><span data-stu-id="ae21e-444">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="ae21e-445">(Esta propiedad debe comenzar con `IPM.NOTE`; este formato es similar al de la `IPM.NOTE.X` clase de mensaje). Esta propiedad incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ae21e-445">(This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="ae21e-446">`Source`: Indica el origen de datos de terceros; por ejemplo, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="ae21e-446">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="ae21e-447">`Event`: Indica el tipo de actividad que se realizó en el origen de datos de terceros que generó los elementos; por ejemplo, un Tweet en Twitter o un post en Facebook.</span><span class="sxs-lookup"><span data-stu-id="ae21e-447">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="ae21e-448">Los eventos son específicos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ae21e-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="ae21e-449">Un objetivo de esta propiedad es filtrar elementos específicos en función del origen de datos en el que un elemento se originó o basó, o bien en función del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="ae21e-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="ae21e-450">Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para encontrar todos los tweets publicados por un usuario concreto.</span><span class="sxs-lookup"><span data-stu-id="ae21e-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="ae21e-451">Cuando los elementos se importan correctamente a los buzones de Office 365, un identificador único se devuelve al autor de la llamada como parte de la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae21e-451">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="ae21e-452">Este identificador, llamado `x-IngestionCorrelationID`, se puede usar para solucionar problemas posteriores de los asociados para el seguimiento de elementos de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="ae21e-452">This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="ae21e-453">Se recomienda que los asociados capturen esta información y la registren según corresponda en su extremo.</span><span class="sxs-lookup"><span data-stu-id="ae21e-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="ae21e-454">A continuación se incluye un ejemplo de una respuesta HTTP que muestra este identificador:</span><span class="sxs-lookup"><span data-stu-id="ae21e-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="ae21e-455">Puede usar la herramienta de búsqueda de contenido en el centro de seguridad y cumplimiento para buscar elementos que se importaron a los buzones en Office 365 desde un origen de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="ae21e-456">Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valores y propiedades de mensaje en el cuadro palabra clave para una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="ae21e-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="ae21e-457">**`kind:externaldata`**-Use este par propiedad-valor para buscar todos los tipos de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-457">**`kind:externaldata`** - Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="ae21e-458">Por ejemplo, para buscar elementos que se importaron de un origen de datos de terceros y contenían la palabra "Contoso" en la propiedad subJect del elemento importado, usaría la palabra `kind:externaldata AND subject:contoso`clave Query.</span><span class="sxs-lookup"><span data-stu-id="ae21e-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="ae21e-459">**`itemclass:ipm.externaldata.<third-party data type>`**-Use este par Property-Value solo para buscar un tipo de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae21e-459">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="ae21e-460">Por ejemplo, para buscar únicamente datos de Facebook que contengan la palabra "Contoso" en la propiedad subJect, usaría la `itemclass:ipm.externaldata.Facebook* AND subject:contoso`consulta de palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ae21e-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="ae21e-461">Para obtener una lista completa de los valores que se van a usar para los tipos `itemclass` de datos de terceros para la propiedad, consulte [use Content Search to Search a data de terceros importado a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="ae21e-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="ae21e-462">Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:</span><span class="sxs-lookup"><span data-stu-id="ae21e-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="ae21e-463">Búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="ae21e-463">Content Search in Office 365</span></span>](content-search.md)
    
  - <span data-ttu-id="ae21e-464">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="ae21e-464">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
 

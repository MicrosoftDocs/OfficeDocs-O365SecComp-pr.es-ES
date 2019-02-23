---
title: Archivado de datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a los buzones de la organización de Office 365. Esto le permite archivar datos de Facebook, Twitter y orígenes de datos en Office 365. A continuación, puede appply las características de cumplimiento de Office 365 (como la retención legal, la búsqueda de contenido y las directivas de retención) a datos de terceros.
ms.openlocfilehash: 37811fdbee52cf956c6371deea53a242c2a3c550
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218501"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="a137d-105">Archivado de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="a137d-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="a137d-p102">Office 365 permite a los administradores importar y archivar datos de terceros desde plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, a los buzones de la organización de Office 365. Algunos ejemplos de orígenes de datos de terceros que puede importar a Office 365 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a137d-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="a137d-108">**Social** -Twitter, Facebook, Yammer y LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a137d-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="a137d-109">**Mensajería instantánea** : Yahoo Messenger, Googletalk y Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="a137d-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="a137d-110">**Colaboración en documentos** : Box y Dropbox</span><span class="sxs-lookup"><span data-stu-id="a137d-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="a137d-111">**Sectores verticales** : Customer Relationship Management (por ejemplo, Salesforce chatter) y Financials (como Thomson Reuters y Bloomberg)</span><span class="sxs-lookup"><span data-stu-id="a137d-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="a137d-112">**SMS/mensajería de texto** -BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a137d-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="a137d-p103">Una vez importados los datos de terceros, puede aplicar las características de cumplimiento de Office 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría y las directivas de retención de Office 365, a estos datos. Por ejemplo, cuando un buzón de correo se coloca en retención por juicio, se conservarán los datos de terceros. Puede usar la búsqueda de contenido para buscar datos de terceros. O bien, puede aplicar directivas de archivado y retención a datos de terceros, como lo haría con los datos de Microsoft. En Resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.</span><span class="sxs-lookup"><span data-stu-id="a137d-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="a137d-118">A continuación, se presenta una introducción al proceso y los pasos necesarios para importar datos de terceros a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="a137d-119">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="a137d-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="a137d-120">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="a137d-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="a137d-121">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="a137d-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="a137d-122">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="a137d-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="a137d-123">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a137d-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="a137d-124">Cómo se works> el proceso de importación de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="a137d-124">How the third-party data import process works></span></span>

<span data-ttu-id="a137d-125">En la ilustración y la descripción siguientes se explica cómo funciona el proceso de importación de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="a137d-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![Cómo funciona el proceso de importación de datos de terceros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="a137d-127">El cliente trabaja con su compañero de elección para configurar un conector que extraerá elementos del origen de datos de terceros y, a continuación, importará dichos elementos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="a137d-p104">El conector del asociado se conecta a orígenes de datos de terceros a través de una API de terceros (en una base programada o configurada) y extrae elementos del origen de datos. El conector de asociados convierte el contenido de un elemento en un formato de mensaje de correo electrónico. Consulte la sección [More Information](#more-information) para obtener una descripción del esquema de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a137d-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="a137d-131">El conector del asociado se conecta al servicio de Azure en Office 365 mediante el servicio Web Exchange (EWS) a través de un punto final conocido.</span><span class="sxs-lookup"><span data-stu-id="a137d-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="a137d-p105">Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="a137d-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="a137d-p106">a. **los elementos que tienen un identificador de usuario que se corresponde con una cuenta de usuario de Office 365** : Si el conector del asociado puede asignar el identificador de usuario del elemento del origen de datos de terceros a un identificador de usuario específico en Office 365, \*\*\*\* el elemento se copia en la carpeta purgas del usuario Carpeta elementos recuperables. Los usuarios no pueden tener acceso a los elementos de la carpeta purgas. Sin embargo, puede usar las herramientas de Office 365 eDiscovery para buscar elementos en la carpeta dePuraciones.</span><span class="sxs-lookup"><span data-stu-id="a137d-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="a137d-p107">b. **elementos que no tienen un identificador de usuario correspondiente a una cuenta de usuario de office 365** : Si el conector del asociado no puede asignar el identificador de usuario de un elemento a un identificador de usuario específico en Office 365, el elemento se copia en la carpeta **bandeja de entrada** del buzón de datos de terceros. La importación de elementos a la bandeja de entrada permite que usted u otra persona de su organización inicie sesión en el buzón de correo de terceros para ver y administrar estos elementos y ver si es necesario realizar ajustes en la configuración del conector del asociado.</span><span class="sxs-lookup"><span data-stu-id="a137d-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="a137d-141">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="a137d-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="a137d-p108">Un componente clave para archivar datos de terceros en Office 365 es encontrar y trabajar con un socio de Microsoft que se especializa en capturar datos de un origen de datos de terceros e importarlos a Office 365. Una vez importados los datos, se pueden archivar y conservar junto con los otros datos de Microsoft de la organización, como el correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa. Un asociado crea un conector que extrae datos de los orígenes de datos de terceros de la organización (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa los datos a una API de Office 365 que importa elementos a buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a137d-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="a137d-145">En las secciones siguientes se enumeran los socios de Microsoft (y los orígenes de datos de terceros que admiten) que participan en el programa para archivar datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="a137d-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="a137d-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="a137d-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="a137d-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="a137d-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="a137d-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="a137d-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="a137d-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="a137d-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="a137d-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="a137d-151">Verba</span><span class="sxs-lookup"><span data-stu-id="a137d-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="a137d-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="a137d-152">17a-4 LLC</span></span>

<span data-ttu-id="a137d-153">17a-4 LLC admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="a137d-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a137d-154">BlackBerry</span></span>
    
- <span data-ttu-id="a137d-155">Secuencias de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a137d-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="a137d-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="a137d-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="a137d-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="a137d-157">FactSet</span></span>
    
- <span data-ttu-id="a137d-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="a137d-158">HipChat</span></span>
    
- <span data-ttu-id="a137d-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="a137d-159">InvestEdge</span></span>
    
- <span data-ttu-id="a137d-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="a137d-160">LivePerson</span></span>
    
- <span data-ttu-id="a137d-161">
Secuencias de datos de MessageLabs
</span><span class="sxs-lookup"><span data-stu-id="a137d-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="a137d-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="a137d-162">OpenText</span></span>
    
- <span data-ttu-id="a137d-163">Ayuda de Hacer clic para llamar de Oracle/ATG Live
</span><span class="sxs-lookup"><span data-stu-id="a137d-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="a137d-164">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="a137d-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="a137d-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a137d-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="a137d-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="a137d-166">MindAlign</span></span>
    
- <span data-ttu-id="a137d-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="a137d-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="a137d-168">
Skype Empresarial (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="a137d-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="a137d-169">
Skype Empresarial Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="a137d-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="a137d-170">Bases de datos SQL</span><span class="sxs-lookup"><span data-stu-id="a137d-170">SQL Databases</span></span>
    
- <span data-ttu-id="a137d-171">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="a137d-171">Squawker</span></span>
    
- <span data-ttu-id="a137d-172">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="a137d-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="a137d-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="a137d-173">Actiance</span></span>

<span data-ttu-id="a137d-174">La [acti](https://www.actiance.com) ? a admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a137d-175">AIM</span><span class="sxs-lookup"><span data-stu-id="a137d-175">AIM</span></span>
    
- <span data-ttu-id="a137d-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="a137d-176">American Idol</span></span>
    
- <span data-ttu-id="a137d-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="a137d-177">Apple Juice</span></span>
    
- <span data-ttu-id="a137d-178">
AOL con cliente Pivot
</span><span class="sxs-lookup"><span data-stu-id="a137d-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="a137d-179">Ares</span><span class="sxs-lookup"><span data-stu-id="a137d-179">Ares</span></span>
    
- <span data-ttu-id="a137d-180">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="a137d-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="a137d-181">Bear Share</span><span class="sxs-lookup"><span data-stu-id="a137d-181">Bear Share</span></span>
    
- <span data-ttu-id="a137d-182">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="a137d-182">Bit Torrent</span></span>
    
- <span data-ttu-id="a137d-183">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-184">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-185">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-186">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-187">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="a137d-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="a137d-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="a137d-188">CellTrust</span></span>
    
- <span data-ttu-id="a137d-189">Importación de chat
</span><span class="sxs-lookup"><span data-stu-id="a137d-189">Chat Import</span></span>
    
- <span data-ttu-id="a137d-190">Directiva y registro en tiempo real de chat
</span><span class="sxs-lookup"><span data-stu-id="a137d-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="a137d-191">Chatter
</span><span class="sxs-lookup"><span data-stu-id="a137d-191">Chatter</span></span>
    
- <span data-ttu-id="a137d-192">Servidor de &amp; presencia de mensajería instantánea de Cisco (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="a137d-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="a137d-193">Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="a137d-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="a137d-194">Importación de colaboración
</span><span class="sxs-lookup"><span data-stu-id="a137d-194">Collaboration Import</span></span>
    
- <span data-ttu-id="a137d-195">Registro de colaboración en tiempo real
</span><span class="sxs-lookup"><span data-stu-id="a137d-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="a137d-196">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="a137d-196">Direct Connect</span></span>
    
- <span data-ttu-id="a137d-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="a137d-197">Facebook</span></span>
    
- <span data-ttu-id="a137d-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="a137d-198">FactSet</span></span>
    
- <span data-ttu-id="a137d-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="a137d-199">FastTrack</span></span>
    
- <span data-ttu-id="a137d-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="a137d-200">Gnutella</span></span>
    
- <span data-ttu-id="a137d-201">Google+
</span><span class="sxs-lookup"><span data-stu-id="a137d-201">Google+</span></span>
    
- <span data-ttu-id="a137d-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="a137d-202">GoToMyPC</span></span>
    
- <span data-ttu-id="a137d-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="a137d-203">Hopster</span></span>
    
- <span data-ttu-id="a137d-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="a137d-204">HubConnex</span></span>
    
- <span data-ttu-id="a137d-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
</span><span class="sxs-lookup"><span data-stu-id="a137d-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="a137d-206">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="a137d-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="a137d-207">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="a137d-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="a137d-208">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="a137d-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="a137d-209">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="a137d-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="a137d-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
</span><span class="sxs-lookup"><span data-stu-id="a137d-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="a137d-211">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="a137d-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="a137d-212">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="a137d-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="a137d-213">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="a137d-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="a137d-214">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a137d-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="a137d-215">Importación de mensajería instantánea
</span><span class="sxs-lookup"><span data-stu-id="a137d-215">IM Import</span></span>
    
- <span data-ttu-id="a137d-216">Directiva y registro de mensajería instantánea en tiempo real
</span><span class="sxs-lookup"><span data-stu-id="a137d-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="a137d-217">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="a137d-217">Indii Messenger</span></span>
    
- <span data-ttu-id="a137d-218">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="a137d-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="a137d-219">IRC</span><span class="sxs-lookup"><span data-stu-id="a137d-219">IRC</span></span>
    
- <span data-ttu-id="a137d-220">Jive
</span><span class="sxs-lookup"><span data-stu-id="a137d-220">Jive</span></span>
    
- <span data-ttu-id="a137d-221">Jive 6 Real Time Logging (v6, v7)
</span><span class="sxs-lookup"><span data-stu-id="a137d-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="a137d-222">Jive Import</span><span class="sxs-lookup"><span data-stu-id="a137d-222">Jive Import</span></span>
    
- <span data-ttu-id="a137d-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="a137d-223">JXTA</span></span>
    
- <span data-ttu-id="a137d-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a137d-224">LinkedIn</span></span>
    
- <span data-ttu-id="a137d-225">
Microsoft Lync (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="a137d-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="a137d-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="a137d-226">MFTP</span></span>
    
- <span data-ttu-id="a137d-227">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="a137d-228">Microsoft SharePoint (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="a137d-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="a137d-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a137d-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="a137d-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="a137d-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="a137d-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="a137d-231">MindAlign</span></span>
    
- <span data-ttu-id="a137d-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="a137d-232">Mobile Guard</span></span>
    
- <span data-ttu-id="a137d-233">MSN</span><span class="sxs-lookup"><span data-stu-id="a137d-233">MSN</span></span>
    
- <span data-ttu-id="a137d-234">My Space</span><span class="sxs-lookup"><span data-stu-id="a137d-234">My Space</span></span>
    
- <span data-ttu-id="a137d-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="a137d-235">NEONetwork</span></span>
    
- <span data-ttu-id="a137d-236">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="a137d-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="a137d-237">Mensajería instantánea compartida de Office 365
</span><span class="sxs-lookup"><span data-stu-id="a137d-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="a137d-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a137d-238">Pinterest</span></span>
    
- <span data-ttu-id="a137d-239">Pivot</span><span class="sxs-lookup"><span data-stu-id="a137d-239">Pivot</span></span>
    
- <span data-ttu-id="a137d-240">QQ</span><span class="sxs-lookup"><span data-stu-id="a137d-240">QQ</span></span>
    
- <span data-ttu-id="a137d-241">Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="a137d-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="a137d-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="a137d-242">SoftEther</span></span>
    
- <span data-ttu-id="a137d-243">Symphony
</span><span class="sxs-lookup"><span data-stu-id="a137d-243">Symphony</span></span>
    
- <span data-ttu-id="a137d-244">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="a137d-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="a137d-245">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="a137d-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="a137d-246">Tor</span><span class="sxs-lookup"><span data-stu-id="a137d-246">Tor</span></span>
    
- <span data-ttu-id="a137d-247">TTT</span><span class="sxs-lookup"><span data-stu-id="a137d-247">TTT</span></span>
    
- <span data-ttu-id="a137d-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="a137d-248">Twitter</span></span>
    
- <span data-ttu-id="a137d-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="a137d-249">WinMX</span></span>
    
- <span data-ttu-id="a137d-250">Winny</span><span class="sxs-lookup"><span data-stu-id="a137d-250">Winny</span></span>
    
- <span data-ttu-id="a137d-251">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="a137d-251">Yahoo</span></span>
    
- <span data-ttu-id="a137d-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="a137d-252">Yammer</span></span>
    
- <span data-ttu-id="a137d-253">Integrado</span><span class="sxs-lookup"><span data-stu-id="a137d-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="a137d-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="a137d-254">ArchiveSocial</span></span>

<span data-ttu-id="a137d-255">[ArchiveSocial](https://www.archivesocial.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a137d-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="a137d-256">Facebook</span></span>
    
- <span data-ttu-id="a137d-257">Flickr
</span><span class="sxs-lookup"><span data-stu-id="a137d-257">Flickr</span></span>
    
- <span data-ttu-id="a137d-258">Instagram
</span><span class="sxs-lookup"><span data-stu-id="a137d-258">Instagram</span></span>
    
- <span data-ttu-id="a137d-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a137d-259">LinkedIn</span></span>
    
- <span data-ttu-id="a137d-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a137d-260">Pinterest</span></span>
    
- <span data-ttu-id="a137d-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="a137d-261">Twitter</span></span>
    
- <span data-ttu-id="a137d-262">Integrado</span><span class="sxs-lookup"><span data-stu-id="a137d-262">YouTube</span></span>
    
- <span data-ttu-id="a137d-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="a137d-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="a137d-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="a137d-264">Globanet</span></span>

<span data-ttu-id="a137d-265">[Globanet](https://www.globanet.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a137d-266">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="a137d-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="a137d-267">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-268">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-269">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-270">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="a137d-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a137d-271">Bloomberg Chat
</span><span class="sxs-lookup"><span data-stu-id="a137d-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="a137d-272">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="a137d-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="a137d-273">Cuadro</span><span class="sxs-lookup"><span data-stu-id="a137d-273">Box</span></span>
    
- <span data-ttu-id="a137d-274">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a137d-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="a137d-275">Servidor de &amp; presencia de mensajería instantánea de Cisco (V10, v 10.5.1 SU1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="a137d-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="a137d-276">Equipos Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="a137d-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="a137d-277">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="a137d-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="a137d-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="a137d-278">CrowdCompass</span></span>

- <span data-ttu-id="a137d-279">Archivos de texto delimitados por tabulaciones personalizadas
</span><span class="sxs-lookup"><span data-stu-id="a137d-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="a137d-280">Archivos XML personalizados
</span><span class="sxs-lookup"><span data-stu-id="a137d-280">Custom XML files</span></span>
    
- <span data-ttu-id="a137d-281">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="a137d-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="a137d-282">Factset
</span><span class="sxs-lookup"><span data-stu-id="a137d-282">Factset</span></span>
    
- <span data-ttu-id="a137d-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="a137d-283">FXConnect</span></span>
    
- <span data-ttu-id="a137d-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a137d-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="a137d-285">Jive
</span><span class="sxs-lookup"><span data-stu-id="a137d-285">Jive</span></span>
    
- <span data-ttu-id="a137d-286">Macgregor XIP
</span><span class="sxs-lookup"><span data-stu-id="a137d-286">Macgregor XIP</span></span>

- <span data-ttu-id="a137d-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a137d-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="a137d-288">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="a137d-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="a137d-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a137d-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="a137d-290">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="a137d-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="a137d-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="a137d-291">Mobile Guard</span></span>
    
- <span data-ttu-id="a137d-292">Pivot</span><span class="sxs-lookup"><span data-stu-id="a137d-292">Pivot</span></span>
    
- <span data-ttu-id="a137d-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a137d-293">Salesforce Chatter</span></span>

- <span data-ttu-id="a137d-294">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a137d-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="a137d-295">Skype Empresarial, versiones 2007 R2 - 2016 (local)
</span><span class="sxs-lookup"><span data-stu-id="a137d-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="a137d-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="a137d-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="a137d-297">Symphony
</span><span class="sxs-lookup"><span data-stu-id="a137d-297">Symphony</span></span>
    
- <span data-ttu-id="a137d-298">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="a137d-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="a137d-299">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="a137d-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="a137d-300">Thomson Reuters Dealings 3000 / FX Trading
</span><span class="sxs-lookup"><span data-stu-id="a137d-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="a137d-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="a137d-301">Twitter</span></span>
    
- <span data-ttu-id="a137d-302">UBS Chat
</span><span class="sxs-lookup"><span data-stu-id="a137d-302">UBS Chat</span></span>
    
- <span data-ttu-id="a137d-303">Integrado</span><span class="sxs-lookup"><span data-stu-id="a137d-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="a137d-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="a137d-304">OpenText</span></span>

<span data-ttu-id="a137d-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a137d-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="a137d-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="a137d-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="a137d-307">Axs Exchange</span></span>
    
- <span data-ttu-id="a137d-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="a137d-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="a137d-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="a137d-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="a137d-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="a137d-310">Axs Signed</span></span>
    
- <span data-ttu-id="a137d-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a137d-311">Bloomberg</span></span>
    
- <span data-ttu-id="a137d-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="a137d-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="a137d-313">Verba</span><span class="sxs-lookup"><span data-stu-id="a137d-313">Verba</span></span>

<span data-ttu-id="a137d-314">[Verboa](https://www.verba.com) admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a137d-315">Avaya Aura Video
</span><span class="sxs-lookup"><span data-stu-id="a137d-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="a137d-316">Avaya Aura Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="a137d-317">Avtec Radio
</span><span class="sxs-lookup"><span data-stu-id="a137d-317">Avtec Radio</span></span>
    
- <span data-ttu-id="a137d-318">Bosch/Telex Radio
</span><span class="sxs-lookup"><span data-stu-id="a137d-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="a137d-319">BroadSoft Video
</span><span class="sxs-lookup"><span data-stu-id="a137d-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="a137d-320">BroadSoft Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="a137d-321">Centile Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-321">Centile Voice</span></span>
    
- <span data-ttu-id="a137d-322">Cisco Jabber IM
</span><span class="sxs-lookup"><span data-stu-id="a137d-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="a137d-323">Cisco UC Video
</span><span class="sxs-lookup"><span data-stu-id="a137d-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="a137d-324">Cisco UC Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="a137d-325">Vídeo de Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="a137d-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="a137d-326">Cisco UCCX/UCCE de voz</span><span class="sxs-lookup"><span data-stu-id="a137d-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="a137d-327">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="a137d-327">ESChat Radio</span></span>
    
- <span data-ttu-id="a137d-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="a137d-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="a137d-329">IP Trade Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="a137d-330">Centro de contacto de Luware LUCS</span><span class="sxs-lookup"><span data-stu-id="a137d-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="a137d-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="a137d-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="a137d-332">Mitel MiContact Center for Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="a137d-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="a137d-333">Vídeo de controlador de borde de sesión de paquete Oracle/Acme  
</span><span class="sxs-lookup"><span data-stu-id="a137d-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="a137d-334">Voz de controlador de borde de sesión de paquete Oracle/Acme
</span><span class="sxs-lookup"><span data-stu-id="a137d-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="a137d-335">Singtel Mobile Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="a137d-336">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="a137d-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="a137d-337">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="a137d-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="a137d-338">Skype Empresarial/MI de Lync
</span><span class="sxs-lookup"><span data-stu-id="a137d-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="a137d-339">Skype Empresarial/Vídeo de Lync
</span><span class="sxs-lookup"><span data-stu-id="a137d-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="a137d-340">Skype Empresarial/Voz de Lync
</span><span class="sxs-lookup"><span data-stu-id="a137d-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="a137d-341">Speakerbus Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="a137d-342">Standard SIP/H.323 Video 
</span><span class="sxs-lookup"><span data-stu-id="a137d-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="a137d-343">Standard SIP/H.323 Voice 
</span><span class="sxs-lookup"><span data-stu-id="a137d-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="a137d-344">Truphone Voice
</span><span class="sxs-lookup"><span data-stu-id="a137d-344">Truphone Voice</span></span>
    
- <span data-ttu-id="a137d-345">TwistedPair Radio
</span><span class="sxs-lookup"><span data-stu-id="a137d-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="a137d-346">Pantalla de equipo de escritorio de Windows 
</span><span class="sxs-lookup"><span data-stu-id="a137d-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="a137d-347">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="a137d-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="a137d-p109">Estos son los pasos para crear y configurar un buzón de datos de terceros para importar datos a Office 365. Como se explicó anteriormente, los elementos se importan a este buzón si el conector del asociado no puede asignar el identificador de usuario del elemento a una cuenta de usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="a137d-350">**Completar estas tareas en el centro de administración de Office 365**</span><span class="sxs-lookup"><span data-stu-id="a137d-350">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="a137d-p110">Cree una nueva cuenta de usuario en Office 365 y asígnela una licencia de Exchange Online (plan 2). vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Se necesita una licencia de plan 2 para poner el buzón en retención por juicio o habilitar un buzón de archivo que tenga una cuota de almacenamiento ilimitada.</span><span class="sxs-lookup"><span data-stu-id="a137d-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="a137d-353">Agregue la cuenta de usuario para el buzón de datos de terceros a la función de administrador de **Administrador de Exchange** en Office 365; consulte [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="a137d-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a137d-p111">Escriba las credenciales para esta cuenta de usuario. Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="a137d-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="a137d-356">**Completar estas tareas en el centro de administración de Exchange**</span><span class="sxs-lookup"><span data-stu-id="a137d-356">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="a137d-p112">Ocultar el buzón de datos de terceros de la libreta de direcciones y de otras listas de direcciones de la organización; consulte [Manage User mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Como alternativa, puede ejecutar el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a137d-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="a137d-359">Asignar el permiso **FullAccess** al buzón de datos de terceros para que los administradores o responsables de cumplimiento puedan abrir el buzón de datos de terceros en el cliente de escritorio de Outlook; consulte [administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="a137d-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="a137d-360">Habilite las siguientes características de Office 365 relacionadas con el cumplimiento para el buzón de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="a137d-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="a137d-p113">Habilitar el buzón de archivo; consulte [Habilitar buzones de archivo en el centro de &amp; seguridad y cumplimiento de Office 365](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md). Esto le permitirá liberar espacio de almacenamiento en el buzón de correo principal mediante la configuración de una directiva de archivo que mueva los elementos de datos de terceros al buzón de archivo. Esto le proporcionará almacenamiento ilimitado para los datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="a137d-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="a137d-p114">Coloque el buzón de datos de terceros en retención por juicio. También puede aplicar una directiva de retención de Office 365 en el centro de &amp; seguridad y cumplimiento de Office 365. Colocar este buzón en retención conservará elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evitará que se purguen del buzón. Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="a137d-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="a137d-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="a137d-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="a137d-369">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="a137d-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="a137d-p115">Habilitar el registro de auditoría de buzones de correo para el propietario, el delegado y el acceso de administrador al buzón de datos de terceros; consulte [Habilitar la auditoría de buzones de correo en Office 365](enable-mailbox-auditing.md). Esto le permitirá auditar todas las actividades realizadas por cualquier usuario que tenga acceso al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="a137d-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="a137d-372">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="a137d-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="a137d-p116">El paso siguiente es configurar los buzones de usuario para admitir datos de terceros. Complete estas tareas con el centro de administración de Exchange o con los cmdlets de Windows PowerShell correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a137d-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="a137d-375">Habilitar el buzón de archivo para cada usuario; consulte [Habilitar buzones de archivo en el centro de &amp; seguridad y cumplimiento de Office 365](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a137d-375">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="a137d-376">Coloque los buzones de usuario en retención por juicio o aplique una directiva de retención de Office 365; Consulte uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="a137d-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="a137d-377">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="a137d-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="a137d-378">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="a137d-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="a137d-379">Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="a137d-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="a137d-380">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="a137d-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="a137d-381">El último paso es proporcionar a su asociado la información siguiente para que pueda configurar el conector y conectarse a su organización de Office 365 con el fin de importar datos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="a137d-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="a137d-382">El extremo que se usa para conectarse al servicio de Azure en Office 365:</span><span class="sxs-lookup"><span data-stu-id="a137d-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="a137d-p117">Las credenciales de inicio de sesión (identificador de usuario y contraseña de Office 365) del buzón de datos de terceros que ha creado en el paso 2. Estas credenciales son necesarias para que el conector de asociados pueda obtener acceso e importar elementos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="a137d-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="a137d-385">Paso 5: registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a137d-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="a137d-p118">A partir del 30 de septiembre de 2018, el servicio de Azure en Office 365 empezará a usar la autenticación moderna en Exchange Online para autenticar conectores de datos de terceros que intenten conectarse a su organización de Office 365 para importar datos. El motivo de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se basaba en conectores de terceros de la lista blanca que usan el punto de conexión descrito anteriormente para conectarse al servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="a137d-p118">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data. The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="a137d-p119">Para permitir que un conector de datos de terceros se conecte a Office 365 mediante el nuevo método de autenticación moderna, un administrador de la organización de Office 365 debe dar su consentimiento para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory. Esto se realiza al aceptar una solicitud de permisos para permitir que el conector tenga acceso a los datos de la organización en Azure Active Directory. Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa a Azure Active Directory y se representa como una entidad de servicio. Para obtener más información sobre el proceso de consentimiento, consulte [consentimiento de administrador](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="a137d-p119">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory. This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory. After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal. For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="a137d-392">Estos son los pasos para acceder y aceptar la solicitud para registrar el conector:</span><span class="sxs-lookup"><span data-stu-id="a137d-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="a137d-393">Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e inicie sesión con las credenciales de un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="a137d-p120">Se muestra el siguiente cuadro de diálogo. Puede expandir los Cares para revisar los permisos que se asignarán al conector.</span><span class="sxs-lookup"><span data-stu-id="a137d-p120">The following dialog box is displayed. You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="a137d-396">![Se muestra el cuadro de diálogo de solicitud de permisos](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="a137d-396">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="a137d-397">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a137d-397">Click **Accept**.</span></span>

<span data-ttu-id="a137d-p121">Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) . Para ver la lista de aplicaciones de su organización, haga clic en**aplicaciones empresariales**de **Azure Active Directory** > . El conector de datos de terceros de Office 365 aparece en la hoja **aplicaciones empresariales** .</span><span class="sxs-lookup"><span data-stu-id="a137d-p121">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed. To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**. The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a137d-p122">Después del 30 de septiembre de 2018, los datos de terceros ya no se importarán en los buzones de la organización si no registra un conector de datos de terceros en Azure Active Directory. Nota los conectores de datos de terceros existentes (los creados antes del 30 de septiembre de 2018) también deben registrarse en Azure Active Directory siguiendo el procedimiento que se indica en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="a137d-p122">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory. Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="a137d-403">Revocar el consentimiento de un conector de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="a137d-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="a137d-p123">Una vez que la organización ha Condado permiso a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar ese consentimiento en cualquier momento. Sin embargo, si se revoca el consentimiento de un conector, los datos del origen de datos de terceros ya no se importarán en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-p123">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time. However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="a137d-p124">Para revocar el consentimiento de un conector de datos de terceros, puede eliminar la aplicación (eliminando la entidad de servicio correspondiente) de Azure Active Directory mediante la hoja **aplicaciones empresariales** en el portal de Azure o mediante el [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) en PowerShell de Office 365. También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) en PowerShell de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a137d-p124">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="a137d-408">Más información</span><span class="sxs-lookup"><span data-stu-id="a137d-408">More information</span></span>

- <span data-ttu-id="a137d-p125">Como se explicó anteriormente, los elementos de los orígenes de datos de terceros se importan a los buzones de Exchange como mensajes de correo electrónico. El conector del asociado importa el elemento mediante un esquema requerido por la API 365 de Office. En la tabla siguiente se describen las propiedades de mensaje de un elemento de un origen de datos de terceros después de importarlo a un buzón de Exchange como mensaje de correo electrónico. La tabla también indica si la propiedad Message es obligatoria. Las propiedades obligatorias se deben rellenar. Si a un elemento le falta una propiedad obligatoria, no se importará a Office 365. El proceso de importación devolverá un mensaje de error en el que se explica por qué no se ha importado un elemento y qué propiedad falta.</span><span class="sxs-lookup"><span data-stu-id="a137d-p125">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="a137d-416">**Propiedad del mensaje**</span><span class="sxs-lookup"><span data-stu-id="a137d-416">**Message property**</span></span>|<span data-ttu-id="a137d-417">**Aparecer?**</span><span class="sxs-lookup"><span data-stu-id="a137d-417">**Mandatory?**</span></span>|<span data-ttu-id="a137d-418">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a137d-418">**Description**</span></span>|<span data-ttu-id="a137d-419">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a137d-419">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a137d-420">**FROM**</span><span class="sxs-lookup"><span data-stu-id="a137d-420">**FROM**</span></span> <br/> |<span data-ttu-id="a137d-421">Sí</span><span class="sxs-lookup"><span data-stu-id="a137d-421">Yes</span></span>  <br/> |<span data-ttu-id="a137d-p126">El usuario que creó o envió el elemento originalmente en el origen de datos de terceros. El conector del asociado intentará asignar el identificador de usuario del elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario de Office 365 para todos los participantes (usuarios de los campos de y a). Se importará una copia del mensaje al buzón de cada participante. Si ninguno de los participantes del elemento se puede asignar a una cuenta de usuario de Office 365, el elemento se importará al buzón de archivado de otro fabricante en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a137d-p126">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="a137d-p127">El participante que se identifica como remitente del elemento debe tener un buzón activo en la organización de Office 365 a la que se va a importar el elemento. Si el remitente no tiene un buzón activo, se devuelve el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="a137d-p127">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="a137d-428">**TO**</span><span class="sxs-lookup"><span data-stu-id="a137d-428">**TO**</span></span> <br/> |<span data-ttu-id="a137d-429">Sí</span><span class="sxs-lookup"><span data-stu-id="a137d-429">Yes</span></span>  <br/> |<span data-ttu-id="a137d-430">El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a137d-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="a137d-431">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="a137d-431">**SUBJECT**</span></span> <br/> |<span data-ttu-id="a137d-432">No</span><span class="sxs-lookup"><span data-stu-id="a137d-432">No</span></span>  <br/> |<span data-ttu-id="a137d-433">El asunto del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="a137d-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="a137d-434">**OBSOLET**</span><span class="sxs-lookup"><span data-stu-id="a137d-434">**DATE**</span></span> <br/> |<span data-ttu-id="a137d-435">Sí</span><span class="sxs-lookup"><span data-stu-id="a137d-435">Yes</span></span>  <br/> |<span data-ttu-id="a137d-436">La fecha en la que el elemento originalmente se ha creado o publicado en el origen de datos del cliente; por ejemplo, la fecha en la que se ha publicado un mensaje en Twitter.</span><span class="sxs-lookup"><span data-stu-id="a137d-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="a137d-437">**BODY**</span><span class="sxs-lookup"><span data-stu-id="a137d-437">**BODY**</span></span> <br/> |<span data-ttu-id="a137d-438">No</span><span class="sxs-lookup"><span data-stu-id="a137d-438">No</span></span>  <br/> |<span data-ttu-id="a137d-p128">El contenido del mensaje o la publicación. Para algunos orígenes de datos, el contenido de esta propiedad puede ser el mismo que el contenido de \*\*\*\* la propiedad Subject. Durante el proceso de importación, el conector del asociado intentará mantener la total fidelidad del origen de contenido como sea posible. Si se incluyen en esta propiedad archivos, gráficos u otros contenidos posibles del cuerpo del elemento de origen. De lo contrario, el contenido del elemento de origen se incluye en la propiedad **Attachment** . El contenido de esta propiedad dependerá del conector del asociado y de la capacidad de la plataforma de origen.</span><span class="sxs-lookup"><span data-stu-id="a137d-p128">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="a137d-445">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="a137d-445">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="a137d-446">No</span><span class="sxs-lookup"><span data-stu-id="a137d-446">No</span></span>  <br/> |<span data-ttu-id="a137d-p129">Si un elemento del origen de datos (como un Tweet en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluye imágenes, la conexión del asociado intentará primero incluir datos adjuntos en la propiedad **Body** . Si esto no es posible, se agrega a la propiedad \* \* ATTACHMENT \* \*. Otros ejemplos de datos adjuntos incluyen los gustos en Facebook, los metadatos del origen de contenido y las respuestas a un mensaje o una publicación.</span><span class="sxs-lookup"><span data-stu-id="a137d-p129">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="a137d-450">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="a137d-450">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="a137d-451">Sí</span><span class="sxs-lookup"><span data-stu-id="a137d-451">Yes</span></span>  <br/> | <span data-ttu-id="a137d-p130">Se trata de una propiedad de varios valores, que se crea y rellena con el conector de asociado. El formato de esta propiedad es `IPM.NOTE.Source.Event`. (Esta propiedad debe comenzar con `IPM.NOTE`; este formato es similar al de la `IPM.NOTE.X` clase de mensaje). Esta propiedad incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a137d-p130">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="a137d-455">`Source`: Indica el origen de datos de terceros; por ejemplo, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="a137d-455">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="a137d-p131">`Event`: Indica el tipo de actividad que se realizó en el origen de datos de terceros que generó los elementos; por ejemplo, un Tweet en Twitter o un post en Facebook. Los eventos son específicos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a137d-p131">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="a137d-p132">Un propósito de esta propiedad es filtrar elementos específicos en función del origen de datos en el que se originó un elemento o en función del tipo de evento. Por ejemplo, en una búsqueda de exhibición de documentos electrónicos, podría crear una consulta de búsqueda para encontrar todos los tweets que ha publicado un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="a137d-p132">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="a137d-p133">Cuando los elementos se importan correctamente a los buzones de Office 365, un identificador único se devuelve al autor de la llamada como parte de la respuesta HTTP. Este identificador, llamado `x-IngestionCorrelationID`, se puede usar para solucionar problemas posteriores de los asociados para el seguimiento de elementos de un extremo a otro. Se recomienda que los socios capturen esta información y la registren en consecuencia en el final. Este es un ejemplo de una respuesta HTTP que muestra este identificador:</span><span class="sxs-lookup"><span data-stu-id="a137d-p133">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="a137d-p134">Puede usar la herramienta de búsqueda de contenido en el centro de &amp; seguridad y cumplimiento de Office 365 para buscar elementos que se importaron a los buzones en Office 365 desde un origen de datos de terceros. Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valores y propiedades de mensaje en el cuadro palabra clave para una búsqueda de contenido. .</span><span class="sxs-lookup"><span data-stu-id="a137d-p134">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="a137d-p135">**`kind:externaldata`**-Use este par propiedad-valor para buscar todos los tipos de datos de terceros. Por ejemplo, para buscar elementos que se importaron de un origen de datos de terceros y contenían la palabra "Contoso" en la propiedad subJect del elemento importado, usaría la palabra `kind:externaldata AND subject:contoso`clave Query.</span><span class="sxs-lookup"><span data-stu-id="a137d-p135">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="a137d-p136">**`itemclass:ipm.externaldata.<third-party data type>`**-Use este par Property-Value solo para buscar un tipo de datos de terceros. Por ejemplo, para buscar únicamente datos de Facebook que contengan la palabra "Contoso" en la propiedad subJect, usaría la `itemclass:ipm.externaldata.Facebook* AND subject:contoso`consulta de palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a137d-p136">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="a137d-471">Para obtener una lista completa de los valores que se van a usar para los tipos `itemclass` de datos de terceros para la propiedad, consulte [use Content Search to Search a data de terceros importado a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="a137d-471">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="a137d-472">Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:</span><span class="sxs-lookup"><span data-stu-id="a137d-472">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="a137d-473">Búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="a137d-473">Content Search in Office 365</span></span>](content-search.md)
    
  - <span data-ttu-id="a137d-474">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="a137d-474">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
 

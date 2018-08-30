---
title: Archivado de datos de terceros en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de otros proveedores de plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a buzones de correo en la organización de Office 365. Esto le permite archivar datos de orígenes de datos, Twitter y Facebook en Office 365. A continuación, puede appply las características de cumplimiento de normas de Office 365 (por ejemplo, retención legal, búsqueda de contenido y las directivas de retención) a los datos de otro fabricante.
ms.openlocfilehash: 3d51d9f5cb546b33fa636fab0ca319e4d24b1ad4
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230042"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="7ed19-105">Archivado de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed19-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="7ed19-p102">Permite a los administradores importan y archivar datos de terceros desde plataformas de medios sociales, plataformas y plataformas de colaboración de documentos, a los buzones de correo en la organización de Office 365 de mensajería instantánea de Office 365. Ejemplos de orígenes de datos de terceros que se pueden importar a Office 365 incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="7ed19-108">**Social** - Twitter, Facebook, Yammer y LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7ed19-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="7ed19-109">**Mensajería instantánea** - Yahoo Messenger, GoogleTalk y Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="7ed19-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="7ed19-110">**Colaboración en documentos** - cuadro y lista desplegable</span><span class="sxs-lookup"><span data-stu-id="7ed19-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="7ed19-111">**Industrias verticales** - administración de relaciones de cliente (por ejemplo, la cháchara de fuerza de ventas) y Financials (por ejemplo, Reuters Thomson y Bloomberg)</span><span class="sxs-lookup"><span data-stu-id="7ed19-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="7ed19-112">**Mensajería de texto SMS /** - BlackBerry</span><span class="sxs-lookup"><span data-stu-id="7ed19-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="7ed19-p103">Después de importan datos de otro fabricante, puede aplicar las características de cumplimiento de normas de Office 365, como las directivas de retención de la suspensión por litigio, búsqueda de contenido, en lugar de archivado, auditoría y Office 365 — a estos datos. Por ejemplo, cuando un buzón de correo se coloca en suspensión por litigio, se conservarán los datos de otro fabricante. Puede buscar datos de terceros mediante el uso de búsqueda de contenido. O puede aplicar el archivado y las políticas de retención a los datos de terceros, al igual que puede utilizar para datos de Microsoft. En resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización mantenga la compatibilidad con el gobierno y las directivas de las normativas.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="7ed19-118">Aquí es información general sobre el proceso y los pasos necesarios para importar datos de otros fabricantes a Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ed19-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="7ed19-119">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="7ed19-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="7ed19-120">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed19-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="7ed19-121">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="7ed19-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="7ed19-122">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="7ed19-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="7ed19-123">Proceso de importación de los datos de otros fabricantes de cómo funciona ></span><span class="sxs-lookup"><span data-stu-id="7ed19-123">How the third-party data import process works></span></span>

<span data-ttu-id="7ed19-124">En la ilustración y la descripción siguientes se explica cómo funciona el proceso de importación de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ed19-124">The following illustration and description explain how the third-party data import process works.</span></span>
  
![Cómo funciona el proceso de importación de datos de terceros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="7ed19-126">Cliente funciona con su socio de elección para configurar un conector que se va a extraer los elementos del origen de datos de terceros y, a continuación, importar esos elementos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ed19-126">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="7ed19-p104">El conector de socio se conecta a orígenes de datos de terceros mediante una API de terceros (de forma programada o configurado como) y extrae los elementos del origen de datos. El conector de socio convierte el contenido de un elemento en un formato de mensaje de correo electrónico. Vea la sección [obtener más información](#more-information) para obtener una descripción del esquema de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="7ed19-130">Conector de socio se conecta al servicio de Azure en Office 365 mediante el uso de servicio de Web Exchange (EWS) a través de un punto final conocido.</span><span class="sxs-lookup"><span data-stu-id="7ed19-130">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="7ed19-p105">Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="7ed19-p106">r. **los elementos que tienen un identificador de usuario que corresponde a una cuenta de usuario de Office 365** - si el conector de socio puede asignar el identificador de usuario del elemento en el origen de datos de terceros a un usuario determinado que identificador en Office 365, el elemento se copia a la carpeta de **purga** en el usuario Carpeta elementos recuperables. Los usuarios no pueden tener acceso a los elementos de la carpeta de purga. Sin embargo, puede usar herramientas de exhibición de documentos electrónicos de Office 365 para buscar elementos en la carpeta de purga.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="7ed19-p107">b. **los elementos que no tienen un identificador de usuario que corresponde a una cuenta de usuario de Office 365** - si el conector de socio no puede asignar el identificador de usuario de un elemento a un usuario determinado que identificador en Office 365, el elemento se copia en la carpeta **Bandeja de entrada** del buzón de datos de terceros. Importación de elementos a la Bandeja de entrada permite usted o alguien de su organización para iniciar sesión en el buzón de correo de terceros para ver y administrar estos elementos y vea si los ajustes deben realizarse en la configuración del conector de socio.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="7ed19-140">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="7ed19-140">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="7ed19-p108">Un componente clave para el archivado de datos de terceros en Office 365 es buscar y trabajar con un socio de Microsoft que está especializado en capturar los datos de un origen de datos de terceros y se importa a Office 365. Una vez que se importan los datos, puede archivar y conserva junto con la organización de otros datos de Microsoft, como correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa. Un socio crea un conector que extrae datos de orígenes de datos de terceros de su organización (por ejemplo, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa los datos a una API de Office 365 que importa los elementos a los buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="7ed19-144">Las secciones siguientes enumeran los socios de Microsoft y los orígenes de datos de terceros que admiten — que participan en el programa para el archivado de datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ed19-144">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="7ed19-145">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="7ed19-145">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="7ed19-146">Actiance</span><span class="sxs-lookup"><span data-stu-id="7ed19-146">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="7ed19-147">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="7ed19-147">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="7ed19-148">Globanet</span><span class="sxs-lookup"><span data-stu-id="7ed19-148">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="7ed19-149">OpenText</span><span class="sxs-lookup"><span data-stu-id="7ed19-149">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="7ed19-150">Verba</span><span class="sxs-lookup"><span data-stu-id="7ed19-150">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="7ed19-151">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="7ed19-151">17a-4 LLC</span></span>

<span data-ttu-id="7ed19-152">17a-4 LLC admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-152">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="7ed19-153">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="7ed19-153">BlackBerry</span></span>
    
- <span data-ttu-id="7ed19-154">Secuencias de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="7ed19-154">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="7ed19-155">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="7ed19-155">Cisco Jabber</span></span>
    
- <span data-ttu-id="7ed19-156">FactSet</span><span class="sxs-lookup"><span data-stu-id="7ed19-156">FactSet</span></span>
    
- <span data-ttu-id="7ed19-157">HipChat</span><span class="sxs-lookup"><span data-stu-id="7ed19-157">HipChat</span></span>
    
- <span data-ttu-id="7ed19-158">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="7ed19-158">InvestEdge</span></span>
    
- <span data-ttu-id="7ed19-159">LivePerson</span><span class="sxs-lookup"><span data-stu-id="7ed19-159">LivePerson</span></span>
    
- <span data-ttu-id="7ed19-160">
Secuencias de datos de MessageLabs
</span><span class="sxs-lookup"><span data-stu-id="7ed19-160">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="7ed19-161">OpenText</span><span class="sxs-lookup"><span data-stu-id="7ed19-161">OpenText</span></span>
    
- <span data-ttu-id="7ed19-162">Ayuda de Hacer clic para llamar de Oracle/ATG Live
</span><span class="sxs-lookup"><span data-stu-id="7ed19-162">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="7ed19-163">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="7ed19-163">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="7ed19-164">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ed19-164">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="7ed19-165">MindAlign</span><span class="sxs-lookup"><span data-stu-id="7ed19-165">MindAlign</span></span>
    
- <span data-ttu-id="7ed19-166">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="7ed19-166">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="7ed19-167">
Skype Empresarial (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="7ed19-167">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="7ed19-168">
Skype Empresarial Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-168">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="7ed19-169">Bases de datos SQL</span><span class="sxs-lookup"><span data-stu-id="7ed19-169">SQL Databases</span></span>
    
- <span data-ttu-id="7ed19-170">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="7ed19-170">Squawker</span></span>
    
- <span data-ttu-id="7ed19-171">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="7ed19-171">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="7ed19-172">Actiance</span><span class="sxs-lookup"><span data-stu-id="7ed19-172">Actiance</span></span>

<span data-ttu-id="7ed19-173">[Actiance](https://www.actiance.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-173">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7ed19-174">AIM</span><span class="sxs-lookup"><span data-stu-id="7ed19-174">AIM</span></span>
    
- <span data-ttu-id="7ed19-175">American Idol</span><span class="sxs-lookup"><span data-stu-id="7ed19-175">American Idol</span></span>
    
- <span data-ttu-id="7ed19-176">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="7ed19-176">Apple Juice</span></span>
    
- <span data-ttu-id="7ed19-177">
AOL con cliente Pivot
</span><span class="sxs-lookup"><span data-stu-id="7ed19-177">AOL with Pivot client</span></span>
    
- <span data-ttu-id="7ed19-178">Ares</span><span class="sxs-lookup"><span data-stu-id="7ed19-178">Ares</span></span>
    
- <span data-ttu-id="7ed19-179">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="7ed19-179">Bazaar Voice</span></span>
    
- <span data-ttu-id="7ed19-180">Bear Share</span><span class="sxs-lookup"><span data-stu-id="7ed19-180">Bear Share</span></span>
    
- <span data-ttu-id="7ed19-181">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="7ed19-181">Bit Torrent</span></span>
    
- <span data-ttu-id="7ed19-182">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-182">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-183">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-183">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-184">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-184">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-185">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-185">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-186">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="7ed19-186">Bloomberg Mail</span></span>
    
- <span data-ttu-id="7ed19-187">CellTrust</span><span class="sxs-lookup"><span data-stu-id="7ed19-187">CellTrust</span></span>
    
- <span data-ttu-id="7ed19-188">Importación de chat
</span><span class="sxs-lookup"><span data-stu-id="7ed19-188">Chat Import</span></span>
    
- <span data-ttu-id="7ed19-189">Directiva y registro en tiempo real de chat
</span><span class="sxs-lookup"><span data-stu-id="7ed19-189">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="7ed19-190">Chatter
</span><span class="sxs-lookup"><span data-stu-id="7ed19-190">Chatter</span></span>
    
- <span data-ttu-id="7ed19-191">Mensajería instantánea Cisco &amp; servidor de presencia (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="7ed19-191">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="7ed19-192">Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-192">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="7ed19-193">Importación de colaboración
</span><span class="sxs-lookup"><span data-stu-id="7ed19-193">Collaboration Import</span></span>
    
- <span data-ttu-id="7ed19-194">Registro de colaboración en tiempo real
</span><span class="sxs-lookup"><span data-stu-id="7ed19-194">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="7ed19-195">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="7ed19-195">Direct Connect</span></span>
    
- <span data-ttu-id="7ed19-196">Facebook</span><span class="sxs-lookup"><span data-stu-id="7ed19-196">Facebook</span></span>
    
- <span data-ttu-id="7ed19-197">FactSet</span><span class="sxs-lookup"><span data-stu-id="7ed19-197">FactSet</span></span>
    
- <span data-ttu-id="7ed19-198">FastTrack</span><span class="sxs-lookup"><span data-stu-id="7ed19-198">FastTrack</span></span>
    
- <span data-ttu-id="7ed19-199">Gnutella</span><span class="sxs-lookup"><span data-stu-id="7ed19-199">Gnutella</span></span>
    
- <span data-ttu-id="7ed19-200">Google+
</span><span class="sxs-lookup"><span data-stu-id="7ed19-200">Google+</span></span>
    
- <span data-ttu-id="7ed19-201">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="7ed19-201">GoToMyPC</span></span>
    
- <span data-ttu-id="7ed19-202">Hopster</span><span class="sxs-lookup"><span data-stu-id="7ed19-202">Hopster</span></span>
    
- <span data-ttu-id="7ed19-203">HubConnex</span><span class="sxs-lookup"><span data-stu-id="7ed19-203">HubConnex</span></span>
    
- <span data-ttu-id="7ed19-204">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-204">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="7ed19-205">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="7ed19-205">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="7ed19-206">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="7ed19-206">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="7ed19-207">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="7ed19-207">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="7ed19-208">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="7ed19-208">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="7ed19-209">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-209">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="7ed19-210">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="7ed19-210">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="7ed19-211">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="7ed19-211">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="7ed19-212">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="7ed19-212">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="7ed19-213">HIELO/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="7ed19-213">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="7ed19-214">Importación de mensajería instantánea
</span><span class="sxs-lookup"><span data-stu-id="7ed19-214">IM Import</span></span>
    
- <span data-ttu-id="7ed19-215">Directiva y registro de mensajería instantánea en tiempo real
</span><span class="sxs-lookup"><span data-stu-id="7ed19-215">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="7ed19-216">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="7ed19-216">Indii Messenger</span></span>
    
- <span data-ttu-id="7ed19-217">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="7ed19-217">Instant Bloomberg</span></span>
    
- <span data-ttu-id="7ed19-218">IRC</span><span class="sxs-lookup"><span data-stu-id="7ed19-218">IRC</span></span>
    
- <span data-ttu-id="7ed19-219">Jive
</span><span class="sxs-lookup"><span data-stu-id="7ed19-219">Jive</span></span>
    
- <span data-ttu-id="7ed19-220">Jive 6 Real Time Logging (v6, v7)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-220">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="7ed19-221">Jive Import</span><span class="sxs-lookup"><span data-stu-id="7ed19-221">Jive Import</span></span>
    
- <span data-ttu-id="7ed19-222">JXTA</span><span class="sxs-lookup"><span data-stu-id="7ed19-222">JXTA</span></span>
    
- <span data-ttu-id="7ed19-223">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7ed19-223">LinkedIn</span></span>
    
- <span data-ttu-id="7ed19-224">
Microsoft Lync (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-224">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="7ed19-225">MFTP</span><span class="sxs-lookup"><span data-stu-id="7ed19-225">MFTP</span></span>
    
- <span data-ttu-id="7ed19-226">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-226">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="7ed19-227">Microsoft SharePoint (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-227">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="7ed19-228">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7ed19-228">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="7ed19-229">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="7ed19-229">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="7ed19-230">MindAlign</span><span class="sxs-lookup"><span data-stu-id="7ed19-230">MindAlign</span></span>
    
- <span data-ttu-id="7ed19-231">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="7ed19-231">Mobile Guard</span></span>
    
- <span data-ttu-id="7ed19-232">MSN</span><span class="sxs-lookup"><span data-stu-id="7ed19-232">MSN</span></span>
    
- <span data-ttu-id="7ed19-233">My Space</span><span class="sxs-lookup"><span data-stu-id="7ed19-233">My Space</span></span>
    
- <span data-ttu-id="7ed19-234">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="7ed19-234">NEONetwork</span></span>
    
- <span data-ttu-id="7ed19-235">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="7ed19-235">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="7ed19-236">Mensajería instantánea compartida de Office 365
</span><span class="sxs-lookup"><span data-stu-id="7ed19-236">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="7ed19-237">Pinterest</span><span class="sxs-lookup"><span data-stu-id="7ed19-237">Pinterest</span></span>
    
- <span data-ttu-id="7ed19-238">Pivot</span><span class="sxs-lookup"><span data-stu-id="7ed19-238">Pivot</span></span>
    
- <span data-ttu-id="7ed19-239">QQ</span><span class="sxs-lookup"><span data-stu-id="7ed19-239">QQ</span></span>
    
- <span data-ttu-id="7ed19-240">Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="7ed19-240">Skype for Business 2015</span></span>
    
- <span data-ttu-id="7ed19-241">SoftEther</span><span class="sxs-lookup"><span data-stu-id="7ed19-241">SoftEther</span></span>
    
- <span data-ttu-id="7ed19-242">Symphony
</span><span class="sxs-lookup"><span data-stu-id="7ed19-242">Symphony</span></span>
    
- <span data-ttu-id="7ed19-243">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="7ed19-243">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="7ed19-244">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="7ed19-244">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="7ed19-245">Tor</span><span class="sxs-lookup"><span data-stu-id="7ed19-245">Tor</span></span>
    
- <span data-ttu-id="7ed19-246">TTT</span><span class="sxs-lookup"><span data-stu-id="7ed19-246">TTT</span></span>
    
- <span data-ttu-id="7ed19-247">Twitter</span><span class="sxs-lookup"><span data-stu-id="7ed19-247">Twitter</span></span>
    
- <span data-ttu-id="7ed19-248">WinMX</span><span class="sxs-lookup"><span data-stu-id="7ed19-248">WinMX</span></span>
    
- <span data-ttu-id="7ed19-249">Winny</span><span class="sxs-lookup"><span data-stu-id="7ed19-249">Winny</span></span>
    
- <span data-ttu-id="7ed19-250">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="7ed19-250">Yahoo</span></span>
    
- <span data-ttu-id="7ed19-251">Yammer</span><span class="sxs-lookup"><span data-stu-id="7ed19-251">Yammer</span></span>
    
- <span data-ttu-id="7ed19-252">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ed19-252">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="7ed19-253">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="7ed19-253">ArchiveSocial</span></span>

<span data-ttu-id="7ed19-254">[ArchiveSocial](https://www.archivesocial.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-254">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7ed19-255">Facebook</span><span class="sxs-lookup"><span data-stu-id="7ed19-255">Facebook</span></span>
    
- <span data-ttu-id="7ed19-256">Flickr
</span><span class="sxs-lookup"><span data-stu-id="7ed19-256">Flickr</span></span>
    
- <span data-ttu-id="7ed19-257">Instagram
</span><span class="sxs-lookup"><span data-stu-id="7ed19-257">Instagram</span></span>
    
- <span data-ttu-id="7ed19-258">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7ed19-258">LinkedIn</span></span>
    
- <span data-ttu-id="7ed19-259">Pinterest</span><span class="sxs-lookup"><span data-stu-id="7ed19-259">Pinterest</span></span>
    
- <span data-ttu-id="7ed19-260">Twitter</span><span class="sxs-lookup"><span data-stu-id="7ed19-260">Twitter</span></span>
    
- <span data-ttu-id="7ed19-261">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ed19-261">YouTube</span></span>
    
- <span data-ttu-id="7ed19-262">Vimeo</span><span class="sxs-lookup"><span data-stu-id="7ed19-262">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="7ed19-263">Globanet</span><span class="sxs-lookup"><span data-stu-id="7ed19-263">Globanet</span></span>

<span data-ttu-id="7ed19-264">[Globanet](https://www.globanet.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-264">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7ed19-265">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="7ed19-265">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="7ed19-266">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-266">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-267">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-267">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-268">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-268">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-269">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7ed19-269">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7ed19-270">Bloomberg Chat
</span><span class="sxs-lookup"><span data-stu-id="7ed19-270">Bloomberg Chat</span></span>
    
- <span data-ttu-id="7ed19-271">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="7ed19-271">Bloomberg Mail</span></span>
    
- <span data-ttu-id="7ed19-272">Box
</span><span class="sxs-lookup"><span data-stu-id="7ed19-272">Box</span></span>
    
- <span data-ttu-id="7ed19-273">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="7ed19-273">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="7ed19-274">Mensajería instantánea Cisco &amp; servidor de presencia (v10, v10.5.1 SU1, v11.0, v11.5 Do2)</span><span class="sxs-lookup"><span data-stu-id="7ed19-274">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="7ed19-275">Equipos de Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="7ed19-275">Cisco Webex Teams</span></span>

- <span data-ttu-id="7ed19-276">Área de trabajo de Citrix &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="7ed19-276">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="7ed19-277">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="7ed19-277">CrowdCompass</span></span>

- <span data-ttu-id="7ed19-278">Archivos de texto delimitados por tabulaciones personalizadas
</span><span class="sxs-lookup"><span data-stu-id="7ed19-278">Custom delimited text files</span></span>
    
- <span data-ttu-id="7ed19-279">Archivos XML personalizados
</span><span class="sxs-lookup"><span data-stu-id="7ed19-279">Custom XML files</span></span>
    
- <span data-ttu-id="7ed19-280">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="7ed19-280">Facebook (Pages)</span></span>
    
- <span data-ttu-id="7ed19-281">Factset
</span><span class="sxs-lookup"><span data-stu-id="7ed19-281">Factset</span></span>
    
- <span data-ttu-id="7ed19-282">FXConnect</span><span class="sxs-lookup"><span data-stu-id="7ed19-282">FXConnect</span></span>
    
- <span data-ttu-id="7ed19-283">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="7ed19-283">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="7ed19-284">Jive
</span><span class="sxs-lookup"><span data-stu-id="7ed19-284">Jive</span></span>
    
- <span data-ttu-id="7ed19-285">Macgregor XIP
</span><span class="sxs-lookup"><span data-stu-id="7ed19-285">Macgregor XIP</span></span>

- <span data-ttu-id="7ed19-286">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7ed19-286">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="7ed19-287">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="7ed19-287">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="7ed19-288">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ed19-288">Microsoft Teams</span></span>
       
- <span data-ttu-id="7ed19-289">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="7ed19-289">Microsoft Yammer</span></span>
    
- <span data-ttu-id="7ed19-290">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="7ed19-290">Mobile Guard</span></span>
    
- <span data-ttu-id="7ed19-291">Pivot</span><span class="sxs-lookup"><span data-stu-id="7ed19-291">Pivot</span></span>
    
- <span data-ttu-id="7ed19-292">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="7ed19-292">Salesforce Chatter</span></span>

- <span data-ttu-id="7ed19-293">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7ed19-293">Skype for Business Online</span></span>
    
- <span data-ttu-id="7ed19-294">Skype Empresarial, versiones 2007 R2 - 2016 (local)
</span><span class="sxs-lookup"><span data-stu-id="7ed19-294">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="7ed19-295">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="7ed19-295">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="7ed19-296">Symphony
</span><span class="sxs-lookup"><span data-stu-id="7ed19-296">Symphony</span></span>
    
- <span data-ttu-id="7ed19-297">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="7ed19-297">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="7ed19-298">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="7ed19-298">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="7ed19-299">Thomson Reuters Dealings 3000 / FX Trading
</span><span class="sxs-lookup"><span data-stu-id="7ed19-299">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="7ed19-300">Twitter</span><span class="sxs-lookup"><span data-stu-id="7ed19-300">Twitter</span></span>
    
- <span data-ttu-id="7ed19-301">UBS Chat
</span><span class="sxs-lookup"><span data-stu-id="7ed19-301">UBS Chat</span></span>
    
- <span data-ttu-id="7ed19-302">YouTube</span><span class="sxs-lookup"><span data-stu-id="7ed19-302">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="7ed19-303">OpenText</span><span class="sxs-lookup"><span data-stu-id="7ed19-303">OpenText</span></span>

<span data-ttu-id="7ed19-304">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-304">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7ed19-305">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="7ed19-305">Axs Encrypted</span></span>
    
- <span data-ttu-id="7ed19-306">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="7ed19-306">Axs Exchange</span></span>
    
- <span data-ttu-id="7ed19-307">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="7ed19-307">Axs Local Archive</span></span>
    
- <span data-ttu-id="7ed19-308">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="7ed19-308">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="7ed19-309">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="7ed19-309">Axs Signed</span></span>
    
- <span data-ttu-id="7ed19-310">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="7ed19-310">Bloomberg</span></span>
    
- <span data-ttu-id="7ed19-311">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="7ed19-311">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="7ed19-312">Verba</span><span class="sxs-lookup"><span data-stu-id="7ed19-312">Verba</span></span>

<span data-ttu-id="7ed19-313">[Verba](https://www.verba.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-313">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7ed19-314">Avaya Aura Video
</span><span class="sxs-lookup"><span data-stu-id="7ed19-314">Avaya Aura Video</span></span>
    
- <span data-ttu-id="7ed19-315">Avaya Aura Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-315">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="7ed19-316">Avtec Radio
</span><span class="sxs-lookup"><span data-stu-id="7ed19-316">Avtec Radio</span></span>
    
- <span data-ttu-id="7ed19-317">Bosch/Telex Radio
</span><span class="sxs-lookup"><span data-stu-id="7ed19-317">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="7ed19-318">BroadSoft Video
</span><span class="sxs-lookup"><span data-stu-id="7ed19-318">BroadSoft Video</span></span>
    
- <span data-ttu-id="7ed19-319">BroadSoft Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-319">BroadSoft Voice</span></span>
    
- <span data-ttu-id="7ed19-320">Centile Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-320">Centile Voice</span></span>
    
- <span data-ttu-id="7ed19-321">Cisco Jabber IM
</span><span class="sxs-lookup"><span data-stu-id="7ed19-321">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="7ed19-322">Cisco UC Video
</span><span class="sxs-lookup"><span data-stu-id="7ed19-322">Cisco UC Video</span></span>
    
- <span data-ttu-id="7ed19-323">Cisco UC Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-323">Cisco UC Voice</span></span>
    
- <span data-ttu-id="7ed19-324">Vídeo de Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="7ed19-324">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="7ed19-325">Cisco UCCX/UCCE voz</span><span class="sxs-lookup"><span data-stu-id="7ed19-325">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="7ed19-326">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="7ed19-326">ESChat Radio</span></span>
    
- <span data-ttu-id="7ed19-327">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="7ed19-327">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="7ed19-328">IP Trade Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-328">IP Trade Voice</span></span>
    
- <span data-ttu-id="7ed19-329">Centro de contacto de Luware LUCS</span><span class="sxs-lookup"><span data-stu-id="7ed19-329">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="7ed19-330">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="7ed19-330">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="7ed19-331">Mitel MiContact Center for Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="7ed19-331">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="7ed19-332">Vídeo de controlador de borde de sesión de paquete Oracle/Acme  
</span><span class="sxs-lookup"><span data-stu-id="7ed19-332">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="7ed19-333">Voz de controlador de borde de sesión de paquete Oracle/Acme
</span><span class="sxs-lookup"><span data-stu-id="7ed19-333">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="7ed19-334">Singtel Mobile Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-334">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="7ed19-335">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="7ed19-335">SIPREC Video</span></span>
    
-  <span data-ttu-id="7ed19-336">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="7ed19-336">SIPREC Voice</span></span> 
    
- <span data-ttu-id="7ed19-337">Skype Empresarial/MI de Lync
</span><span class="sxs-lookup"><span data-stu-id="7ed19-337">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="7ed19-338">Skype Empresarial/Vídeo de Lync
</span><span class="sxs-lookup"><span data-stu-id="7ed19-338">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="7ed19-339">Skype Empresarial/Voz de Lync
</span><span class="sxs-lookup"><span data-stu-id="7ed19-339">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="7ed19-340">Speakerbus Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-340">Speakerbus Voice</span></span>
    
- <span data-ttu-id="7ed19-341">Standard SIP/H.323 Video 
</span><span class="sxs-lookup"><span data-stu-id="7ed19-341">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="7ed19-342">Standard SIP/H.323 Voice 
</span><span class="sxs-lookup"><span data-stu-id="7ed19-342">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="7ed19-343">Truphone Voice
</span><span class="sxs-lookup"><span data-stu-id="7ed19-343">Truphone Voice</span></span>
    
- <span data-ttu-id="7ed19-344">TwistedPair Radio
</span><span class="sxs-lookup"><span data-stu-id="7ed19-344">TwistedPair Radio</span></span>
    
- <span data-ttu-id="7ed19-345">Pantalla de equipo de escritorio de Windows 
</span><span class="sxs-lookup"><span data-stu-id="7ed19-345">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="7ed19-346">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed19-346">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="7ed19-p109">Estos son los pasos para crear y configurar un buzón de correo de datos de terceros para la importación de datos a Office 365. Como anterior se explica, los elementos se importan a este buzón de correo si el conector de socio no puede asignar el identificador de usuario del elemento a una cuenta de usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="7ed19-349">**Completar estas tareas en el centro de administración de Office 365**</span><span class="sxs-lookup"><span data-stu-id="7ed19-349">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="7ed19-p110">Crear una nueva cuenta de usuario en Office 365 y asignar una licencia de Exchange Online Plan 2; vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Se requiere una licencia de Plan 2 para colocar el buzón de correo en juicio o habilitar un buzón de archivo que tiene una cuota de almacenamiento de información ilimitado.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="7ed19-352">Agregar la cuenta de usuario para el buzón de correo de terceros datos al rol de administrador de **Administrador de Exchange** en Office 365; vea [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="7ed19-352">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7ed19-p111">Escriba las credenciales para esta cuenta de usuario. Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="7ed19-355">**Completar estas tareas en el centro de administración de Exchange**</span><span class="sxs-lookup"><span data-stu-id="7ed19-355">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="7ed19-p112">Ocultar el buzón de correo de terceros datos desde la libreta de direcciones y otras listas de direcciones de su organización; vea [administrar buzones de usuario](https://go.microsoft.com/fwlink/p/?LinkId=616058). Como alternativa, puede ejecutar el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="7ed19-358">Asignar **contar** con permiso para el buzón de correo de datos de terceros para que los administradores o responsables del cumplimiento normativo pueden abrir el buzón de correo de datos de terceros en el cliente de escritorio de Outlook; vea [Administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="7ed19-358">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="7ed19-359">Habilitar las siguientes características de Office 365 relacionados con el cumplimiento de normas para el buzón de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="7ed19-359">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="7ed19-p113">Habilitar el buzón de archivo; vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md). Esto le permitirá libere espacio en el buzón principal mediante la configuración de una directiva de archivo que mueve los elementos de datos de terceros para el buzón de archivo. Esto le proporcionará almacenamiento ilimitado de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="7ed19-p114">Colocar el buzón de correo de datos de terceros en juicio. También puede aplicar una directiva de retención de Office 365 en la seguridad de Office 365 &amp; centro de cumplimiento. Colocar este buzón de correo en espera va a conservar los elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evitar que se purgarán desde el buzón de correo. Vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="7ed19-367">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="7ed19-367">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="7ed19-368">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed19-368">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="7ed19-p115">Habilitar el registro para el acceso al buzón de otro fabricante datos; propietario, delegado y administración de auditoría de buzón de correo vea la sección [Habilitar auditoría en Office 365 de buzón de correo](enable-mailbox-auditing.md). Esto le permitirá auditar la actividad de todos los realizado por cualquier usuario que tenga acceso al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="7ed19-371">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="7ed19-371">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="7ed19-p116">El siguiente paso es configurar los buzones de usuario para admitir los datos de otro fabricante. Completar estas tareas mediante el centro de administración de Exchange o mediante el uso de los cmdlets de Windows PowerShell correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="7ed19-374">Habilitar el buzón de archivo para cada usuario; vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7ed19-374">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="7ed19-375">Colocar buzones de usuario en juicio o aplicar una directiva de retención Office 365; vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7ed19-375">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="7ed19-376">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="7ed19-376">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="7ed19-377">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed19-377">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="7ed19-378">Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="7ed19-378">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="7ed19-379">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="7ed19-379">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="7ed19-380">El último paso es proporcionar a su asociado la información siguiente para que pueda configurar el conector y conectarse a su organización de Office 365 con el fin de importar datos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ed19-380">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="7ed19-381">El extremo que se usa para conectarse al servicio de Azure en Office 365:</span><span class="sxs-lookup"><span data-stu-id="7ed19-381">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="7ed19-p117">El inicio de sesión credenciales (identificador de usuario de Office 365 y la contraseña) del buzón de datos de terceros que creó en el paso 2. Estas credenciales son necesarias para que el conector de socio puede tener acceso e importar elementos a los buzones de usuario y el buzón de correo de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
    

  
## <a name="more-information"></a><span data-ttu-id="7ed19-384">Más información</span><span class="sxs-lookup"><span data-stu-id="7ed19-384">More information</span></span>

- <span data-ttu-id="7ed19-p118">Explica lo anterior, los elementos de datos de terceros orígenes se importan a los buzones de Exchange como mensajes de correo electrónico. El conector de socio importa el elemento mediante un esquema requerido por la API de Office 365. En la siguiente tabla se describe las propiedades de mensaje de un elemento de un origen de datos de terceros después de que se importa a un buzón de Exchange como un mensaje de correo electrónico. En la tabla también se indica si la propiedad message es obligatoria. Deben rellenarse propiedades obligatorias. Si un elemento no tiene una propiedad obligatoria, no se importan a Office 365. El proceso de importación devolverá un mensaje de error que explica por qué un elemento no se ha importado y qué propiedad es que faltan.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p118">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="7ed19-392">**Propiedad del mensaje**</span><span class="sxs-lookup"><span data-stu-id="7ed19-392">**Message property**</span></span>|<span data-ttu-id="7ed19-393">**¿Obligatorio?**</span><span class="sxs-lookup"><span data-stu-id="7ed19-393">**Mandatory?**</span></span>|<span data-ttu-id="7ed19-394">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7ed19-394">**Description**</span></span>|<span data-ttu-id="7ed19-395">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="7ed19-395">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7ed19-396">**FROM**</span><span class="sxs-lookup"><span data-stu-id="7ed19-396">**FROM**</span></span> <br/> |<span data-ttu-id="7ed19-397">Sí</span><span class="sxs-lookup"><span data-stu-id="7ed19-397">Yes</span></span>  <br/> |<span data-ttu-id="7ed19-p119">El usuario que creó originalmente o envía el elemento en el origen de datos de terceros. El conector de socio se intentará asignar el identificador de usuario desde el elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario de Office 365 para todos los participantes (los usuarios de los campos FROM y TO). Se va a importar una copia del mensaje al buzón de todos los participantes. Si ninguno de los participantes del elemento se pueden asignar a una cuenta de usuario de Office 365, el elemento se importará para el buzón de correo archivado de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p119">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="7ed19-p120">El participante que se identificó como el remitente del elemento debe tener un buzón en la organización de Office 365 que el elemento se importa a activo. Si el remitente no tiene un buzón de correo activo, se devuelve el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p120">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="7ed19-404">**TO**</span><span class="sxs-lookup"><span data-stu-id="7ed19-404">**TO**</span></span> <br/> |<span data-ttu-id="7ed19-405">Sí</span><span class="sxs-lookup"><span data-stu-id="7ed19-405">Yes</span></span>  <br/> |<span data-ttu-id="7ed19-406">El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7ed19-406">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="7ed19-407">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="7ed19-407">**SUBJECT**</span></span> <br/> |<span data-ttu-id="7ed19-408">No</span><span class="sxs-lookup"><span data-stu-id="7ed19-408">No</span></span>  <br/> |<span data-ttu-id="7ed19-409">El asunto del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="7ed19-409">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="7ed19-410">**FECHA**</span><span class="sxs-lookup"><span data-stu-id="7ed19-410">**DATE**</span></span> <br/> |<span data-ttu-id="7ed19-411">Sí</span><span class="sxs-lookup"><span data-stu-id="7ed19-411">Yes</span></span>  <br/> |<span data-ttu-id="7ed19-412">La fecha en la que el elemento originalmente se ha creado o publicado en el origen de datos del cliente; por ejemplo, la fecha en la que se ha publicado un mensaje en Twitter.</span><span class="sxs-lookup"><span data-stu-id="7ed19-412">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="7ed19-413">**BODY**</span><span class="sxs-lookup"><span data-stu-id="7ed19-413">**BODY**</span></span> <br/> |<span data-ttu-id="7ed19-414">No</span><span class="sxs-lookup"><span data-stu-id="7ed19-414">No</span></span>  <br/> |<span data-ttu-id="7ed19-p121">El contenido del mensaje o post. Para algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT** . Durante el proceso de importación, el conector de socio se intentará mantener fidelidad completa desde el origen de contenido como sea posible. Si es posible archivos, gráficos u otro contenido desde el cuerpo del elemento de origen se incluye en esta propiedad. De lo contrario, el contenido desde el elemento de origen se incluye en la propiedad **datos adjuntos** . El contenido de esta propiedad dependerán del conector de socio y en la capacidad de la plataforma de origen.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p121">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="7ed19-421">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="7ed19-421">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="7ed19-422">No</span><span class="sxs-lookup"><span data-stu-id="7ed19-422">No</span></span>  <br/> |<span data-ttu-id="7ed19-p122">Si un elemento en el origen de datos (por ejemplo, un mensajes en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluir imágenes, el socio conectar será el primer intento para incluir datos adjuntos en la propiedad **BODY** . Si eso no es posible, a continuación, se agrega a la ** datos adjuntos ** (propiedad). Otros ejemplos de los datos adjuntos son "Me gusta" en Facebook, metadatos desde el origen de contenido y las respuestas a un mensaje o post.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p122">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the ** ATTACHMENT ** property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="7ed19-426">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="7ed19-426">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="7ed19-427">Sí</span><span class="sxs-lookup"><span data-stu-id="7ed19-427">Yes</span></span>  <br/> | <span data-ttu-id="7ed19-p123">Se trata de una propiedad multivalor, que se crea y se rellena por el conector de socio. El formato de esta propiedad es `IPM.NOTE.Source.Event`. (Esta propiedad debe comenzar con `IPM.NOTE`; este formato es similar a la de la `IPM.NOTE.X` clase de mensaje.) Esta propiedad incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p123">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="7ed19-431">`Source`-Indica el origen de datos de terceros; Por ejemplo, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="7ed19-431">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="7ed19-p124">`Event`-Indica el tipo de actividad que se llevó a cabo en el origen de datos de otros fabricantes que producen los elementos; Por ejemplo, un mensajes en Twitter o una entrada en Facebook. Eventos son específicos para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p124">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="7ed19-p125">Uno de los objetivos de esta propiedad es filtrar elementos específicos según el origen de datos donde un elemento se originó o en función del tipo de evento. Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para buscar todos los tweets a la que se contabilizaron por un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p125">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="7ed19-p126">Cuando los elementos se importan correctamente a los buzones de correo en Office 365, se devuelve un identificador único al autor de la llamada como parte de la respuesta HTTP. Este identificador, denominado `x-IngestionCorrelationID`— puede usarse para fines de solución de problemas posteriores por los socios para realizar un seguimiento de los elementos de extremo a otro. Se recomienda que los socios capturan esta información y registrarla según corresponda en su extremo. Este es un ejemplo de una respuesta HTTP que muestra este identificador:</span><span class="sxs-lookup"><span data-stu-id="7ed19-p126">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="7ed19-p127">Puede usar la herramienta de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar los elementos que se han importado a buzones de correo en Office 365 desde un origen de datos de terceros. Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valor de la propiedad de mensaje en el cuadro de palabra clave para una búsqueda de contenido. .</span><span class="sxs-lookup"><span data-stu-id="7ed19-p127">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="7ed19-p128">**`kind:externaldata`**-Use este par de valor de la propiedad para buscar todos los tipos de datos de terceros. Por ejemplo, para buscar los elementos que se importaron desde un origen de datos de terceros y contiene la palabra "contoso" en la propiedad Subject del elemento importado, usaría la consulta de palabra clave `kind:externaldata AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p128">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="7ed19-p129">**`itemclass:ipm.externaldata.<third-party data type>`**-Usar este par de valor de la propiedad a la búsqueda sólo un tipo de especificar de datos de terceros. Por ejemplo, para buscar sólo los datos de Facebook que contiene la palabra "contoso" en la propiedad Subject, usaría la consulta de palabra clave `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="7ed19-p129">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="7ed19-447">Para obtener una lista completa de los valores que se usará para tipos de datos de terceros para la `itemclass` (propiedad), consulte [Usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="7ed19-447">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="7ed19-448">Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:</span><span class="sxs-lookup"><span data-stu-id="7ed19-448">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="7ed19-449">Búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="7ed19-449">Content Search in Office 365</span></span>](content-search.md)
    
  - <span data-ttu-id="7ed19-450">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="7ed19-450">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
 

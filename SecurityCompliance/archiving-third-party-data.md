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
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Los administradores pueden importar datos de otros proveedores de plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos a buzones de correo en la organización de Office 365. Esto le permite archivar datos de orígenes de datos, Twitter y Facebook en Office 365. A continuación, puede appply las características de cumplimiento de normas de Office 365 (por ejemplo, retención legal, búsqueda de contenido y las directivas de retención) a los datos de otro fabricante.
ms.openlocfilehash: 5e8fe94e0c3e8b39aec479f4755a263438513d35
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038113"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="13c1e-105">Archivado de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="13c1e-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="13c1e-p102">Permite a los administradores importan y archivar datos de terceros desde plataformas de medios sociales, plataformas y plataformas de colaboración de documentos, a los buzones de correo en la organización de Office 365 de mensajería instantánea de Office 365. Ejemplos de orígenes de datos de terceros que se pueden importar a Office 365 incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="13c1e-108">**Social** - Twitter, Facebook, Yammer y LinkedIn</span><span class="sxs-lookup"><span data-stu-id="13c1e-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="13c1e-109">**Mensajería instantánea** - Yahoo Messenger, GoogleTalk y Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="13c1e-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="13c1e-110">**Colaboración en documentos** - cuadro y lista desplegable</span><span class="sxs-lookup"><span data-stu-id="13c1e-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="13c1e-111">**Industrias verticales** - administración de relaciones de cliente (por ejemplo, la cháchara de fuerza de ventas) y Financials (por ejemplo, Reuters Thomson y Bloomberg)</span><span class="sxs-lookup"><span data-stu-id="13c1e-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="13c1e-112">**Mensajería de texto SMS /** - BlackBerry</span><span class="sxs-lookup"><span data-stu-id="13c1e-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="13c1e-p103">Después de importan datos de otro fabricante, puede aplicar las características de cumplimiento de normas de Office 365, como las directivas de retención de la suspensión por litigio, búsqueda de contenido, en lugar de archivado, auditoría y Office 365 — a estos datos. Por ejemplo, cuando un buzón de correo se coloca en suspensión por litigio, se conservarán los datos de otro fabricante. Puede buscar datos de terceros mediante el uso de búsqueda de contenido. O puede aplicar el archivado y las políticas de retención a los datos de terceros, al igual que puede utilizar para datos de Microsoft. En resumen, el archivado de datos de terceros en Office 365 puede ayudar a su organización mantenga la compatibilidad con el gobierno y las directivas de las normativas.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="13c1e-118">Aquí es información general sobre el proceso y los pasos necesarios para importar datos de otros fabricantes a Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="13c1e-119">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="13c1e-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="13c1e-120">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="13c1e-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="13c1e-121">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="13c1e-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="13c1e-122">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="13c1e-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="13c1e-123">Paso 5: Registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13c1e-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="13c1e-124">Proceso de importación de los datos de otros fabricantes de cómo funciona ></span><span class="sxs-lookup"><span data-stu-id="13c1e-124">How the third-party data import process works></span></span>

<span data-ttu-id="13c1e-125">En la ilustración y la descripción siguientes se explica cómo funciona el proceso de importación de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="13c1e-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![Cómo funciona el proceso de importación de datos de terceros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="13c1e-127">Cliente funciona con su socio de elección para configurar un conector que se va a extraer los elementos del origen de datos de terceros y, a continuación, importar esos elementos a Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="13c1e-p104">El conector de socio se conecta a orígenes de datos de terceros mediante una API de terceros (de forma programada o configurado como) y extrae los elementos del origen de datos. El conector de socio convierte el contenido de un elemento en un formato de mensaje de correo electrónico. Vea la sección [obtener más información](#more-information) para obtener una descripción del esquema de formato de mensaje.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="13c1e-131">Conector de socio se conecta al servicio de Azure en Office 365 mediante el uso de servicio de Web Exchange (EWS) a través de un punto final conocido.</span><span class="sxs-lookup"><span data-stu-id="13c1e-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="13c1e-p105">Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="13c1e-p106">r. **los elementos que tienen un identificador de usuario que corresponde a una cuenta de usuario de Office 365** - si el conector de socio puede asignar el identificador de usuario del elemento en el origen de datos de terceros a un usuario determinado que identificador en Office 365, el elemento se copia a la carpeta de **purga** en el usuario Carpeta elementos recuperables. Los usuarios no pueden tener acceso a los elementos de la carpeta de purga. Sin embargo, puede usar herramientas de exhibición de documentos electrónicos de Office 365 para buscar elementos en la carpeta de purga.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="13c1e-p107">b. **los elementos que no tienen un identificador de usuario que corresponde a una cuenta de usuario de Office 365** - si el conector de socio no puede asignar el identificador de usuario de un elemento a un usuario determinado que identificador en Office 365, el elemento se copia en la carpeta **Bandeja de entrada** del buzón de datos de terceros. Importación de elementos a la Bandeja de entrada permite usted o alguien de su organización para iniciar sesión en el buzón de correo de terceros para ver y administrar estos elementos y vea si los ajustes deben realizarse en la configuración del conector de socio.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="13c1e-141">Paso 1: Buscar un asociado de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="13c1e-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="13c1e-p108">Un componente clave para el archivado de datos de terceros en Office 365 es buscar y trabajar con un socio de Microsoft que está especializado en capturar los datos de un origen de datos de terceros y se importa a Office 365. Una vez que se importan los datos, puede archivar y conserva junto con la organización de otros datos de Microsoft, como correo electrónico de Exchange y los documentos de SharePoint y OneDrive para la empresa. Un socio crea un conector que extrae datos de orígenes de datos de terceros de su organización (por ejemplo, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter y YouTube) y pasa los datos a una API de Office 365 que importa los elementos a los buzones de Exchange como mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="13c1e-145">Las secciones siguientes enumeran los socios de Microsoft y los orígenes de datos de terceros que admiten — que participan en el programa para el archivado de datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="13c1e-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="13c1e-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="13c1e-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="13c1e-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="13c1e-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="13c1e-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="13c1e-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="13c1e-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="13c1e-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="13c1e-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="13c1e-151">Verba</span><span class="sxs-lookup"><span data-stu-id="13c1e-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="13c1e-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="13c1e-152">17a-4 LLC</span></span>

<span data-ttu-id="13c1e-153">17a-4 LLC admite los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="13c1e-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="13c1e-154">BlackBerry</span></span>
    
- <span data-ttu-id="13c1e-155">Secuencias de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="13c1e-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="13c1e-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="13c1e-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="13c1e-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="13c1e-157">FactSet</span></span>
    
- <span data-ttu-id="13c1e-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="13c1e-158">HipChat</span></span>
    
- <span data-ttu-id="13c1e-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="13c1e-159">InvestEdge</span></span>
    
- <span data-ttu-id="13c1e-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="13c1e-160">LivePerson</span></span>
    
- <span data-ttu-id="13c1e-161">
Secuencias de datos de MessageLabs
</span><span class="sxs-lookup"><span data-stu-id="13c1e-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="13c1e-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="13c1e-162">OpenText</span></span>
    
- <span data-ttu-id="13c1e-163">Ayuda de Hacer clic para llamar de Oracle/ATG Live
</span><span class="sxs-lookup"><span data-stu-id="13c1e-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="13c1e-164">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="13c1e-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="13c1e-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="13c1e-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="13c1e-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="13c1e-166">MindAlign</span></span>
    
- <span data-ttu-id="13c1e-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="13c1e-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="13c1e-168">
Skype Empresarial (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="13c1e-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="13c1e-169">
Skype Empresarial Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="13c1e-170">Bases de datos SQL</span><span class="sxs-lookup"><span data-stu-id="13c1e-170">SQL Databases</span></span>
    
- <span data-ttu-id="13c1e-171">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="13c1e-171">Squawker</span></span>
    
- <span data-ttu-id="13c1e-172">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="13c1e-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="13c1e-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="13c1e-173">Actiance</span></span>

<span data-ttu-id="13c1e-174">[Actiance](https://www.actiance.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="13c1e-175">AIM</span><span class="sxs-lookup"><span data-stu-id="13c1e-175">AIM</span></span>
    
- <span data-ttu-id="13c1e-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="13c1e-176">American Idol</span></span>
    
- <span data-ttu-id="13c1e-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="13c1e-177">Apple Juice</span></span>
    
- <span data-ttu-id="13c1e-178">
AOL con cliente Pivot
</span><span class="sxs-lookup"><span data-stu-id="13c1e-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="13c1e-179">Ares</span><span class="sxs-lookup"><span data-stu-id="13c1e-179">Ares</span></span>
    
- <span data-ttu-id="13c1e-180">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="13c1e-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="13c1e-181">Bear Share</span><span class="sxs-lookup"><span data-stu-id="13c1e-181">Bear Share</span></span>
    
- <span data-ttu-id="13c1e-182">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="13c1e-182">Bit Torrent</span></span>
    
- <span data-ttu-id="13c1e-183">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-184">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-185">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-186">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-187">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="13c1e-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="13c1e-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="13c1e-188">CellTrust</span></span>
    
- <span data-ttu-id="13c1e-189">Importación de chat
</span><span class="sxs-lookup"><span data-stu-id="13c1e-189">Chat Import</span></span>
    
- <span data-ttu-id="13c1e-190">Directiva y registro en tiempo real de chat
</span><span class="sxs-lookup"><span data-stu-id="13c1e-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="13c1e-191">Chatter
</span><span class="sxs-lookup"><span data-stu-id="13c1e-191">Chatter</span></span>
    
- <span data-ttu-id="13c1e-192">Mensajería instantánea Cisco &amp; servidor de presencia (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="13c1e-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="13c1e-193">Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="13c1e-194">Importación de colaboración
</span><span class="sxs-lookup"><span data-stu-id="13c1e-194">Collaboration Import</span></span>
    
- <span data-ttu-id="13c1e-195">Registro de colaboración en tiempo real
</span><span class="sxs-lookup"><span data-stu-id="13c1e-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="13c1e-196">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="13c1e-196">Direct Connect</span></span>
    
- <span data-ttu-id="13c1e-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="13c1e-197">Facebook</span></span>
    
- <span data-ttu-id="13c1e-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="13c1e-198">FactSet</span></span>
    
- <span data-ttu-id="13c1e-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="13c1e-199">FastTrack</span></span>
    
- <span data-ttu-id="13c1e-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="13c1e-200">Gnutella</span></span>
    
- <span data-ttu-id="13c1e-201">Google+
</span><span class="sxs-lookup"><span data-stu-id="13c1e-201">Google+</span></span>
    
- <span data-ttu-id="13c1e-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="13c1e-202">GoToMyPC</span></span>
    
- <span data-ttu-id="13c1e-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="13c1e-203">Hopster</span></span>
    
- <span data-ttu-id="13c1e-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="13c1e-204">HubConnex</span></span>
    
- <span data-ttu-id="13c1e-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="13c1e-206">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="13c1e-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="13c1e-207">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="13c1e-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="13c1e-208">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="13c1e-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="13c1e-209">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="13c1e-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="13c1e-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="13c1e-211">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="13c1e-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="13c1e-212">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="13c1e-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="13c1e-213">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="13c1e-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="13c1e-214">HIELO/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="13c1e-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="13c1e-215">Importación de mensajería instantánea
</span><span class="sxs-lookup"><span data-stu-id="13c1e-215">IM Import</span></span>
    
- <span data-ttu-id="13c1e-216">Directiva y registro de mensajería instantánea en tiempo real
</span><span class="sxs-lookup"><span data-stu-id="13c1e-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="13c1e-217">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="13c1e-217">Indii Messenger</span></span>
    
- <span data-ttu-id="13c1e-218">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="13c1e-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="13c1e-219">IRC</span><span class="sxs-lookup"><span data-stu-id="13c1e-219">IRC</span></span>
    
- <span data-ttu-id="13c1e-220">Jive
</span><span class="sxs-lookup"><span data-stu-id="13c1e-220">Jive</span></span>
    
- <span data-ttu-id="13c1e-221">Jive 6 Real Time Logging (v6, v7)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="13c1e-222">Jive Import</span><span class="sxs-lookup"><span data-stu-id="13c1e-222">Jive Import</span></span>
    
- <span data-ttu-id="13c1e-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="13c1e-223">JXTA</span></span>
    
- <span data-ttu-id="13c1e-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="13c1e-224">LinkedIn</span></span>
    
- <span data-ttu-id="13c1e-225">
Microsoft Lync (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="13c1e-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="13c1e-226">MFTP</span></span>
    
- <span data-ttu-id="13c1e-227">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="13c1e-228">Microsoft SharePoint (2010, 2013)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="13c1e-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="13c1e-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="13c1e-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="13c1e-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="13c1e-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="13c1e-231">MindAlign</span></span>
    
- <span data-ttu-id="13c1e-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="13c1e-232">Mobile Guard</span></span>
    
- <span data-ttu-id="13c1e-233">MSN</span><span class="sxs-lookup"><span data-stu-id="13c1e-233">MSN</span></span>
    
- <span data-ttu-id="13c1e-234">My Space</span><span class="sxs-lookup"><span data-stu-id="13c1e-234">My Space</span></span>
    
- <span data-ttu-id="13c1e-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="13c1e-235">NEONetwork</span></span>
    
- <span data-ttu-id="13c1e-236">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="13c1e-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="13c1e-237">Mensajería instantánea compartida de Office 365
</span><span class="sxs-lookup"><span data-stu-id="13c1e-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="13c1e-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="13c1e-238">Pinterest</span></span>
    
- <span data-ttu-id="13c1e-239">Pivot</span><span class="sxs-lookup"><span data-stu-id="13c1e-239">Pivot</span></span>
    
- <span data-ttu-id="13c1e-240">QQ</span><span class="sxs-lookup"><span data-stu-id="13c1e-240">QQ</span></span>
    
- <span data-ttu-id="13c1e-241">Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="13c1e-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="13c1e-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="13c1e-242">SoftEther</span></span>
    
- <span data-ttu-id="13c1e-243">Symphony
</span><span class="sxs-lookup"><span data-stu-id="13c1e-243">Symphony</span></span>
    
- <span data-ttu-id="13c1e-244">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="13c1e-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="13c1e-245">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="13c1e-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="13c1e-246">Tor</span><span class="sxs-lookup"><span data-stu-id="13c1e-246">Tor</span></span>
    
- <span data-ttu-id="13c1e-247">TTT</span><span class="sxs-lookup"><span data-stu-id="13c1e-247">TTT</span></span>
    
- <span data-ttu-id="13c1e-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="13c1e-248">Twitter</span></span>
    
- <span data-ttu-id="13c1e-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="13c1e-249">WinMX</span></span>
    
- <span data-ttu-id="13c1e-250">Winny</span><span class="sxs-lookup"><span data-stu-id="13c1e-250">Winny</span></span>
    
- <span data-ttu-id="13c1e-251">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="13c1e-251">Yahoo</span></span>
    
- <span data-ttu-id="13c1e-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="13c1e-252">Yammer</span></span>
    
- <span data-ttu-id="13c1e-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="13c1e-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="13c1e-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="13c1e-254">ArchiveSocial</span></span>

<span data-ttu-id="13c1e-255">[ArchiveSocial](https://www.archivesocial.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="13c1e-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="13c1e-256">Facebook</span></span>
    
- <span data-ttu-id="13c1e-257">Flickr
</span><span class="sxs-lookup"><span data-stu-id="13c1e-257">Flickr</span></span>
    
- <span data-ttu-id="13c1e-258">Instagram
</span><span class="sxs-lookup"><span data-stu-id="13c1e-258">Instagram</span></span>
    
- <span data-ttu-id="13c1e-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="13c1e-259">LinkedIn</span></span>
    
- <span data-ttu-id="13c1e-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="13c1e-260">Pinterest</span></span>
    
- <span data-ttu-id="13c1e-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="13c1e-261">Twitter</span></span>
    
- <span data-ttu-id="13c1e-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="13c1e-262">YouTube</span></span>
    
- <span data-ttu-id="13c1e-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="13c1e-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="13c1e-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="13c1e-264">Globanet</span></span>

<span data-ttu-id="13c1e-265">[Globanet](https://www.globanet.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="13c1e-266">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="13c1e-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="13c1e-267">Registros de llamadas de BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-268">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-269">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-270">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="13c1e-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="13c1e-271">Bloomberg Chat
</span><span class="sxs-lookup"><span data-stu-id="13c1e-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="13c1e-272">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="13c1e-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="13c1e-273">Box
</span><span class="sxs-lookup"><span data-stu-id="13c1e-273">Box</span></span>
    
- <span data-ttu-id="13c1e-274">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="13c1e-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="13c1e-275">Mensajería instantánea Cisco &amp; servidor de presencia (v10, v10.5.1 SU1, v11.0, v11.5 Do2)</span><span class="sxs-lookup"><span data-stu-id="13c1e-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="13c1e-276">Equipos de Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="13c1e-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="13c1e-277">Área de trabajo de Citrix &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="13c1e-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="13c1e-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="13c1e-278">CrowdCompass</span></span>

- <span data-ttu-id="13c1e-279">Archivos de texto delimitados por tabulaciones personalizadas
</span><span class="sxs-lookup"><span data-stu-id="13c1e-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="13c1e-280">Archivos XML personalizados
</span><span class="sxs-lookup"><span data-stu-id="13c1e-280">Custom XML files</span></span>
    
- <span data-ttu-id="13c1e-281">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="13c1e-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="13c1e-282">Factset
</span><span class="sxs-lookup"><span data-stu-id="13c1e-282">Factset</span></span>
    
- <span data-ttu-id="13c1e-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="13c1e-283">FXConnect</span></span>
    
- <span data-ttu-id="13c1e-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="13c1e-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="13c1e-285">Jive
</span><span class="sxs-lookup"><span data-stu-id="13c1e-285">Jive</span></span>
    
- <span data-ttu-id="13c1e-286">Macgregor XIP
</span><span class="sxs-lookup"><span data-stu-id="13c1e-286">Macgregor XIP</span></span>

- <span data-ttu-id="13c1e-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="13c1e-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="13c1e-288">Microsoft OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="13c1e-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="13c1e-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13c1e-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="13c1e-290">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="13c1e-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="13c1e-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="13c1e-291">Mobile Guard</span></span>
    
- <span data-ttu-id="13c1e-292">Pivot</span><span class="sxs-lookup"><span data-stu-id="13c1e-292">Pivot</span></span>
    
- <span data-ttu-id="13c1e-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="13c1e-293">Salesforce Chatter</span></span>

- <span data-ttu-id="13c1e-294">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="13c1e-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="13c1e-295">Skype Empresarial, versiones 2007 R2 - 2016 (local)
</span><span class="sxs-lookup"><span data-stu-id="13c1e-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="13c1e-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="13c1e-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="13c1e-297">Symphony
</span><span class="sxs-lookup"><span data-stu-id="13c1e-297">Symphony</span></span>
    
- <span data-ttu-id="13c1e-298">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="13c1e-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="13c1e-299">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="13c1e-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="13c1e-300">Thomson Reuters Dealings 3000 / FX Trading
</span><span class="sxs-lookup"><span data-stu-id="13c1e-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="13c1e-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="13c1e-301">Twitter</span></span>
    
- <span data-ttu-id="13c1e-302">UBS Chat
</span><span class="sxs-lookup"><span data-stu-id="13c1e-302">UBS Chat</span></span>
    
- <span data-ttu-id="13c1e-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="13c1e-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="13c1e-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="13c1e-304">OpenText</span></span>

<span data-ttu-id="13c1e-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="13c1e-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="13c1e-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="13c1e-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="13c1e-307">Axs Exchange</span></span>
    
- <span data-ttu-id="13c1e-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="13c1e-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="13c1e-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="13c1e-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="13c1e-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="13c1e-310">Axs Signed</span></span>
    
- <span data-ttu-id="13c1e-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="13c1e-311">Bloomberg</span></span>
    
- <span data-ttu-id="13c1e-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="13c1e-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="13c1e-313">Verba</span><span class="sxs-lookup"><span data-stu-id="13c1e-313">Verba</span></span>

<span data-ttu-id="13c1e-314">[Verba](https://www.verba.com) es compatible con los siguientes orígenes de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="13c1e-315">Avaya Aura Video
</span><span class="sxs-lookup"><span data-stu-id="13c1e-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="13c1e-316">Avaya Aura Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="13c1e-317">Avtec Radio
</span><span class="sxs-lookup"><span data-stu-id="13c1e-317">Avtec Radio</span></span>
    
- <span data-ttu-id="13c1e-318">Bosch/Telex Radio
</span><span class="sxs-lookup"><span data-stu-id="13c1e-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="13c1e-319">BroadSoft Video
</span><span class="sxs-lookup"><span data-stu-id="13c1e-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="13c1e-320">BroadSoft Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="13c1e-321">Centile Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-321">Centile Voice</span></span>
    
- <span data-ttu-id="13c1e-322">Cisco Jabber IM
</span><span class="sxs-lookup"><span data-stu-id="13c1e-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="13c1e-323">Cisco UC Video
</span><span class="sxs-lookup"><span data-stu-id="13c1e-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="13c1e-324">Cisco UC Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="13c1e-325">Vídeo de Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="13c1e-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="13c1e-326">Cisco UCCX/UCCE voz</span><span class="sxs-lookup"><span data-stu-id="13c1e-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="13c1e-327">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="13c1e-327">ESChat Radio</span></span>
    
- <span data-ttu-id="13c1e-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="13c1e-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="13c1e-329">IP Trade Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="13c1e-330">Centro de contacto de Luware LUCS</span><span class="sxs-lookup"><span data-stu-id="13c1e-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="13c1e-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="13c1e-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="13c1e-332">Mitel MiContact Center for Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="13c1e-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="13c1e-333">Vídeo de controlador de borde de sesión de paquete Oracle/Acme  
</span><span class="sxs-lookup"><span data-stu-id="13c1e-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="13c1e-334">Voz de controlador de borde de sesión de paquete Oracle/Acme
</span><span class="sxs-lookup"><span data-stu-id="13c1e-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="13c1e-335">Singtel Mobile Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="13c1e-336">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="13c1e-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="13c1e-337">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="13c1e-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="13c1e-338">Skype Empresarial/MI de Lync
</span><span class="sxs-lookup"><span data-stu-id="13c1e-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="13c1e-339">Skype Empresarial/Vídeo de Lync
</span><span class="sxs-lookup"><span data-stu-id="13c1e-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="13c1e-340">Skype Empresarial/Voz de Lync
</span><span class="sxs-lookup"><span data-stu-id="13c1e-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="13c1e-341">Speakerbus Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="13c1e-342">Standard SIP/H.323 Video 
</span><span class="sxs-lookup"><span data-stu-id="13c1e-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="13c1e-343">Standard SIP/H.323 Voice 
</span><span class="sxs-lookup"><span data-stu-id="13c1e-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="13c1e-344">Truphone Voice
</span><span class="sxs-lookup"><span data-stu-id="13c1e-344">Truphone Voice</span></span>
    
- <span data-ttu-id="13c1e-345">TwistedPair Radio
</span><span class="sxs-lookup"><span data-stu-id="13c1e-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="13c1e-346">Pantalla de equipo de escritorio de Windows 
</span><span class="sxs-lookup"><span data-stu-id="13c1e-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="13c1e-347">Paso 2: Crear y configurar un buzón de datos de terceros en Office 365</span><span class="sxs-lookup"><span data-stu-id="13c1e-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="13c1e-p109">Estos son los pasos para crear y configurar un buzón de correo de datos de terceros para la importación de datos a Office 365. Como anterior se explica, los elementos se importan a este buzón de correo si el conector de socio no puede asignar el identificador de usuario del elemento a una cuenta de usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="13c1e-350">**Completar estas tareas en el centro de administración de Office 365**</span><span class="sxs-lookup"><span data-stu-id="13c1e-350">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="13c1e-p110">Crear una nueva cuenta de usuario en Office 365 y asignar una licencia de Exchange Online Plan 2; vea [Agregar usuarios a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Se requiere una licencia de Plan 2 para colocar el buzón de correo en juicio o habilitar un buzón de archivo que tiene una cuota de almacenamiento de información ilimitado.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="13c1e-353">Agregar la cuenta de usuario para el buzón de correo de terceros datos al rol de administrador de **Administrador de Exchange** en Office 365; vea [asignar roles de administrador en Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="13c1e-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="13c1e-p111">Escriba las credenciales para esta cuenta de usuario. Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="13c1e-356">**Completar estas tareas en el centro de administración de Exchange**</span><span class="sxs-lookup"><span data-stu-id="13c1e-356">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="13c1e-p112">Ocultar el buzón de correo de terceros datos desde la libreta de direcciones y otras listas de direcciones de su organización; vea [administrar buzones de usuario](https://go.microsoft.com/fwlink/p/?LinkId=616058). Como alternativa, puede ejecutar el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="13c1e-359">Asignar **contar** con permiso para el buzón de correo de datos de terceros para que los administradores o responsables del cumplimiento normativo pueden abrir el buzón de correo de datos de terceros en el cliente de escritorio de Outlook; vea [Administrar permisos para los destinatarios](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="13c1e-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="13c1e-360">Habilitar las siguientes características de Office 365 relacionados con el cumplimiento de normas para el buzón de datos de terceros:</span><span class="sxs-lookup"><span data-stu-id="13c1e-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="13c1e-p113">Habilitar el buzón de archivo; vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md). Esto le permitirá libere espacio en el buzón principal mediante la configuración de una directiva de archivo que mueve los elementos de datos de terceros para el buzón de archivo. Esto le proporcionará almacenamiento ilimitado de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="13c1e-p114">Colocar el buzón de correo de datos de terceros en juicio. También puede aplicar una directiva de retención de Office 365 en la seguridad de Office 365 &amp; centro de cumplimiento. Colocar este buzón de correo en espera va a conservar los elementos de datos de terceros (indefinidamente o durante un tiempo especificado) y evitar que se purgarán desde el buzón de correo. Vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="13c1e-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="13c1e-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="13c1e-369">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="13c1e-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="13c1e-p115">Habilitar el registro para el acceso al buzón de otro fabricante datos; propietario, delegado y administración de auditoría de buzón de correo vea la sección [Habilitar auditoría en Office 365 de buzón de correo](enable-mailbox-auditing.md). Esto le permitirá auditar la actividad de todos los realizado por cualquier usuario que tenga acceso al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="13c1e-372">Paso 3: Configurar los buzones de usuario para los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="13c1e-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="13c1e-p116">El siguiente paso es configurar los buzones de usuario para admitir los datos de otro fabricante. Completar estas tareas mediante el centro de administración de Exchange o mediante el uso de los cmdlets de Windows PowerShell correspondientes.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="13c1e-375">Habilitar el buzón de archivo para cada usuario; vea [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md) y [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="13c1e-375">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="13c1e-376">Colocar buzones de usuario en juicio o aplicar una directiva de retención Office 365; vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="13c1e-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="13c1e-377">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="13c1e-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="13c1e-378">Introducción a las directivas de retención en Office 365</span><span class="sxs-lookup"><span data-stu-id="13c1e-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="13c1e-379">Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="13c1e-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="13c1e-380">Paso 4: Proporcionar información al asociado</span><span class="sxs-lookup"><span data-stu-id="13c1e-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="13c1e-381">El último paso es proporcionar a su asociado la información siguiente para que pueda configurar el conector y conectarse a su organización de Office 365 con el fin de importar datos a los buzones de usuario y al buzón de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="13c1e-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="13c1e-382">El extremo que se usa para conectarse al servicio de Azure en Office 365:</span><span class="sxs-lookup"><span data-stu-id="13c1e-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="13c1e-p117">El inicio de sesión credenciales (identificador de usuario de Office 365 y la contraseña) del buzón de datos de terceros que creó en el paso 2. Estas credenciales son necesarias para que el conector de socio puede tener acceso e importar elementos a los buzones de usuario y el buzón de correo de datos de terceros.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="13c1e-385">Paso 5: Registrar el conector de datos de terceros en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13c1e-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="13c1e-p118">Iniciar el 30 de septiembre de 2018, el servicio de Azure en Office 365 comenzará con autenticación moderna en Exchange Online para autenticar los conectores de datos de terceros que intenten conectarse a la organización de Office 365 para importar datos. La razón de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se ha basado en la lista blanca los conectores de terceros que usan el extremo descrito anteriormente para conectarse al servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p118">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data. The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="13c1e-p119">Para habilitar un conector de datos de terceros para conectarse a Office 365 con el nuevo método de autenticación moderno, debe consentimiento de un administrador de la organización de Office 365 para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory. Esto se realiza mediante la aceptación de una solicitud de permisos para permitir que el conector de acceso a datos de la organización de Azure Active Directory. Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa para Azure Active Directory y representado como una entidad de seguridad de servicio. Para el proceso de consentimiento de obtener más información, vea [Administración de inquilinos da su consentimiento](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="13c1e-p119">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory. This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory. After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal. For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="13c1e-392">Estos son los pasos para tener acceso y aceptar la solicitud para registrar el conector:</span><span class="sxs-lookup"><span data-stu-id="13c1e-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="13c1e-393">Vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="13c1e-p120">Se muestra el cuadro de diálogo siguiente. Puede expandir los corchetes angulares para revisar los permisos que se asignará al conector.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p120">The following dialog box is displayed. You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="13c1e-396">![Se muestra el cuadro de diálogo de solicitud de permisos](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="13c1e-396">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="13c1e-397">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13c1e-397">Click **Accept**.</span></span>

<span data-ttu-id="13c1e-p121">Después de aceptar la solicitud, se muestra el [portal de Azure](https://portal.azure.com) . Para ver la lista de aplicaciones para su organización, haga clic en **Azure Active Directory** > **aplicaciones empresariales**. El conector de datos de terceros para Office 365 se muestra en el servidor blade de **aplicaciones de empresa** .</span><span class="sxs-lookup"><span data-stu-id="13c1e-p121">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed. To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**. The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13c1e-p122">Después de 30 de septiembre de 2018, datos de otro fabricante ya no se importará en buzones de la organización si no registrar un conector de datos de terceros en Azure Active Directory. Tenga en cuenta los existentes conectores de datos de terceros (los que se crean antes del 30 de septiembre de 2018) también debe estar registrada en Azure Active Directory mediante el procedimiento descrito en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p122">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory. Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="13c1e-403">Revocar el consentimiento para un conector de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="13c1e-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="13c1e-p123">Después de la organización da su consentimiento a la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar dicho consentimiento en cualquier momento. Sin embargo, revocar el consentimiento para un conector significa que ya no se importará los datos desde el origen de datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p123">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time. However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="13c1e-p124">Para revocar el consentimiento para un conector de datos de terceros, puede eliminar la aplicación (mediante la eliminación de la entidad de seguridad de servicio correspondiente) de Azure Active Directory con el servidor blade de **aplicaciones empresariales** en el portal de Azure, o mediante el uso de la [ Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) en PowerShell de Office 365. También puede usar el cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) en Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p124">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="13c1e-408">Más información</span><span class="sxs-lookup"><span data-stu-id="13c1e-408">More information</span></span>

- <span data-ttu-id="13c1e-p125">Explica lo anterior, los elementos de datos de terceros orígenes se importan a los buzones de Exchange como mensajes de correo electrónico. El conector de socio importa el elemento mediante un esquema requerido por la API de Office 365. En la siguiente tabla se describe las propiedades de mensaje de un elemento de un origen de datos de terceros después de que se importa a un buzón de Exchange como un mensaje de correo electrónico. En la tabla también se indica si la propiedad message es obligatoria. Deben rellenarse propiedades obligatorias. Si un elemento no tiene una propiedad obligatoria, no se importan a Office 365. El proceso de importación devolverá un mensaje de error que explica por qué un elemento no se ha importado y qué propiedad es que faltan.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p125">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="13c1e-416">**Propiedad del mensaje**</span><span class="sxs-lookup"><span data-stu-id="13c1e-416">**Message property**</span></span>|<span data-ttu-id="13c1e-417">**¿Obligatorio?**</span><span class="sxs-lookup"><span data-stu-id="13c1e-417">**Mandatory?**</span></span>|<span data-ttu-id="13c1e-418">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13c1e-418">**Description**</span></span>|<span data-ttu-id="13c1e-419">**Valor de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="13c1e-419">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="13c1e-420">**FROM**</span><span class="sxs-lookup"><span data-stu-id="13c1e-420">**FROM**</span></span> <br/> |<span data-ttu-id="13c1e-421">Sí</span><span class="sxs-lookup"><span data-stu-id="13c1e-421">Yes</span></span>  <br/> |<span data-ttu-id="13c1e-p126">El usuario que creó originalmente o envía el elemento en el origen de datos de terceros. El conector de socio se intentará asignar el identificador de usuario desde el elemento de origen (por ejemplo, un controlador de Twitter) a una cuenta de usuario de Office 365 para todos los participantes (los usuarios de los campos FROM y TO). Se va a importar una copia del mensaje al buzón de todos los participantes. Si ninguno de los participantes del elemento se pueden asignar a una cuenta de usuario de Office 365, el elemento se importará para el buzón de correo archivado de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p126">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="13c1e-p127">El participante que se identificó como el remitente del elemento debe tener un buzón en la organización de Office 365 que el elemento se importa a activo. Si el remitente no tiene un buzón de correo activo, se devuelve el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p127">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="13c1e-428">**TO**</span><span class="sxs-lookup"><span data-stu-id="13c1e-428">**TO**</span></span> <br/> |<span data-ttu-id="13c1e-429">Sí</span><span class="sxs-lookup"><span data-stu-id="13c1e-429">Yes</span></span>  <br/> |<span data-ttu-id="13c1e-430">El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="13c1e-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="13c1e-431">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="13c1e-431">**SUBJECT**</span></span> <br/> |<span data-ttu-id="13c1e-432">No</span><span class="sxs-lookup"><span data-stu-id="13c1e-432">No</span></span>  <br/> |<span data-ttu-id="13c1e-433">El asunto del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="13c1e-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="13c1e-434">**FECHA**</span><span class="sxs-lookup"><span data-stu-id="13c1e-434">**DATE**</span></span> <br/> |<span data-ttu-id="13c1e-435">Sí</span><span class="sxs-lookup"><span data-stu-id="13c1e-435">Yes</span></span>  <br/> |<span data-ttu-id="13c1e-436">La fecha en la que el elemento originalmente se ha creado o publicado en el origen de datos del cliente; por ejemplo, la fecha en la que se ha publicado un mensaje en Twitter.</span><span class="sxs-lookup"><span data-stu-id="13c1e-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="13c1e-437">**BODY**</span><span class="sxs-lookup"><span data-stu-id="13c1e-437">**BODY**</span></span> <br/> |<span data-ttu-id="13c1e-438">No</span><span class="sxs-lookup"><span data-stu-id="13c1e-438">No</span></span>  <br/> |<span data-ttu-id="13c1e-p128">El contenido del mensaje o post. Para algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT** . Durante el proceso de importación, el conector de socio se intentará mantener fidelidad completa desde el origen de contenido como sea posible. Si es posible archivos, gráficos u otro contenido desde el cuerpo del elemento de origen se incluye en esta propiedad. De lo contrario, el contenido desde el elemento de origen se incluye en la propiedad **datos adjuntos** . El contenido de esta propiedad dependerán del conector de socio y en la capacidad de la plataforma de origen.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p128">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="13c1e-445">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="13c1e-445">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="13c1e-446">No</span><span class="sxs-lookup"><span data-stu-id="13c1e-446">No</span></span>  <br/> |<span data-ttu-id="13c1e-p129">Si un elemento en el origen de datos (por ejemplo, un mensajes en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluir imágenes, el socio conectar será el primer intento para incluir datos adjuntos en la propiedad **BODY** . Si eso no es posible, a continuación, se agrega a la \*\* datos adjuntos \*\* (propiedad). Otros ejemplos de los datos adjuntos son "Me gusta" en Facebook, metadatos desde el origen de contenido y las respuestas a un mensaje o post.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p129">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="13c1e-450">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="13c1e-450">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="13c1e-451">Sí</span><span class="sxs-lookup"><span data-stu-id="13c1e-451">Yes</span></span>  <br/> | <span data-ttu-id="13c1e-p130">Se trata de una propiedad multivalor, que se crea y se rellena por el conector de socio. El formato de esta propiedad es `IPM.NOTE.Source.Event`. (Esta propiedad debe comenzar con `IPM.NOTE`; este formato es similar a la de la `IPM.NOTE.X` clase de mensaje.) Esta propiedad incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p130">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="13c1e-455">`Source`-Indica el origen de datos de terceros; Por ejemplo, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="13c1e-455">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="13c1e-p131">`Event`-Indica el tipo de actividad que se llevó a cabo en el origen de datos de otros fabricantes que producen los elementos; Por ejemplo, un mensajes en Twitter o una entrada en Facebook. Eventos son específicos para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p131">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="13c1e-p132">Uno de los objetivos de esta propiedad es filtrar elementos específicos según el origen de datos donde un elemento se originó o en función del tipo de evento. Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para buscar todos los tweets a la que se contabilizaron por un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p132">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="13c1e-p133">Cuando los elementos se importan correctamente a los buzones de correo en Office 365, se devuelve un identificador único al autor de la llamada como parte de la respuesta HTTP. Este identificador, denominado `x-IngestionCorrelationID`— puede usarse para fines de solución de problemas posteriores por los socios para realizar un seguimiento de los elementos de extremo a otro. Se recomienda que los socios capturan esta información y registrarla según corresponda en su extremo. Este es un ejemplo de una respuesta HTTP que muestra este identificador:</span><span class="sxs-lookup"><span data-stu-id="13c1e-p133">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="13c1e-p134">Puede usar la herramienta de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar los elementos que se han importado a buzones de correo en Office 365 desde un origen de datos de terceros. Para buscar específicamente estos elementos importados, puede usar los siguientes pares de valor de la propiedad de mensaje en el cuadro de palabra clave para una búsqueda de contenido. .</span><span class="sxs-lookup"><span data-stu-id="13c1e-p134">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="13c1e-p135">**`kind:externaldata`**-Use este par de valor de la propiedad para buscar todos los tipos de datos de terceros. Por ejemplo, para buscar los elementos que se importaron desde un origen de datos de terceros y contiene la palabra "contoso" en la propiedad Subject del elemento importado, usaría la consulta de palabra clave `kind:externaldata AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p135">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="13c1e-p136">**`itemclass:ipm.externaldata.<third-party data type>`**-Usar este par de valor de la propiedad a la búsqueda sólo un tipo de especificar de datos de terceros. Por ejemplo, para buscar sólo los datos de Facebook que contiene la palabra "contoso" en la propiedad Subject, usaría la consulta de palabra clave `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span><span class="sxs-lookup"><span data-stu-id="13c1e-p136">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="13c1e-471">Para obtener una lista completa de los valores que se usará para tipos de datos de terceros para la `itemclass` (propiedad), consulte [Usar la búsqueda de contenido para buscar datos de terceros que se importaron a Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="13c1e-471">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="13c1e-472">Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:</span><span class="sxs-lookup"><span data-stu-id="13c1e-472">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="13c1e-473">Búsqueda de contenido en Office 365</span><span class="sxs-lookup"><span data-stu-id="13c1e-473">Content Search in Office 365</span></span>](content-search.md)
    
  - <span data-ttu-id="13c1e-474">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="13c1e-474">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
 

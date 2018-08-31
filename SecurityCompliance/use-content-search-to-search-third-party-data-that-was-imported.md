---
title: Usar búsqueda de contenido para buscar datos de terceros que se importaron a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Use la herramienta de exhibición de documentos electrónicos de búsqueda de contenido para buscar los elementos que se han importado a buzones de correo en Office 365 desde un origen de datos de terceros. Puede crear una consulta para buscar todos los elementos importados o crear una consulta para buscar tipos específicos de datos de terceros. En este artículo se enumeran los valores que puede utilizar en una consulta de palabra clave para buscar los tipos de datos de terceros que se pueden importar a Office 365.
ms.openlocfilehash: 90d9dc52dcd9dba9bc273dfcf1c5f22e3913d6ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536444"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="c88df-105">Usar búsqueda de contenido para buscar datos de terceros que se importaron a Office 365</span><span class="sxs-lookup"><span data-stu-id="c88df-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="c88df-p102">Puede usar la [herramienta de búsqueda de contenido de exhibición de documentos electrónicos](content-search.md) en la seguridad de Office 365 &amp; centro de cumplimiento para buscar los elementos que se han importado a buzones de correo en Office 365 desde un origen de datos de terceros. Puede crear una consulta para buscar importados todos los elementos de datos de terceros o puede crear una consulta de búsqueda solo los elementos de datos específicos de otro fabricante. Además, también puede crear una directiva de conservación basada en consultas o mantenga una exhibición de documentos electrónicos basada en consultas para conservar los datos de terceros en Office 365.</span><span class="sxs-lookup"><span data-stu-id="c88df-p102">You can use the [Content Search eDiscovery tool](content-search.md) in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items. Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="c88df-109">Para obtener más información acerca de la importación de datos de terceros y una lista de los tipos de datos de terceros que se pueden importar a Office 365, vea [datos de terceros de archivado en Office 365](archiving-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="c88df-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="c88df-110">Creación de una consulta para buscar todos los datos de terceros</span><span class="sxs-lookup"><span data-stu-id="c88df-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="c88df-p103">Para buscar (o pone en espera) cualquier tipo de datos de terceros que se han importado a Office 365, puede puede usar el `kind:externaldata` par de mensajes de valor de la propiedad en el cuadro de palabra clave para una búsqueda de contenido o al crear una suspensión basada en consultas. Por ejemplo, para buscar los elementos que se importaron desde cualquier origen de datos de terceros y contienen la palabra "contoso" en la propiedad Subject del elemento importado, usaría la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="c88df-p103">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold. For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="c88df-p104">El ejemplo anterior de consulta de palabra clave incluye la propiedad subject. Para obtener una lista de las demás propiedades para los elementos de datos de terceros que pueden incluyan en una consulta de palabra clave, vea la sección "Más información" en [datos de otros fabricantes de archivado en Office 365](archiving-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="c88df-p104">The previous keyword query example includes the subject property. For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="c88df-p105">Al crear consultas para buscar y retener los datos de otro fabricante, también puede utilizar condiciones para restringir los resultados de búsqueda. Para obtener más información acerca de cómo crear consultas de búsqueda de contenido, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="c88df-p105">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results. For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="c88df-117">Creación de una consulta para buscar tipos específicos de datos de terceros</span><span class="sxs-lookup"><span data-stu-id="c88df-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="c88df-118">En lugar de buscar todos los tipos de datos de terceros, puede crear consultas que sólo la búsqueda para un tipo de especificar de datos de terceros mediante el par de valor de la propiedad de mensaje siguiente en el cuadro de palabra clave para una búsqueda de contenido:</span><span class="sxs-lookup"><span data-stu-id="c88df-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="c88df-119">Por ejemplo, para buscar sólo los datos de Facebook que contiene la palabra "contoso" en la propiedad Subject, usaría la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="c88df-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="c88df-p106">En la siguiente tabla se enumera los tipos de datos de terceros que se pueden buscar y el valor que se usará para la `itemclass:` message (propiedad) búsqueda de específicamente para ese tipo de datos de terceros. Tenga en cuenta que la sintaxis de consulta no está entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c88df-p106">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data. Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="c88df-122">**Tipo de datos de terceros**</span><span class="sxs-lookup"><span data-stu-id="c88df-122">**Third-party data type**</span></span>|<span data-ttu-id="c88df-123">**El valor para `itemclass:` (propiedad)**</span><span class="sxs-lookup"><span data-stu-id="c88df-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c88df-124">AIM</span><span class="sxs-lookup"><span data-stu-id="c88df-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="c88df-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="c88df-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="c88df-126">AOL con cliente Pivot</span><span class="sxs-lookup"><span data-stu-id="c88df-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="c88df-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="c88df-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="c88df-128">Ares</span><span class="sxs-lookup"><span data-stu-id="c88df-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="c88df-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="c88df-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="c88df-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="c88df-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="c88df-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="c88df-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="c88df-132">Marcador de posición de AX</span><span class="sxs-lookup"><span data-stu-id="c88df-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="c88df-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="c88df-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="c88df-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="c88df-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="c88df-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="c88df-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="c88df-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="c88df-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="c88df-137">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="c88df-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="c88df-138">Registros de llamadas de blackBerry</span><span class="sxs-lookup"><span data-stu-id="c88df-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="c88df-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="c88df-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="c88df-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="c88df-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="c88df-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="c88df-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="c88df-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c88df-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="c88df-143">Bloomberg Mail
</span><span class="sxs-lookup"><span data-stu-id="c88df-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="c88df-144">Mensajería de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="c88df-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="c88df-145">Box
</span><span class="sxs-lookup"><span data-stu-id="c88df-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="c88df-146">Mensajería instantánea Cisco &amp; servidor de presencia</span><span class="sxs-lookup"><span data-stu-id="c88df-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="c88df-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="c88df-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="c88df-148">CipherCloud para Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c88df-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="c88df-149">Conexión directa</span><span class="sxs-lookup"><span data-stu-id="c88df-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="c88df-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="c88df-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="c88df-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="c88df-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="c88df-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="c88df-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="c88df-153">Flickr
</span><span class="sxs-lookup"><span data-stu-id="c88df-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="c88df-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="c88df-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="c88df-155">Google+
</span><span class="sxs-lookup"><span data-stu-id="c88df-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="c88df-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="c88df-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="c88df-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="c88df-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="c88df-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="c88df-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="c88df-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="c88df-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="c88df-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="c88df-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="c88df-161">Conexiones de IBM</span><span class="sxs-lookup"><span data-stu-id="c88df-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="c88df-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="c88df-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="c88df-163">Chat de ICE</span><span class="sxs-lookup"><span data-stu-id="c88df-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="c88df-164">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="c88df-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="c88df-165">Instagram
</span><span class="sxs-lookup"><span data-stu-id="c88df-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="c88df-166">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="c88df-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="c88df-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="c88df-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="c88df-168">IRC</span><span class="sxs-lookup"><span data-stu-id="c88df-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="c88df-169">Jive
</span><span class="sxs-lookup"><span data-stu-id="c88df-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="c88df-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="c88df-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="c88df-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="c88df-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="c88df-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="c88df-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="c88df-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="c88df-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="c88df-174">Comunicaciones unificadas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c88df-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="c88df-175">Alinear cuenta</span><span class="sxs-lookup"><span data-stu-id="c88df-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="c88df-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="c88df-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="c88df-177">MSN</span><span class="sxs-lookup"><span data-stu-id="c88df-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="c88df-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="c88df-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="c88df-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="c88df-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="c88df-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="c88df-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="c88df-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="c88df-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="c88df-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="c88df-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="c88df-183">QQ</span><span class="sxs-lookup"><span data-stu-id="c88df-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="c88df-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="c88df-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="c88df-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="c88df-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="c88df-186">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c88df-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="c88df-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="c88df-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="c88df-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="c88df-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="c88df-189">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="c88df-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="c88df-190">Symphony
</span><span class="sxs-lookup"><span data-stu-id="c88df-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="c88df-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="c88df-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="c88df-192">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="c88df-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="c88df-193">Tor</span><span class="sxs-lookup"><span data-stu-id="c88df-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="c88df-194">TTT</span><span class="sxs-lookup"><span data-stu-id="c88df-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="c88df-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="c88df-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="c88df-196">UBS Chat
</span><span class="sxs-lookup"><span data-stu-id="c88df-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="c88df-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="c88df-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="c88df-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="c88df-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="c88df-199">Winny</span><span class="sxs-lookup"><span data-stu-id="c88df-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="c88df-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c88df-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="c88df-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="c88df-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="c88df-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="c88df-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="c88df-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="c88df-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |

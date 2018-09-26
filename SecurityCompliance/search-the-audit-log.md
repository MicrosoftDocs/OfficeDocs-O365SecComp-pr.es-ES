---
title: Buscar el registro de auditoría para la actividad de usuario y administración de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'El registro de auditoría de Office 365 es un registro de auditoría unificadas. ¿Por qué se registra una auditoría unificada? Debido a que los eventos de la mayoría de Office 365 los servicios que se encuentra la organización se suscribe a se registran en un solo registro de auditoría que se puede buscar. Esto significa que puede buscar el usuario y la actividad de administración de estos servicios:'
ms.openlocfilehash: 230502f331babeef8f89eacce0d19a7756cb96fc
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038033"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="7dadd-106">Buscar el registro de auditoría para la actividad de usuario y administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="7dadd-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="7dadd-p102">El registro de auditoría de Office 365 es un registro de auditoría unificadas. ¿Por qué se registra una auditoría unificada? Debido a que los eventos de la mayoría de Office 365 los servicios que se encuentra la organización se suscribe a se registran en un solo registro de auditoría que se puede buscar. Esto significa que puede buscar el usuario y la actividad de administración de estos servicios:</span><span class="sxs-lookup"><span data-stu-id="7dadd-p102">The Office 365 audit log is a unified audit log. Why a unified audit log? Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search. That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="7dadd-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7dadd-111">SharePoint</span></span>
- <span data-ttu-id="7dadd-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="7dadd-112">OneDrive</span></span>
- <span data-ttu-id="7dadd-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="7dadd-113">Exchange</span></span>
- <span data-ttu-id="7dadd-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7dadd-114">Azure Active Directory</span></span>
- <span data-ttu-id="7dadd-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7dadd-115">Microsoft Teams</span></span>
- <span data-ttu-id="7dadd-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7dadd-116">eDiscovery</span></span>
- <span data-ttu-id="7dadd-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="7dadd-117">Power BI</span></span>
- <span data-ttu-id="7dadd-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="7dadd-118">Yammer</span></span>
- <span data-ttu-id="7dadd-119">Sway</span><span class="sxs-lookup"><span data-stu-id="7dadd-119">Sway</span></span>
- <span data-ttu-id="7dadd-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7dadd-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="7dadd-121">Configurar la auditoría</span><span class="sxs-lookup"><span data-stu-id="7dadd-121">Set up auditing</span></span>
  
<span data-ttu-id="7dadd-122">Hay algunas cosas que debe hacer antes de que puede buscar el registro de auditoría de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7dadd-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="7dadd-123">[Activar la búsqueda de registro de auditoría](turn-audit-log-search-on-or-off.md) para iniciar la grabación de eventos que puede buscar</span><span class="sxs-lookup"><span data-stu-id="7dadd-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="7dadd-124">[Habilitar la auditoría de buzón de correo](enable-mailbox-auditing.md) de forma que pueda buscar eventos relacionados con el buzón de correo; Por ejemplo, cuando un usuario inicia sesión en sus elementos de buzón de correo o purga de su carpeta de elementos recuperables</span><span class="sxs-lookup"><span data-stu-id="7dadd-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="7dadd-125">Buscar en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="7dadd-125">Search the audit log</span></span>
  
<span data-ttu-id="7dadd-126">Después de activar la auditoría, busque cientos de determinados tipos de eventos de varios servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7dadd-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="7dadd-127">[Búsqueda del registro de auditoría](search-the-audit-log-in-security-and-compliance.md) para actividades de administrador y usuario</span><span class="sxs-lookup"><span data-stu-id="7dadd-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="7dadd-128">[Comprender las propiedades detalladas](detailed-properties-in-the-office-365-audit-log.md) de cada registro de auditoría incluido en los resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="7dadd-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="7dadd-129">[Búsqueda de actividades relacionadas con la exhibición de documentos electrónicos](search-for-ediscovery-activities-in-the-audit-log.md) realizada por los jefes de administradores y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7dadd-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 

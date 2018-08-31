---
title: Límites de recursos de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Información sobre recursos límites para las diferentes aplicaciones de Office 365.'
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536861"
---
# <a name="resource-limits"></a><span data-ttu-id="9c76b-103">Límites de recursos</span><span class="sxs-lookup"><span data-stu-id="9c76b-103">Resource Limits</span></span>

<span data-ttu-id="9c76b-p101">Uso de cuotas (límites) y limitación de peticiones, se aplican los límites de recursos. Azure Active Directory y los servicios de Office 365 individuales utilizan ambos. Los límites son específicos de servicio y cambien a través del tiempo tal y como se agregan nuevas capacidades. Para obtener información detallada acerca de los límites actuales para los distintos servicios, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c76b-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="9c76b-108">Restricciones y límites del servicio Active Directory de Azure</span><span class="sxs-lookup"><span data-stu-id="9c76b-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="9c76b-109">Límites de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9c76b-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="9c76b-110">Límites de Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9c76b-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="9c76b-111">Límites y límites de software de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9c76b-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="9c76b-112">Skype para conocer los límites de negocio</span><span class="sxs-lookup"><span data-stu-id="9c76b-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="9c76b-113">API de REST de yammer y límites de frecuencia</span><span class="sxs-lookup"><span data-stu-id="9c76b-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="9c76b-114">Límites de tamaño de archivo en balanceo</span><span class="sxs-lookup"><span data-stu-id="9c76b-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="9c76b-p102">Además de estos límites, se usan varios mecanismos de limitación en Active Directory de Azure y Office 365. Limitación de peticiones dentro del servicio es especialmente importante, dado que los recursos de red en centros de datos de Microsoft están optimizados para el amplio conjunto de clientes que utilizan los servicios. Mecanismos de limitación se incluyen:</span><span class="sxs-lookup"><span data-stu-id="9c76b-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="9c76b-118">Azure Active Directory y limitación de nivel de usuario del característica de Office 365, lo que limita el número de transacciones o llamadas simultáneas (por secuencia de comandos o código) que se pueden realizar un único usuario.</span><span class="sxs-lookup"><span data-stu-id="9c76b-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="9c76b-p103">Un valor predeterminado PowerShell directiva de limitación se asigna a cada inquilino durante la creación del inquilino. Estas configuraciones afectan a otros elementos, como el número máximo de sesiones simultáneas de PowerShell que puede abrirse con un único administrador.</span><span class="sxs-lookup"><span data-stu-id="9c76b-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="9c76b-121">Cada cliente de Exchange Online tiene una directiva de Exchange Web Services (EWS) predeterminado que está optimizada para las operaciones de cliente EWS y limitación de peticiones se aplica a todos los clientes de Outlook.</span><span class="sxs-lookup"><span data-stu-id="9c76b-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>

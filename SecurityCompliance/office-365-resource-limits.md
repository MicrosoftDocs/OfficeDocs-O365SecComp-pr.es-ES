---
title: Office 365 límites de recursos
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: información acerca de los límites de recursos para las distintas aplicaciones de Office 365.'
ms.openlocfilehash: ee44bde8bd93d3628ed3f31f5bbbce024a3056b5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220220"
---
# <a name="resource-limits"></a><span data-ttu-id="cebbf-103">Límites de recursos</span><span class="sxs-lookup"><span data-stu-id="cebbf-103">Resource Limits</span></span>

<span data-ttu-id="cebbf-p101">Los límites de recursos se aplican mediante cuotas (límites) y limitación. Azure Active Directory y los servicios individuales de Office 365 usan ambos. Los límites son específicos del servicio y cambian a lo largo del tiempo a medida que se agregan nuevas capacidades. Para obtener más información sobre los límites actuales para los distintos servicios, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="cebbf-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="cebbf-108">Límites y restricciones del servicio Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cebbf-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="cebbf-109">Límites de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cebbf-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="cebbf-110">Límites de Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cebbf-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="cebbf-111">Límites y límites del software de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cebbf-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="cebbf-112">Límites de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="cebbf-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="cebbf-113">Límites de frecuencia y API de REST de Yammer</span><span class="sxs-lookup"><span data-stu-id="cebbf-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="cebbf-114">Límites de tamaño de archivo en Sway</span><span class="sxs-lookup"><span data-stu-id="cebbf-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="cebbf-p102">Además de estos límites, se usan varios mecanismos de limitación a través de Azure Active Directory y Office 365. La limitación en el servicio es especialmente importante, dado que los recursos de red en los centros de recursos de Microsoft están optimizados para el amplio conjunto de clientes que usan los servicios. Los mecanismos de limitación incluyen:</span><span class="sxs-lookup"><span data-stu-id="cebbf-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="cebbf-118">Azure Active Directory y Office 365 característica de limitación a nivel de usuario, que limitan el número de transacciones o llamadas simultáneas (por script o código) que un solo usuario puede realizar.</span><span class="sxs-lookup"><span data-stu-id="cebbf-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="cebbf-p103">Se asigna una directiva de limitación de PowerShell predeterminada a cada inquilino en la creación del espacio empresarial. Esta configuración afecta a otros elementos, como el número máximo de sesiones simultáneas de PowerShell que puede abrir un administrador único.</span><span class="sxs-lookup"><span data-stu-id="cebbf-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="cebbf-121">Cada cliente de Exchange Online tiene una directiva de servicios web Exchange (EWS) predeterminada que se ajusta a las operaciones de cliente de EWS y que se aplica a todos los clientes de Outlook.</span><span class="sxs-lookup"><span data-stu-id="cebbf-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>

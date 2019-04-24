---
title: Office 365 cifrado para los datos en tránsito
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumen: breve explicación de cómo Microsoft cifra los datos en tránsito.'
ms.openlocfilehash: ba1317a0a2a685d0f3ac2216939d04e402503e49
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262802"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="ae001-103">Office 365 cifrado para los datos en tránsito</span><span class="sxs-lookup"><span data-stu-id="ae001-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="ae001-104">Además de proteger los datos de clientes en reposo, Microsoft usa tecnologías de cifrado para proteger los datos de clientes de Office 365 en tránsito.</span><span class="sxs-lookup"><span data-stu-id="ae001-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="ae001-105">Los datos están en tránsito:</span><span class="sxs-lookup"><span data-stu-id="ae001-105">Data is in transit:</span></span>

- <span data-ttu-id="ae001-106">Cuando un equipo cliente se comunica con un servidor de Office 365;</span><span class="sxs-lookup"><span data-stu-id="ae001-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="ae001-107">Cuando un servidor de Office 365 se comunica con otro servidor de Office 365; y</span><span class="sxs-lookup"><span data-stu-id="ae001-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="ae001-108">Cuando un servidor de Office 365 se comunica con un servidor que no es Office 365 (por ejemplo, Exchange online que entrega el correo electrónico a un servidor de correo electrónico externo).</span><span class="sxs-lookup"><span data-stu-id="ae001-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="ae001-109">Las comunicaciones entre centros de recursos entre Office 365 Servers tienen lugar a través de TLS o IPsec, y todos los servidores orientados a clientes negocian una sesión segura mediante TLS con los equipos cliente (por ejemplo, Exchange online usa TLS 1,2 con la intensidad de cifrado de 256 bits (FIPS). se usa FIPS. 140-2 de nivel 2: validado).</span><span class="sxs-lookup"><span data-stu-id="ae001-109">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="ae001-110">(Consulte [información de referencia técnica sobre el cifrado en Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) para obtener una lista de los conjuntos de cifrado de TLS compatibles con Office 365). Esto se aplica a los protocolos que usan los clientes como Outlook, Skype empresarial y Outlook en la web (por ejemplo, HTTP, POP3, etc.).</span><span class="sxs-lookup"><span data-stu-id="ae001-110">(See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="ae001-111">Los certificados públicos los emite SSL de Microsoft IT con SSLAdmin, una herramienta interna de Microsoft para proteger la confidencialidad de la información transmitida.</span><span class="sxs-lookup"><span data-stu-id="ae001-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="ae001-112">Todos los certificados emitidos por Microsoft IT tienen un mínimo de 2048 bits de longitud [](http://www.webtrust.org/homepage-documents/item70372.pdf) y el cumplimiento de WebTrust requiere SSLAdmin para asegurarse de que los certificados solo se emiten para las direcciones IP públicas que pertenecen a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae001-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="ae001-113">Las direcciones IP que no cumplan este criterio se enrutan a través de un proceso de excepción.</span><span class="sxs-lookup"><span data-stu-id="ae001-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="ae001-114">Todos los detalles de implementación, como la versión de TLS que se usa, si la confidencialidad directa (FS) está habilitada, el orden de los conjuntos de cifrado, etc., están disponibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="ae001-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="ae001-115">Una forma de ver estos detalles es usar un sitio web de terceros, como Qualys SSL Labs (www.ssllabs.com).</span><span class="sxs-lookup"><span data-stu-id="ae001-115">One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com).</span></span> <span data-ttu-id="ae001-116">A continuación se muestran los vínculos a páginas de prueba automatizadas desde Qualys que muestran información para los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="ae001-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="ae001-117">Portal de Office 365</span><span class="sxs-lookup"><span data-stu-id="ae001-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="ae001-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ae001-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="ae001-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ae001-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="ae001-120">Skype empresarial (SIP)</span><span class="sxs-lookup"><span data-stu-id="ae001-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="ae001-121">Skype empresarial (Web)</span><span class="sxs-lookup"><span data-stu-id="ae001-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="ae001-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ae001-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="ae001-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae001-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="ae001-124">Para la protección en línea de Exchange, las direcciones URL varían según los nombres de los inquilinos; sin embargo, todos los clientes pueden probar Office 365 mediante **Microsoft-com.mail.Protection.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="ae001-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>

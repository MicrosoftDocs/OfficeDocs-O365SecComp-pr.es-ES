---
title: Cifrado de Office 365 para los datos en tránsito
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
description: 'Resumen: Una breve explicación de cómo Microsoft cifra los datos en tránsito.'
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535650"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="695cb-103">Cifrado de Office 365 para los datos en tránsito</span><span class="sxs-lookup"><span data-stu-id="695cb-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="695cb-104">Además de proteger los datos en reposo de cliente, Microsoft usa tecnologías de cifrado para proteger los datos de cliente de Office 365 en tránsito.</span><span class="sxs-lookup"><span data-stu-id="695cb-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="695cb-105">Datos están en tránsito:</span><span class="sxs-lookup"><span data-stu-id="695cb-105">Data is in transit:</span></span>
- <span data-ttu-id="695cb-106">Cuando un equipo cliente se comunica con un servidor de Office 365.</span><span class="sxs-lookup"><span data-stu-id="695cb-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="695cb-107">Cuando un servidor de Office 365 se comunica con otro servidor de Office 365; y</span><span class="sxs-lookup"><span data-stu-id="695cb-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="695cb-108">Cuando un servidor de Office 365 se comunica con un servidor que no sean Office 365 (por ejemplo, Exchange Online enviando correo electrónico a un servidor de correo electrónico externas).</span><span class="sxs-lookup"><span data-stu-id="695cb-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="695cb-p101">Centro de datos entre las comunicaciones entre los servidores de Office 365 se lleva a cabo a través de TLS o IPsec, y todos los servidores orientados al cliente negocian una sesión segura con TLS con los equipos cliente (por ejemplo, Exchange Online usa se utiliza TLS 1.2 con intensidad de cifrado de 256 bits (FIPS Nivel de 140-2 validan 2). (Consulte los [Detalles de referencia técnica acerca del cifrado en Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) para obtener una lista de conjuntos de cifrado TLS compatibles con Office 365). Esto se aplica a los protocolos que se usan clientes como Outlook, Skype para la empresa y Outlook en la web (por ejemplo, HTTP, POP3, etcetera).</span><span class="sxs-lookup"><span data-stu-id="695cb-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="695cb-p102">Los certificados públicos emitidos por Microsoft IT SSL con SSLAdmin, una herramienta interna de Microsoft para proteger la confidencialidad de la información transmitida. Todos los certificados emitidos por Microsoft IT tengan un mínimo de 2048 bits de longitud y cumplimiento [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) requiere SSLAdmin para asegurarse de que los certificados se emiten únicamente a las direcciones IP públicas que pertenecen a Microsoft. Todas las direcciones IP que no cumplen este criterio se enrutan a través de un proceso de excepción.</span><span class="sxs-lookup"><span data-stu-id="695cb-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="695cb-p103">Todos los detalles de la implementación, como la versión de TLS usada, si está habilitada la confidencialidad hacia delante (FS), el orden de los conjuntos de aplicaciones de cifrado, etc., están disponibles públicamente. Una manera de ver estos detalles consiste en usar un sitio Web de terceros, como Qualys SSL laboratorios (www.ssllabs.com). A continuación están los vínculos a las páginas de prueba automatizada en Qualys que muestran información de los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="695cb-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>
- [<span data-ttu-id="695cb-117">Portal de Office 365</span><span class="sxs-lookup"><span data-stu-id="695cb-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="695cb-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="695cb-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="695cb-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="695cb-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="695cb-120">Skype para la empresa (SIP)</span><span class="sxs-lookup"><span data-stu-id="695cb-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="695cb-121">Skype para la empresa (Web)</span><span class="sxs-lookup"><span data-stu-id="695cb-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="695cb-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="695cb-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="695cb-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="695cb-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="695cb-124">Para Exchange Online Protection, las direcciones URL pueden variar por nombres de inquilino; Sin embargo, todos los clientes pueden probar Office 365 con **microsoft com.mail.protection.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="695cb-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>

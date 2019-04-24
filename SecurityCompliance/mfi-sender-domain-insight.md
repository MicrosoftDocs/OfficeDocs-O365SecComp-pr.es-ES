---
title: Revisión del conocimiento del dominio del remitente
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre la información sobre cómo solucionar el dominio del remitente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bd62d6d0b42edfd1eedf543d7d8bb68903c7c608
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252198"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="7424e-103">Revisión del conocimiento del dominio del remitente</span><span class="sxs-lookup"><span data-stu-id="7424e-103">Fix sender domain insight</span></span>

> [!NOTE]
> <span data-ttu-id="7424e-104">Las características descritas en este tema no se han implementado en todas las organizaciones de Office 365 y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="7424e-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="7424e-105">Office 365 requiere mensajes que envían desde entornos de correo electrónico locales internos a Office 365 para cumplir ciertos criterios de seguridad:</span><span class="sxs-lookup"><span data-stu-id="7424e-105">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="7424e-106">Ha creado un conector de entrada en Office 365 para autenticar las conexiones SMTP desde el servidor de correo electrónico local mediante el uso de la dirección IP de origen o un certificado.</span><span class="sxs-lookup"><span data-stu-id="7424e-106">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="7424e-107">Ha configurado su servidor de correo electrónico local para retransmitir el correo electrónico a través de Office 365 a un mundo externo.</span><span class="sxs-lookup"><span data-stu-id="7424e-107">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="7424e-108">En la configuración, se cumple una de las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="7424e-108">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="7424e-109">El dominio de correo electrónico del remitente está registrado en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7424e-109">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="7424e-110">Para obtener más información, vea Agregar dominios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7424e-110">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="7424e-111">El servidor de correo electrónico local está configurado para usar un certificado para enviar correo electrónico a Office 365, el certificado contiene o coincide exactamente con un nombre de dominio que se ha registrado en Office 365 y ha creado un conector basado en certificado en Office 365 con ese Reserva.</span><span class="sxs-lookup"><span data-stu-id="7424e-111">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="7424e-112">Los mensajes que no cumplen los criterios no se atribuirán a la organización y podrían rechazarse.</span><span class="sxs-lookup"><span data-stu-id="7424e-112">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="7424e-113">La introducción a la **solución de dominio del remitente** muestra el correo electrónico de su entorno local que no cumple los criterios, le ayuda a identificar las cuentas de usuario y equipos potencialmente comprometidos en su entorno de correo electrónico local y le ayuda a tomar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="7424e-113">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![La información del dominio de remitentes Fix del panel flujo de correo del centro de seguridad & cumplimiento](media/sender-domain-insight-selected.png)

<span data-ttu-id="7424e-115">Al hacer clic en **Ver detalles**, se le lleva a otro widget con más detalles como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="7424e-115">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Widget de detalles en el información sobre la solución de dominio del remitente](media/sender-domain-view-details.png)

<span data-ttu-id="7424e-117">Verá el conector de entrada que se usó para entregar los mensajes a Office 365.</span><span class="sxs-lookup"><span data-stu-id="7424e-117">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="7424e-118">También puede hacer clic en **ver identificadores de mensaje de ejemplo** para ver los detalles de los mensajes que se enviaron desde su entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="7424e-118">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="7424e-119">Debido a que estos mensajes fueron rechazados por Office 365, no puede usar el seguimiento de mensajes, pero puede usar los identificadores de mensaje de ejemplo para realizar un seguimiento de los mensajes en su entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="7424e-119">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Ver identificadores de mensaje de ejemplo en el información de dominio del remitente de corrección](media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="7424e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7424e-121">See also</span></span>

<span data-ttu-id="7424e-122">Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7424e-122">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

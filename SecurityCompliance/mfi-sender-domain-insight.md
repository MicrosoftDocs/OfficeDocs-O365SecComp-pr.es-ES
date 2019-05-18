---
title: Revisión del conocimiento del dominio del remitente
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden obtener información sobre la información sobre cómo solucionar el dominio del remitente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 181f224064b5f31fd17c348cc4547826fbcd29a9
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158712"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="8033d-103">Revisión del conocimiento del dominio del remitente</span><span class="sxs-lookup"><span data-stu-id="8033d-103">Fix sender domain insight</span></span>

<span data-ttu-id="8033d-104">Office 365 requiere mensajes que envían desde entornos de correo electrónico locales internos a Office 365 para cumplir ciertos criterios de seguridad:</span><span class="sxs-lookup"><span data-stu-id="8033d-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="8033d-105">Ha creado un conector de entrada en Office 365 para autenticar las conexiones SMTP desde el servidor de correo electrónico local mediante el uso de la dirección IP de origen o un certificado.</span><span class="sxs-lookup"><span data-stu-id="8033d-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="8033d-106">Ha configurado su servidor de correo electrónico local para retransmitir el correo electrónico a través de Office 365 a un mundo externo.</span><span class="sxs-lookup"><span data-stu-id="8033d-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="8033d-107">En la configuración, se cumple una de las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="8033d-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="8033d-108">El dominio de correo electrónico del remitente está registrado en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8033d-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="8033d-109">Para obtener más información, vea Agregar dominios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="8033d-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="8033d-110">El servidor de correo electrónico local está configurado para usar un certificado para enviar correo electrónico a Office 365, el certificado contiene o coincide exactamente con un nombre de dominio que se ha registrado en Office 365 y ha creado un conector basado en certificado en Office 365 con ese Reserva.</span><span class="sxs-lookup"><span data-stu-id="8033d-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="8033d-111">Los mensajes que no cumplen los criterios no se atribuirán a la organización y podrían rechazarse.</span><span class="sxs-lookup"><span data-stu-id="8033d-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="8033d-112">La introducción a la **solución de dominio del remitente** muestra el correo electrónico de su entorno local que no cumple los criterios, le ayuda a identificar las cuentas de usuario y equipos potencialmente comprometidos en su entorno de correo electrónico local y le ayuda a tomar acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="8033d-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![La información del dominio de remitentes Fix del panel flujo de correo del centro de seguridad & cumplimiento](media/sender-domain-insight-selected.png)

<span data-ttu-id="8033d-114">Al hacer clic en **Ver detalles**, se le lleva a otro widget con más detalles como se muestra en el siguiente diagrama:</span><span class="sxs-lookup"><span data-stu-id="8033d-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![Widget de detalles en el información sobre la solución de dominio del remitente](media/sender-domain-view-details.png)

<span data-ttu-id="8033d-116">Verá el conector de entrada que se usó para entregar los mensajes a Office 365.</span><span class="sxs-lookup"><span data-stu-id="8033d-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="8033d-117">También puede hacer clic en **ver identificadores de mensaje de ejemplo** para ver los detalles de los mensajes que se enviaron desde su entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="8033d-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="8033d-118">Debido a que estos mensajes fueron rechazados por Office 365, no puede usar el seguimiento de mensajes, pero puede usar los identificadores de mensaje de ejemplo para realizar un seguimiento de los mensajes en su entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="8033d-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Ver identificadores de mensaje de ejemplo en el información de dominio del remitente de corrección](media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="8033d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8033d-120">See also</span></span>

<span data-ttu-id="8033d-121">Para obtener más información acerca de otras indicaciones de flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad _AMP_ cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8033d-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

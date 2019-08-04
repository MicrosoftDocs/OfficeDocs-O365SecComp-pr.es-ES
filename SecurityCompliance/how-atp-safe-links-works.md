---
title: Funcionamiento de los vínculos seguros de Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La característica de vínculos seguros proporciona la comprobación del tiempo de clic de los hipervínculos en los documentos de Office y en los mensajes de correo electrónico. Lea este artículo para obtener información sobre cómo funciona el vínculo seguro ATP.
ms.openlocfilehash: 67779560e279028c158179c265196199b5d37d1c
ms.sourcegitcommit: 7c1cb9e8adb1c3e9c667f4cf02ca3cec3ec1e171
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792046"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="1c944-104">Funcionamiento de los vínculos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1c944-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="1c944-105">Cómo funciona el vínculo seguro ATP con direcciones URL en el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="1c944-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="1c944-106">En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en el correo electrónico (hospedado en Office 365, no en local):</span><span class="sxs-lookup"><span data-stu-id="1c944-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="1c944-107">Los usuarios reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="1c944-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="1c944-108">Todo el correo electrónico se envía a través de Exchange Online Protection, donde se aplican los filtros de protocolo de Internet (IP) y sobre, protección contra malware basada en firmas, filtros de correo no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="1c944-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="1c944-109">El correo electrónico llega a las bandejas de entrada de las personas.</span><span class="sxs-lookup"><span data-stu-id="1c944-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="1c944-110">Un usuario inicia sesión en Office 365 y se dirige a su bandeja de entrada de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1c944-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="1c944-111">El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1c944-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="1c944-112">La característica de vínculos seguros de ATP comprueba inmediatamente la dirección URL antes de abrir el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="1c944-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="1c944-113">La dirección URL se identifica como bloqueada, malintencionada o segura.</span><span class="sxs-lookup"><span data-stu-id="1c944-113">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="1c944-114">Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se abre el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="1c944-114">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="1c944-115">Si la dirección URL es un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="1c944-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="1c944-116">Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="1c944-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="1c944-117">Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) de la organización están configuradas para analizar dicho contenido, se comprueba el archivo descargable.</span><span class="sxs-lookup"><span data-stu-id="1c944-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="1c944-118">Si se determina que la dirección URL es segura, se abrirá el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="1c944-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="1c944-119">Cómo funciona el vínculo seguro ATP con direcciones URL en documentos de Office</span><span class="sxs-lookup"><span data-stu-id="1c944-119">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="1c944-120">En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en Office 365 ProPlus Applications (versiones actuales de Word, Excel y PowerPoint en Windows o Mac, aplicaciones de Office en dispositivos iOS o Android, Visio en Windows, OneNote en un explorador y Office en un explorador):</span><span class="sxs-lookup"><span data-stu-id="1c944-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser, and Office in a browser):</span></span>
  
1. <span data-ttu-id="1c944-121">Los usuarios han instalado Office 365 ProPlus en su equipo, smartphone o tableta.</span><span class="sxs-lookup"><span data-stu-id="1c944-121">People have installed Office 365 ProPlus on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="1c944-122">(O bien, usan Office en su explorador).</span><span class="sxs-lookup"><span data-stu-id="1c944-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="1c944-123">Un usuario abre un Word, Excel, PowerPoint o Visio y inicia sesión en Office 365 Enterprise con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="1c944-123">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="1c944-124">El documento contiene direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="1c944-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="1c944-125">Cuando el usuario hace clic en una dirección URL del documento, el servicio de vínculos seguros de ATP comprueba el vínculo.</span><span class="sxs-lookup"><span data-stu-id="1c944-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="1c944-126">Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, dicho usuario se dirigirá al sitio Web.</span><span class="sxs-lookup"><span data-stu-id="1c944-126">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="1c944-127">Si la dirección URL se redirigirá a un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se dirigirá al usuario a una [Página de advertencia](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="1c944-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="1c944-128">Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se le dirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="1c944-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="1c944-129">Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) están configuradas para analizar tales descargas, se comprueba el archivo descargable.</span><span class="sxs-lookup"><span data-stu-id="1c944-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="1c944-130">Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.</span><span class="sxs-lookup"><span data-stu-id="1c944-130">If the URL is considered safe, the user is taken to the website.</span></span>


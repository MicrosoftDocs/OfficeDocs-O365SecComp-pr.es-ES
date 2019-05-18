---
title: Configurar la configuración S/MIME en Exchange Online para Outlook en la web
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descripción de lo que los administradores de Exchange Online deben hacer para ver y configurar la configuración S/MIME en Outlook en la web en Exchange Online.
ms.openlocfilehash: 2be1d7599d65601671504b7d6caf03e915f10fff
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153862"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="e01d3-103">Configurar la configuración S/MIME en Exchange Online para Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="e01d3-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="e01d3-104">Como administrador de Exchange Online, puede configurar Outlook en la web (anteriormente conocido como Outlook Web App) para permitir el envío y la recepción de mensajes protegidos por S/MIME.</span><span class="sxs-lookup"><span data-stu-id="e01d3-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="e01d3-105">Use los cmdlets **Get-SmimeConfig** y **set-SmimeConfig** para ver y administrar esta característica en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e01d3-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="e01d3-106">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="e01d3-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="e01d3-107">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) y [set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="e01d3-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="e01d3-108">Consideraciones sobre Chrome</span><span class="sxs-lookup"><span data-stu-id="e01d3-108">Considerations for Chrome</span></span>

<span data-ttu-id="e01d3-109">Para usar S/MIME en Outlook en la web en el explorador web Google Chrome, usted (u otro administrador) debe establecer y configurar la Directiva de cromo denominada **ExtensionInstallForcelist** para instalar la extensión S/MIME de Microsoft en Chrome.</span><span class="sxs-lookup"><span data-stu-id="e01d3-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="e01d3-110">El valor de la `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`Directiva es.</span><span class="sxs-lookup"><span data-stu-id="e01d3-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="e01d3-111">Además, tenga en cuenta que la aplicación de esta directiva requiere equipos Unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos Unidos a un dominio de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="e01d3-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="e01d3-112">Para obtener más información sobre la directiva **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="e01d3-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

<span data-ttu-id="e01d3-113">Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME instalado por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e01d3-113">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="e01d3-114">Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante su primer uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="e01d3-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="e01d3-115">O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.</span><span class="sxs-lookup"><span data-stu-id="e01d3-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e01d3-116">Más información</span><span class="sxs-lookup"><span data-stu-id="e01d3-116">For more information</span></span>

[<span data-ttu-id="e01d3-117">S/MIME para la firma y el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="e01d3-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

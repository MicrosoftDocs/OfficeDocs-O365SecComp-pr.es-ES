---
title: Establecer una fecha de expiración para el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con Office 365 avanzadas capacidades de cifrado de mensajes sobre el cifrado de mensajes de Office 365 (OME), puede ampliar su seguridad de correo electrónico estableciendo una fecha de expiración en los correos electrónicos a través de una plantilla personalizada de personalización de marca.
ms.openlocfilehash: 260e6032d3b7a4c9b81fca73dfbcd57fa01168cb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157677"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="6883b-103">Establecer una fecha de expiración para el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="6883b-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="6883b-104">Office 365 Advanced Message Encryption está disponible sobre el cifrado de mensajes de Office 365 en determinadas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="6883b-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="6883b-105">El cifrado de mensajes avanzado se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="6883b-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="6883b-106">Si su organización tiene una suscripción de Office 365 que no incluye el cifrado avanzado de mensajes de Office 365, puede comprar el cifrado de mensajes avanzado como complemento con la compatibilidad con E5 del SKU de compatibilidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="6883b-106">If your organization has an Office 365 subscription that doesn't include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="6883b-107">Puede usar la expiración de mensajes en los correos electrónicos que los usuarios envían a los destinatarios externos que usan el portal OME para acceder a los correos electrónicos cifrados.</span><span class="sxs-lookup"><span data-stu-id="6883b-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="6883b-108">Obliga a los destinatarios a usar el portal OME para ver y responder a los correos electrónicos cifrados enviados por la organización mediante una plantilla personalizada que especifica una fecha de expiración en Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6883b-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="6883b-109">Como administrador global de O365, cuando aplique la marca de su compañía para personalizar la apariencia de los mensajes de correo electrónico de su organización de Office 365, también puede especificar una expiración para estos mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6883b-109">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="6883b-110">Con Office 365 Advanced Message Encryption, puede crear varias plantillas para mensajes de correo electrónico cifrados que se originan en su organización.</span><span class="sxs-lookup"><span data-stu-id="6883b-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="6883b-111">Mediante el uso de una plantilla, puede controlar durante cuánto tiempo los destinatarios tienen acceso al correo enviado por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6883b-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="6883b-112">Cuando un usuario final recibe un correo con una fecha de expiración establecida, el usuario ve la fecha de expiración en el correo electrónico del contenedor.</span><span class="sxs-lookup"><span data-stu-id="6883b-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="6883b-113">Si un usuario intenta abrir un correo expirado, aparece un error en el portal OME.</span><span class="sxs-lookup"><span data-stu-id="6883b-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="6883b-114">Solo se pueden establecer fechas de caducidad para los correos electrónicos a los destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="6883b-114">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="6883b-115">Con Office 365 Advanced Message Encryption, siempre que aplique la personalización de marca personalizada, la Office 365 aplica el contenedor a correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6883b-115">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="6883b-116">Además, solo puede usar la expiración si usa la personalización de marca personalizada.</span><span class="sxs-lookup"><span data-stu-id="6883b-116">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="6883b-117">Crear una plantilla de personalización de marca personalizada para forzar la expiración del correo mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="6883b-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="6883b-118">[Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) con una cuenta que tenga permisos de administrador global en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6883b-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="6883b-119">Ejecute el cmdlet New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6883b-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="6883b-120">Donde:</span><span class="sxs-lookup"><span data-stu-id="6883b-120">Where:</span></span>

- <span data-ttu-id="6883b-121">`Identity`es el nombre de la plantilla personalizada.</span><span class="sxs-lookup"><span data-stu-id="6883b-121">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="6883b-122">`ExternalMailExpiryInDays`identifica el número de días que los destinatarios pueden conservar el correo antes de que expire.</span><span class="sxs-lookup"><span data-stu-id="6883b-122">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="6883b-123">Puede usar cualquier valor entre 1 y 730 días.</span><span class="sxs-lookup"><span data-stu-id="6883b-123">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="6883b-124">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="6883b-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="6883b-125">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="6883b-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="6883b-126">Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="6883b-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="6883b-127">Descripción de la Directiva de mensajes y el servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6883b-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
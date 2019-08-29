---
title: Crear una política tipo de información confidencial para su organización mediante el cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumen: Directiva de cifrado de mensajes de Office 365 para tipos de información confidencial.'
ms.openlocfilehash: d74712798ba9d46614b5fc916e4b1ce111582304
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658126"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="a4d3f-103">Crear una política tipo de información confidencial para su organización mediante el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="a4d3f-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="a4d3f-104">Puede usar las reglas de flujo de correo de Exchange o la prevención de pérdida de datos (DLP) de Office 365 para crear una directiva de tipo de información confidencial con el cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="a4d3f-105">Para crear una regla de flujo de correo de Exchange, puede usar el centro de administración de Exchange (EAC) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="a4d3f-106">Para crear la Directiva mediante reglas de flujo de correo en el EAC</span><span class="sxs-lookup"><span data-stu-id="a4d3f-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="a4d3f-107">Inicie sesión en el centro de administración de Exchange (EAC) y vaya a**reglas**de **flujo** > de correo.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="a4d3f-108">En la página reglas, cree una regla que aplique el cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="a4d3f-109">Puede crear una regla basada en condiciones como la presencia de determinadas palabras clave o tipos de información confidencial en el mensaje o los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="a4d3f-110">Para crear la Directiva mediante reglas de flujo de correo en PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4d3f-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="a4d3f-111">Use una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a4d3f-112">Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="a4d3f-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="a4d3f-113">Use los cmdlets Set-IRMConfiguration y New-TransportRule para crear la Directiva.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="a4d3f-114">Ejemplo de regla de flujo de correo creada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4d3f-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="a4d3f-115">Ejecute los siguientes comandos en PowerShell para crear una regla de flujo de correo de Exchange que cifre automáticamente los correos electrónicos enviados fuera de la organización con la directiva *de solo cifrado* si los mensajes de correo electrónico o los datos adjuntos contienen la siguiente información confidencial. distintos</span><span class="sxs-lookup"><span data-stu-id="a4d3f-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="a4d3f-116">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="a4d3f-116">ABA routing number</span></span>
- <span data-ttu-id="a4d3f-117">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a4d3f-117">Credit card Number</span></span>
- <span data-ttu-id="a4d3f-118">Número de la Agencia para la imposición de drogas (DEA)</span><span class="sxs-lookup"><span data-stu-id="a4d3f-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="a4d3f-119">ESTADOS UNIDOS/REINO UNIDO</span><span class="sxs-lookup"><span data-stu-id="a4d3f-119">U.S. / U.K.</span></span> <span data-ttu-id="a4d3f-120">passport number</span><span class="sxs-lookup"><span data-stu-id="a4d3f-120">passport number</span></span>
- <span data-ttu-id="a4d3f-121">Número de cuenta bancaria de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a4d3f-121">U.S. bank account number</span></span>
- <span data-ttu-id="a4d3f-122">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="a4d3f-123">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="a4d3f-124">Para más información, vea [set-IRMConfiguration](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) y [New-TransportRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a4d3f-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="a4d3f-125">Acceso a datos adjuntos de destinatarios</span><span class="sxs-lookup"><span data-stu-id="a4d3f-125">How recipients access attachments</span></span>

<span data-ttu-id="a4d3f-126">Después de que Office 365 cifra un mensaje, los destinatarios tienen acceso no restringido a los datos adjuntos cuando acceden y abren su correo electrónico cifrado.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-126">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="a4d3f-127">Para prepararse para este cambio</span><span class="sxs-lookup"><span data-stu-id="a4d3f-127">To prepare for this change</span></span>

<span data-ttu-id="a4d3f-128">Es posible que desee actualizar toda la documentación para el usuario final y los materiales de formación correspondientes para preparar a los usuarios de su organización para este cambio.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="a4d3f-129">Comparta estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:</span><span class="sxs-lookup"><span data-stu-id="a4d3f-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="a4d3f-130">Enviar, ver y responder mensajes cifrados en Outlook para PC</span><span class="sxs-lookup"><span data-stu-id="a4d3f-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="a4d3f-131">Vídeo de Office 365 Essentials: cifrado de mensajes de Office</span><span class="sxs-lookup"><span data-stu-id="a4d3f-131">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="a4d3f-132">Ver estos cambios en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="a4d3f-132">View these changes in the Audit log</span></span>

<span data-ttu-id="a4d3f-133">Office 365 audita esta actividad y la pone a disposición de los administradores de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4d3f-133">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="a4d3f-134">La operación es ' New-TransportRule ' y un fragmento de código de una entrada de auditoría de la búsqueda del registro de auditoría en el centro de seguridad & cumplimiento se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="a4d3f-134">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="a4d3f-135">Para deshabilitar o personalizar la Directiva de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="a4d3f-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="a4d3f-136">Una vez que haya creado la regla de flujo de correo de Exchange, puede deshabilitarla [o editarla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) en**reglas** de **flujo** > de correo en el centro de administración de Exchange (EAC) y deshabilitar la regla "*cifrar mensajes de correo electrónico confidenciales salientes" (regla* "no es de la casilla") ".</span><span class="sxs-lookup"><span data-stu-id="a4d3f-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

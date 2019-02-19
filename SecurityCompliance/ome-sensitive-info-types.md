---
title: Directiva de cifrado de mensajes de Office 365 para información confidencial
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: la Directiva de cifrado de mensajes de Office 365 para tipos de información confidencial ahora está disponible.'
ms.openlocfilehash: e2a72ee85ca65a2fe8ae1543979b51915ff0a88f
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696204"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="dc045-103">Directiva de cifrado de mensajes de Office 365 para información confidencial</span><span class="sxs-lookup"><span data-stu-id="dc045-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="dc045-p101">Actualización (1/30/19): en el 2018 de octubre, hemos trabajado con una pequeña muestra de clientes para comprender si podemos simplificar la protección al cifrar automáticamente los correos electrónicos confidenciales en función de determinados tipos de información confidencial. En función de los comentarios positivos de este ejemplo, decidimos expandir a un perfil más diverso de los inquilinos en diciembre de 2018. Después de comunicar la próxima implementación para seleccionar los inquilinos, escuchamos sus comentarios y determinamos que los clientes con entornos más complejos querían implementar las reglas con más cuidado y que, por lo tanto, estamos ajustando los planes.</span><span class="sxs-lookup"><span data-stu-id="dc045-p101">Update (1/30/19): In October 2018, we worked with a small sample of customers to understand if we can simplify protection by automatically encrypting sensitive emails based on certain sensitive information types. Based on positive feedback from this sample, we decided to expand to a more diverse profile of tenants in December 2018. After communicating the next roll-out to select tenants, we listened to your feedback and determined that customers with more complex environments wanted to implement the rules more cautiously, and we are therefore adjusting our plans.</span></span>

<span data-ttu-id="dc045-p102">Si la organización se seleccionó para la implementación a partir del 15 de enero de 2019, no se implementará la Directiva automática. En su lugar, proporcionaremos instrucciones en este artículo sobre cómo puede completar la implementación de. Siga leyendo para saber cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="dc045-p102">If your organization was selected for the roll-out starting January 15, 2019, we will not roll out the automatic policy. Instead, we are providing instructions in this article on how you can complete the roll-out yourselves. Keep reading to find out how.</span></span>

||
|:-----|
|<span data-ttu-id="dc045-p103">Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="dc045-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a><span data-ttu-id="dc045-113">Cómo crear la Directiva de tipo de información confidencial para su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="dc045-113">How to create the sensitive information type policy for your tenant</span></span>

<span data-ttu-id="dc045-p104">Puede usar las reglas de flujo de correo de Exchange o la prevención de pérdida de datos (DLP) de Office 365 para crear la Directiva de tipo de información confidencial. Para crear una regla de flujo de correo de Exchange, puede usar el centro de administración de Exchange (EAC) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc045-p104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create the sensitive information type policy. To create an Exchange mail flow rule you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="dc045-116">Para crear la Directiva mediante reglas de flujo de correo en el EAC</span><span class="sxs-lookup"><span data-stu-id="dc045-116">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="dc045-p105">Inicie sesión en el centro de administración de Exchange (EAC) y vaya a**reglas**de **flujo** > de correo. Allí, cree una regla que aplique el cifrado de mensajes de Office 365 basándose en condiciones como la presencia de determinadas palabras clave o tipos de información confidencial en el mensaje o los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="dc045-p105">Sign-in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**. There, create a rule that applies Office 365 Message Encryption based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="dc045-119">Para crear la Directiva mediante reglas de flujo de correo en PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc045-119">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="dc045-p106">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell). Use los cmdlets Set-IRMConfiguration y New-TransporRule para crear la Directiva.</span><span class="sxs-lookup"><span data-stu-id="dc045-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Use the Set-IRMConfiguration and New-TransporRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="dc045-123">Ejemplo de regla de flujo de correo creada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc045-123">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="dc045-124">Ejecutar los siguientes comandos en PowerShell cree una regla de flujo de correo de Exchange que cifre automáticamente los correos electrónicos que se encuentran fuera de la organización con la Directiva de *solo cifrado* si los mensajes de correo electrónico o los datos adjuntos contienen los siguientes elementos confidenciales tipos de información:</span><span class="sxs-lookup"><span data-stu-id="dc045-124">Running the following commands in PowerShell create an Exchange mail flow rule that automatically encrypts emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="dc045-125">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="dc045-125">ABA routing number</span></span>
- <span data-ttu-id="dc045-126">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="dc045-126">Credit card Number</span></span>
- <span data-ttu-id="dc045-127">Número de la Agencia para la imPosición de drogas (DEA)</span><span class="sxs-lookup"><span data-stu-id="dc045-127">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="dc045-p107">Número de pasaporte de Estados Unidos/Reino Unido</span><span class="sxs-lookup"><span data-stu-id="dc045-p107">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="dc045-130">Número de cuenta bancaria de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="dc045-130">U.S. bank account number</span></span>
- <span data-ttu-id="dc045-131">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="dc045-131">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="dc045-132">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="dc045-132">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="dc045-133">Acceso a datos adjuntos de destinatarios</span><span class="sxs-lookup"><span data-stu-id="dc045-133">How recipients access attachments</span></span>

<span data-ttu-id="dc045-134">Una vez que un mensaje está cifrado, los destinatarios tendrán acceso sin restricciones a los datos adjuntos una vez que accedan y abran el correo electrónico cifrado.</span><span class="sxs-lookup"><span data-stu-id="dc045-134">Once a message is encrypted, recipients will have unrestricted access to attachments once they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="dc045-135">Para prepararse para este cambio</span><span class="sxs-lookup"><span data-stu-id="dc045-135">To prepare for this change</span></span>

<span data-ttu-id="dc045-p108">Es posible que desee actualizar toda la documentación para el usuario final y los materiales de formación correspondientes para preparar a los usuarios de su organización para este cambio. Comparta estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:</span><span class="sxs-lookup"><span data-stu-id="dc045-p108">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="dc045-138">Enviar, ver y responder mensajes cifrados en Outlook para PC</span><span class="sxs-lookup"><span data-stu-id="dc045-138">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="dc045-139">Vídeo de Office 365 Essentials: cifrado de mensajes de Office</span><span class="sxs-lookup"><span data-stu-id="dc045-139">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="dc045-140">Ver estos cambios en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="dc045-140">View these changes in the Audit log</span></span>

<span data-ttu-id="dc045-p109">Esta actividad se audita y está disponible para los administradores de Office 365. La operación es ' New-TransportRule ' y un fragmento de código de una entrada de auditoría de la búsqueda de registros de auditoría en el centro de seguridad & Compliance Center se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="dc045-p109">This activity is audited and is available to Office 365 administrators. The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="dc045-143">*{"CreationTime": "2018-11-28T23:35:01", "ID": "a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c", "Operation": "New-TransportRule", "OrganizationId": "123456-221d-12345", "RecordType": 1, "ResultStatus": "true", "UserKey": "Microsoft Operator", " UserType ": 3," versión ": 1" carga de trabajo ":" Exchange "," ClientIP ":" 123.456.147.68:17584 "," ObjectId ":" "," UserId ":" Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso. My Microsoft. com "," OriginatingServer ":" CY4PR13MBXXXX ( 15.20.1382.008) "," paraMeters ": {" Name ":" Organization "," Value ":" 123456-221d-12346 "{" Name ":" ApplyRightsProtectionTemplate "," Value ":" enCrypt "}, {" Name ":" Name "," Value ":" enCrypt saliente Sensitive email (regla no actualizada) "}, {" Name ":" MessageContainsDataClassifications "... demás.*</span><span class="sxs-lookup"><span data-stu-id="dc045-143">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span> |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="dc045-144">Para deshabilitar o personalizar la Directiva de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dc045-144">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="dc045-145">Una vez que haya creado la regla de flujo de correo de Exchange, puede deshabilitarla [o editarla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) en**reglas** de **flujo** > de correo en el centro de administración de Exchange (EAC) y deshabilitar la regla "*cifrar mensajes de correo electrónico confidenciales salientes" (regla* "no es de la casilla") ".</span><span class="sxs-lookup"><span data-stu-id="dc045-145">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

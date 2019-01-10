---
title: Nueva directiva de cifrado de mensajes de Office 365 para información confidencial
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Aplica automáticamente la directiva de cifrado de mensajes de Office 365 para implantar para todos los inquilinos de tipos de información confidencial.'
ms.openlocfilehash: a8cd132af2b1429698ea92779a3c54559e2b13e2
ms.sourcegitcommit: b936a2fd4b7f7a7099b96cc29580ed55bdb8bf2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789458"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="88827-103">Directiva de cifrado de mensajes de Office 365 para información confidencial</span><span class="sxs-lookup"><span data-stu-id="88827-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="88827-p101">Se van a crear una nueva directiva automática en los inquilinos de Office 365 que se aplicarán el cifrado de mensajes de Office 365 a todos los correos electrónicos que contienen información confidencial y que se están enviando fuera de su organización. Esta nueva regla de flujo de correo de Exchange se crearán automáticamente en el inquilino de Office 365 para que su organización se protegerán de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="88827-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="when-to-expect-the-update-for-your-tenant"></a><span data-ttu-id="88827-106">Cuándo se espera que la actualización para el inquilino</span><span class="sxs-lookup"><span data-stu-id="88827-106">When to expect the update for your tenant</span></span>

<span data-ttu-id="88827-p102">La organización recibirá una notificación en el centro de mensajes de Office 365 notificarlo a la fecha en la que se creará esta directiva automática en su inquilino. Se le dará al menos un aviso de 30 días y también tendrá la opción de voluntaria. Un escenario en el que es posible que desee excluir potencialmente es si tiene una solución de prevención de pérdida de datos 3rd terceros que ya se examina para tipos de confidenciales. Para obtener más detalles acerca de cómo voluntaria están disponibles más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="88827-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types. More details on how to opt-out are available later in this article.</span></span>

## <a name="sensitive-information-type-policy-details"></a><span data-ttu-id="88827-110">Detalles de directivas de tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="88827-110">Sensitive information type policy details</span></span>

<span data-ttu-id="88827-111">Se creará una regla de flujo de correo de Exchange en la organización que se va a cifrar automáticamente mensajes de correo electrónico desde fuera de la organización con el *Solo cifrar* directiva si los mensajes de correo electrónico o sus datos adjuntos contienen los siguientes tipos de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="88827-111">An Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="88827-112">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="88827-112">ABA routing number</span></span>
- <span data-ttu-id="88827-113">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="88827-113">Credit card Number</span></span>
- <span data-ttu-id="88827-114">Número de drogas Agencia de cumplimiento (DEA)</span><span class="sxs-lookup"><span data-stu-id="88827-114">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="88827-p103">Estados Unidos / número de pasaporte del Reino Unido</span><span class="sxs-lookup"><span data-stu-id="88827-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="88827-117">Número de cuenta bancaria de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="88827-117">U.S. bank account number</span></span>
- <span data-ttu-id="88827-118">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="88827-118">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="88827-119">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="88827-119">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="88827-120">Los tipos de confidenciales exactos pueden diferir mediante la configuración regional de su organización y se comunican en la notificación de centro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="88827-120">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="88827-121">¿Qué es necesario hacer para preparar para este cambio?</span><span class="sxs-lookup"><span data-stu-id="88827-121">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="88827-p104">No es necesario que actualizar o modificar los valores de configuración de Office 365 existentes antes de realizar este cambio nuevo. Sin embargo, es posible que desee actualizar cualquier documentación procede del usuario final y el material de aprendizaje para preparar las personas de su organización para que este cambio. Compartir estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:</span><span class="sxs-lookup"><span data-stu-id="88827-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="88827-125">Enviar, ver y responder a los mensajes cifrados en Outlook para PC</span><span class="sxs-lookup"><span data-stu-id="88827-125">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="88827-126">Office 365 Essentials vídeo: Cifrado de mensajes de Office</span><span class="sxs-lookup"><span data-stu-id="88827-126">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="88827-127">¿Cómo se representará este cambio en el registro de auditoría?</span><span class="sxs-lookup"><span data-stu-id="88827-127">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="88827-p105">Esta actividad se audita y está disponible para los clientes.  La operación es 'New-TransportRule' y es un fragmento de código de una entrada de auditoría de ejemplo de la búsqueda de registro de auditoría en el centro de cumplimiento y seguridad a continuación:</span><span class="sxs-lookup"><span data-stu-id="88827-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="88827-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey": "Operador de Microsoft"," UserType": 3,"versión": 1,"carga de trabajo":"Exchange","IPCliente":"123.456.147.68:17584","ObjectId":"UserId "," ":"() Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX de Microsoft 15.20.1382.008)","Parameters": {"Nombre":"Organización","Valor":" d. 123456-221-12346"{"Nombre":"ApplyRightsProtectionTemplate","Valor":"Cifrar"}, {"Nombre":"Nombre","Valor":"Cifrar correos con información confidencial salientes (fuera de la regla del cuadro)"}, {"Nombre":" MessageContainsDataClassifications"... etcetera.*</span><span class="sxs-lookup"><span data-stu-id="88827-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="88827-131">¿Voluntaria?</span><span class="sxs-lookup"><span data-stu-id="88827-131">How do I opt-out?</span></span>

<span data-ttu-id="88827-132">Si le gustaría voluntaria de este cambio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="88827-132">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="88827-p106">Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="88827-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>
2. <span data-ttu-id="88827-135">Ejecute el cmdlet Set-IRMConfiguration como sigue:</span><span class="sxs-lookup"><span data-stu-id="88827-135">Run the Set-IRMConfiguration cmdlet as follows:</span></span>

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-or-customize-the-automatic-policy"></a><span data-ttu-id="88827-136">¿Cómo deshabilitar o personalizar la directiva automática?</span><span class="sxs-lookup"><span data-stu-id="88827-136">How do I disable or customize the automatic policy?</span></span>

<span data-ttu-id="88827-137">Si no voluntaria de este cambio y ya se ha creado la regla de flujo de correo de Exchange, puede [Deshabilitar o editar la regla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) yendo al **flujo de correo** > **reglas** en el Exchange admin center (EAC) y deshabilite la regla "*cifrar correos salientes con información confidencial (fuera de la regla del cuadro)*".</span><span class="sxs-lookup"><span data-stu-id="88827-137">If you didn’t opt-out of this change and the Exchange mail flow rule has already been created, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

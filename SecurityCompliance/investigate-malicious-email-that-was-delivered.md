---
title: Buscar y investigar correo electrónico malintencionado que se entregó (Office 365 de investigación y respuesta de amenazas
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo usar la investigación de amenazas y las capacidades de respuesta para buscar y investigar correo electrónico malintencionado.
ms.openlocfilehash: 5f8c615bed07b75cd3c06ec48f5ba73586f0f6d5
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394295"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a><span data-ttu-id="3e30b-103">Buscar e investigar correo electrónico malintencionado que se entregó (Office 365 Advanced Threat Protection Plan 2)</span><span class="sxs-lookup"><span data-stu-id="3e30b-103">Find and investigate malicious email that was delivered (Office 365 Advanced Threat Protection Plan 2)</span></span>

<span data-ttu-id="3e30b-104">[Office 365 Advanced Threat Protection](office-365-atp.md) le permite investigar las actividades que ponen en riesgo a los usuarios y emprender acciones para proteger su organización.</span><span class="sxs-lookup"><span data-stu-id="3e30b-104">[Office 365 Advanced Threat Protection](office-365-atp.md) lets you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="3e30b-105">Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3e30b-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="3e30b-106">Para ello, puede usar el [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="3e30b-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="3e30b-107">Antes de comenzar...</span><span class="sxs-lookup"><span data-stu-id="3e30b-107">Before you begin...</span></span>

<span data-ttu-id="3e30b-108">Asegúrese de que se cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="3e30b-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="3e30b-109">Su organización tiene [Office 365 Advanced Threat Protection](office-365-atp.md) (plan 1 o plan 2) y [se asignan licencias a los usuarios](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="3e30b-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Plan 1 or Plan 2) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="3e30b-110">El [registro de auditoría de Office 365](turn-audit-log-search-on-or-off.md) está activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="3e30b-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="3e30b-111">Su organización tiene directivas definidas para protección contra correo electrónico no deseado, antimalware, antiphishing, etc.</span><span class="sxs-lookup"><span data-stu-id="3e30b-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="3e30b-112">Consulte [proteger contra amenazas en Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="3e30b-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="3e30b-113">Es un administrador global de Office 365 o bien tiene el rol de administrador de seguridad o de búsqueda y depuración asignado en &amp; el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3e30b-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="3e30b-114">Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3e30b-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="3e30b-115">Tratar los correos sospechosos</span><span class="sxs-lookup"><span data-stu-id="3e30b-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="3e30b-116">Los atacantes malintencionados pueden enviar correo a sus usuarios para probar y phish sus credenciales y obtener acceso a sus secretos corporativos.</span><span class="sxs-lookup"><span data-stu-id="3e30b-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="3e30b-117">Para evitarlo, debe usar los servicios de protección contra amenazas en Office 365, incluidos [Exchange Online Protection](eop/exchange-online-protection-overview.md) y la [protección contra amenazas avanzada](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="3e30b-117">To prevent this, you should use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="3e30b-118">Sin embargo, hay veces en las que un atacante puede enviar correo a los usuarios que contengan una dirección URL y que, más adelante, esta dirección URL apunte a contenido malintencionado (malware, etc.).</span><span class="sxs-lookup"><span data-stu-id="3e30b-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> <span data-ttu-id="3e30b-119">Como alternativa, es posible que se vea demasiado tarde que un usuario de la organización se ha puesto en peligro y, mientras que el usuario ha estado en peligro, el atacante ha usado esa cuenta para enviar correo electrónico a otros usuarios de la compañía.</span><span class="sxs-lookup"><span data-stu-id="3e30b-119">Alternately, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="3e30b-120">Como parte de la limpieza de ambos escenarios, es posible que desee quitar los mensajes de correo electrónico de las bandejas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3e30b-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="3e30b-121">En situaciones como estas, puede aprovechar [el explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md) para buscar y quitar los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3e30b-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a><span data-ttu-id="3e30b-122">Dónde se encuentran los mensajes de correo electrónico redistribuidos una vez que se llevan a cabo acciones</span><span class="sxs-lookup"><span data-stu-id="3e30b-122">Where re-routed emails are located after actions are taken</span></span>

<span data-ttu-id="3e30b-123">Detecciones en tiempo real del explorador de amenazas ha agregado los campos acción de entrega y ubicación de entrega en el estado del lugar de entrega.</span><span class="sxs-lookup"><span data-stu-id="3e30b-123">Threat Explorer real-time detections has added the Delivery Action and Delivery Location fields in the place of Delivery Status.</span></span> <span data-ttu-id="3e30b-124">Esto da como resultado una imagen más completa de dónde se encuentran los correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3e30b-124">This results in a more complete picture of where your emails land.</span></span> <span data-ttu-id="3e30b-125">Parte del objetivo de este cambio es facilitar la búsqueda para los operadores de seguridad, pero el resultado neto es conocer la ubicación de los correos electrónicos con problemas de un vistazo.</span><span class="sxs-lookup"><span data-stu-id="3e30b-125">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="3e30b-126">El estado de entrega ahora se divide en dos columnas:</span><span class="sxs-lookup"><span data-stu-id="3e30b-126">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="3e30b-127">**Acción de entrega** : ¿Cuál es el estado de este correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="3e30b-127">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="3e30b-128">**Ubicación de entrega** : ¿Dónde se distribuyó este correo electrónico como resultado?</span><span class="sxs-lookup"><span data-stu-id="3e30b-128">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="3e30b-129">La acción de entrega es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes.</span><span class="sxs-lookup"><span data-stu-id="3e30b-129">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="3e30b-130">Estas son las posibles acciones que puede realizar un correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="3e30b-130">Here are the possible actions an email can take:</span></span>

1. <span data-ttu-id="3e30b-131">**Delivered** : el correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.</span><span class="sxs-lookup"><span data-stu-id="3e30b-131">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
2. <span data-ttu-id="3e30b-132">Correo electrónico **no deseado** : el correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los correos electrónicos en su carpeta de correo no deseado o eliminado.</span><span class="sxs-lookup"><span data-stu-id="3e30b-132">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to emails in their Junk or Deleted folder.</span></span>
3. <span data-ttu-id="3e30b-133">**Bloqueado** : cualquier correo electrónico que esté en cuarentena, que falle o que se haya cancelado.</span><span class="sxs-lookup"><span data-stu-id="3e30b-133">**Blocked** – any emails that's quarantined, that  failed, or was dropped.</span></span> <span data-ttu-id="3e30b-134">El usuario no tiene acceso completamente a esto.</span><span class="sxs-lookup"><span data-stu-id="3e30b-134">This is completely inaccessible by the user!</span></span>
4. <span data-ttu-id="3e30b-135">**Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por archivos. txt que indican que los datos adjuntos eran malintencionados.</span><span class="sxs-lookup"><span data-stu-id="3e30b-135">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="3e30b-136">Ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega.</span><span class="sxs-lookup"><span data-stu-id="3e30b-136">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="3e30b-137">Está vinculado a una acción de entrega.</span><span class="sxs-lookup"><span data-stu-id="3e30b-137">It's linked to a Delivery Action.</span></span> <span data-ttu-id="3e30b-138">Este campo se agregó para proporcionar información sobre la acción tomada cuando se encuentra un mensaje problemático.</span><span class="sxs-lookup"><span data-stu-id="3e30b-138">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="3e30b-139">Estos son los valores posibles de la ubicación de entrega:</span><span class="sxs-lookup"><span data-stu-id="3e30b-139">Here are the possible values of delivery location:</span></span>

1. <span data-ttu-id="3e30b-140">**Bandeja de entrada o carpeta** : el correo electrónico se encuentra en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="3e30b-140">**Inbox or folder** – The email is in inbox or a folder (according to your email rules).</span></span>
2. <span data-ttu-id="3e30b-141">Local **o externa** : el buzón de correo no existe en la nube pero es local.</span><span class="sxs-lookup"><span data-stu-id="3e30b-141">**On-prem or external** – The mailbox doesn’t exist on cloud but is on -premises.</span></span>
3. <span data-ttu-id="3e30b-142">**Carpeta de correo no deseado** : el correo electrónico en la carpeta de correo no deseado de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3e30b-142">**Junk folder** – The email in in the Junk folder of a user.</span></span>
4. <span data-ttu-id="3e30b-143">**Carpeta elementos eliminados** : el correo electrónico de la carpeta elementos eliminados de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3e30b-143">**Deleted items folder** – The email in the Deleted items folder of a user.</span></span>
5. <span data-ttu-id="3e30b-144">**Cuarentena** : el correo electrónico en cuarentena y no se encuentra en el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="3e30b-144">**Quarantine** – The email in quarantine, and is not in a user’s mailbox.</span></span>
6. <span data-ttu-id="3e30b-145">**Failed** – el correo electrónico no pudo llegar al buzón.</span><span class="sxs-lookup"><span data-stu-id="3e30b-145">**Failed** – The email failed to reach the mailbox.</span></span>
7. <span data-ttu-id="3e30b-146">\*\*\*\* Perdido: el correo electrónico se pierde en algún lugar del flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="3e30b-146">**Dropped** – The email gets lost somewhere in the Mailflow.</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="3e30b-147">Buscar y eliminar correo electrónico sospechoso que se entregó</span><span class="sxs-lookup"><span data-stu-id="3e30b-147">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="3e30b-148">El explorador de amenazas (a veces denominado explorador) es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación.</span><span class="sxs-lookup"><span data-stu-id="3e30b-148">Threat Explorer (sometimes called Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="3e30b-149">El siguiente procedimiento se centra en usar el explorador para buscar y eliminar correo electrónico malintencionado de los buzones de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="3e30b-149">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

<span data-ttu-id="3e30b-150">Para ver los cambios en el campo Estado de entrega anterior (ahora acción de entrega y ubicación de entrega):</span><span class="sxs-lookup"><span data-stu-id="3e30b-150">To see the changes to the former Delivery Status field (now Delivery Action and Delivery Location):</span></span> 

1. <span data-ttu-id="3e30b-151">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365.</span><span class="sxs-lookup"><span data-stu-id="3e30b-151">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="3e30b-152">Esto le llevará al centro de &amp; seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3e30b-152">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="3e30b-153">En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="3e30b-153">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

![Captura de pantalla del explorador de amenazas.](media/Threat Explorer Delivery Action and Delivery Location.PNG)

<!--Comment>
    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a><span data-ttu-id="3e30b-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3e30b-155">Related topics</span></span>

[<span data-ttu-id="3e30b-156">Plan 2 de protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="3e30b-156">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="3e30b-157">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="3e30b-157">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="3e30b-158">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="3e30b-158">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  


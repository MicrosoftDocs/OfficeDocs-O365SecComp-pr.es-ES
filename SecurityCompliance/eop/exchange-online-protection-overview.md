---
title: Información general de Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Protección de Exchange Online (EOP) es un servicio de filtro de correo electrónico basado en nube que ayuda a proteger su organización contra correo no deseado y malware, e incluye características para proteger a su organización contra incumplimiento de directivas de mensajería.
ms.openlocfilehash: 89852c7ba211ccb266c8b231b00d3d83987a5f20
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026697"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="3b7da-103">Información general de Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3b7da-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="3b7da-p101">Microsoft Exchange Online Protection (EOP) es un servicio de filtrado de correo basado en la nube que ayuda a proteger la organización frente al correo no deseado y el malware, e incluye características que protegen también frente al incumplimiento de las directivas de mensajería. EOP simplifica la administración del entorno de mensajes y puede aliviar muchas de las cargas asociadas al mantenimiento del software y el hardware local.</span><span class="sxs-lookup"><span data-stu-id="3b7da-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>
  
<span data-ttu-id="3b7da-106">Estas son las principales formas en las que se puede usar EOP para la protección de mensajes:</span><span class="sxs-lookup"><span data-stu-id="3b7da-106">The following are the primary ways you can use EOP for messaging protection:</span></span>
  
- <span data-ttu-id="3b7da-107">**En un escenario independiente** EOP ofrece protección de correo electrónico basada en la nube para su entorno de Microsoft Exchange Server 2013 local, versiones heredadas de Exchange Server, o cualquier otro local solución de correo electrónico SMTP.</span><span class="sxs-lookup"><span data-stu-id="3b7da-107">**In a standalone scenario** EOP provides cloud-based email protection for your on-premises Microsoft Exchange Server 2013 environment, legacy Exchange Server versions, or for any other on-premises SMTP email solution.</span></span> 
    
- <span data-ttu-id="3b7da-108">**Como parte de Microsoft Exchange Online**: de manera predeterminada, EOP protege los buzones de Microsoft Exchange Online hospedados en la nube.</span><span class="sxs-lookup"><span data-stu-id="3b7da-108">**As a part of Microsoft Exchange Online** By default, EOP protects Microsoft Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="3b7da-109">**En una implementación híbrida**: EOP se puede configurar para que proteja el entorno de mensajería y controle el enrutamiento del correo cuando se tiene una mezcla de buzones locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="3b7da-109">**In a hybrid deployment** EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span> 
    
## <a name="how-eop-works"></a><span data-ttu-id="3b7da-110">Cómo funciona EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-110">How EOP works</span></span>

<span data-ttu-id="3b7da-111">Para comprender el funcionamiento de EOP, es muy útil ver cómo se procesa el correo entrante:</span><span class="sxs-lookup"><span data-stu-id="3b7da-111">To understand how EOP works, it helps to see how it processes incoming email:</span></span>
  
![Procesamiento de correo electrónico de elevación de privilegios](../media/EOP-email-processing.png)
  
<span data-ttu-id="3b7da-p102">Inicialmente, un mensaje entrante se pasa a través de filtrado de la conexión, que comprobaciones de reputación del remitente e inspecciona el mensaje de malware. La mayoría de correo no deseado es detenida en este momento y eliminar mediante la elevación de privilegios. Los mensajes se siguen a través del filtrado de directiva, donde se evalúan los mensajes con reglas de transporte personalizados que cree o aplicar a partir de una plantilla. Por ejemplo, puede tener una regla que envía una notificación a un administrador cuando llegue correo de un remitente específico. (Comprobaciones de prevención de pérdida de datos también se producen en este momento, si tiene que la característica; para obtener información acerca de la disponibilidad de la característica, vea la [Descripción del servicio Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=320619).) A continuación, los mensajes pasan a través de filtrado de contenido, donde se comprueba contenido terminología o propiedades comunes a correo no deseado. Un mensaje determinado spam por el filtro de contenido se puede enviar a carpeta de correo electrónico no deseado de un usuario o a la cuarentena, entre otras opciones, en función de la configuración. Después de que un mensaje pase correctamente todas estas capas de protección, se entrega al destinatario.</span><span class="sxs-lookup"><span data-stu-id="3b7da-p102">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware. The majority of spam is stopped at this point and deleted by EOP. Messages continue through policy filtering, where messages are evaluated against custom transport rules that you create or enforce from a template. For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender. (Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam. A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options, based on your settings. After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>
  
### <a name="eop-datacenters"></a><span data-ttu-id="3b7da-120">Centros de datos de EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-120">EOP datacenters</span></span>

<span data-ttu-id="3b7da-p103">EOP se ejecuta en una red mundial de centros de datos que están diseñados para proporcionar la mejor disponibilidad. Por ejemplo, si un centro de datos no está disponible, los mensajes de correo electrónico se enrutan automáticamente a otro centro de datos sin interrupciones del servicio. Los servidores de los centros de datos aceptan mensajes en nombre del usuario y disponen una capa de separación entre la organización e Internet, lo que permite reducir la carga en los servidores. Gracias a esta red de alta disponibilidad, Microsoft se asegura que el correo llegue a la organización de manera puntual.</span><span class="sxs-lookup"><span data-stu-id="3b7da-p103">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span> 
  
<span data-ttu-id="3b7da-p104">EOP realiza el equilibrio de carga entre los centros de datos, pero solo dentro de una región. Si está aprovisionado en una región, todos sus mensajes se procesarán usando el enrutamiento de correo de esa región. La siguiente lista muestra cómo funciona el enrutamiento regional de correo para los centros de datos de EOP:</span><span class="sxs-lookup"><span data-stu-id="3b7da-p104">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>
  
- <span data-ttu-id="3b7da-p105">En el de los Estados Unidos, Exchange todos los Online buzones se encuentren en centros de datos de Estados Unidos, con la excepción de Sudamérica, donde se usan los centros de datos en Brasil y Chile y Canadá donde se usan los centros de datos en Canadá. Todos los mensajes de correo electrónico, incluidos los mensajes para los clientes de Sudamérica y Canadá, se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP; Sin embargo, correo electrónico de mensajes de correo puestos se almacena en el centro de datos donde se encuentra el inquilino..</span><span class="sxs-lookup"><span data-stu-id="3b7da-p105">In the America's, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used. All email messages, including messages for customers in South America and Canada, are routed through U.S. datacenters for EOP filtering; however quaratined email is stored in the datacenter where the tenant is located..</span></span>
    
- <span data-ttu-id="3b7da-130">En Europa, Oriente Medio y África (EMEA), todos los buzones de Exchange Online están ubicados en centros de datos de EMEA, y todos los mensajes se enrutan a través de EMEA para el filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="3b7da-130">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="3b7da-p106">En Asia Pacífico (APAC), todos los buzones de Exchange Online están ubicados en centros de datos de APAC, pero los mensajes se enrutan a través de centros de datos de EMEA para el filtrado de EOP. Está previsto que esto cambie en el cuarto trimestre de 2014, cuando los mensajes se enrutarán a través de centros de datos de APAC para el filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="3b7da-p106">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, but messages are currently routed through EMEA datacenters for EOP filtering. This is targeted to be changing in the fourth quarter of 2014, when messages will be routed through APAC datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="3b7da-133">Para la nube de la comunidad de organismos oficiales (GCC), todos los buzones de Exchange Online están ubicados en centros de datos de Estados Unidos y los mensajes se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="3b7da-133">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>
    
## <a name="eop-plans-and-features"></a><span data-ttu-id="3b7da-134">Planes y características de EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-134">EOP plans and features</span></span>

<span data-ttu-id="3b7da-135">A continuación se detallan los planes de suscripción de EOP disponibles:</span><span class="sxs-lookup"><span data-stu-id="3b7da-135">The following are the available EOP subscription plans:</span></span>
  
- <span data-ttu-id="3b7da-136">**EOP independiente**: EOP protege los buzones locales.</span><span class="sxs-lookup"><span data-stu-id="3b7da-136">**EOP standalone** Where EOP protects your on-premises mailboxes.</span></span> 
    
- <span data-ttu-id="3b7da-137">**Características de EOP en Exchange Online**: EOP protege los buzones de Exchange Online hospedados en la nube.</span><span class="sxs-lookup"><span data-stu-id="3b7da-137">**EOP features in Exchange Online** Where EOP protects your Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="3b7da-138">**Exchange Enterprise CAL con servicios** Donde EOP protege los buzones locales, tal como EOP independiente, e incluye prevención de pérdida de datos (DLP) e informes que usan servicios web.</span><span class="sxs-lookup"><span data-stu-id="3b7da-138">**Exchange Enterprise CAL with Services** Where EOP protects your on-premises mailboxes, like EOP standalone, and includes data loss prevention (DLP) and reporting using web services.</span></span> 
    
<span data-ttu-id="3b7da-139">Para más información sobre los requisitos, límites importantes y disponibilidad de características en todos los planes de suscripción de EOP, vea la [Descripción de servicio Protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span><span class="sxs-lookup"><span data-stu-id="3b7da-139">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span></span>
  
## <a name="setting-up-eop"></a><span data-ttu-id="3b7da-140">Configurar EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-140">Setting up EOP</span></span>

<span data-ttu-id="3b7da-p107">Configurar EOP puede ser fácil, especialmente en las compañías pequeñas con pocas reglas de cumplimiento. Sin embargo, si tiene una organización grande con muchos dominios, reglas de cumplimiento personalizadas o flujo de correo híbrido, la configuración puede llevar más tiempo e implicar más planeación.</span><span class="sxs-lookup"><span data-stu-id="3b7da-p107">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>
  
<span data-ttu-id="3b7da-143">Si ya ha comprado EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md) para asegurarse de completar todos los pasos necesarios para configurar EOP de modo que proteja el entorno de mensajería.</span><span class="sxs-lookup"><span data-stu-id="3b7da-143">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="3b7da-144">Más información</span><span class="sxs-lookup"><span data-stu-id="3b7da-144">For more information</span></span>

[<span data-ttu-id="3b7da-145">Características de EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-145">EOP features</span></span>](eop-features.md)
  
[<span data-ttu-id="3b7da-146">Vídeos de introducción a EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-146">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="3b7da-147">Preguntas más frecuentes sobre EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-147">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="3b7da-148">Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-148">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)
  
[<span data-ttu-id="3b7da-149">Preguntas más frecuentes sobre administración delegada</span><span class="sxs-lookup"><span data-stu-id="3b7da-149">Delegated administration FAQ</span></span>](delegated-administration-faq.md)
  
[<span data-ttu-id="3b7da-150">Mover dominios y opciones de configuración de una organización de EOP a otra organización de EOP</span><span class="sxs-lookup"><span data-stu-id="3b7da-150">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  


---
title: Inteligencia de flujo de correo en Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Los administradores pueden obtener información sobre los códigos de error que están asociados con la entrega de mensajes mediante conectores en Office 365 (también conocido como inteligencia de flujo de correo).
ms.openlocfilehash: 9f27dfd4c265eb62028d68c27764183202692ef4
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327092"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="c960f-103">Inteligencia de flujo de correo en Office 365</span><span class="sxs-lookup"><span data-stu-id="c960f-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="c960f-p101">Normalmente, se utiliza un conector para enrutar mensajes de correo electrónico de la organización de Office 365 a su entorno de correo electrónico local. También puede usar un conector para enrutar los mensajes de Office 365 para una organización asociada. Cuando Office 365 no puede entregar estos mensajes a través del conector, está en cola en Office 365. Office 365 seguirá intentando entrega para cada mensaje durante 48 horas. Después de 48 horas, caducará el mensaje en cola y se devolverá el mensaje al remitente original en un informe de no entrega (también conocido como un mensaje NDR o rebote).</span><span class="sxs-lookup"><span data-stu-id="c960f-p101">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="c960f-p102">Office 365 genera un error cuando no se puede entregar un mensaje mediante el uso de un conector. En este tema se describen los errores más comunes y sus soluciones. De forma colectiva, poner en cola y notificación de errores para los mensajes no entregados enviados a través de los conectores se conoce como _inteligencia de flujo de correo_.</span><span class="sxs-lookup"><span data-stu-id="c960f-p102">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="c960f-112">Código de error: error en la consulta DNS 450 4.4.312</span><span class="sxs-lookup"><span data-stu-id="c960f-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="c960f-p103">Normalmente, este error significa que Office 365 intentó conectarse al host inteligente que se especifica en el conector, pero la consulta DNS para encontrar las direcciones IP del host inteligente no se pudo. Las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="c960f-p103">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed. The possible causes for this error are:</span></span>

- <span data-ttu-id="c960f-115">Hay un problema con DNS de su dominio que hospeda el servicio (es decir, la parte que mantiene los servidores de autorización de nombres para su dominio).</span><span class="sxs-lookup"><span data-stu-id="c960f-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="c960f-116">Recientemente ha caducado su dominio, por lo que no se puede recuperar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="c960f-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="c960f-117">Recientemente ha cambiado el registro MX de su dominio y los servidores DNS de Office 365 todavía se previamente almacenado en caché la información de DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="c960f-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="c960f-118">¿Cómo soluciono el código de error 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="c960f-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="c960f-119">Trabajar con el que hospeda el servicio DNS para identificar y solucionar el problema con su dominio.</span><span class="sxs-lookup"><span data-stu-id="c960f-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="c960f-120">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), póngase en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="c960f-121">Código de error: 450 4.4.315 conexión agotó el tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="c960f-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="c960f-p104">Normalmente, esto significa que Office 365 no se puede conectar al servidor de correo electrónico de destino. Los detalles del error, explican el problema. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c960f-p104">Typically, this means Office 365 can't connect to the destination email server. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="c960f-125">El servidor de correo electrónico de local está inactivo.</span><span class="sxs-lookup"><span data-stu-id="c960f-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="c960f-126">Hay un error en la configuración del host inteligente del conector para que Office 365 está intentando para conectarse a la dirección IP incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c960f-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="c960f-127">¿Cómo soluciono el código de error 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="c960f-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="c960f-p105">Averiguar qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha trabajado correctamente y no ha cambiado la configuración del conector, debe comprobar el entorno de correo electrónico local para ver si el servidor está inactivo, o si ha habido cambios en la infraestructura de red (por ejemplo, se han cambiado proveedores de servicios de internet, por lo que ahora tiene diferentes direcciones IP).</span><span class="sxs-lookup"><span data-stu-id="c960f-p105">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="c960f-130">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), póngase en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="c960f-131">Código de error: 450 4.4.316 ha rechazado la conexión</span><span class="sxs-lookup"><span data-stu-id="c960f-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="c960f-p106">Normalmente, este error significa que Office 365 encontró un error de conexión al intentar conectarse al servidor de correo electrónico de destino. Una causa común de este error es que el servidor de seguridad está bloqueando las conexiones de direcciones IP de Office 365. O bien, este error podría ser por diseño si haya terminado de migrar su local del sistema de correo electrónico a Office 365 y apague el entorno de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="c960f-p106">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="c960f-135">¿Cómo soluciono el código de error 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="c960f-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="c960f-p107">Si tiene buzones de correo en su entorno local, debe modificar la configuración del firewall para permitir conexiones desde las direcciones IP de Office 365 en el puerto TCP 25 a los servidores de correo electrónico local. Para obtener una lista de las direcciones IP de Office 365, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span><span class="sxs-lookup"><span data-stu-id="c960f-p107">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="c960f-p108">Si no hay más mensajes deben entregarse a su entorno local, haga clic en **corregir ahora** en la alerta para que Office 365 puede rechazar inmediatamente los mensajes con destinatarios no válidos. Esto permite reducir el riesgo de superación del límite de cuota de la organización para los destinatarios no válidos, lo que podrían afectar la entrega del mensaje normal. O bien, puede usar las siguientes instrucciones para solucionar el problema de forma manual:</span><span class="sxs-lookup"><span data-stu-id="c960f-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="c960f-141">En el [Centro de administración de Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) en Office 365, deshabilitar o eliminar el conector que entrega el correo electrónico de Office 365 a su entorno de correo electrónico local:</span><span class="sxs-lookup"><span data-stu-id="c960f-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="c960f-142">En el EAC, vaya a **flujo de correo** \> **conectores**.</span><span class="sxs-lookup"><span data-stu-id="c960f-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="c960f-143">Seleccione el conector con el valor **de** **Office 365** y el valor **al** **servidor de correo electrónico de la organización** y siga uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c960f-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="c960f-144">Eliminar el conector haciendo clic en **Eliminar** ![icono de eliminación](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="c960f-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="c960f-145">Deshabilitar el conector haciendo clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) y desactivar **activarla**.</span><span class="sxs-lookup"><span data-stu-id="c960f-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="c960f-p109">Cambiar el dominio aceptado en Office 365 que está asociado con su entorno de correo electrónico local de **Retransmisión interna** en **autoritativo**. Para obtener instrucciones, vea [Administrar dominios aceptados en Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span><span class="sxs-lookup"><span data-stu-id="c960f-p109">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="c960f-p110">**Nota**: normalmente, estos cambios tardan entre 30 minutos y una hora para que surtan efecto. Después de una hora, compruebe que ya no recibe el error.</span><span class="sxs-lookup"><span data-stu-id="c960f-p110">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="c960f-150">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="c960f-151">Código de error: 450 4.4.317 no se puede conectar al servidor remoto</span><span class="sxs-lookup"><span data-stu-id="c960f-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="c960f-p111">Normalmente, este error significa que Office 365 conectado al servidor de correo electrónico de destino, pero el servidor responde con un error inmediato, o no cumple los requisitos de conexión. Los detalles del error, explican el problema. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c960f-p111">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="c960f-155">El servidor de correo electrónico de destino respondió con un error "Servicio no disponible", que indica que el servidor es no se puede mantener la comunicación con Office 365.</span><span class="sxs-lookup"><span data-stu-id="c960f-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="c960f-156">El conector está configurado para requerir TLS, pero el servidor de correo electrónico de destino no admite TLS.</span><span class="sxs-lookup"><span data-stu-id="c960f-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="c960f-157">¿Cómo soluciono el código de error 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="c960f-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="c960f-158">Compruebe la configuración de TLS y certificados en los servidores de correo electrónico local y la configuración de TLS en el conector.</span><span class="sxs-lookup"><span data-stu-id="c960f-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="c960f-159">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="c960f-160">Código de error: 450 4.4.318 conexión se ha cerrado de manera repentina</span><span class="sxs-lookup"><span data-stu-id="c960f-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="c960f-p112">Normalmente, este error significa que Office 365 es tiene dificultades para comunicarse con su entorno de correo electrónico local, por lo que se quitó la conexión. Las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="c960f-p112">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped. The possible causes for this error are:</span></span>

- <span data-ttu-id="c960f-163">El servidor de seguridad usa las reglas de examen de paquetes de SMTP, y dichas reglas no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="c960f-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="c960f-164">El servidor de correo electrónico local no es trabajar correctamente (por ejemplo, se bloquea de servicio, se bloquea o recursos del sistema baja), que es lo que provoca que el servidor de tiempo de espera y cerrar la conexión a Office 365.</span><span class="sxs-lookup"><span data-stu-id="c960f-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="c960f-165">Hay problemas de red entre su entorno local y Office 365.</span><span class="sxs-lookup"><span data-stu-id="c960f-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="c960f-166">¿Cómo soluciono el código de error 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="c960f-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="c960f-167">Averiguar qué escenario se aplica a usted y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="c960f-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="c960f-168">Si el problema está causado por problemas de red entre su entorno local y Office 365, póngase en contacto con su equipo de red para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="c960f-169">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="c960f-170">Código de error: error de validación de certificado 450 4.7.320</span><span class="sxs-lookup"><span data-stu-id="c960f-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="c960f-p113">Normalmente, este error significa que Office 365 encontró un error al intentar validar el certificado del servidor de correo electrónico de destino. Los detalles del error, explican el error. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c960f-p113">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server. The error details will explain the error. For example:</span></span>

- <span data-ttu-id="c960f-174">Certificado caducado</span><span class="sxs-lookup"><span data-stu-id="c960f-174">Certificate expired</span></span>

- <span data-ttu-id="c960f-175">Error de coincidencia de asunto de certificado</span><span class="sxs-lookup"><span data-stu-id="c960f-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="c960f-176">Certificado ya no es válido</span><span class="sxs-lookup"><span data-stu-id="c960f-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="c960f-177">¿Cómo soluciono el código de error 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="c960f-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="c960f-178">Corregir el certificado o la configuración en el conector de modo que los mensajes en cola en Office 365 se puede entregar.</span><span class="sxs-lookup"><span data-stu-id="c960f-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="c960f-179">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="c960f-180">Otros códigos de error</span><span class="sxs-lookup"><span data-stu-id="c960f-180">Other error codes</span></span>

<span data-ttu-id="c960f-p114">Office 365 es tiene dificultades para entregar mensajes a su local o servidor de correo electrónico de socio. Use la información de **servidor de destino** en el error para examinar el problema en su entorno, o modificar el conector si se ha producido un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="c960f-p114">Office 365 is having difficulty delivering messages to your on-premises or partner email server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="c960f-183">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="c960f-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

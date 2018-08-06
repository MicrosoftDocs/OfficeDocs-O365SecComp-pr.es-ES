---
title: Inteligencia de flujo de correo en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 'Normalmente, se utiliza un conector para enrutar los mensajes desde la organización de Office 365 para sus instalaciones en el entorno de mensajería. También puede usar un conector para enrutar los mensajes de Office 365 para una organización asociada. Cuando Office 365 no puede entregar estos mensajes a través del conector, está en cola en Office 365. '
ms.openlocfilehash: 495d73524afb3ab3a34fd2f1f5f4cd747481f9d8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027627"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="bd249-105">Inteligencia de flujo de correo en Office 365</span><span class="sxs-lookup"><span data-stu-id="bd249-105">Mail flow intelligence in Office 365</span></span>
  
<span data-ttu-id="bd249-p102">Normalmente, se utiliza un conector para enrutar los mensajes desde la organización de Office 365 para sus instalaciones en el entorno de mensajería. También puede usar un conector para enrutar los mensajes de Office 365 para una organización asociada. Cuando Office 365 no puede entregar estos mensajes a través del conector, está en cola en Office 365. Office 365 seguirá intentando entrega para cada mensaje durante 48 horas. Después de 48 horas, caducará el mensaje en cola y se devolverá el mensaje al remitente original en un informe de no entrega (también conocido como un mensaje NDR o rebote).</span><span class="sxs-lookup"><span data-stu-id="bd249-p102">Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>
  
<span data-ttu-id="bd249-p103">Office 365 genera un error cuando no se puede entregar un mensaje mediante el uso de un conector. En este tema se describen los errores más comunes y sus soluciones. De forma colectiva, poner en cola y notificación de errores para los mensajes no entregados enviados a través de los conectores se conoce como inteligencia de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="bd249-p103">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as mailflow intelligence.</span></span>
  
 <span data-ttu-id="bd249-114">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="bd249-114">**Contents**</span></span>
  
- [<span data-ttu-id="bd249-115">Código de error: error en la consulta DNS 450 4.4.312</span><span class="sxs-lookup"><span data-stu-id="bd249-115">Error code: 450 4.4.312 DNS query failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [<span data-ttu-id="bd249-116">Código de error: 450 4.4.315 conexión agotó el tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="bd249-116">Error code: 450 4.4.315 Connection timed out</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [<span data-ttu-id="bd249-117">Código de error: 450 4.4.316 ha rechazado la conexión</span><span class="sxs-lookup"><span data-stu-id="bd249-117">Error code: 450 4.4.316 Connection refused</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [<span data-ttu-id="bd249-118">Código de error: 450 4.4.317 no se puede conectar al servidor remoto</span><span class="sxs-lookup"><span data-stu-id="bd249-118">Error code: 450 4.4.317 Cannot connect to remote server</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [<span data-ttu-id="bd249-119">Código de error: 450 4.4.318 conexión se ha cerrado de manera repentina</span><span class="sxs-lookup"><span data-stu-id="bd249-119">Error code: 450 4.4.318 Connection was closed abruptly</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [<span data-ttu-id="bd249-120">Código de error: error de validación de certificado 450 4.7.320</span><span class="sxs-lookup"><span data-stu-id="bd249-120">Error code: 450 4.7.320 Certificate validation failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="bd249-121">Código de error: error en la consulta DNS 450 4.4.312</span><span class="sxs-lookup"><span data-stu-id="bd249-121">Error code: 450 4.4.312 DNS query failed</span></span>
<span data-ttu-id="bd249-122"><a name="ErrorCode44312"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-122"></span></span>

<span data-ttu-id="bd249-p104">Normalmente, este error significa que Office 365 intentó conectarse al host inteligente que se especifica en el conector, pero la consulta DNS para buscar la dirección IP de host inteligente direcciones no se pudo. Las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="bd249-p104">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host IP addresses failed. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="bd249-125">Hay un problema con DNS de su dominio que hospeda el servicio (es decir, la parte que mantiene los servidores de autorización de nombres para su dominio).</span><span class="sxs-lookup"><span data-stu-id="bd249-125">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>
    
- <span data-ttu-id="bd249-126">Recientemente ha caducado su dominio, por lo que no se puede recuperar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="bd249-126">Your domain has recently expired, so the MX record can't be retrieved.</span></span>
    
- <span data-ttu-id="bd249-127">Recientemente ha cambiado el registro MX de su dominio y los servidores DNS de Office 365 todavía se previamente almacenado en caché la información de DNS para su dominio.</span><span class="sxs-lookup"><span data-stu-id="bd249-127">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>
    
<span data-ttu-id="bd249-128">Debe trabajar con el servicio de hospedaje de DNS para corregir el problema DNS.</span><span class="sxs-lookup"><span data-stu-id="bd249-128">You need to fix the DNS issue by working with your DNS hosting service.</span></span>
  
<span data-ttu-id="bd249-129">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-129">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="bd249-130">Código de error: 450 4.4.315 conexión agotó el tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="bd249-130">Error code: 450 4.4.315 Connection timed out</span></span>
<span data-ttu-id="bd249-131"><a name="ErrorCode44315"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-131"></span></span>

<span data-ttu-id="bd249-p105">Normalmente, esto significa que Office 365 no se puede conectar al servidor de mensajería de destino. Los detalles del error, explican el problema. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd249-p105">Typically, this means Office 365 can't connect to the destination messaging server. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="bd249-135">Su local es el servidor de mensajería hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="bd249-135">Your on-premises messaging server is down.</span></span>
    
- <span data-ttu-id="bd249-136">Hay un error en la configuración del host inteligente del conector para que Office 365 está intentando para conectarse a la dirección IP incorrecta.</span><span class="sxs-lookup"><span data-stu-id="bd249-136">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>
    
<span data-ttu-id="bd249-p106">Averiguar qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha trabajado correctamente y no ha cambiado la configuración del conector, debe comprobar su local para ver si el servidor está inactivo, o si ha habido cambios en la infraestructura de red (por ejemplo, el entorno de mensajería se han cambiado proveedores de servicios de Internet, por lo que ahora tiene diferentes direcciones IP).</span><span class="sxs-lookup"><span data-stu-id="bd249-p106">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises messaging environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed Internet service providers, so you now have different IP addresses).</span></span>
  
<span data-ttu-id="bd249-139">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-139">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="bd249-140">Código de error: 450 4.4.316 ha rechazado la conexión</span><span class="sxs-lookup"><span data-stu-id="bd249-140">Error code: 450 4.4.316 Connection refused</span></span>
<span data-ttu-id="bd249-141"><a name="ErrorCode44316"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-141"></span></span>

<span data-ttu-id="bd249-p107">Normalmente, este error significa que Office 365 encontró un error de conexión al intentar conectarse al servidor de mensajería de destino. Una causa común de este error es que el servidor de seguridad está bloqueando las conexiones de direcciones IP de Office 365. O bien, este error podría ser por diseño si haya terminado de migrar su local mensajería del sistema para Office 365 y apague su local en el entorno de mensajería..</span><span class="sxs-lookup"><span data-stu-id="bd249-p107">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination messaging server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises messaging system to Office 365 and shut down your on-premises messaging environment..</span></span>
  
- <span data-ttu-id="bd249-p108">Si tiene buzones de correo en su entorno local, necesita modificar la configuración del firewall para permitir conexiones desde las direcciones IP de Office 365 en el puerto TCP 25 a sus instalaciones en servidores de mensajería. Para obtener una lista de las direcciones IP de Office 365, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?linkid=228887).</span><span class="sxs-lookup"><span data-stu-id="bd249-p108">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises messaging servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=228887).</span></span>
    
- <span data-ttu-id="bd249-p109">Si no hay más mensajes deben entregarse a su entorno local, haga clic en **corregir ahora** en la alerta para que Office 365 puede rechazar inmediatamente los mensajes con destinatarios no válidos. Esto permite reducir el riesgo de superación del límite de cuota de la organización para los destinatarios no válidos, lo que podrían afectar la entrega del mensaje normal. O bien, puede usar las siguientes instrucciones para solucionar el problema de forma manual:</span><span class="sxs-lookup"><span data-stu-id="bd249-p109">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span> 
    
  - <span data-ttu-id="bd249-p110">Deshabilitar o eliminar el conector de Office 365 a su entorno local: Centro de administración de Office 365 \> **centros de administración** \> **Exchange** \> **flujo de correo** \> **conectores** \> seleccione la conector con el valor **de** **Office 365** y **para** el valor de **servidor de correo electrónico de la organización**. Eliminar el conector haciendo clic en **Eliminar**![icono de eliminación](media/ITPro-EAC-DeleteIcon.png), o deshabilitar el conector haciendo clic en **Editar**![icono Editar](media/ITPro-EAC-EditIcon.png) y desactivar **activarla**.</span><span class="sxs-lookup"><span data-stu-id="bd249-p110">Disable or delete the connector from Office 365 to your on-premises environment: Office 365 admin center \> **Admin centers** \> **Exchange** \> **Mail flow** \> **Connectors** \> select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server**. Delete the connector by clicking **Delete**![Delete icon](media/ITPro-EAC-DeleteIcon.png), or disable the connector by clicking **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png) and unchecking **Turn it on**.</span></span>
    
  - <span data-ttu-id="bd249-p111">Cambiar el dominio aceptado en Office 365 que está asociado con su local entorno de mensajería de **Retransmisión interna** en **autoritativo**. Para obtener instrucciones, vea [Administrar dominios aceptados en Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd249-p111">Change the accepted domain in Office 365 that's associated with your on-premises messaging environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span></span>
    
    <span data-ttu-id="bd249-p112">**Nota**: normalmente, estos cambios tardan entre 30 minutos y una hora para que surtan efecto. Después de una hora, compruebe que ya no recibe el error.</span><span class="sxs-lookup"><span data-stu-id="bd249-p112">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>
    
<span data-ttu-id="bd249-156">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-156">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="bd249-157">Código de error: 450 4.4.317 no se puede conectar al servidor remoto</span><span class="sxs-lookup"><span data-stu-id="bd249-157">Error code: 450 4.4.317 Cannot connect to remote server</span></span>
<span data-ttu-id="bd249-158"><a name="ErrorCode44317"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-158"></span></span>

<span data-ttu-id="bd249-p113">Normalmente, este error significa que Office 365 conectado al servidor de mensajería de destino, pero el servidor responde con un error inmediato, o no cumple los requisitos de conexión. Los detalles del error, explican el problema. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd249-p113">Typically, this error means Office 365 connected to the destination messaging server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="bd249-162">El servidor de mensajería de destino respondió con un error "Servicio no disponible", que indica que el servidor es no se puede mantener la comunicación con Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd249-162">The destination messaging server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>
    
- <span data-ttu-id="bd249-163">El conector está configurado para requerir TLS, pero el servidor de mensajería de destino no admite TLS.</span><span class="sxs-lookup"><span data-stu-id="bd249-163">The connector is configured to require TLS, but the destination messaging server doesn't support TLS.</span></span>
    
<span data-ttu-id="bd249-164">Compruebe la configuración de TLS y certificados en sus instalaciones en servidores y la configuración de TLS en el conector de mensajería.</span><span class="sxs-lookup"><span data-stu-id="bd249-164">Verify the TLS settings and certificates on your on-premises messaging servers, and the TLS settings on the connector.</span></span>
  
<span data-ttu-id="bd249-165">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-165">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="bd249-166">Código de error: 450 4.4.318 conexión se ha cerrado de manera repentina</span><span class="sxs-lookup"><span data-stu-id="bd249-166">Error code: 450 4.4.318 Connection was closed abruptly</span></span>
<span data-ttu-id="bd249-167"><a name="ErrorCode44318"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-167"></span></span>

<span data-ttu-id="bd249-p114">Normalmente, este error significa que Office 365 es tiene dificultades para comunicarse con sus instalaciones en el entorno de mensajería, por lo que se quitó la conexión. Las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="bd249-p114">Typically, this error means Office 365 is having difficulty communicating with your on-premises messaging environment, so the connection was dropped. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="bd249-170">El servidor de seguridad usa las reglas de examen de paquetes de SMTP, y dichas reglas no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd249-170">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>
    
- <span data-ttu-id="bd249-171">Su local servidor de mensajería no funciona correctamente (por ejemplo, se bloquea de servicio, se bloquea o recursos del sistema baja), que es lo que provoca que el servidor de tiempo de espera y cerrar la conexión a Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd249-171">Your on-premises messaging server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>
    
- <span data-ttu-id="bd249-p115">Hay problemas de red entre su entorno local y Office 365. Si el problema persiste, póngase en contacto con su equipo de red para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-p115">There are network issues between your on-premises environment and Office 365. If the problem persists, contact your network team to troubleshoot the issue.</span></span>
    
<span data-ttu-id="bd249-174">Averiguar qué escenario se aplica a usted y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="bd249-174">Find out which scenario applies to you, and make the necessary corrections.</span></span>
  
<span data-ttu-id="bd249-175">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-175">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="bd249-176">Código de error: error de validación de certificado 450 4.7.320</span><span class="sxs-lookup"><span data-stu-id="bd249-176">Error code: 450 4.7.320 Certificate validation failed</span></span>
<span data-ttu-id="bd249-177"><a name="ErrorCode47320"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-177"></span></span>

<span data-ttu-id="bd249-p116">Normalmente, este error significa que Office 365 encontró un error al intentar validar el certificado del servidor de mensajería de destino. Los detalles del error, explican el error. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd249-p116">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination messaging server. The error details will explain the error. For example:</span></span>
  
- <span data-ttu-id="bd249-181">Certificado caducado</span><span class="sxs-lookup"><span data-stu-id="bd249-181">Certificate expired</span></span>
    
- <span data-ttu-id="bd249-182">Error de coincidencia de asunto de certificado</span><span class="sxs-lookup"><span data-stu-id="bd249-182">Certificate subject mismatch</span></span>
    
- <span data-ttu-id="bd249-183">Certificado ya no es válido</span><span class="sxs-lookup"><span data-stu-id="bd249-183">Certificate is no longer valid</span></span>
    
<span data-ttu-id="bd249-184">Corregir el certificado o el conector para que se entregue mensajes en cola en Office 365can.</span><span class="sxs-lookup"><span data-stu-id="bd249-184">Please fix the certificate or the connector so that queued messages in Office 365can be delivered.</span></span>
  
<span data-ttu-id="bd249-185">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-185">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="other-error-codes"></a><span data-ttu-id="bd249-186">Otros códigos de error</span><span class="sxs-lookup"><span data-stu-id="bd249-186">Other error codes</span></span>
<span data-ttu-id="bd249-187"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="bd249-187"></span></span>

<span data-ttu-id="bd249-p117">Office 365 está teniendo dificultades para la entrega de mensajes su local o asociados al servidor de mensajería. Use la información de **servidor de destino** en el error para examinar el problema en su entorno, o modificar el conector si se ha producido un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="bd249-p117">Office 365 is having difficulty delivering messages to your on-premises or partner messaging server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 
  
<span data-ttu-id="bd249-190">Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="bd249-190">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  


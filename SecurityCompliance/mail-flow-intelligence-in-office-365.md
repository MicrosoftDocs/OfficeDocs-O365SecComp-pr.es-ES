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
# <a name="mail-flow-intelligence-in-office-365"></a>Inteligencia de flujo de correo en Office 365
  
Normalmente, se utiliza un conector para enrutar los mensajes desde la organización de Office 365 para sus instalaciones en el entorno de mensajería. También puede usar un conector para enrutar los mensajes de Office 365 para una organización asociada. Cuando Office 365 no puede entregar estos mensajes a través del conector, está en cola en Office 365. Office 365 seguirá intentando entrega para cada mensaje durante 48 horas. Después de 48 horas, caducará el mensaje en cola y se devolverá el mensaje al remitente original en un informe de no entrega (también conocido como un mensaje NDR o rebote).
  
Office 365 genera un error cuando no se puede entregar un mensaje mediante el uso de un conector. En este tema se describen los errores más comunes y sus soluciones. De forma colectiva, poner en cola y notificación de errores para los mensajes no entregados enviados a través de los conectores se conoce como inteligencia de flujo de correo.
  
 **Contenido**
  
- [Código de error: error en la consulta DNS 450 4.4.312](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [Código de error: 450 4.4.315 conexión agotó el tiempo de espera](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [Código de error: 450 4.4.316 ha rechazado la conexión](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [Código de error: 450 4.4.317 no se puede conectar al servidor remoto](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [Código de error: 450 4.4.318 conexión se ha cerrado de manera repentina](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [Código de error: error de validación de certificado 450 4.7.320](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a>Código de error: error en la consulta DNS 450 4.4.312
<a name="ErrorCode44312"> </a>

Normalmente, este error significa que Office 365 intentó conectarse al host inteligente que se especifica en el conector, pero la consulta DNS para buscar la dirección IP de host inteligente direcciones no se pudo. Las posibles causas de este error son:
  
- Hay un problema con DNS de su dominio que hospeda el servicio (es decir, la parte que mantiene los servidores de autorización de nombres para su dominio).
    
- Recientemente ha caducado su dominio, por lo que no se puede recuperar el registro MX.
    
- Recientemente ha cambiado el registro MX de su dominio y los servidores DNS de Office 365 todavía se previamente almacenado en caché la información de DNS para su dominio.
    
Debe trabajar con el servicio de hospedaje de DNS para corregir el problema DNS.
  
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  
## <a name="error-code-450-44315-connection-timed-out"></a>Código de error: 450 4.4.315 conexión agotó el tiempo de espera
<a name="ErrorCode44315"> </a>

Normalmente, esto significa que Office 365 no se puede conectar al servidor de mensajería de destino. Los detalles del error, explican el problema. Por ejemplo:
  
- Su local es el servidor de mensajería hacia abajo.
    
- Hay un error en la configuración del host inteligente del conector para que Office 365 está intentando para conectarse a la dirección IP incorrecta.
    
Averiguar qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha trabajado correctamente y no ha cambiado la configuración del conector, debe comprobar su local para ver si el servidor está inactivo, o si ha habido cambios en la infraestructura de red (por ejemplo, el entorno de mensajería se han cambiado proveedores de servicios de Internet, por lo que ahora tiene diferentes direcciones IP).
  
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  
## <a name="error-code-450-44316-connection-refused"></a>Código de error: 450 4.4.316 ha rechazado la conexión
<a name="ErrorCode44316"> </a>

Normalmente, este error significa que Office 365 encontró un error de conexión al intentar conectarse al servidor de mensajería de destino. Una causa común de este error es que el servidor de seguridad está bloqueando las conexiones de direcciones IP de Office 365. O bien, este error podría ser por diseño si haya terminado de migrar su local mensajería del sistema para Office 365 y apague su local en el entorno de mensajería..
  
- Si tiene buzones de correo en su entorno local, necesita modificar la configuración del firewall para permitir conexiones desde las direcciones IP de Office 365 en el puerto TCP 25 a sus instalaciones en servidores de mensajería. Para obtener una lista de las direcciones IP de Office 365, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://go.microsoft.com/fwlink/p/?linkid=228887).
    
- Si no hay más mensajes deben entregarse a su entorno local, haga clic en **corregir ahora** en la alerta para que Office 365 puede rechazar inmediatamente los mensajes con destinatarios no válidos. Esto permite reducir el riesgo de superación del límite de cuota de la organización para los destinatarios no válidos, lo que podrían afectar la entrega del mensaje normal. O bien, puede usar las siguientes instrucciones para solucionar el problema de forma manual: 
    
  - Deshabilitar o eliminar el conector de Office 365 a su entorno local: Centro de administración de Office 365 \> **centros de administración** \> **Exchange** \> **flujo de correo** \> **conectores** \> seleccione la conector con el valor **de** **Office 365** y **para** el valor de **servidor de correo electrónico de la organización**. Eliminar el conector haciendo clic en **Eliminar**![icono de eliminación](media/ITPro-EAC-DeleteIcon.png), o deshabilitar el conector haciendo clic en **Editar**![icono Editar](media/ITPro-EAC-EditIcon.png) y desactivar **activarla**.
    
  - Cambiar el dominio aceptado en Office 365 que está asociado con su local entorno de mensajería de **Retransmisión interna** en **autoritativo**. Para obtener instrucciones, vea [Administrar dominios aceptados en Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).
    
    **Nota**: normalmente, estos cambios tardan entre 30 minutos y una hora para que surtan efecto. Después de una hora, compruebe que ya no recibe el error.
    
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de error: 450 4.4.317 no se puede conectar al servidor remoto
<a name="ErrorCode44317"> </a>

Normalmente, este error significa que Office 365 conectado al servidor de mensajería de destino, pero el servidor responde con un error inmediato, o no cumple los requisitos de conexión. Los detalles del error, explican el problema. Por ejemplo:
  
- El servidor de mensajería de destino respondió con un error "Servicio no disponible", que indica que el servidor es no se puede mantener la comunicación con Office 365.
    
- El conector está configurado para requerir TLS, pero el servidor de mensajería de destino no admite TLS.
    
Compruebe la configuración de TLS y certificados en sus instalaciones en servidores y la configuración de TLS en el conector de mensajería.
  
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de error: 450 4.4.318 conexión se ha cerrado de manera repentina
<a name="ErrorCode44318"> </a>

Normalmente, este error significa que Office 365 es tiene dificultades para comunicarse con sus instalaciones en el entorno de mensajería, por lo que se quitó la conexión. Las posibles causas de este error son:
  
- El servidor de seguridad usa las reglas de examen de paquetes de SMTP, y dichas reglas no funcionan correctamente.
    
- Su local servidor de mensajería no funciona correctamente (por ejemplo, se bloquea de servicio, se bloquea o recursos del sistema baja), que es lo que provoca que el servidor de tiempo de espera y cerrar la conexión a Office 365.
    
- Hay problemas de red entre su entorno local y Office 365. Si el problema persiste, póngase en contacto con su equipo de red para solucionar el problema.
    
Averiguar qué escenario se aplica a usted y realice las correcciones necesarias.
  
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  
## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de error: error de validación de certificado 450 4.7.320
<a name="ErrorCode47320"> </a>

Normalmente, este error significa que Office 365 encontró un error al intentar validar el certificado del servidor de mensajería de destino. Los detalles del error, explican el error. Por ejemplo:
  
- Certificado caducado
    
- Error de coincidencia de asunto de certificado
    
- Certificado ya no es válido
    
Corregir el certificado o el conector para que se entregue mensajes en cola en Office 365can.
  
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  
## <a name="other-error-codes"></a>Otros códigos de error
<a name="sectionSection6"> </a>

Office 365 está teniendo dificultades para la entrega de mensajes su local o asociados al servidor de mensajería. Use la información de **servidor de destino** en el error para examinar el problema en su entorno, o modificar el conector si se ha producido un error de configuración. 
  
Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.
  


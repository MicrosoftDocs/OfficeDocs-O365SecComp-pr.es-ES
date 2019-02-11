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
# <a name="mail-flow-intelligence-in-office-365"></a>Inteligencia de flujo de correo en Office 365

Normalmente, se utiliza un conector para enrutar mensajes de correo electrónico de la organización de Office 365 a su entorno de correo electrónico local. También puede usar un conector para enrutar los mensajes de Office 365 para una organización asociada. Cuando Office 365 no puede entregar estos mensajes a través del conector, está en cola en Office 365. Office 365 seguirá intentando entrega para cada mensaje durante 48 horas. Después de 48 horas, caducará el mensaje en cola y se devolverá el mensaje al remitente original en un informe de no entrega (también conocido como un mensaje NDR o rebote).

Office 365 genera un error cuando no se puede entregar un mensaje mediante el uso de un conector. En este tema se describen los errores más comunes y sus soluciones. De forma colectiva, poner en cola y notificación de errores para los mensajes no entregados enviados a través de los conectores se conoce como _inteligencia de flujo de correo_.

## <a name="error-code-450-44312-dns-query-failed"></a>Código de error: error en la consulta DNS 450 4.4.312

Normalmente, este error significa que Office 365 intentó conectarse al host inteligente que se especifica en el conector, pero la consulta DNS para encontrar las direcciones IP del host inteligente no se pudo. Las posibles causas de este error son:

- Hay un problema con DNS de su dominio que hospeda el servicio (es decir, la parte que mantiene los servidores de autorización de nombres para su dominio).

- Recientemente ha caducado su dominio, por lo que no se puede recuperar el registro MX.

- Recientemente ha cambiado el registro MX de su dominio y los servidores DNS de Office 365 todavía se previamente almacenado en caché la información de DNS para su dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>¿Cómo soluciono el código de error 450 4.4.312?

- Trabajar con el que hospeda el servicio DNS para identificar y solucionar el problema con su dominio.

- Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), póngase en contacto con su socio para corregir el problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Código de error: 450 4.4.315 conexión agotó el tiempo de espera

Normalmente, esto significa que Office 365 no se puede conectar al servidor de correo electrónico de destino. Los detalles del error, explican el problema. Por ejemplo:

- El servidor de correo electrónico de local está inactivo.

- Hay un error en la configuración del host inteligente del conector para que Office 365 está intentando para conectarse a la dirección IP incorrecta.

### <a name="how-do-i-fix-error-code-450-44315"></a>¿Cómo soluciono el código de error 450 4.4.315?

- Averiguar qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha trabajado correctamente y no ha cambiado la configuración del conector, debe comprobar el entorno de correo electrónico local para ver si el servidor está inactivo, o si ha habido cambios en la infraestructura de red (por ejemplo, se han cambiado proveedores de servicios de internet, por lo que ahora tiene diferentes direcciones IP).

- Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), póngase en contacto con su socio para corregir el problema.

## <a name="error-code-450-44316-connection-refused"></a>Código de error: 450 4.4.316 ha rechazado la conexión

Normalmente, este error significa que Office 365 encontró un error de conexión al intentar conectarse al servidor de correo electrónico de destino. Una causa común de este error es que el servidor de seguridad está bloqueando las conexiones de direcciones IP de Office 365. O bien, este error podría ser por diseño si haya terminado de migrar su local del sistema de correo electrónico a Office 365 y apague el entorno de correo electrónico local.

### <a name="how-do-i-fix-error-code-450-44316"></a>¿Cómo soluciono el código de error 450 4.4.316?

- Si tiene buzones de correo en su entorno local, debe modificar la configuración del firewall para permitir conexiones desde las direcciones IP de Office 365 en el puerto TCP 25 a los servidores de correo electrónico local. Para obtener una lista de las direcciones IP de Office 365, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).

- Si no hay más mensajes deben entregarse a su entorno local, haga clic en **corregir ahora** en la alerta para que Office 365 puede rechazar inmediatamente los mensajes con destinatarios no válidos. Esto permite reducir el riesgo de superación del límite de cuota de la organización para los destinatarios no válidos, lo que podrían afectar la entrega del mensaje normal. O bien, puede usar las siguientes instrucciones para solucionar el problema de forma manual:

  - En el [Centro de administración de Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) en Office 365, deshabilitar o eliminar el conector que entrega el correo electrónico de Office 365 a su entorno de correo electrónico local:

    1. En el EAC, vaya a **flujo de correo** \> **conectores**.

    2. Seleccione el conector con el valor **de** **Office 365** y el valor **al** **servidor de correo electrónico de la organización** y siga uno de los siguientes pasos:

       - Eliminar el conector haciendo clic en **Eliminar** ![icono de eliminación](media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Deshabilitar el conector haciendo clic en **Editar** ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) y desactivar **activarla**.

  - Cambiar el dominio aceptado en Office 365 que está asociado con su entorno de correo electrónico local de **Retransmisión interna** en **autoritativo**. Para obtener instrucciones, vea [Administrar dominios aceptados en Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).

  **Nota**: normalmente, estos cambios tardan entre 30 minutos y una hora para que surtan efecto. Después de una hora, compruebe que ya no recibe el error.

- Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de error: 450 4.4.317 no se puede conectar al servidor remoto

Normalmente, este error significa que Office 365 conectado al servidor de correo electrónico de destino, pero el servidor responde con un error inmediato, o no cumple los requisitos de conexión. Los detalles del error, explican el problema. Por ejemplo:

- El servidor de correo electrónico de destino respondió con un error "Servicio no disponible", que indica que el servidor es no se puede mantener la comunicación con Office 365.

- El conector está configurado para requerir TLS, pero el servidor de correo electrónico de destino no admite TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>¿Cómo soluciono el código de error 450 4.4.317?

- Compruebe la configuración de TLS y certificados en los servidores de correo electrónico local y la configuración de TLS en el conector.

- Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de error: 450 4.4.318 conexión se ha cerrado de manera repentina

Normalmente, este error significa que Office 365 es tiene dificultades para comunicarse con su entorno de correo electrónico local, por lo que se quitó la conexión. Las posibles causas de este error son:

- El servidor de seguridad usa las reglas de examen de paquetes de SMTP, y dichas reglas no funcionan correctamente.

- El servidor de correo electrónico local no es trabajar correctamente (por ejemplo, se bloquea de servicio, se bloquea o recursos del sistema baja), que es lo que provoca que el servidor de tiempo de espera y cerrar la conexión a Office 365.

- Hay problemas de red entre su entorno local y Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>¿Cómo soluciono el código de error 450 4.4.318?

- Averiguar qué escenario se aplica a usted y realice las correcciones necesarias.

- Si el problema está causado por problemas de red entre su entorno local y Office 365, póngase en contacto con su equipo de red para solucionar el problema.

- Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de error: error de validación de certificado 450 4.7.320

Normalmente, este error significa que Office 365 encontró un error al intentar validar el certificado del servidor de correo electrónico de destino. Los detalles del error, explican el error. Por ejemplo:

- Certificado caducado

- Error de coincidencia de asunto de certificado

- Certificado ya no es válido

### <a name="how-do-i-fix-error-code-450-47320"></a>¿Cómo soluciono el código de error 450 4.7.320?

- Corregir el certificado o la configuración en el conector de modo que los mensajes en cola en Office 365 se puede entregar.

- Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.

## <a name="other-error-codes"></a>Otros códigos de error

Office 365 es tiene dificultades para entregar mensajes a su local o servidor de correo electrónico de socio. Use la información de **servidor de destino** en el error para examinar el problema en su entorno, o modificar el conector si se ha producido un error de configuración. 

Si el error es desde la organización de socios (por ejemplo, un 3 º parte en la nube proveedor de servicios), debe ponerse en contacto con su socio para corregir el problema.

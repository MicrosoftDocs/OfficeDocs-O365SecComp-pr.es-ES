---
title: Inteligencia de flujo de correo en Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Los administradores pueden obtener información sobre los códigos de error asociados a la entrega de mensajes con conectores en Office 365 (también conocido como inteligencia de flujo de correo).
ms.openlocfilehash: a679a3a50c2333a9f66509b69ec06ee96960bc83
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218720"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Inteligencia de flujo de correo en Office 365

Normalmente, se usa un conector para enrutar mensajes de correo electrónico de la organización de Office 365 a su entorno de correo electrónico local. También puede usar un conector para enrutar los mensajes de Office 365 a una organización asociada. Cuando Office 365 no puede entregar estos mensajes a través del conector, se ponen en cola en Office 365. Office 365 seguirá reintentando la entrega para cada mensaje durante 48 horas. TransCurridos 48 horas, el mensaje en cola expirará y el mensaje se devolverá al remitente original en un informe de no entrega (también conocido como un mensaje NDR o de devolución).

Office 365 genera un error cuando no se puede entregar un mensaje con un conector. Los errores más comunes y sus soluciones se describen en este tema. Colectivamente, los errores de cola y de notificación para los mensajes no entregados que se envían a través de conectores se conocen como _inteligencia de flujo de correo_.

## <a name="error-code-450-44312-dns-query-failed"></a>Código de error: error de consulta DNS de 450 4.4.312

Normalmente, este error significa que Office 365 ha intentado conectar con el host inteligente especificado en el conector, pero la consulta DNS para encontrar las direcciones IP del host inteligente ha generado un error. Las causas posibles de este error son:

- Hay un problema con el servicio de hospedaje de DNS de su dominio (la parte que mantiene los servidores de nombres autoritativos para su dominio).

- El dominio ha expirado recientemente, por lo que no se puede recuperar el registro MX.

- El registro MX de su dominio ha cambiado recientemente y los servidores DNS de Office 365 siguen teniendo en caché previamente la información DNS de su dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>¿Cómo soluciono el código de error 450 4.4.312?

- Trabaje con el servicio de hospedaje DNS para identificar y solucionar el problema en su dominio.

- Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Código de error: 450 4.4.315 se agotó el tiempo de espera de la conexión

Normalmente, esto significa que Office 365 no se puede conectar con el servidor de correo electrónico de destino. Los detalles del error explicarán el problema. Por ejemplo:

- El servidor de correo electrónico local no está disponible.

- Hay un error en la configuración de host inteligente del conector, por lo que Office 365 está intentando conectarse a una dirección IP incorrecta.

### <a name="how-do-i-fix-error-code-450-44315"></a>¿Cómo soluciono el código de error 450 4.4.315?

- Averigüe qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha estado funcionando correctamente y no ha cambiado la configuración del conector, debe comprobar el entorno de correo electrónico local para ver si el servidor está inactivo o si ha habido cambios en la infraestructura de red (por ejemplo, ha cambiado los proveedores de servicios de Internet, por lo que ahora tiene direcciones IP diferentes.

- Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44316-connection-refused"></a>Código de error: 450 4.4.316 conexión rechazada

Normalmente, este error significa que Office 365 encontró un error de conexión al intentar conectar con el servidor de correo electrónico de destino. Un motivo probable de este error es que el Firewall está bloqueando las conexiones de las direcciones IP 365 de Office. O bien, este error puede ser por diseño si ha migrado por completo su sistema de correo electrónico local a Office 365 y ha cerrado su entorno de correo electrónico local.

### <a name="how-do-i-fix-error-code-450-44316"></a>¿Cómo soluciono el código de error 450 4.4.316?

- Si tiene buzones de correo en su entorno local, debe modificar la configuración del firewall para permitir conexiones desde direcciones IP 365 de Office en el puerto TCP 25 a los servidores de correo electrónico locales. Para obtener una lista de las direcciones IP de Office 365, consulte [direcciones URL e intervalos de direcciones IP de office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).

- Si no se van a entregar más mensajes en su entorno local, haga clic en **corregir ahora** en la alerta para que Office 365 pueda rechazar inmediatamente los mensajes con destinatarios no válidos. Esto reducirá el riesgo de superar la cuota de su organización para los destinatarios no válidos, lo que podría afectar a la entrega de mensajes normal. O bien, puede usar las siguientes instrucciones para corregir manualmente el problema:

  - En el [centro de administración de Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) en Office 365, deshabilite o elimine el conector que entrega el correo electrónico de Office 365 a su entorno de correo electrónico local:

    1. En el EAC, vaya a **** \> **conectores**de flujo de correo.

    2. Seleccione el conector con el valor **de del** **Office 365** y el valor **para** el **servidor de correo electrónico de su organización** , y siga uno de estos pasos:

       - Eliminar el conector haciendo clic en **eliminar** ![icono quitar](media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Deshabilite el conector haciendo **** ![clic en Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) icono de edición y desactivando la **activación**.

  - Cambie el dominio aceptado en Office 365 que está asociado a su entorno de correo electrónico local de **retransmisión interna** a **autorizado**. Para obtener instrucciones, vea [administrar dominios aceptados en Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).

  **Nota**: normalmente, estos cambios tardan entre 30 minutos y una hora en surtir efecto. Después de una hora, compruebe que ya no recibe el error.

- Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de error: 450 4.4.317 no se puede conectar con el servidor remoto

Normalmente, este error significa que Office 365 está conectado al servidor de correo electrónico de destino, pero el servidor respondió con un error inmediato o no cumple los requisitos de conexión. Los detalles del error explicarán el problema. Por ejemplo:

- El servidor de correo electrónico de destino respondió con el error "servicio no disponible", lo que indica que el servidor no puede mantener la comunicación con Office 365.

- El conector está configurado para requerir TLS, pero el servidor de correo electrónico de destino no admite TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>¿Cómo soluciono el código de error 450 4.4.317?

- Compruebe la configuración de TLS y los certificados en los servidores de correo locales y la configuración de TLS en el conector.

- Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de error: 450 4.4.318 la conexión se cerró repentinamente

Normalmente, este error significa que Office 365 tiene dificultades para comunicarse con su entorno de correo electrónico local, por lo que la conexión se interrumpió. Las causas posibles de este error son:

- El Firewall usa reglas de examen de paquetes SMTP y estas reglas no funcionan correctamente.

- El servidor de correo electrónico local no funciona correctamente (por ejemplo, los bloqueos del servicio, los bloqueos o los recursos del sistema son bajos), lo que hace que el servidor agote el tiempo de espera y cierre la conexión con Office 365.

- Hay problemas de red entre su entorno local y Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>¿Cómo soluciono el código de error 450 4.4.318?

- Averigüe qué escenario se aplica a usted y realice las correcciones necesarias.

- Si el problema se debe a problemas de red entre el entorno local y Office 365, póngase en contacto con su equipo de red para solucionar el problema.

- Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de error: error de validación del certificado 450 4.7.320

Normalmente, este error significa que Office 365 encontró un error al intentar validar el certificado del servidor de correo electrónico de destino. En los detalles del error se explicará el error. Por ejemplo:

- Certificado expirado

- Discrepancia de sujeto de certificado

- El certificado ya no es válido

### <a name="how-do-i-fix-error-code-450-47320"></a>¿Cómo soluciono el código de error 450 4.7.320?

- Corrija el certificado o la configuración en el conector para que se puedan entregar los mensajes en cola en Office 365.

- Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="other-error-codes"></a>Otros códigos de error

Office 365 tiene dificultades para entregar mensajes a su servidor de correo electrónico local o asociado. Use la información del **servidor de destino** en el error para examinar el problema en su entorno o modifique el conector si hay un error de configuración. 

Si el error procede de la organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

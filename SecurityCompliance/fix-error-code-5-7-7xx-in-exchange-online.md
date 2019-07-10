---
title: Corregir problemas de entrega de correo electrónico para el código de error 5.7.7 XX en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo solucionar problemas de correo electrónico para el código de error 5.7.7 XX en Exchange Online (inquilino bloqueado del envío de correo).
ms.openlocfilehash: d55bc1f8a051a7f9932528a75aac8f1efa18911c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599336"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Corregir problemas de entrega de correo electrónico para el código de error 5.7.7 XX en Exchange Online

En este tema se describe lo que puede hacer si ve el código de estado 550 5.7.7 XX en un informe de no entrega (también conocido como NDR, mensaje de devolución, notificación de estado de entrega o DSN). Verá esta notificación automática cuando se restringe el envío de correo electrónico de su inquilino de una forma u otra. Estos códigos de error normalmente se incluyen como 705 o 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: el inquilino ha superado la restricción de umbral: lo que debe saber

Los remitentes internos podrían ver este NDR siempre que intente enviar correo si su inquilino se ha puesto en peligro. Normalmente, esto se occus cuando la mayor parte del tráfico de su inquilino se ha detectado como sospechoso y ha dado como resultado la prohibición de envío de la capacidad para el inquilino. Esto también puede ocurrir si los usuarios envían una gran cantidad de correo masivo desde Office 365. Como se indicó en la descripción del servicio, los clientes de Exchange online que necesiten enviar un correo electrónico comercial masivo válido (por ejemplo, boletines de clientes) deben usar proveedores de terceros especializados en estos servicios.

Una vez que los usuarios, en su conjunto, como un inquilino, envían una determinada cantidad de correo sospechoso a través del servicio, se puede impedir que todos los usuarios envíen correo hasta que se solucione el problema. Los usuarios recibirán un informe de no entrega (NDR) que indica lo siguiente:

- 550 5.7.705 acceso denegado, el inquilino ha superado el umbral

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: restricción de correo electrónico del dominio no registrado: lo que debe saber

Office 365 permite que los inquilinos retransmitan algunos mensajes a través de Exchange Online Protection (EOP). Un ejemplo admitido sería cuando los usuarios tienen un buzón de correo de Office 365 y alguien externo les envía correos electrónicos pero el reenvío de correo electrónico se configura de modo que vuelva al buzón externo del usuario. Esto es lo más habitual en los entornos educativos en los que los alumnos quieren aprovechar su interfaz de correo electrónico personal, pero siguen teniendo correos electrónicos relacionados con la escuela. Otro ejemplo es cuando los clientes se encuentran en un escenario híbrido y tienen servidores locales que envían correo electrónico fuera de EOP.

### <a name="problems-with-unregistered-domains"></a>Problemas con dominios no registrados

El problema se encuentra cuando los servidores locales se ven comprometidos y retransmiten un gran volumen de correo no deseado de EOP. En casi todos los casos, los conectores correctos se configuran, pero el correo electrónico se envía desde dominios no registrados, también conocidos como no aprovisionados. Office 365 permite que una cantidad razonable de correo proceda de dominios no registrados, pero debe configurarse un dominio aceptado en el centro de administración para cada dominio en el que tenga previsto enviar un.

Una vez comprometida, se impedirá que los inquilinos envíen correo saliente para los dominios no registrados. Los usuarios recibirán un informe de no entrega (NDR) que indica lo siguiente:

- 550 5.7.750 servicio no disponible. El cliente bloqueó el envío de dominios no registrados

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>Cómo desbloquear el inquilino para enviar de nuevo

Hay varias cosas que debe hacer si el inquilino se bloquea para enviar correo electrónico:

1. Asegúrese de registrar todos los dominios en el centro de administración de Microsoft 365. Puede encontrar más información [aquí](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Busque conectores inusuales. A menudo, los actores malintencionados crean conectores entrantes nuevos en el inquilino de Office 365 para enviar correo no deseado. Puede encontrar más información sobre cómo comprobar los conectores [](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloquee los servidores locales y asegúrese de que no están comprometidos.

> [!TIP]
> Hay muchos factores implicados aquí, especialmente si se trata de servidores de terceros. Por lo tanto, tendrá que confirmar que todo el correo que sale de los servidores es legítimo.

4. Una vez hecho, deberá llamar al soporte técnico de Microsoft y pedirle que desbloquee el espacio empresarial para enviar de nuevo desde dominios no registrados.  Proporcionarle el código de error es útil, pero tendrá que probar que su entorno está protegido y que el correo no deseado no se enviará de nuevo. Puede encontrar más información sobre cómo abrir un caso de soporte [aquí](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Más información

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Informes de no entrega de correo electrónico en Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurar el reenvío de correo electrónico para un buzón de correo](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Cómo configurar una aplicación o dispositivo multifunción para enviar correos electrónicos mediante Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

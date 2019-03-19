---
title: Correo electrónico de dominio no registrado
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Si envía un gran volumen de correo electrónico de dominio no registrado, corre el riesgo de que se bloquee el correo electrónico. Lea este artículo para obtener más información.
ms.openlocfilehash: 21c403c8072902565f63048782b06c531cdbceb0
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670545"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>Correo electrónico de dominio no registrado: lo que debe saber

Office 365 permite que los inquilinos retransmitan algunos mensajes a través de Exchange Online Protection (EOP). Un ejemplo admitido sería cuando los usuarios tienen un buzón de correo de Office 365 y alguien externo les envía correos electrónicos pero el reenvío de correo electrónico se configura de modo que vuelva al buzón externo del usuario. Esto es lo más habitual en los entornos educativos en los que los alumnos quieren aprovechar su interfaz de correo electrónico personal, pero siguen teniendo correos electrónicos relacionados con la escuela. Otro ejemplo es cuando los clientes se encuentran en un escenario híbrido y tienen servidores locales que envían correo electrónico fuera de EOP.

## <a name="problems-with-unregistered-domains"></a>Problemas con dominios no registrados

El problema se encuentra cuando los servidores locales se ven comprometidos y retransmiten un gran volumen de correo no deseado de EOP. En casi todos los casos, los conectores correctos se configuran, pero el correo electrónico se envía desde dominios no registrados, también conocidos como no aprovisionados. Office 365 permite que una cantidad razonable de correo proceda de dominios no registrados, pero debe configurarse un dominio aceptado en el centro de administración para cada dominio en el que tenga previsto enviar un.

Una vez comprometida, se impedirá que los inquilinos envíen correo saliente para los dominios no registrados. Los usuarios recibirán un informe de no entrega (NDR) que indica lo siguiente:

- 550 5.7.750 servicio no disponible. El cliente bloqueó el envío de dominios no registrados

## <a name="unblocking-tenant-in-order-to-send-again"></a>Desbloqueo de inquilino para enviar de nuevo

Hay varias cosas que debe hacer si se bloquea para enviar desde dominios no registrados:

1. Asegúrese de registrar todos los dominios en el centro de administración de Microsoft 365. Puede encontrar más información [aquí](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Busque conectores inusuales. A menudo, los actores malintencionados crean conectores entrantes nuevos en el inquilino de Office 365 para enviar correo no deseado. Puede encontrar más información sobre cómo comprobar los conectores [](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloquee los servidores locales y asegúrese de que no están comprometidos.

> [!TIP]
> Hay muchos factores implicados aquí, especialmente si se trata de servidores de terceros. Por lo tanto, tendrá que confirmar que todo el correo que sale de los servidores es legítimo.

4. Una vez hecho, deberá llamar al soporte técnico de Microsoft y pedirle que desbloquee el espacio empresarial para enviar de nuevo desde dominios no registrados.  Proporcionarle el código de error es útil, pero tendrá que probar que su entorno está protegido y que el correo no deseado no se enviará de nuevo. Puede encontrar más información sobre cómo abrir un caso de soporte [aquí](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Para obtener más información

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Informes de no entrega de correo electrónico en Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurar el reenvío de correo electrónico para un buzón de correo](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Cómo configurar una aplicación o dispositivo multifunción para enviar correos electrónicos mediante Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

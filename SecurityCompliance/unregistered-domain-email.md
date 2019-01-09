---
title: Correo electrónico de dominio no registradas
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Si envía un gran volumen de correo electrónico de dominio no registradas, corre el riesgo de su correo electrónico se bloquean. Lea este artículo para obtener más información.
ms.openlocfilehash: f632c5f7ab94a200a364828408b13c0026335869
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769793"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>Correo electrónico de dominio no registrada: ¿Qué necesita saber

Office 365 permite los inquilinos para que transmita algunos mensajes a través de Exchange Online Protection (EOP). Un ejemplo compatible de esto sería cuando los usuarios tienen un buzón de Office 365 y alguien externo envía correo electrónico pero reenvío de correo electrónico está configurado para que vuelve para el buzón del usuario externo. Esto es más comunes en entornos de educación donde los alumnos desean sacar provecho de su interfaz de correo electrónico personal, aunque siguen teniendo correos electrónicos relacionados a la escuela. Otro ejemplo es cuando los clientes se encuentran en un escenario híbrido y tienen los servidores locales que envían correo electrónico fuera de la elevación de privilegios.

## <a name="problems-with-unregistered-domains"></a>Problemas con los dominios no registradas

El problema es cuando los servidores locales obtengan en riesgo y terminen la retransmisión de un gran volumen de correo no deseado fuera de la elevación de privilegios. En casi todos los casos, se configuran los conectores derecho pero se está enviando correo electrónico de dominios no registradas, también conocido como no aprovisionadas. Office 365 permitir una cantidad razonable de correo a proceden de dominios no registradas, pero debe configurarse un dominio aceptado en el centro de administración para cada dominio que planea enviar fuera de.

Una vez que se ve comprometida, los inquilinos no podrán enviar correo saliente para dominios no registradas. Los usuarios recibirán un informe de no entrega (NDR) que indica:

- 550 5.7.750 servicio no disponible. Cliente bloqueado el envío de dominios no registradas

## <a name="unblocking-tenant-in-order-to-send-again"></a>Desbloqueo inquilino con el fin de volver a enviar

Hay varias cosas que debe hacer en el caso de que se obtenga bloqueado para el envío de dominios no registradas:

1. Asegúrese de registrar todos los dominios en el centro de administración de Office 365. Puede encontrar más información [aquí](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Busque los conectores poco habituales. Actores malintencionados a menudo va a crear los conectores de entrada nueva en el inquilino de Office 365 para que envíen correo no deseado. Puede encontrar más información sobre la comprobación de los conectores [aquí](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloquear los servidores locales y asegúrese de que no se comprometido.

> [!TIP]
> Hay muchos factores implicados aquí, especialmente si se trata de los servidores de aplicaciones de terceros. No obstante, debe ser capaz de confirmar que todo el correo dejando los servidores son legítimos.

4. Una vez hecho, debe llamar a Microsoft Support y preguntar obtener al inquilino desbloqueado para enviar de nuevo de dominios no registradas.  Proporcionar el código de error es útil, pero necesita demostrar que el entorno está protegido y que spam no se enviarán nuevo. Puede encontrar más información acerca de cómo abrir un caso de soporte [aquí](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Más información

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Informes de no entrega de correo electrónico en Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurar el reenvío de correo electrónico para un buzón de correo](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Cómo configurar una aplicación o dispositivo multifunción para enviar correos electrónicos mediante Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Administrar dominios aceptados en Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

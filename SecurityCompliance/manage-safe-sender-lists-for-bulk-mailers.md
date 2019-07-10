---
title: Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente. El servicio respeta los remitentes y los dominios seguros al inspeccionar la dirección RFC 5321.MailFrom y la dirección RFC 5322.From, mientras que Outlook agrega la dirección RFC 5322.From a la lista de remitentes seguros de un usuario. (Nota: El servicio inspecciona tanto la dirección 5321.MailFrom como la dirección 5322.From en busca de remitentes y dominios bloqueados).'
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598796"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico

Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente. El servicio de Office 365 respeta a los remitentes y dominios seguros mediante la inspección de la dirección RFC 5321. MailFrom y la dirección RFC 5322. from, mientras que Outlook agrega la 5322 de RFC. from a la lista de remitentes seguros de un usuario. (Nota: El servicio inspecciona tanto la dirección 5321.MailFrom como la dirección 5322.From en busca de remitentes y dominios bloqueados).
  
La dirección CORREO SMTP DE, también conocida como dirección RFC 5321.MailFrom, es la dirección de correo electrónico que se usa para realizar comprobaciones de SPF, y si el correo no se puede entregar, se proporciona la ruta de acceso a la que se rechaza el mensaje. Se trata de la dirección de correo electrónico que se coloca en Return-Path en los encabezados de mensaje de forma predeterminada, aunque es posible que el remitente designe una dirección de Return-Path diferente.
  
La dirección De: en los encabezados de los mensajes, también conocida como la dirección RFC 5322.From, es la dirección de correo electrónico que se muestra en el cliente de correo como Outlook.
  
La mayoría de las veces las direcciones 5321.MailFrom y 5322.From son las mismas. Esto es típico para la comunicación de persona a persona. No obstante, cuando el correo electrónico se envía en nombre de otra persona, las direcciones son frecuentemente diferentes. Esto generalmente ocurre con mucha frecuencia en mensajes de correo masivos.
  
Por ejemplo, supongamos que la aerolínea Blue Yonder Airlines ha contratado a Margie's Travel para que distribuya su publicidad mediante correo electrónico. Luego, obtiene un mensaje en su bandeja de entrada del remitente blueyonder@news.blueyonderairlines.com. En este caso, la dirección 5321. MailFrom es blueyonder.airlines@margiestravel.com y blueyonder@news.blueyonderairlines.com es la dirección 5322. from que es la que se ve en Outlook. Debido a que el servicio respeta la dirección de RFC 5322. from, para evitar que se filtre este mensaje, puede Agregar la dirección RFC 5322. from como remitente seguro en Outlook (como un usuario) o, si es un administrador, configurar una regla de flujo de correo, tal como se muestra en el [anti-spam Sección protección](anti-spam-protection.md) .
  


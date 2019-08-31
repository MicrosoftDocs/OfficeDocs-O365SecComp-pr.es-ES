---
title: ¿Qué es EOP?
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Este documento introductorio le ayudará a comprender Exchange Online Protection (EOP) y una terminología importante. Esto es aplicable a los clientes de Office 365 que protegen buzones de correo hospedados en la nube de Exchange Online y a clientes independientes de EOP que protegen buzones locales como Exchange Server 2016.
ms.openlocfilehash: c2dba2cbb16126e2169e0fb3907ceabe8185e82a
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699198"
---
## <a name="what-is-exchange-online-protection-eop"></a>¿Qué es Exchange Online Protection (EOP)?

Exchange Online Protection (EOP) es un servicio de filtrado de correo electrónico basado en la nube que ayuda a proteger la organización contra el correo no deseado y el malware. Si tiene buzones de correo en Office 365, estos se protegen automáticamente mediante EOP, ya que forma parte del servicio. Esto incluye a las organizaciones que tienen buzones de correo en Office 365 y local, lo que se conoce comúnmente como escenario híbrido. EOP independiente también está disponible para los clientes que no tienen buzones de correo en la nube pero que quieren proteger sus buzones locales.

EOP intenta filtrar el correo no deseado y mantener la bandeja de entrada sin contenido que los usuarios no desean ver. Normalmente, el correo no deseado se entrega a la carpeta de correo no deseado. Algunos usuarios desean comprobar que el filtrado está haciendo lo que desea, por lo que la carpeta de correo no deseado es una forma fácil de que los usuarios comprueben su propio contenido.  

> [!TIP]
> Lo más importante es que el correo electrónico no deseado o el correo no deseado se envíen automáticamente a la carpeta correo electrónico no deseado. El servicio hará lo necesario en función de cuál es el estado de configuración predeterminada o personalizada del administrador. Es decir, los usuarios no deben preocuparse por ver un gran número de mensajes de correo no deseado en la carpeta correo electrónico no deseado. Si los administradores prefieren mover todo el correo no deseado fuera de la vista, la cuarentena debe estar configurada. Para obtener más información, consulte el artículo [cuarentena de mensajes de correo electrónico en Office 365](../quarantine-email-messages.md) .

## <a name="important-terms"></a>Términos importantes

**Entrante**: mensajes que entran en Office 365.

**Saliente**: mensajes que salen de la oficina 365.

**Internos**: mensajes de alguien dentro de la organización a alguien dentro de la organización. Esto incluye a los clientes que están en escenarios híbridos y un buzón de correo puede ser local y el otro buzón de correo está en la nube.

**Falso negativo (FN)**: correo no deseado y otro correo no deseado que se envía de forma incorrecta a la bandeja de entrada.

**Falso positivo (FP)**: mensajes legítimos que se marcan de forma incorrecta como correo no deseado y se colocan en la carpeta de correo no deseado o en cuarentena.

**Correo no deseado, también conocido como correo electrónico no solicitado**: se trata de publicidad comercial, cartas en cadena, correos políticos, etc. Este es el correo electrónico en el que los usuarios no se suscriben a y desde los remitentes de correo no deseado que intentan solicitar productos o intentar confirmar su fraude.

**Phish**: la suplantación de identidad (phishing) es un tipo especial de correo no deseado destinado a engañarle para que proporcione información personal con el propósito de confirmar el robo de identidad o el fraude. Este tipo de mensaje suele contener un vínculo o datos adjuntos malintencionados, pero no siempre.

Suplantación de **identidad**: la suplantación de identidades es cuando los remitentes de correo no deseado falsifican el encabezado para que los mensajes parecen haber sido originados por alguien o en algún lugar distinto del origen real. Esto puede ser correo no deseado, pero se usa con más frecuencia para phish a los usuarios.

**** Suplantación: este tipo de correo no deseado también es una forma de falsificar la dirección del remitente, pero se realiza modificando parte del nombre o del dominio para que tenga un aspecto similar al origen real. Por ejemplo, Bi11@micr0s0ft.com, donde "l" era realmente el número once y la "o" en Microsoft se reemplazó por el número cero.

En **masa**: normalmente, los usuarios solicitan correo masivo, aunque a veces las empresas venden información a otras compañías. Es habitual que los usuarios se suscriban intencionadamente para correo masivo (es decir, newletters), pero olvídese más adelante y piense que es correo no deseado. El correo masivo se convierte en correo no deseado cuando los remitentes masivos de correo envían más de un registro y los niveles de queja se hacen demasiado altos.

---
title: Cómo se combinan las directivas y las protecciones cuando el correo está marcado con color rojo
description: Qué directivas se aplican y qué acciones realizar, cuando el correo electrónico está marcado como malware, correo no deseado, correo no deseado de alta confianza, phishing y masivo por EOP o ATP.
keywords: seguridad, malware, Microsoft 365, M365, Security Center, ATP, Windows Defender ATP, Office 365 ATP, ATP de Azure
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7aa0f89eed379273cb069cd65c083749a9552e91
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30926477"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>Qué Directiva se aplica cuando se ejecutan varios métodos de protección y exámenes de detección en el correo electrónico

Potencialmente, puede que el correo entrante esté marcado por varias formas de protección (por ejemplo, EOP *y* ATP) y varios exámenes de detección (como correo no deseado *y* suplantación de identidad). Esto es posible porque hay directivas antiphishing contra ATP para los clientes de ATP y las directivas antiphishing de EOP para los clientes de EOP. Esto también significa que el mensaje puede navegar por varios exámenes de detección de malware, suplantación de identidad (phishing) y usuario-suplantación, por ejemplo. Teniendo en cuentan toda esta actividad, puede que haya cierta confusión con respecto a qué directiva se aplica.

En general, la Directiva aplicada a un mensaje se identifica en el encabezado **X-Forefront-antispam-Report** en la propiedad **CAT (categoría)** . Si tiene varias directivas antiphishing, se aplicará la que tenga la prioridad más alta.

Las directivas siguientes se aplican a _todas las organizaciones_.

|Priority |Directiva  |Categoría  |Donde se administra |
|---------|---------|---------|---------|
|1     | Malware      | MALW      | Directiva de malware   |
|segundo     | Phishing     | PHSH     | Configurar las directivas de filtro de correo no deseado     |
|3     | Correo no deseado de alta confianza      | HSPM        | Configurar las directivas de filtro de correo no deseado        |
|4     | Suplantación        | SPOOF        | Directiva contra la suplantación de identidad, inteligencia de suplantación        |
|2,5     | Correo no deseado         | SPM         | Configurar las directivas de filtro de correo no deseado         |
|6,5     | Masivo         | BULK        | Configurar las directivas de filtro de correo no deseado         |

Además, estas directivas se aplican a _organizaciones con ATP_.

|Priority |Directiva  |Categoría  |Donde se administra |
|---------|---------|---------|---------|
|0,7     | Suplantación de dominio         | DIMP         | Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365        |
|8,5     | Suplantación de usuario        | UIMP         | Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365         |

Por ejemplo, si tiene dos directivas:

|Directiva  |Priority  |Suplantación de usuario/dominio  |Directiva contra la suplantación  |
|---------|---------|---------|---------|
|A     | 1        | Activada        |Desactivada         |
|B     | segundo        | Desactivada        | Activada        |

Si un mensaje se identifica como suplantación de _usuario_ e _imitación_ (consulte anti-spoofing en la tabla anterior) y el mismo conjunto de usuarios en el ámbito de la Directiva a es el ámbito de la Directiva B, el mensaje se marca y se trata como _falso_, pero no se aplica la acción porque la suplantación de identidad está desactivada y la suplantación de **identidad se ejecuta con una prioridad superior (4) que la suplantación del usuario (8)**.

Para que se apliquen otros tipos de directivas de suplantación de identidad, tendrá que ajustar la configuración de la persona a la que se aplican las distintas directivas.



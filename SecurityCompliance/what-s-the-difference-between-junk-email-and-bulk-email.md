---
title: ¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
description: ¿Los clientes a veces askwhat de la diferencia entre correo electrónico no deseado y mensajes de correo electrónico masivo? El propósito de este tema es para explicar la diferencia y para proporcionar información sobre las diferentes opciones que están disponibles para ambos tipos en Exchange Online y Exchange Online Protection (EOP).
ms.openlocfilehash: 2cd9d9d91cf44af910983c045192ed7639d27417
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026247"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?

En ocasiones los clientes preguntan "cuál es la diferencia entre los mensajes de correo electrónico no deseado y los de correo electrónico masivo"? El objetivo de este tema es explicar la diferencia y proporcionar información sobre las diferentes opciones que están disponibles para ambos en Exchange Online y Exchange Online Protection (EOP).
  
 **¿Qué es el correo electrónico no deseado?**
  
Los mensajes de correo electrónico no deseado son mensajes de correo electrónico no solicitados (y normalmente no deseados) que el servicio filtra. De manera predeterminada, el servicio rechaza el mensaje de correo no deseado con base en la reputación de la dirección IP del remitente. Sin embargo, si pasa una inspección de IP pero los filtros de contenido lo clasifican como correo no deseado, el mensaje se envía a la carpeta Correo electrónico no deseado de los destinatarios especificados. 
  
> [!NOTE]
> La acción realizada en los mensajes filtrados por contenido es configurable a través de las directivas de filtro de contenido en el centro de administración de Exchange (EAC), tal como se describe en [configurar sus directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Además, si no está de acuerdo con la clasificación de spam, puede informar los mensajes que se consideran correo no deseado o que no sean de correo no deseado a Microsoft de varias maneras, como se describe en el [envío de correo no deseado, que no sean de correo no deseado y mensajes de estafas de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **¿Qué es el correo electrónico masivo?**
  
El correo electrónico masivo, también conocido como correo gris, es un tipo de mensaje de correo electrónico que es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo masivo suele estar formado por un anuncio o mensaje de marketing que probablemente no se envíe repetidamente. El correo masivo es deseado para algunos usuarios y, de hecho, es posible que ellos se hayan suscrito deliberadamente para recibir dichos mensajes, mientras que otros usuarios pueden considerar estos tipos de mensajes como correo no deseado. Por ejemplo, algunos usuarios desean recibir mensajes de anuncios de Contoso Corporation o invitaciones para una próxima conferencia sobre seguridad cibernética, mientras que otros usuarios consideran dichos mensajes como correo no deseado.
  
## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

La administración del correo electrónico masivo no es una decisión clara, porque si todo el correo masivo se clasifica como correo no deseado, los usuarios que lo desean se pueden quejar y enviarlo como mensajes falsos positivos (correo deseado) que se marcaron incorrectamente como correo no deseado. Por otro lado, si se admite todo el correo masivo, los usuarios que no lo desean se pueden quejar y enviarlo como mensajes de correo no deseado no detectados (falsos negativos) que llegaron incorrectamente a su bandeja de entrada.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Habilitar el control de sensibilidad de correo masivo en la directiva de filtro de contenido

Según la directiva de su empresa sobre mensajes de correo electrónico masivo, los administradores pueden seleccionar el umbral que se asignará al correo electrónico masivo. El valor se puede configurar mediante directivas de filtro de contenido en el EAC. Consulte [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) para ver los pasos. Puede elegir una valor de umbral de 1 a 9, donde 1 marca la mayor parte del correo electrónico masivo como correo no deseado y 9 permite entregar la mayoría del correo electrónico masivo. A continuación, el servicio realiza la acción configurada, por ejemplo, enviar el mensaje a la carpeta Correo electrónico no deseado del destinatario. 
  


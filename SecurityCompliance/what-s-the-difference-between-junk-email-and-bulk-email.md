---
title: ¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: A veces, los clientes askwhatn la diferencia entre los mensajes de correo electrónico no deseado y masivo. El objetivo de este tema es explicar la diferencia y proporcionar información sobre las diferentes opciones que están disponibles para Exchange Online y Exchange Online Protection (EOP).
ms.openlocfilehash: 877912c94af5d4b399769759189d091c62d50075
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275720"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?

En ocasiones los clientes preguntan "cuál es la diferencia entre los mensajes de correo electrónico no deseado y los de correo electrónico masivo"? El objetivo de este tema es explicar la diferencia y proporcionar información sobre las diferentes opciones que están disponibles para ambos en Exchange Online y Exchange Online Protection (EOP).
  
 **¿Qué es el correo electrónico no deseado?**
  
Los mensajes de correo electrónico no deseado son mensajes de correo electrónico no solicitados (y normalmente no deseados) que el servicio filtra. De manera predeterminada, el servicio rechaza el mensaje de correo no deseado con base en la reputación de la dirección IP del remitente. Sin embargo, si pasa una inspección de IP pero los filtros de contenido lo clasifican como correo no deseado, el mensaje se envía a la carpeta Correo electrónico no deseado de los destinatarios especificados. 
  
> [!NOTE]
> La acción realizada en los mensajes filtrados por contenido se puede configurar mediante directivas de filtro de contenido en el centro de administración de Exchange (EAC), tal como se describe en [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Además, si no está de acuerdo con la clasificación de correo no deseado, puede informar de los mensajes que considera que son correo no deseado o que no son correo no deseado de Microsoft de varias maneras, como se describe en [enviar mensajes de correo no deseado, no correo no deseado y estafas de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **¿Qué es el correo electrónico masivo?**
  
El correo electrónico masivo, también conocido como correo gris, es un tipo de mensaje de correo electrónico que es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo masivo suele estar formado por un anuncio o mensaje de marketing que probablemente no se envíe repetidamente. El correo masivo es deseado para algunos usuarios y, de hecho, es posible que ellos se hayan suscrito deliberadamente para recibir dichos mensajes, mientras que otros usuarios pueden considerar estos tipos de mensajes como correo no deseado. Por ejemplo, algunos usuarios desean recibir mensajes de anuncios de Contoso Corporation o invitaciones para una próxima conferencia sobre seguridad cibernética, mientras que otros usuarios consideran dichos mensajes como correo no deseado.
  
## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

La administración del correo electrónico masivo no es una decisión clara, porque si todo el correo masivo se clasifica como correo no deseado, los usuarios que lo desean se pueden quejar y enviarlo como mensajes falsos positivos (correo deseado) que se marcaron incorrectamente como correo no deseado. Por otro lado, si se admite todo el correo masivo, los usuarios que no lo desean se pueden quejar y enviarlo como mensajes de correo no deseado no detectados (falsos negativos) que llegaron incorrectamente a su bandeja de entrada.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Habilitar el control de sensibilidad de correo masivo en la directiva de filtro de contenido

Según la Directiva de la compañía en mensajes de correo electrónico en masa, los administradores pueden seleccionar un umbral para asignar el correo electrónico masivo. La configuración se puede configurar mediante directivas de filtro de contenido en el EAC. Consulte [configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md) para los pasos. Puede elegir un valor de umbral de 1-9, donde 1 marca la mayor parte del correo electrónico masivo como correo no deseado y 9 permite que se entregue la mayor parte del correo electrónico masivo. A continuación, el servicio realiza la acción configurada, como enviar el mensaje a la carpeta de correo no deseado del destinatario. 
  


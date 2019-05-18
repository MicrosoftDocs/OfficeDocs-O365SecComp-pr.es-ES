---
title: Valores de nivel de queja de correo masivo
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los troyanos de envío masivo de correo electrónico varían en sus patrones de envío, la creación de contenido y las prácticas de adquisición de listas. Algunos son buenos troyanos de envío de correo electrónico que envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Para distinguir estos tipos de troyanos de envío masivo de correo, se asigna una clasificación de nivel de queja de correo masivo (BCL) a los troyanos de envío masivo de correo electrónico. Las clasificaciones de BCL oscilan entre 1 y 9, según la probabilidad con la que el troyano de envío masivo de correo electrónico generará quejas. Es probable que un remitente que tiene una clasificación 9 de BCL genere muchas quejas por parte de los destinatarios, mientras que es poco probable que una clasificación 3 de BCL genere muchas quejas. Microsoft usa fuentes internas y de terceros para identificar el correo masivo y determinar el BCL adecuado. Esta clasificación se expone en el encabezado X-Microsoft-Antispam de cada mensaje. Para obtener más información acerca de este encabezado de mensaje, consulte anti-spam Message headers.
ms.openlocfilehash: 490823f045e2e3fcf6b537d9717ab12abc323da6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152135"
---
# <a name="bulk-complaint-level-values"></a>Valores de nivel de queja de correo masivo

Los troyanos de envío masivo de correo electrónico varían en sus patrones de envío, la creación de contenido y las prácticas de adquisición de listas. Algunos son buenos troyanos de envío de correo electrónico que envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Para distinguir estos tipos de troyanos de envío masivo de correo, se asigna una clasificación de nivel de queja de correo masivo (BCL) a los troyanos de envío masivo de correo electrónico. Las clasificaciones de BCL oscilan entre 1 y 9, según la probabilidad con la que el troyano de envío masivo de correo electrónico generará quejas. Es probable que un remitente que tiene una clasificación 9 de BCL genere muchas quejas por parte de los destinatarios, mientras que es poco probable que una clasificación 3 de BCL genere muchas quejas. Microsoft usa fuentes internas y de terceros para identificar el correo masivo y determinar el BCL adecuado. Esta clasificación se expone en el encabezado **X-Microsoft-Antispam** de cada mensaje. Para obtener más información sobre este encabezado de mensaje, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md). 
  
Para usar los valores de BCL a fin de establecer el nivel deseado de filtrado de correo masivo que requiere su organización, siga estos pasos en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
Se están agregando más valores de BCL y se incluirán aquí en el futuro. En la tabla siguiente se enumeran y describen los valores de BCL que están actualmente en uso.
  
|||
|:-----|:-----|
|**Valor de BCL** <br/> |**Descripción** <br/> |
|comprendi  <br/> |El mensaje no es de un remitente de correo masivo.  <br/> |
|1, 2, 3  <br/> |El mensaje proviene de un remitente de correo masivo que genera pocas quejas.  <br/> |
|4, 5, 6, 7  <br/> |El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.  <br/> |
|8, 9  <br/> |El mensaje proviene de un remitente de correo masivo que genera un número elevado de quejas.  <br/> |
   


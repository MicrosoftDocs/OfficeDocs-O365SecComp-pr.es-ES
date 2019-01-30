---
title: Subprocesos de correo electrónico
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2340128f508a3be389afce86596f7e6395a0bb7e
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608379"
---
# <a name="email-threading"></a>Subprocesos de correo electrónico
Considere la posibilidad de una conversación de correo electrónico que ha ocurrido durante un tiempo. En la mayoría de los casos, el último correo electrónico en el subproceso incluirá el contenido de todos los correos anteriores; revisar el último correo electrónico le proporcionará un contexto completo de la conversación que se realizaron en el subproceso. Correo electrónico threading identifica como mensajes de correo electrónico para que los revisores pueden revisar una fracción de documentos recopilados sin perder cualquier contexto.

## <a name="what-does-email-threading-do"></a>¿Qué hace threading de correo electrónico?
Correo electrónico threading analiza cada correo electrónico y desconstructs para los mensajes individuales; cada correo electrónico es una cadena de mensajes individuales. A continuación, analiza todos los mensajes de correo electrónico en el conjunto de trabajo para determinar si un correo electrónico tiene contenido único o si la cadena de contenidas completo en un correo electrónico diferente. Al final, los correos electrónicos se dividen en cuatro categorías:
- Inclusives: el último mensaje en el correo electrónico tiene contenido único, y el correo electrónico tiene todos los datos adjuntos que se incluyeron en otros mensajes de correo electrónico de que el contenido está contenido completo de este correo electrónico.
- Inclusive menos: el último mensaje en el correo electrónico tiene contenido único, pero el correo electrónico no contienen algunos de los datos adjuntos que se incluyeron en otros mensajes de correo electrónico de que el contenido está contenido completo de este correo electrónico.
- Copia inclusive: una copia exacta de un inclusive/inclusive menos correo electrónico
- Ninguno: El contenido de este correo electrónico contenido completo en al menos un correo electrónico que se marca como menos inclusive inclusive.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>¿Cómo es diferente de las conversaciones en Outlook?
Un vistazo, esto suena muy similar a las agrupaciones de conversación en Outlook. Sin embargo, existen algunas diferencias importantes. Considere la posibilidad de una conversación de correo electrónico que obtuvo bifurcada en dos conversación; Por ejemplo, alguien ha respondido a un correo electrónico que no es la más reciente en la conversación, por lo que los dos últimos mensajes de correo electrónico en la conversación ambos tienen contenido único.

Outlook aún podría agrupar los mensajes de correo electrónico en una conversación único; leer el último correo electrónico significaría que falta el contexto del correo electrónico del segundo a último, que también contiene contenido único. Debido a que el correo electrónico threading analiza cada correo electrónico en los componentes individuales y los compara, correo electrónico threading sería marcar ambos de los dos últimos correos electrónicos de como inclusives, asegurarse de que no se pierda cualquier contexto como leer todos los mensajes de correo electrónico marcados como inclusivas.
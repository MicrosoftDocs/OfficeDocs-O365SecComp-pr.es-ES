---
title: Subprocesos de correo electrónico
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a3c4f940c34a9c51bf58107d10e04d0ed60f28a8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213430"
---
# <a name="email-threading"></a>Subprocesos de correo electrónico

Considere una conversación de correo electrónico que ha estado ocurriendo durante un rato. En la mayoría de los casos, el último correo electrónico del hilo incluirá el contenido de todos los mensajes de correo electrónico anteriores; la revisión del último correo electrónico proporcionará un contexto completo de la conversación que se produjo en el hilo. El encadenamiento de correo electrónico identifica dichos mensajes para que los revisores puedan revisar una fracción de los documentos recopilados sin perder ningún contexto.

## <a name="what-does-email-threading-do"></a>¿Qué hace la función de subprocesos de correo electrónico?

La creación de subprocesos de correo electrónico analiza cada correo electrónico y lo construye en mensajes individuales; cada correo electrónico es una cadena de mensajes individuales. A continuación, analiza todos los correos electrónicos en el conjunto de trabajo para determinar si un correo electrónico tiene contenido único o si la cadena está contenida por completo en un correo electrónico diferente. En los mensajes de correo electrónico finales se dividen en cuatro categorías:

- **Ambos inclusive**: el último mensaje del correo electrónico tiene contenido único y el correo electrónico tiene todos los datos adjuntos que se incluyeron en otros mensajes de correo electrónico cuyo contenido está incluido por completo en este correo.


- **Menos inclusivo**: el último mensaje del correo electrónico tiene contenido único, pero el correo electrónico no contiene algunos de los datos adjuntos que se incluyeron en otros mensajes de correo electrónico cuyo contenido está contenido por completo en este correo electrónico.

- **Copia inclusiva**: copia exacta de un correo electrónico menos inclusivo inclusive

- **Ninguno**: el contenido de este correo electrónico está contenido por completo en al menos un mensaje de correo electrónico que está marcado como incluido/incluido en el signo menos.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>¿En qué se diferencia de las conversaciones en Outlook?
De un solo vistazo, esto suena muy parecido a las agrupaciones de conversaciones en Outlook. Sin embargo, hay algunas distinciones importantes. Considere una conversación de correo electrónico que se ha bifurcado en dos conversaciones; por ejemplo, alguien respondió a un correo electrónico que no es el más reciente en la conversación, por lo que los dos últimos correos electrónicos de la conversación tienen contenido único.

Outlook seguiría agrupando los correos electrónicos en una sola conversación; leer solo el último correo electrónico significa que falta el contexto del segundo al último correo electrónico, que también incluye contenido único. Como el subprocesamiento de correo electrónico analiza cada correo electrónico en componentes individuales y los compara, el subprocesamiento de correo electrónico marcaría los dos últimos correos electrónicos como incluidos, lo que garantiza que no perderá ningún contexto mientras haya leído todos los correos electrónicos marcados como incluidos.
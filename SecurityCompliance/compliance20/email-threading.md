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
# <a name="email-threading"></a><span data-ttu-id="ca836-102">Subprocesos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ca836-102">Email threading</span></span>
<span data-ttu-id="ca836-p101">Considere la posibilidad de una conversación de correo electrónico que ha ocurrido durante un tiempo. En la mayoría de los casos, el último correo electrónico en el subproceso incluirá el contenido de todos los correos anteriores; revisar el último correo electrónico le proporcionará un contexto completo de la conversación que se realizaron en el subproceso. Correo electrónico threading identifica como mensajes de correo electrónico para que los revisores pueden revisar una fracción de documentos recopilados sin perder cualquier contexto.</span><span class="sxs-lookup"><span data-stu-id="ca836-p101">Consider an email conversation that has been going on for a while. In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread. Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="ca836-106">¿Qué hace threading de correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="ca836-106">What does email threading do?</span></span>
<span data-ttu-id="ca836-p102">Correo electrónico threading analiza cada correo electrónico y desconstructs para los mensajes individuales; cada correo electrónico es una cadena de mensajes individuales. A continuación, analiza todos los mensajes de correo electrónico en el conjunto de trabajo para determinar si un correo electrónico tiene contenido único o si la cadena de contenidas completo en un correo electrónico diferente. Al final, los correos electrónicos se dividen en cuatro categorías:</span><span class="sxs-lookup"><span data-stu-id="ca836-p102">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages. Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email. In the end emails are divided into four categories:</span></span>
- <span data-ttu-id="ca836-110">Inclusives: el último mensaje en el correo electrónico tiene contenido único, y el correo electrónico tiene todos los datos adjuntos que se incluyeron en otros mensajes de correo electrónico de que el contenido está contenido completo de este correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca836-110">Inclusives: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>
- <span data-ttu-id="ca836-111">Inclusive menos: el último mensaje en el correo electrónico tiene contenido único, pero el correo electrónico no contienen algunos de los datos adjuntos que se incluyeron en otros mensajes de correo electrónico de que el contenido está contenido completo de este correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca836-111">Inclusive minus: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>
- <span data-ttu-id="ca836-112">Copia inclusive: una copia exacta de un inclusive/inclusive menos correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ca836-112">Inclusive copy: an exact copy of an inclusive/inclusive minus email</span></span>
- <span data-ttu-id="ca836-113">Ninguno: El contenido de este correo electrónico contenido completo en al menos un correo electrónico que se marca como menos inclusive inclusive.</span><span class="sxs-lookup"><span data-stu-id="ca836-113">None: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="ca836-114">¿Cómo es diferente de las conversaciones en Outlook?</span><span class="sxs-lookup"><span data-stu-id="ca836-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="ca836-p103">Un vistazo, esto suena muy similar a las agrupaciones de conversación en Outlook. Sin embargo, existen algunas diferencias importantes. Considere la posibilidad de una conversación de correo electrónico que obtuvo bifurcada en dos conversación; Por ejemplo, alguien ha respondido a un correo electrónico que no es la más reciente en la conversación, por lo que los dos últimos mensajes de correo electrónico en la conversación ambos tienen contenido único.</span><span class="sxs-lookup"><span data-stu-id="ca836-p103">At a glance, this sounds very similar to conversation groupings in Outlook. However, there are some important distinctions. Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="ca836-p104">Outlook aún podría agrupar los mensajes de correo electrónico en una conversación único; leer el último correo electrónico significaría que falta el contexto del correo electrónico del segundo a último, que también contiene contenido único. Debido a que el correo electrónico threading analiza cada correo electrónico en los componentes individuales y los compara, correo electrónico threading sería marcar ambos de los dos últimos correos electrónicos de como inclusives, asegurarse de que no se pierda cualquier contexto como leer todos los mensajes de correo electrónico marcados como inclusivas.</span><span class="sxs-lookup"><span data-stu-id="ca836-p104">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content. Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
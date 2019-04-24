---
title: Temas
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7c9d1a52acef48d96816fefbb1c836032d262b93
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240982"
---
# <a name="themes"></a>Temas
¿Cómo escribe un documento un usuario? Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y se redactan con palabras que se alinean con las ideas. Cuanto más frecuente sea la idea, más frecuentes serán las palabras relacionadas con dicha idea. Esto informa de cómo los usuarios también usan los documentos; lo más importante para obtener información sobre cómo leer un documento son las ideas que el documento está tratando de transmitir, así como las ideas en las que aparecen y las relaciones entre las ideas.

Esto puede ampliarse a cómo una persona desea consumir un conjunto de documentos. Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando sobre esas ideas. Además, si encuentran un documento concreto de interés, quieren poder ver documentos que discutan ideas similares.

El módulo temas intenta imitar la razón de los usuarios de los documentos, analizando los "temas" que se tratan en un conjunto de trabajo y los asigna a los documentos. Los temas van un paso más allá y identifican por documento el "tema dominante"; es decir, el tema que más se muestra.

## <a name="how-does-themes-work"></a>¿Cómo funciona los temas?
Los temas analizan los documentos con texto en un conjunto de trabajo para analizar los temas comunes que aparecen en los documentos. A continuación, asigna esos temas a los documentos en los que aparecen. También etiqueta cada con las palabras que se usan en los documentos representativos del tema. Dado que un documento puede estar sobre más de un asunto, en muchos casos, un documento tiene más de un tema asignado. El tema que aparece más visiblemente en un documento se designa como su tema dominante.
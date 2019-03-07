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
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454682"
---
# <a name="themes"></a><span data-ttu-id="71c25-102">Temas</span><span class="sxs-lookup"><span data-stu-id="71c25-102">Themes</span></span>
<span data-ttu-id="71c25-103">¿Cómo escribe un documento un usuario?</span><span class="sxs-lookup"><span data-stu-id="71c25-103">How does a person write a document?</span></span> <span data-ttu-id="71c25-104">Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y se redactan con palabras que se alinean con las ideas.</span><span class="sxs-lookup"><span data-stu-id="71c25-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="71c25-105">Cuanto más frecuente sea la idea, más frecuentes serán las palabras relacionadas con dicha idea.</span><span class="sxs-lookup"><span data-stu-id="71c25-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="71c25-106">Esto informa de cómo los usuarios también usan los documentos; lo más importante para obtener información sobre cómo leer un documento son las ideas que el documento está tratando de transmitir, así como las ideas en las que aparecen y las relaciones entre las ideas.</span><span class="sxs-lookup"><span data-stu-id="71c25-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="71c25-107">Esto puede ampliarse a cómo una persona desea consumir un conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="71c25-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="71c25-108">Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando sobre esas ideas.</span><span class="sxs-lookup"><span data-stu-id="71c25-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="71c25-109">Además, si encuentran un documento concreto de interés, quieren poder ver documentos que discutan ideas similares.</span><span class="sxs-lookup"><span data-stu-id="71c25-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="71c25-110">El módulo temas intenta imitar la razón de los usuarios de los documentos, analizando los "temas" que se tratan en un conjunto de trabajo y los asigna a los documentos.</span><span class="sxs-lookup"><span data-stu-id="71c25-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a working set and assigning them to documents.</span></span> <span data-ttu-id="71c25-111">Los temas van un paso más allá y identifican por documento el "tema dominante"; es decir, el tema que más se muestra.</span><span class="sxs-lookup"><span data-stu-id="71c25-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="71c25-112">¿Cómo funciona los temas?</span><span class="sxs-lookup"><span data-stu-id="71c25-112">How does Themes work?</span></span>
<span data-ttu-id="71c25-113">Los temas analizan los documentos con texto en un conjunto de trabajo para analizar los temas comunes que aparecen en los documentos.</span><span class="sxs-lookup"><span data-stu-id="71c25-113">Themes analyzes documents with text in a working set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="71c25-114">A continuación, asigna esos temas a los documentos en los que aparecen.</span><span class="sxs-lookup"><span data-stu-id="71c25-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="71c25-115">También etiqueta cada con las palabras que se usan en los documentos representativos del tema.</span><span class="sxs-lookup"><span data-stu-id="71c25-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="71c25-116">Dado que un documento puede estar sobre más de un asunto, en muchos casos, un documento tiene más de un tema asignado.</span><span class="sxs-lookup"><span data-stu-id="71c25-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="71c25-117">El tema que aparece más visiblemente en un documento se designa como su tema dominante.</span><span class="sxs-lookup"><span data-stu-id="71c25-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
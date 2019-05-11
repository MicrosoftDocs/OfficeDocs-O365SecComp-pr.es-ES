---
title: Configuración de etiquetas inteligentes para abogados-detección de privilegios de cliente en eDiscovery avanzado
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 721426f23aec862bcefbd13b8e61415dac3aeb27
ms.sourcegitcommit: aa8ea45d5854f8906714e0a407937585ec7993ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2019
ms.locfileid: "33951709"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a><span data-ttu-id="d4b18-102">Configurar etiquetas inteligentes para revisión asistida por ML en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="d4b18-102">Set up smart tags for ML-assisted review in Advanced eDiscovery</span></span>

<span data-ttu-id="d4b18-103">Las capacidades de aprendizaje de máquina en eDiscovery avanzado están pensadas para facilitar el proceso de toma de decisiones en los documentos.</span><span class="sxs-lookup"><span data-stu-id="d4b18-103">Machine learning capabilities in Advanced eDiscovery are meant to help make decision process on documents more efficient.</span></span> <span data-ttu-id="d4b18-104">Las etiquetas inteligentes son una forma de incorporar las funciones de aprendizaje de la máquina en donde se registran las decisiones: etiquetas y grupos de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="d4b18-104">Smart tags is a way to bring the machine learning capabilities into where the decisions are recorded: tags and tag groups.</span></span> <span data-ttu-id="d4b18-105">Cuando se crea un grupo de etiquetas inteligentes, las decisiones del modelo de los ML asignadas al grupo se mostrarán en línea con las etiquetas del grupo para ayudarle a ver la información en línea, donde el contexto es más lógico.</span><span class="sxs-lookup"><span data-stu-id="d4b18-105">When you create a smart tag group, then the decisions of the ML model mapped to the group will be shown in-line with the tags in the group to help you see the information in-line, where they contextually make most sense.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="d4b18-106">Cómo configurar un grupo de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="d4b18-106">How to set up a smart tag group</span></span>

1. <span data-ttu-id="d4b18-107">En un conjunto de revisiones, vaya a **Manage View Set** -> **Manage Tags**.</span><span class="sxs-lookup"><span data-stu-id="d4b18-107">In a review set, go to **Manage review set** -> **Manage tags**.</span></span>

2. <span data-ttu-id="d4b18-108">Haga clic en la lista desplegable junto a **Agregar grupo de etiquetas** y seleccione **Agregar grupo de etiquetas inteligentes**.</span><span class="sxs-lookup"><span data-stu-id="d4b18-108">Click on the drop-down next to **Add tag group** and select **Add smart tag group**.</span></span>

3. <span data-ttu-id="d4b18-109">Seleccione el modelo que desea asignar a este grupo.</span><span class="sxs-lookup"><span data-stu-id="d4b18-109">Select the model you want to map to this group.</span></span> <span data-ttu-id="d4b18-110">De este modo, se creará una sección de etiqueta y N etiquetas secundarias, donde N es el número de salidas posibles del modelo.</span><span class="sxs-lookup"><span data-stu-id="d4b18-110">This will create a tag section and N child tags, where N is the number of possible outputs of the model.</span></span> <span data-ttu-id="d4b18-111">Por ejemplo, el modelo de detección de privilegios de abogado-Client tiene dos posibles resultados-privileges y no privileged; al seleccionar este modelo se crearán dos etiquetas secundarias en el conjunto de revisión, cada una correspondiente a una de las posibles salidas.</span><span class="sxs-lookup"><span data-stu-id="d4b18-111">For instance, attorney-client privilege detection model has two possible outputs - privileged and not privileged; selecting this model will create two child tags in the review set, each corresponding to one of the possible outputs.</span></span>

4. <span data-ttu-id="d4b18-112">Cambie el nombre del grupo de etiquetas y las etiquetas según su ajuste.</span><span class="sxs-lookup"><span data-stu-id="d4b18-112">Rename the tag group and tags as you see fit.</span></span>

## <a name="how-to-use-a-smart-tag-group"></a><span data-ttu-id="d4b18-113">Cómo usar un grupo de etiquetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="d4b18-113">How to use a smart tag group</span></span>

<span data-ttu-id="d4b18-114">Al revisar un documento, los resultados del modelo se expondrán junto al valor de etiqueta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d4b18-114">When reviewing a document, the model's results will be exposed next to the appropriate tag value.</span></span> <span data-ttu-id="d4b18-115">Por ejemplo, si tiene un grupo de etiquetas inteligentes para la detección de privilegios de clientes de abogados y revisa un documento que el modelo ha decidido que es potencialmente privilegiado, verá el motivo por el que se encuentra junto a la etiqueta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d4b18-115">For instance, if you have a smart tag group for attorney-client privilege detection and you review a document that the model has decided is potentially privileged, you will see the reason for that next to the appropriate tag.</span></span> <span data-ttu-id="d4b18-116">Es importante tener en cuenta que la etiqueta no se aplica automáticamente; para todas las necesidades, las etiquetas dentro de un grupo de etiquetas inteligentes actúan exactamente igual que las etiquetas normales, excepto que exponen los resultados del modelo junto a ellos cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="d4b18-116">It is important to note that the tag is not automatically applied; for all intents and purposes, tags within a smart tag group act just like normal tags, except that they expose the model results next to them when appropriate.</span></span>
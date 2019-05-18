---
title: Etiquetar documentos en un conjunto de revisión
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a3b588f4b8e24783cd0d7198ea995f0fd6c8ae3e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154032"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="41dcd-102">Etiquetar documentos en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="41dcd-102">Tag documents in a review set</span></span>

<span data-ttu-id="41dcd-103">La organización de contenido en un conjunto de revisión es importante para completar varios flujos de trabajo en el proceso de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="41dcd-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="41dcd-104">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="41dcd-104">This includes:</span></span>

-  <span data-ttu-id="41dcd-105">Selección de contenido innecesario</span><span class="sxs-lookup"><span data-stu-id="41dcd-105">Culling unnecessary content</span></span>

- <span data-ttu-id="41dcd-106">Identificación del contenido relevante</span><span class="sxs-lookup"><span data-stu-id="41dcd-106">Identifying relevant content</span></span>
 
-  <span data-ttu-id="41dcd-107">Identificación de contenido que debe ser revisado por un experto o un abogado</span><span class="sxs-lookup"><span data-stu-id="41dcd-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="41dcd-108">Cuando expertos, abogados u otros usuarios revisan el contenido de un conjunto de revisión, se pueden capturar sus opiniones relacionadas con el contenido mediante el uso de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="41dcd-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="41dcd-109">Por ejemplo, si la intención es deseleccionar contenido innecesario, un usuario puede etiquetar documentos con una etiqueta como "sin respuesta".</span><span class="sxs-lookup"><span data-stu-id="41dcd-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="41dcd-110">Una vez que se ha revisado y etiquetado el contenido, se puede crear una búsqueda de conjunto de revisión para excluir cualquier Contenido etiquetado como "sin respuesta", lo que elimina este contenido de los pasos siguientes en el flujo de trabajo de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="41dcd-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="41dcd-111">El panel de etiquetas se puede personalizar para cada caso, de modo que las etiquetas puedan admitir el flujo de trabajo de revisión previsto.</span><span class="sxs-lookup"><span data-stu-id="41dcd-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="41dcd-112">Tipos de etiquetas</span><span class="sxs-lookup"><span data-stu-id="41dcd-112">Tag types</span></span>

<span data-ttu-id="41dcd-113">La exhibición avanzada de documentos electrónicos proporciona dos tipos de etiquetas:</span><span class="sxs-lookup"><span data-stu-id="41dcd-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="41dcd-114">**Etiquetas de opción única** : limita a los usuarios a seleccionar una sola etiqueta dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="41dcd-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="41dcd-115">Esto puede ser útil para asegurarse de que los usuarios no seleccionan etiquetas conflictivas como "receptivo" y "sin respuesta".</span><span class="sxs-lookup"><span data-stu-id="41dcd-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> 

- <span data-ttu-id="41dcd-116">**Etiquetas de varias opciones** : permite a los usuarios seleccionar varias etiquetas dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="41dcd-116">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="41dcd-117">Estructura de etiquetas</span><span class="sxs-lookup"><span data-stu-id="41dcd-117">Tag structure</span></span>

<span data-ttu-id="41dcd-118">Además de los tipos de etiqueta, la estructura de las etiquetas que se organizan en el panel etiqueta se puede usar para que los documentos de etiquetado sean más intuitivos.</span><span class="sxs-lookup"><span data-stu-id="41dcd-118">In addition to the tag types, the structure of how tags are organization in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="41dcd-119">Las etiquetas se agrupan por secciones.</span><span class="sxs-lookup"><span data-stu-id="41dcd-119">Tags are grouped by sections.</span></span> <span data-ttu-id="41dcd-120">revisión Set Search admite la capacidad de buscar por etiqueta y por etiqueta.</span><span class="sxs-lookup"><span data-stu-id="41dcd-120">review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="41dcd-121">Esto significa que puede crear una búsqueda de conjunto de revisión para recuperar documentos etiquetados con cualquier etiqueta en una sección.</span><span class="sxs-lookup"><span data-stu-id="41dcd-121">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Secciones de etiquetas en el panel etiqueta](../media/Tagtypes.png)

<span data-ttu-id="41dcd-123">Las etiquetas se pueden organizar en mayor profundidad si se anidan dentro de una sección.</span><span class="sxs-lookup"><span data-stu-id="41dcd-123">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="41dcd-124">Por ejemplo, si la intención es identificar y etiquetar contenido privilegiado, se puede usar la anidación para dejar claro que un usuario puede etiquetar un documento como "privilegiado" y seleccionar el tipo de privilegio comprobando la etiqueta anidada adecuada.</span><span class="sxs-lookup"><span data-stu-id="41dcd-124">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![Etiquetas anidadas dentro de una sección de etiqueta](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="41dcd-126">Aplicar etiquetas</span><span class="sxs-lookup"><span data-stu-id="41dcd-126">Applying tags</span></span>

<span data-ttu-id="41dcd-127">Hay varias formas de aplicar una etiqueta al contenido.</span><span class="sxs-lookup"><span data-stu-id="41dcd-127">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="41dcd-128">Etiquetado de un solo documento</span><span class="sxs-lookup"><span data-stu-id="41dcd-128">Tagging a single document</span></span>

<span data-ttu-id="41dcd-129">Al ver un documento en un conjunto de revisiones, puede mostrar las etiquetas que puede usar una revisión haciendo clic en **Panel de codificación**.</span><span class="sxs-lookup"><span data-stu-id="41dcd-129">When viewing a document in a review set, you can display the tags that a review can use by clicking **Coding panel**.</span></span>

![Haga clic en el panel de etiquetas para mostrar el panel de etiquetas](../media/Singledoctag.png)

<span data-ttu-id="41dcd-131">Esto le permitirá aplicar etiquetas al documento que se muestra en el visor.</span><span class="sxs-lookup"><span data-stu-id="41dcd-131">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="41dcd-132">Etiquetado masivo</span><span class="sxs-lookup"><span data-stu-id="41dcd-132">Bulk tagging</span></span>

<span data-ttu-id="41dcd-133">La etiquetación en masa se puede realizar seleccionando varios archivos en la cuadrícula de resultados y, a continuación, usando las etiquetas en el **Panel de codificación** , de forma similar a la etiqueta de un único documento.</span><span class="sxs-lookup"><span data-stu-id="41dcd-133">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Coding panel** similar to tagging single documents.</span></span> <span data-ttu-id="41dcd-134">Para realizar un etiquetado masivo, puede seleccionar las etiquetas dos veces; el primer clic aplicará la etiqueta y la segunda se asegurará de que la etiqueta se borre para todos los archivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="41dcd-134">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Una captura de pantalla de una descripción de teléfono móvil generada automáticamente](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="41dcd-136">Cuando se realiza un etiquetado masivo, el panel etiquetado muestra un recuento de archivos que se etiquetan para cada etiqueta del panel.</span><span class="sxs-lookup"><span data-stu-id="41dcd-136">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="41dcd-137">Etiquetado en otros paneles de revisión</span><span class="sxs-lookup"><span data-stu-id="41dcd-137">Tagging in other review panels</span></span>

<span data-ttu-id="41dcd-138">Al revisar los documentos, puede usar los otros paneles de revisión para revisar otras características de los documentos en la cuadrícula de resultados.</span><span class="sxs-lookup"><span data-stu-id="41dcd-138">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="41dcd-139">Esto incluye la revisión de otros documentos relacionados, subprocesos de correo electrónico, Near duplicados y duplicados de hash.</span><span class="sxs-lookup"><span data-stu-id="41dcd-139">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="41dcd-140">Por ejemplo, cuando se revisan documentos relacionados (mediante el panel revisión de **familia de documentos** ), puede reducir significativamente el tiempo de revisión mediante la etiquetación en masa de los documentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="41dcd-140">For example, when your reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="41dcd-141">Por ejemplo, si un mensaje de correo electrónico tiene varios datos adjuntos y desea asegurarse de que toda la familia se etiquete de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="41dcd-141">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="41dcd-142">Por ejemplo, aquí se muestra cómo mostrar el **Panel de codificación** al usar el panel revisión de **familia de documentos** :</span><span class="sxs-lookup"><span data-stu-id="41dcd-142">For example, here's how to display the **Coding panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="41dcd-143">Con el panel revisión abierto para un documento seleccionado (por ejemplo, mostrando la lista de contenido relacionado en el panel revisión de **familia de documentos** , haga clic en **documentos de código** en la parte superior del panel revisión actual).</span><span class="sxs-lookup"><span data-stu-id="41dcd-143">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Code documents** at the top of the current review panel.</span></span>

   <span data-ttu-id="41dcd-144">El panel de codificación se muestra como una ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="41dcd-144">The Coding panel is displayed is a pop-up window.</span></span>

2. <span data-ttu-id="41dcd-145">Elija una o más etiquetas para aplicar el documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="41dcd-145">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="41dcd-146">Para etiquetar todos los documentos, seleccione todos los documentos en el panel de la **familia de documentos** , haga clic en **documentos de código**y, a continuación, elija las etiquetas que se aplicarán a toda la familia de documentos.</span><span class="sxs-lookup"><span data-stu-id="41dcd-146">To tag all documents, select all documents in the **Document family** panel, click **Code documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Captura de pantalla de una descripción de post de medio social generada automáticamente](../media/Relatedtag.png)

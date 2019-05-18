---
title: Usar el editor de comunicaciones
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
ms.openlocfilehash: 78865efc5c10ebcff9742f922f675b637bb9b2b0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151493"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="6ba54-102">Usar el editor de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="6ba54-102">Use the communications editor</span></span>

<span data-ttu-id="6ba54-103">Al definir el contenido del contenido del portal, las notificaciones de retención legal y los avisos/escalas relacionados, puede aprovechar el editor de comunicaciones para formatear y personalizar el contenido de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="6ba54-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="6ba54-104">Editor de texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="6ba54-104">Rich text editor</span></span> 

<span data-ttu-id="6ba54-105">El editor de comunicaciones permite al usuario personalizar el texto con las opciones del editor.</span><span class="sxs-lookup"><span data-stu-id="6ba54-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="6ba54-106">Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido, etc.</span><span class="sxs-lookup"><span data-stu-id="6ba54-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="6ba54-107">Combinar variables de campo</span><span class="sxs-lookup"><span data-stu-id="6ba54-107">Merge field variables</span></span>

<span data-ttu-id="6ba54-108">Puede aprovechar las variables de combinación de correo electrónico del editor de comunicaciones para incrustar atributos de custodios personalizados en el texto del cuerpo de una comunicación.</span><span class="sxs-lookup"><span data-stu-id="6ba54-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="6ba54-109">Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6ba54-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="6ba54-110">Por ejemplo, cuando se envía a custodio Andrés Díaz, el campo de combinación [nombre del custodio] se convertiría con el nombre correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6ba54-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="6ba54-111">Puede usar los campos de combinación de correo electrónico seleccionando los iconos de **campo de combinación** en la parte superior del control del editor de texto enriquecido.</span><span class="sxs-lookup"><span data-stu-id="6ba54-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="6ba54-112">El marcador de posición se agregará en función de la ubicación del cursor de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ba54-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="6ba54-113">Lista de variables de campo de combinación</span><span class="sxs-lookup"><span data-stu-id="6ba54-113">List of merge field variables</span></span>

| <span data-ttu-id="6ba54-114">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="6ba54-114">Field name</span></span>                  | <span data-ttu-id="6ba54-115">Detalles de campo</span><span class="sxs-lookup"><span data-stu-id="6ba54-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="6ba54-116">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="6ba54-116">Display Name</span></span>  | <span data-ttu-id="6ba54-117">Nombre y apellido del custodio.</span><span class="sxs-lookup"><span data-stu-id="6ba54-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="6ba54-118">Vínculo de confirmación</span><span class="sxs-lookup"><span data-stu-id="6ba54-118">Acknowledgement Link</span></span> | <span data-ttu-id="6ba54-119">Un vínculo personalizado para registrar la confirmación de cada custodio.</span><span class="sxs-lookup"><span data-stu-id="6ba54-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="6ba54-120">Vínculo al portal</span><span class="sxs-lookup"><span data-stu-id="6ba54-120">Portal Link</span></span>     | <span data-ttu-id="6ba54-121">Un vínculo personalizado para el portal de cumplimiento de la custodio.</span><span class="sxs-lookup"><span data-stu-id="6ba54-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="6ba54-122">Responsable de la expedición</span><span class="sxs-lookup"><span data-stu-id="6ba54-122">Issuing Officer</span></span>                   | <span data-ttu-id="6ba54-123">La dirección de correo electrónico del oficial de expedición especificado.</span><span class="sxs-lookup"><span data-stu-id="6ba54-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="6ba54-124">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="6ba54-124">Issuing Date</span></span>                   | <span data-ttu-id="6ba54-125">La fecha en que se emitió el aviso (UTC).</span><span class="sxs-lookup"><span data-stu-id="6ba54-125">The date that the notice was issued (UTC).</span></span>              |
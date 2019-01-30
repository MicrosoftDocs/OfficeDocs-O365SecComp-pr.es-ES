---
title: Con el editor de comunicaciones
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
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608367"
---
# <a name="using-the-communications-editor"></a><span data-ttu-id="6a9be-102">Con el Editor de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="6a9be-102">Using the Communications Editor</span></span>
<span data-ttu-id="6a9be-103">Tal y como se define el contenido del contenido del portal, con fines legales mantenga las notificaciones y avisos/escalaciones relacionados, puede aprovechar el Editor de comunicaciones para aplicar formato y personalizar dinámicamente el contenido.</span><span class="sxs-lookup"><span data-stu-id="6a9be-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="6a9be-104">Editor de texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="6a9be-104">Rich-Text Editor</span></span> 

<span data-ttu-id="6a9be-p101">El Editor de Communications permite al usuario personalizar el texto con las opciones del editor. Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, contenido de resaltado y mucho más.</span><span class="sxs-lookup"><span data-stu-id="6a9be-p101">The Communications Editor allows user to customize the text using the editor options. For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

<<include screenshot>>

## <a name="merge-field-variables"></a><span data-ttu-id="6a9be-107">Combinar Variables de campo</span><span class="sxs-lookup"><span data-stu-id="6a9be-107">Merge Field Variables</span></span>

<span data-ttu-id="6a9be-p102">Puede sacar provecho de las variables de combinación de correo electrónico desde el Editor de comunicaciones para incrustar atributos de custodia personalizada en texto de cuerpo de una comunicación. Cuando se envía a la custodia, se rellenará el campo de combinación con el campo correspondiente. Por ejemplo, cuando se envía a custodia John Smith, el campo de combinación de [nombre de custodia] ¿traducirse con el nombre correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6a9be-p102">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text. When sent to the custodian, the merge field will be populated with the corresponding field. For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="6a9be-p103">Puede usar los campos de combinación de correo electrónico mediante la selección de los iconos de **Campo de combinación** en la parte superior del control de editor de texto enriquecido. El marcador de posición se agregarán en función desactiva la ubicación del cursor de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a9be-p103">You can use email merge fields by selecting the **Merge Field** icons on the top of the rich-text editor control. The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="6a9be-113">Lista de Variables de campo de combinación</span><span class="sxs-lookup"><span data-stu-id="6a9be-113">List of Merge Field Variables</span></span>
| <span data-ttu-id="6a9be-114">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="6a9be-114">Field Name</span></span>                  | <span data-ttu-id="6a9be-115">Detalles del campo</span><span class="sxs-lookup"><span data-stu-id="6a9be-115">Field Details</span></span> | 
| :------------------- | :-------------------: |
| <span data-ttu-id="6a9be-116">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="6a9be-116">Display Name</span></span>  | <span data-ttu-id="6a9be-117">Custodia y los apellidos del nombre</span><span class="sxs-lookup"><span data-stu-id="6a9be-117">Custodian's first and last name</span></span> | 
| <span data-ttu-id="6a9be-118">Vínculo de confirmación</span><span class="sxs-lookup"><span data-stu-id="6a9be-118">Acknowledgement Link</span></span>                 | <span data-ttu-id="6a9be-119">Vínculo personalizado para registrar la confirmación de cada custodia</span><span class="sxs-lookup"><span data-stu-id="6a9be-119">Customized link to record each custodian's acknowledgement</span></span>                 |
| <span data-ttu-id="6a9be-120">Vínculo del portal</span><span class="sxs-lookup"><span data-stu-id="6a9be-120">Portal Link</span></span>     | <span data-ttu-id="6a9be-121">Vínculo personalizado para el Portal de cumplimiento de normas de custodia</span><span class="sxs-lookup"><span data-stu-id="6a9be-121">Customized link for the custodian's Compliance Portal</span></span>                 |
| <span data-ttu-id="6a9be-122">Emitir ordenador</span><span class="sxs-lookup"><span data-stu-id="6a9be-122">Issuing Officer</span></span>                   | <span data-ttu-id="6a9be-123">Dirección de correo electrónico del ordenador emisora especificado</span><span class="sxs-lookup"><span data-stu-id="6a9be-123">Email address of the specified issuing officer</span></span>                   |
| <span data-ttu-id="6a9be-124">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="6a9be-124">Issuing Date</span></span>                   | <span data-ttu-id="6a9be-125">fecha en la que el aviso se emitió (UTC)</span><span class="sxs-lookup"><span data-stu-id="6a9be-125">date that the notice was issued (UTC)</span></span>              |
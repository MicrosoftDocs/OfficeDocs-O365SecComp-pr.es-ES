---
title: Cómo se identifica el contenido para las recomendaciones de gobierno de datos
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. En este tema se enumeran las recomendaciones de gobierno de datos que puede ver y se describe el contenido que se detecta para desencadenar cada uno.
ms.openlocfilehash: 24e41501ed11d54e60f8b3d9f27a2e96f3cde112
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220440"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="2c979-106">Cómo se identifica el contenido para las recomendaciones de gobierno de datos</span><span class="sxs-lookup"><span data-stu-id="2c979-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="2c979-p102">El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. </span><span class="sxs-lookup"><span data-stu-id="2c979-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="2c979-110">En este tema se enumeran las recomendaciones de gobierno de datos que es posible que vea y se describe el contenido que se detecte para desencadenar cada uno.</span><span class="sxs-lookup"><span data-stu-id="2c979-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="2c979-111">Limpiar el correo de voz</span><span class="sxs-lookup"><span data-stu-id="2c979-111">Clean up voicemail</span></span>

<span data-ttu-id="2c979-p103">Esta recomendación aparece cuando se detectan mensajes de correo identificados como tipo de mensaje "correo de voz" en los buzones de usuarios. Obtenga más información sobre las [propiedades de mensajes en Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="2c979-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="2c979-114">Etiquetar contenido de privilegios abogado-cliente </span><span class="sxs-lookup"><span data-stu-id="2c979-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="2c979-115">Esta recomendación aparece cuando se cumple uno de los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="2c979-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="2c979-116">Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="2c979-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="2c979-117">ACP</span><span class="sxs-lookup"><span data-stu-id="2c979-117">ACP</span></span>
    - <span data-ttu-id="2c979-118">Privilegio de abogado cliente</span><span class="sxs-lookup"><span data-stu-id="2c979-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="2c979-119">Privilegio de abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="2c979-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="2c979-120">Confidencialidad abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="2c979-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="2c979-121">Cualquier combinación de estas palabras clave se detectan en archivos de SharePoint o OneDrive:</span><span class="sxs-lookup"><span data-stu-id="2c979-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="2c979-122">ACP</span><span class="sxs-lookup"><span data-stu-id="2c979-122">ACP</span></span>
    - <span data-ttu-id="2c979-123">Privilegio de abogado cliente\*</span><span class="sxs-lookup"><span data-stu-id="2c979-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="2c979-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="2c979-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="2c979-125">Conservar archivos de audio</span><span class="sxs-lookup"><span data-stu-id="2c979-125">Retain audio files</span></span>

<span data-ttu-id="2c979-126">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2c979-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2c979-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="2c979-127">.MP3</span></span>
- <span data-ttu-id="2c979-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="2c979-128">.WMA</span></span>
- <span data-ttu-id="2c979-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="2c979-129">.WAV</span></span>
- <span data-ttu-id="2c979-130">.RA</span><span class="sxs-lookup"><span data-stu-id="2c979-130">.RA</span></span>
- <span data-ttu-id="2c979-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="2c979-131">.RAM</span></span>
- <span data-ttu-id="2c979-132">.RM</span><span class="sxs-lookup"><span data-stu-id="2c979-132">.RM</span></span>
- <span data-ttu-id="2c979-133">.MID</span><span class="sxs-lookup"><span data-stu-id="2c979-133">.MID</span></span>
- <span data-ttu-id="2c979-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="2c979-134">.OGG</span></span>
- <span data-ttu-id="2c979-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="2c979-135">.AIFF</span></span>
- <span data-ttu-id="2c979-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="2c979-136">.PCM</span></span>
- <span data-ttu-id="2c979-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="2c979-137">.AAC</span></span>
- <span data-ttu-id="2c979-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="2c979-138">.FLAC</span></span>
- <span data-ttu-id="2c979-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="2c979-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="2c979-140">Conservar archivos CAD</span><span class="sxs-lookup"><span data-stu-id="2c979-140">Retain CAD files</span></span>

<span data-ttu-id="2c979-141">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2c979-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2c979-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="2c979-142">.3DXML</span></span>
- <span data-ttu-id="2c979-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="2c979-143">.ACIS</span></span>
- <span data-ttu-id="2c979-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="2c979-144">.ARC</span></span>
- <span data-ttu-id="2c979-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="2c979-145">.ASM</span></span>
- <span data-ttu-id="2c979-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="2c979-146">.CAT\*</span></span>
- <span data-ttu-id="2c979-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="2c979-147">.CGR</span></span>
- <span data-ttu-id="2c979-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="2c979-148">.DW\*</span></span>
- <span data-ttu-id="2c979-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="2c979-149">.DX\*</span></span>
- <span data-ttu-id="2c979-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="2c979-150">.EDRW</span></span>
- <span data-ttu-id="2c979-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="2c979-151">.IAM</span></span>
- <span data-ttu-id="2c979-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="2c979-152">.IGES</span></span>
- <span data-ttu-id="2c979-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="2c979-153">.IGS</span></span>
- <span data-ttu-id="2c979-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="2c979-154">.IPT</span></span>
- <span data-ttu-id="2c979-155">.JT</span><span class="sxs-lookup"><span data-stu-id="2c979-155">.JT</span></span>
- <span data-ttu-id="2c979-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="2c979-156">.MF1</span></span>
- <span data-ttu-id="2c979-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="2c979-157">.NEU</span></span>
- <span data-ttu-id="2c979-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="2c979-158">.PAR</span></span>
- <span data-ttu-id="2c979-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="2c979-159">.PKG</span></span>
- <span data-ttu-id="2c979-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="2c979-160">.PRC</span></span>
- <span data-ttu-id="2c979-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="2c979-161">.PRT</span></span>
- <span data-ttu-id="2c979-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="2c979-162">.PSM</span></span>
- <span data-ttu-id="2c979-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="2c979-163">.PWD</span></span>
- <span data-ttu-id="2c979-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="2c979-164">.SLD\*</span></span>
- <span data-ttu-id="2c979-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="2c979-165">.STEP</span></span>
- <span data-ttu-id="2c979-166">.STL</span><span class="sxs-lookup"><span data-stu-id="2c979-166">.STL</span></span>
- <span data-ttu-id="2c979-167">.STP</span><span class="sxs-lookup"><span data-stu-id="2c979-167">.STP</span></span>
- <span data-ttu-id="2c979-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="2c979-168">.U3D</span></span>
- <span data-ttu-id="2c979-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="2c979-169">.UNV</span></span>
- <span data-ttu-id="2c979-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="2c979-170">.VRML</span></span>
- <span data-ttu-id="2c979-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="2c979-171">.WRL</span></span>
- <span data-ttu-id="2c979-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="2c979-172">.X_\*</span></span>
- <span data-ttu-id="2c979-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="2c979-173">.XAS</span></span>
- <span data-ttu-id="2c979-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="2c979-174">.XMT\*</span></span>
- <span data-ttu-id="2c979-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="2c979-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="2c979-176">Conservar archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="2c979-176">Retain image files</span></span>

<span data-ttu-id="2c979-177">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2c979-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2c979-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="2c979-178">.JPEG</span></span>
- <span data-ttu-id="2c979-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="2c979-179">.GIF</span></span>
- <span data-ttu-id="2c979-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="2c979-180">.TIF\*</span></span>
- <span data-ttu-id="2c979-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="2c979-181">.BMP</span></span>
- <span data-ttu-id="2c979-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="2c979-182">.PNG</span></span>
- <span data-ttu-id="2c979-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="2c979-183">.RAW</span></span>
- <span data-ttu-id="2c979-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="2c979-184">.PSD</span></span>
- <span data-ttu-id="2c979-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="2c979-185">.PSP</span></span>
- <span data-ttu-id="2c979-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="2c979-186">.JPG</span></span>
- <span data-ttu-id="2c979-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="2c979-187">.EXIF</span></span>
- <span data-ttu-id="2c979-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="2c979-188">.PPM</span></span>
- <span data-ttu-id="2c979-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="2c979-189">.PGM</span></span>
- <span data-ttu-id="2c979-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="2c979-190">.PBM</span></span>
- <span data-ttu-id="2c979-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="2c979-191">.PNM</span></span>
- <span data-ttu-id="2c979-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="2c979-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="2c979-193">Conservar contenido NDA</span><span class="sxs-lookup"><span data-stu-id="2c979-193">Retain NDA content</span></span> 

<span data-ttu-id="2c979-194">Esta recomendación aparece cuando se cumple uno de los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="2c979-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="2c979-195">Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="2c979-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="2c979-196">NDA</span><span class="sxs-lookup"><span data-stu-id="2c979-196">NDA</span></span>
    - <span data-ttu-id="2c979-197">“Acuerdo de confidencialidad”</span><span class="sxs-lookup"><span data-stu-id="2c979-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="2c979-198">“Acuerdo de confidencialidad”</span><span class="sxs-lookup"><span data-stu-id="2c979-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="2c979-199">Cualquier combinación de estas palabras clave se detectan en archivos .PDF o .DOC en SharePoint o OneDrive:</span><span class="sxs-lookup"><span data-stu-id="2c979-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="2c979-200">NDA</span><span class="sxs-lookup"><span data-stu-id="2c979-200">NDA</span></span>
    - <span data-ttu-id="2c979-201">Acuerdo de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="2c979-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="2c979-202">Conservar archivos de desarrollo de software </span><span class="sxs-lookup"><span data-stu-id="2c979-202">Retain software development files</span></span>

<span data-ttu-id="2c979-203">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2c979-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2c979-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="2c979-204">.ASAX</span></span>
- <span data-ttu-id="2c979-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="2c979-205">.ASM</span></span>
- <span data-ttu-id="2c979-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="2c979-206">.ASP\*</span></span>
- <span data-ttu-id="2c979-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="2c979-207">.BAT</span></span>
- <span data-ttu-id="2c979-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="2c979-208">.CONFIG</span></span>
- <span data-ttu-id="2c979-209">.CS</span><span class="sxs-lookup"><span data-stu-id="2c979-209">.CS</span></span>
- <span data-ttu-id="2c979-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="2c979-210">.CSS</span></span>
- <span data-ttu-id="2c979-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="2c979-211">.DISCO</span></span>
- <span data-ttu-id="2c979-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="2c979-212">.HTM\*</span></span>
- <span data-ttu-id="2c979-213">.INC</span><span class="sxs-lookup"><span data-stu-id="2c979-213">.INC</span></span>
- <span data-ttu-id="2c979-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="2c979-214">.JAD</span></span>
- <span data-ttu-id="2c979-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="2c979-215">.JAVA</span></span>
- <span data-ttu-id="2c979-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="2c979-216">.JS\*</span></span>
- <span data-ttu-id="2c979-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="2c979-217">.LIB</span></span>
- <span data-ttu-id="2c979-218">.O</span><span class="sxs-lookup"><span data-stu-id="2c979-218">.O</span></span>
- <span data-ttu-id="2c979-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="2c979-219">.PHP</span></span>
- <span data-ttu-id="2c979-220">.RC</span><span class="sxs-lookup"><span data-stu-id="2c979-220">.RC</span></span>
- <span data-ttu-id="2c979-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="2c979-221">.RESX</span></span>
- <span data-ttu-id="2c979-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="2c979-222">.RPT</span></span>
- <span data-ttu-id="2c979-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="2c979-223">.RSS</span></span>
- <span data-ttu-id="2c979-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="2c979-224">.SCPT</span></span>
- <span data-ttu-id="2c979-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="2c979-225">.SRC</span></span>
- <span data-ttu-id="2c979-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="2c979-226">.VB\*</span></span>
- <span data-ttu-id="2c979-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="2c979-227">.WSF</span></span>
- <span data-ttu-id="2c979-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="2c979-228">.XCODEPROJ</span></span>
- <span data-ttu-id="2c979-229">.XML</span><span class="sxs-lookup"><span data-stu-id="2c979-229">.XML</span></span>
- <span data-ttu-id="2c979-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="2c979-230">.XSD</span></span>
- <span data-ttu-id="2c979-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="2c979-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="2c979-232">Conservar archivos de vídeo</span><span class="sxs-lookup"><span data-stu-id="2c979-232">Retain video files</span></span>

<span data-ttu-id="2c979-233">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2c979-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="2c979-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="2c979-234">.AVCHD</span></span>
- <span data-ttu-id="2c979-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="2c979-235">.AVI</span></span>
- <span data-ttu-id="2c979-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="2c979-236">.FLV</span></span>
- <span data-ttu-id="2c979-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="2c979-237">.MOV</span></span>
- <span data-ttu-id="2c979-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="2c979-238">.MP2V</span></span>
- <span data-ttu-id="2c979-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="2c979-239">.MP4</span></span>
- <span data-ttu-id="2c979-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="2c979-240">.MP4V</span></span>
- <span data-ttu-id="2c979-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="2c979-241">.MPE</span></span>
- <span data-ttu-id="2c979-242">MPEG</span><span class="sxs-lookup"><span data-stu-id="2c979-242">.MPEG</span></span>
- <span data-ttu-id="2c979-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="2c979-243">.MPEG1</span></span>
- <span data-ttu-id="2c979-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="2c979-244">.MPEG2</span></span>
- <span data-ttu-id="2c979-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="2c979-245">.MPEG4</span></span>
- <span data-ttu-id="2c979-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="2c979-246">.MPG</span></span>
- <span data-ttu-id="2c979-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="2c979-247">.MPG2</span></span>
- <span data-ttu-id="2c979-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="2c979-248">.MPG4</span></span>
- <span data-ttu-id="2c979-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="2c979-249">.WMV</span></span>
- <span data-ttu-id="2c979-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="2c979-250">.XMV</span></span>

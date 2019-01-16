---
title: Cómo se identifica el contenido para las recomendaciones de gobierno de datos
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. En este tema se enumeran las recomendaciones de gobierno de datos que puede ver y se describe el contenido que se detecta para desencadenar cada uno.
ms.openlocfilehash: a3f803105ea5c2626c8c2a26ad898df5f45af2f0
ms.sourcegitcommit: c7737903ff2e1d047682ee61f7ac21b0bdd1c6fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "28263952"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="ba5e7-106">Cómo se identifica el contenido para las recomendaciones de gobierno de datos</span><span class="sxs-lookup"><span data-stu-id="ba5e7-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="ba5e7-p102">El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. </span><span class="sxs-lookup"><span data-stu-id="ba5e7-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="ba5e7-110">En este tema se enumeran las recomendaciones de gobierno de datos que es posible que vea y se describe el contenido que se detecte para desencadenar cada uno.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="ba5e7-111">Limpiar el correo de voz</span><span class="sxs-lookup"><span data-stu-id="ba5e7-111">Clean up voicemail</span></span>

<span data-ttu-id="ba5e7-p103">Esta recomendación aparece cuando se detectan mensajes de correo identificados como tipo de mensaje "correo de voz" en los buzones de usuarios. Obtenga más información sobre las [propiedades de mensajes en Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="ba5e7-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="ba5e7-114">Etiquetar contenido de privilegios abogado-cliente </span><span class="sxs-lookup"><span data-stu-id="ba5e7-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="ba5e7-115">Esta recomendación aparece cuando se cumple uno de los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="ba5e7-116">Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="ba5e7-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="ba5e7-117">ACP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-117">ACP</span></span>
    - <span data-ttu-id="ba5e7-118">Privilegio de abogado cliente</span><span class="sxs-lookup"><span data-stu-id="ba5e7-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="ba5e7-119">Privilegio de abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="ba5e7-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="ba5e7-120">Confidencialidad abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="ba5e7-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="ba5e7-121">Cualquier combinación de estas palabras clave se detectan en archivos de SharePoint o OneDrive:</span><span class="sxs-lookup"><span data-stu-id="ba5e7-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="ba5e7-122">ACP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-122">ACP</span></span>
    - <span data-ttu-id="ba5e7-123">Privilegio de abogado cliente\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="ba5e7-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="ba5e7-125">Conservar archivos de audio</span><span class="sxs-lookup"><span data-stu-id="ba5e7-125">Retain audio files</span></span>

<span data-ttu-id="ba5e7-126">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="ba5e7-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="ba5e7-127">MP3 (default)</span></span>
- <span data-ttu-id="ba5e7-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="ba5e7-128">WMA</span></span>
- <span data-ttu-id="ba5e7-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="ba5e7-129">WAV</span></span>
- <span data-ttu-id="ba5e7-130">.RA</span><span class="sxs-lookup"><span data-stu-id="ba5e7-130">.RA</span></span>
- <span data-ttu-id="ba5e7-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-131">RAM</span></span>
- <span data-ttu-id="ba5e7-132">.RM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-132">rm</span></span>
- <span data-ttu-id="ba5e7-133">.MID</span><span class="sxs-lookup"><span data-stu-id="ba5e7-133">.MID</span></span>
- <span data-ttu-id="ba5e7-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-134">.OGG</span></span>
- <span data-ttu-id="ba5e7-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="ba5e7-135">.AIFF</span></span>
- <span data-ttu-id="ba5e7-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-136">.PCM</span></span>
- <span data-ttu-id="ba5e7-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-137">.AAC</span></span>
- <span data-ttu-id="ba5e7-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-138">.FLAC</span></span>
- <span data-ttu-id="ba5e7-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="ba5e7-140">Conservar archivos CAD</span><span class="sxs-lookup"><span data-stu-id="ba5e7-140">Retain CAD files</span></span>

<span data-ttu-id="ba5e7-141">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="ba5e7-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="ba5e7-142">.3DXML</span></span>
- <span data-ttu-id="ba5e7-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="ba5e7-143">.ACIS</span></span>
- <span data-ttu-id="ba5e7-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-144">ARC
</span></span>
- <span data-ttu-id="ba5e7-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-145">asm</span></span>
- <span data-ttu-id="ba5e7-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-146">cat</span></span>
- <span data-ttu-id="ba5e7-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="ba5e7-147">.CGR</span></span>
- <span data-ttu-id="ba5e7-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-148">DW</span></span>
- <span data-ttu-id="ba5e7-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-149">Dx</span></span>
- <span data-ttu-id="ba5e7-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="ba5e7-150">.EDRW</span></span>
- <span data-ttu-id="ba5e7-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-151">.IAM</span></span>
- <span data-ttu-id="ba5e7-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="ba5e7-152">.IGES</span></span>
- <span data-ttu-id="ba5e7-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="ba5e7-153">.IGS</span></span>
- <span data-ttu-id="ba5e7-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="ba5e7-154">.IPT</span></span>
- <span data-ttu-id="ba5e7-155">.JT</span><span class="sxs-lookup"><span data-stu-id="ba5e7-155">.JT</span></span>
- <span data-ttu-id="ba5e7-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="ba5e7-156">.MF1</span></span>
- <span data-ttu-id="ba5e7-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="ba5e7-157">.NEU</span></span>
- <span data-ttu-id="ba5e7-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="ba5e7-158">.PAR</span></span>
- <span data-ttu-id="ba5e7-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-159">.PKG</span></span>
- <span data-ttu-id="ba5e7-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-160">PRC
</span></span>
- <span data-ttu-id="ba5e7-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="ba5e7-161">.PRT</span></span>
- <span data-ttu-id="ba5e7-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-162">.PSM</span></span>
- <span data-ttu-id="ba5e7-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="ba5e7-163">.PWD</span></span>
- <span data-ttu-id="ba5e7-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-164">.SLD\*</span></span>
- <span data-ttu-id="ba5e7-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-165">Step</span></span>
- <span data-ttu-id="ba5e7-166">.STL</span><span class="sxs-lookup"><span data-stu-id="ba5e7-166">.STL</span></span>
- <span data-ttu-id="ba5e7-167">.STP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-167">.STP</span></span>
- <span data-ttu-id="ba5e7-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="ba5e7-168">.U3D</span></span>
- <span data-ttu-id="ba5e7-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="ba5e7-169">.UNV</span></span>
- <span data-ttu-id="ba5e7-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="ba5e7-170">.VRML</span></span>
- <span data-ttu-id="ba5e7-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="ba5e7-171">.WRL</span></span>
- <span data-ttu-id="ba5e7-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-172">X</span></span>
- <span data-ttu-id="ba5e7-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="ba5e7-173">.XAS</span></span>
- <span data-ttu-id="ba5e7-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-174">.XMT\*</span></span>
- <span data-ttu-id="ba5e7-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="ba5e7-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="ba5e7-176">Conservar archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="ba5e7-176">Retain image files</span></span>

<span data-ttu-id="ba5e7-177">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="ba5e7-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-178">JPEG</span></span>
- <span data-ttu-id="ba5e7-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="ba5e7-179">GIF</span></span>
- <span data-ttu-id="ba5e7-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-180">tif</span></span>
- <span data-ttu-id="ba5e7-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-181">.bmp</span></span>
- <span data-ttu-id="ba5e7-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-182">PNG</span></span>
- <span data-ttu-id="ba5e7-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="ba5e7-183">.RAW</span></span>
- <span data-ttu-id="ba5e7-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="ba5e7-184">.PSD</span></span>
- <span data-ttu-id="ba5e7-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-185">PSP
</span></span>
- <span data-ttu-id="ba5e7-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-186">.jpg</span></span>
- <span data-ttu-id="ba5e7-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="ba5e7-187">.EXIF</span></span>
- <span data-ttu-id="ba5e7-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-188">PPM capabilities</span></span>
- <span data-ttu-id="ba5e7-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-189">.PGM</span></span>
- <span data-ttu-id="ba5e7-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-190">.PBM</span></span>
- <span data-ttu-id="ba5e7-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-191">.PNM</span></span>
- <span data-ttu-id="ba5e7-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="ba5e7-193">Conservar contenido NDA</span><span class="sxs-lookup"><span data-stu-id="ba5e7-193">Retain NDA content</span></span> 

<span data-ttu-id="ba5e7-194">Esta recomendación aparece cuando se cumple uno de los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="ba5e7-195">Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="ba5e7-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="ba5e7-196">NDA</span><span class="sxs-lookup"><span data-stu-id="ba5e7-196">NDA</span></span>
    - <span data-ttu-id="ba5e7-197">“Acuerdo de confidencialidad”</span><span class="sxs-lookup"><span data-stu-id="ba5e7-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="ba5e7-198">“Acuerdo de confidencialidad”</span><span class="sxs-lookup"><span data-stu-id="ba5e7-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="ba5e7-199">Cualquier combinación de estas palabras clave se detectan en archivos .PDF o .DOC en SharePoint o OneDrive:</span><span class="sxs-lookup"><span data-stu-id="ba5e7-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="ba5e7-200">NDA</span><span class="sxs-lookup"><span data-stu-id="ba5e7-200">NDA</span></span>
    - <span data-ttu-id="ba5e7-201">Acuerdo de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="ba5e7-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="ba5e7-202">Conservar archivos de desarrollo de software </span><span class="sxs-lookup"><span data-stu-id="ba5e7-202">Retain software development files</span></span>

<span data-ttu-id="ba5e7-203">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="ba5e7-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="ba5e7-204">.ASAX</span></span>
- <span data-ttu-id="ba5e7-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="ba5e7-205">asm</span></span>
- <span data-ttu-id="ba5e7-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-206">asp</span></span>
- <span data-ttu-id="ba5e7-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="ba5e7-207">bat</span></span>
- <span data-ttu-id="ba5e7-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-208">.config</span></span>
- <span data-ttu-id="ba5e7-209">.CS</span><span class="sxs-lookup"><span data-stu-id="ba5e7-209">cs</span></span>
- <span data-ttu-id="ba5e7-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="ba5e7-210">CSS</span></span>
- <span data-ttu-id="ba5e7-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="ba5e7-211">.DISCO</span></span>
- <span data-ttu-id="ba5e7-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-212">htm</span></span>
- <span data-ttu-id="ba5e7-213">.INC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-213">.INC</span></span>
- <span data-ttu-id="ba5e7-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="ba5e7-214">.JAD</span></span>
- <span data-ttu-id="ba5e7-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="ba5e7-215">Java</span></span>
- <span data-ttu-id="ba5e7-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-216">.js</span></span>
- <span data-ttu-id="ba5e7-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="ba5e7-217">.LIB</span></span>
- <span data-ttu-id="ba5e7-218">.O</span><span class="sxs-lookup"><span data-stu-id="ba5e7-218">O</span></span>
- <span data-ttu-id="ba5e7-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="ba5e7-219">PHP</span></span>
- <span data-ttu-id="ba5e7-220">.RC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-220">.RC</span></span>
- <span data-ttu-id="ba5e7-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="ba5e7-221">\*.resx</span></span>
- <span data-ttu-id="ba5e7-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="ba5e7-222">.RPT</span></span>
- <span data-ttu-id="ba5e7-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="ba5e7-223">RSS</span></span>
- <span data-ttu-id="ba5e7-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="ba5e7-224">.SCPT</span></span>
- <span data-ttu-id="ba5e7-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="ba5e7-225">.SRC</span></span>
- <span data-ttu-id="ba5e7-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-226">.vb</span></span>
- <span data-ttu-id="ba5e7-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="ba5e7-227">.wsf</span></span>
- <span data-ttu-id="ba5e7-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="ba5e7-228">.XCODEPROJ</span></span>
- <span data-ttu-id="ba5e7-229">.XML</span><span class="sxs-lookup"><span data-stu-id="ba5e7-229">XML</span></span>
- <span data-ttu-id="ba5e7-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="ba5e7-230">.XSD</span></span>
- <span data-ttu-id="ba5e7-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="ba5e7-231">XSL</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="ba5e7-232">Conservar archivos de vídeo</span><span class="sxs-lookup"><span data-stu-id="ba5e7-232">Retain video files</span></span>

<span data-ttu-id="ba5e7-233">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba5e7-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="ba5e7-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="ba5e7-234">.AVCHD</span></span>
- <span data-ttu-id="ba5e7-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="ba5e7-235">avi</span></span>
- <span data-ttu-id="ba5e7-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="ba5e7-236">.FLV</span></span>
- <span data-ttu-id="ba5e7-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="ba5e7-237">.MOV</span></span>
- <span data-ttu-id="ba5e7-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="ba5e7-238">.MP2V</span></span>
- <span data-ttu-id="ba5e7-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="ba5e7-239">.MP4</span></span>
- <span data-ttu-id="ba5e7-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="ba5e7-240">.MP4V</span></span>
- <span data-ttu-id="ba5e7-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="ba5e7-241">.MPE</span></span>
- <span data-ttu-id="ba5e7-242">MPEG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-242">MPEG</span></span>
- <span data-ttu-id="ba5e7-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="ba5e7-243">.MPEG1</span></span>
- <span data-ttu-id="ba5e7-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="ba5e7-244">.MPEG2</span></span>
- <span data-ttu-id="ba5e7-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="ba5e7-245">.MPEG4</span></span>
- <span data-ttu-id="ba5e7-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="ba5e7-246">.MPG</span></span>
- <span data-ttu-id="ba5e7-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="ba5e7-247">.MPG2</span></span>
- <span data-ttu-id="ba5e7-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="ba5e7-248">.MPG4</span></span>
- <span data-ttu-id="ba5e7-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="ba5e7-249">.WMV</span></span>
- <span data-ttu-id="ba5e7-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="ba5e7-250">.XMV</span></span>

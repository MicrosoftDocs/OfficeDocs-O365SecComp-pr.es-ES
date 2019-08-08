---
title: Envíos de administración en Office 365, envíos de O365, Office 365 problema de correo no deseado, O365 falso negativo, enviar phish en Office 365, enviar correo electrónico para analizar, correo electrónico sospechoso en Office 365, analizar un mensaje, hacer que Microsoft analice en caso de Phish, hacer que Microsoft busque correo no deseado, enviar correo electrónico, enviar correo electrónico
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo enviar correos sospechosos, direcciones URL y mensajes de suplantación de identidad sospechoso, correo no deseado y otros mensajes potencialmente peligrosos, direcciones URL y archivos desde el inquilino de Office 365 a Microsoft para su análisis.
ms.openlocfilehash: 5a909e8b587e2a1265c1b2afbd5e063d46a04e2c
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230954"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="88119-103">Cómo enviar sospechoso de correo no deseado, phish, direcciones URL y archivos a Microsoft para el análisis de Office 365</span><span class="sxs-lookup"><span data-stu-id="88119-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="88119-104">Los administradores pueden enviar correos electrónicos mediante el identificador de mensajes de red o archivos, las direcciones URL y los archivos para que Microsoft los analice en Office 365.</span><span class="sxs-lookup"><span data-stu-id="88119-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="88119-105">La sección de presentaciones actualizadas sigue incluyendo mensajes de usuario que han sido notificados y disponibles para todos los clientes que usen EOP.</span><span class="sxs-lookup"><span data-stu-id="88119-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="88119-106">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="88119-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="88119-107">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas ETR.</span><span class="sxs-lookup"><span data-stu-id="88119-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="88119-108">Cómo enviar contenido a Microsoft para el análisis de Office 365</span><span class="sxs-lookup"><span data-stu-id="88119-108">How to submit content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="88119-109">Para enviar contenido a Microsoft, haga clic en el botón **nuevo envío** en el lado superior izquierdo de la página envíos.</span><span class="sxs-lookup"><span data-stu-id="88119-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="88119-110">Un control flotante en el lado derecho de la página aparece con la opción de enviar un correo electrónico, una dirección URL o un archivo.</span><span class="sxs-lookup"><span data-stu-id="88119-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-an-email-to-microsoft"></a><span data-ttu-id="88119-111">Enviar un correo electrónico a Microsoft</span><span class="sxs-lookup"><span data-stu-id="88119-111">Submit an email to Microsoft</span></span>
![Ejemplo de envío de correo electrónico](media/submission-flyout-email.PNG)
1. <span data-ttu-id="88119-113">Para enviar un correo electrónico, seleccione **correo electrónico** y especifique el **identificador de mensaje de red** de correo electrónico o cargue el archivo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="88119-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="88119-114">Especifique el destinatario o los destinatarios con los que desea ejecutar la comprobación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="88119-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="88119-115">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a directivas de nivel de usuario o de inquilino.</span><span class="sxs-lookup"><span data-stu-id="88119-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="88119-116">Especifique si el correo electrónico se debe haber bloqueado o no.</span><span class="sxs-lookup"><span data-stu-id="88119-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="88119-117">Si el correo electrónico debe haberse bloqueado, especifique si debe haberse bloqueado como correo no deseado, suplantación de identidad (phishing) o malware.</span><span class="sxs-lookup"><span data-stu-id="88119-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="88119-118">Si no está seguro de qué tipo puede ser, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="88119-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="88119-119">Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="88119-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="88119-120">Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="88119-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="88119-121">Para ver más información sobre el envío, haga clic en el vínculo estado.</span><span class="sxs-lookup"><span data-stu-id="88119-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="88119-122">Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo.</span><span class="sxs-lookup"><span data-stu-id="88119-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="88119-123">Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.</span><span class="sxs-lookup"><span data-stu-id="88119-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="88119-124">Haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="88119-124">Click the **Submit** button.</span></span>

### <a name="submit-a-url-to-microsoft"></a><span data-ttu-id="88119-125">Enviar una dirección URL a Microsoft</span><span class="sxs-lookup"><span data-stu-id="88119-125">Submit a URL to Microsoft</span></span>
![Ejemplo de envío de correo electrónico](media/submission-url-flyout.png)
1. <span data-ttu-id="88119-127">Para enviar una dirección URL, seleccione **dirección URL** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="88119-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="88119-128">Escriba la dirección URL completa, incluido el protocolo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="88119-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="88119-129">Si seleccionó **debería haber sido filtrada**, especifique si la dirección URL es phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="88119-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="88119-130">Haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="88119-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-file-to-microsoft"></a><span data-ttu-id="88119-131">Enviar un archivo a Microsoft</span><span class="sxs-lookup"><span data-stu-id="88119-131">Submit a file to Microsoft</span></span>
![Ejemplo de envío de correo electrónico](media/submission-file-flyout.PNG)
1. <span data-ttu-id="88119-133">Para enviar un archivo de \*\*\*\* selección de archivo desde el control flotante y cargar el archivo que desea examinar.</span><span class="sxs-lookup"><span data-stu-id="88119-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="88119-134">Haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="88119-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="88119-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="88119-135">Related topics</span></span>

[<span data-ttu-id="88119-136">Plan 2 de protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="88119-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="88119-137">Protección contra amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="88119-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="88119-138">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="88119-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  


---
title: Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: Lea este artículo para obtener información sobre cómo configurar una lista de direcciones URL bloqueadas para su organización mediante la protección de amenaza avanzada de Office 365. Las direcciones URL bloqueadas se aplicarán a los mensajes de correo electrónico y documentos de Office según las directivas de vínculos seguros de ATP.
ms.openlocfilehash: cd1e7858c8929bf468b2a4d5e09ccde9d5adc7b1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536240"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="b839b-104">Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos</span><span class="sxs-lookup"><span data-stu-id="b839b-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="b839b-p102">Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener una lista personalizada de direcciones de sitios Web (URL) que están bloqueados. Cuando se bloquea una dirección URL, se toman las personas que haga clic en vínculos a la dirección URL bloqueada a una [página de advertencia](atp-safe-links-warning-pages.md) que es similar a la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="b839b-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Este sitio está bloqueado](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="b839b-108">Se define la lista de direcciones URL bloqueadas por el equipo de seguridad de Office 365 de su organización, y esa lista se aplica a todas las personas de la organización que está cubierta por las directivas de Office 365 ATP seguros vínculos.</span><span class="sxs-lookup"><span data-stu-id="b839b-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="b839b-109">Lea este artículo para obtener información sobre cómo configurar la lista de direcciones URL personalizada bloqueada de su organización para [ATP vínculos seguros en Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="b839b-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="b839b-110">Ver o editar una lista personalizada de direcciones URL bloqueadas</span><span class="sxs-lookup"><span data-stu-id="b839b-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="b839b-p103">[ATP vínculos seguros en Office 365](atp-safe-links.md) usa varias listas, incluida la lista de direcciones URL personalizada bloqueada de su organización. Si tiene los permisos necesarios, puede configurar la lista personalizada de su organización. Para ello, mediante la edición de la directiva de su organización predeterminada vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="b839b-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>
  
1. <span data-ttu-id="b839b-114">Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="b839b-114">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="b839b-115">En la izquierda, en **administración de amenaza**, elija **Directiva** \> **Vínculos seguros**.</span><span class="sxs-lookup"><span data-stu-id="b839b-115">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="b839b-116">En la sección de **directivas que se aplican a toda la organización** , seleccione **predeterminado**y, a continuación, elija **Editar** (el botón Editar se parece a un lápiz).</span><span class="sxs-lookup"><span data-stu-id="b839b-116">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![Haga clic en Editar para editar la directiva predeterminada para la protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    <span data-ttu-id="b839b-p104">Esto es donde vaya a ver la lista de direcciones URL bloqueadas. Tenga en cuenta que, en primer lugar, no tendrá ningún direcciones URL que aparecen.</span><span class="sxs-lookup"><span data-stu-id="b839b-p104">This is where you go to view your list of blocked URLs. Note that at first, you won't have any URLs listed.</span></span>
    
    ![La lista de direcciones URL bloqueado está en el valor predeterminado directiva vínculos seguros que se aplica a toda la organización.](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. <span data-ttu-id="b839b-p105">Seleccione el cuadro **Escriba una dirección URL válida** y, a continuación, escriba una dirección URL y, a continuación, elija el signo más (+). A continuación presentamos algunas cosas que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="b839b-p105">Select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). Here are a few things to keep in mind:</span></span> 
    
  - <span data-ttu-id="b839b-p106">Puede especificar una dirección URL de dominio (como `contoso.com` o `tailspintoys.com`). Esto bloqueará clics en cualquier dirección URL que contiene el dominio.</span><span class="sxs-lookup"><span data-stu-id="b839b-p106">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>
    
  - <span data-ttu-id="b839b-p107">No incluya una barra diagonal ( **/**) al final de la dirección URL. Por ejemplo, en lugar de escribir `http://www.contoso.com/`, escriba `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="b839b-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
  - <span data-ttu-id="b839b-p108">Puede incluir hasta tres asteriscos comodín (\*) por la dirección URL. La siguiente tabla se enumeran algunos ejemplos de lo que puede escribir y el efecto que esas entradas tienen.</span><span class="sxs-lookup"><span data-stu-id="b839b-p108">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="b839b-129">**Entrada de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="b839b-129">**Example Entry**</span></span>|<span data-ttu-id="b839b-130">**Para qué sirve**</span><span class="sxs-lookup"><span data-stu-id="b839b-130">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b839b-131">`contoso.com`o`\*contoso.com\*`</span><span class="sxs-lookup"><span data-stu-id="b839b-131">`contoso.com` or `\*contoso.com\*`</span></span>  <br/> |<span data-ttu-id="b839b-132">Bloquea el dominio, subdominios y rutas de acceso, como `https://www.contoso.com`, `http://sub.contoso.com`, y`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="b839b-132">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="b839b-133">Bloquea un sitio `http://contoso.com/a` pero subtrazados no adicionales, como`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="b839b-133">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a\*`  <br/> |<span data-ttu-id="b839b-134">Bloquea un sitio `http://contoso.com/a` y subtrazados adicionales, como`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="b839b-134">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
5. <span data-ttu-id="b839b-135">Cuando haya terminado de agregar las direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b839b-135">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="what-if-i-want-to-define-exceptions-for-certain-users-in-my-organization"></a><span data-ttu-id="b839b-136">¿Qué ocurre si deseo definir excepciones para algunos usuarios de mi organización?</span><span class="sxs-lookup"><span data-stu-id="b839b-136">What if I want to define exceptions for certain users in my organization?</span></span>

<span data-ttu-id="b839b-p109">Si desea que ciertos grupos puedan ver las direcciones URL que podrían estar bloqueadas para que otros usuarios, puede especificar una directiva de vínculos seguros de ATP que se aplica a determinados destinatarios. Consulte [Configurar una "no reescritura" las direcciones URL de lista personalizada con vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b839b-p109">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b839b-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b839b-139">Related topics</span></span>

[<span data-ttu-id="b839b-140">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="b839b-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="b839b-141">Vínculos de ATP seguros en Office 365</span><span class="sxs-lookup"><span data-stu-id="b839b-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="b839b-142">Configurar directivas de vínculos seguros de ATP en Office 365</span><span class="sxs-lookup"><span data-stu-id="b839b-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="b839b-143">Datos adjuntos seguros de ATP en Office 365</span><span class="sxs-lookup"><span data-stu-id="b839b-143">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)

[<span data-ttu-id="b839b-144">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b839b-144">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


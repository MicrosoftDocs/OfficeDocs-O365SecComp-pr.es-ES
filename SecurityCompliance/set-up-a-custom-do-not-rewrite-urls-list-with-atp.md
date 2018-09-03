---
title: Configurar una lista personalizada de direcciones URL de reescritura de no hacer con Office 365 ATP seguros vínculos
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: Al configurar las directivas de vínculos seguros de ATP, puede incluir una reescritura de no hacer ' lista de direcciones URL para habilitar algunas personas de la organización visitar sitios que se incluyen en la lista.
ms.openlocfilehash: 0ee9c87c90e6e30d6c43fb0de5291dd85b03be07
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782167"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="26248-103">Configurar una lista personalizada de direcciones URL de reescritura de no hacer con Office 365 ATP seguros vínculos</span><span class="sxs-lookup"><span data-stu-id="26248-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="26248-p101">Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener un [URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md), por ejemplo, que cuando haga clic en personas en web direcciones (URL) en mensajes de correo electrónico o de determinados documentos de Office, se impide que se va a esas direcciones. La organización también puede tener listas personalizadas "no reescritura" para grupos específicos de la organización. Una lista "no reescritura" permite algunas personas visitar las direcciones URL que en caso contrario, están bloqueadas por [ATP vínculos seguros en Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="26248-p101">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="26248-107">En este artículo se describe cómo especificar una lista de direcciones URL que se excluyen de examen de vínculos seguros de ATP y algunos puntos importantes que deben tenerse en cuenta.</span><span class="sxs-lookup"><span data-stu-id="26248-107">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="26248-108">Configurar una lista "no reescritura de"</span><span class="sxs-lookup"><span data-stu-id="26248-108">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="26248-p102">Protección de vínculos seguros de ATP utiliza varias listas, incluida la lista de direcciones URL bloqueadas de la organización y las listas de "no volver a escribir" para las excepciones. Si tiene los permisos necesarios, puede configurar las listas personalizadas "no reescritura de". Para ello, al agregar o editar las directivas de seguros vínculos que se aplican a determinados destinatarios en la organización.</span><span class="sxs-lookup"><span data-stu-id="26248-p102">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 
  
1. <span data-ttu-id="26248-112">Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="26248-112">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="26248-113">En la izquierda, en **administración de amenaza** \> **Directiva** \> **Vínculos seguros**.</span><span class="sxs-lookup"><span data-stu-id="26248-113">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="26248-p103">En la sección de **directivas que se aplican a determinados destinatarios** , elija **nuevo** (el botón nuevo se parece a un signo más ( **+**)) para crear una nueva directiva. (Como alternativa, puede editar una directiva existente).</span><span class="sxs-lookup"><span data-stu-id="26248-p103">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span>
    
    ![Elija nuevo para agregar una directiva de vínculos seguros para los destinatarios de correo electrónico específica](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. <span data-ttu-id="26248-117">Especifique un nombre y una descripción para la directiva.</span><span class="sxs-lookup"><span data-stu-id="26248-117">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="26248-118">En la sección **no de reescritura de las siguientes direcciones URL** , seleccione el cuadro **Escriba una dirección URL válida** y, a continuación, escriba una dirección URL y, a continuación, elija el signo más (+).</span><span class="sxs-lookup"><span data-stu-id="26248-118">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="26248-p104">En la sección **Aplicar a** , elija **el destinatario es un miembro de**y, a continuación, elija el grupo o grupos que desea incluir en la directiva. Elija **Agregar**y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="26248-p104">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="26248-121">Cuando haya terminado de agregar las direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="26248-121">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="26248-p105">Asegúrese de revisar la lista personalizada de la organización de las URL bloqueadas. Consulte [Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span><span class="sxs-lookup"><span data-stu-id="26248-p105">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="26248-124">Puntos importantes que deben tenerse en cuenta</span><span class="sxs-lookup"><span data-stu-id="26248-124">Important points to keep in mind</span></span>

- <span data-ttu-id="26248-125">Cualquier dirección URL que especifique en la lista "no reescritura" se excluye de vínculos seguros ATP análisis para los destinatarios que especifique.</span><span class="sxs-lookup"><span data-stu-id="26248-125">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="26248-p106">Cuando se especifica una lista de "no volver a escribir" para una directiva de vínculos seguros ATP, puede incluir hasta tres asteriscos comodín (\*). Caracteres comodín (\*) se supone que las entradas de como `contoso.com`, que no explícitamente incluir prefijos o subdominios, como `http://` o `https://`. Esto significa que una entrada, como `contoso.com` es similar a `\*contoso.com\*` para la lista de "no volver a escribir".</span><span class="sxs-lookup"><span data-stu-id="26248-p106">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `\*contoso.com\*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="26248-p107">Si ya tiene una lista de direcciones URL en la lista de "no reescritura", asegúrese de revisar esa lista y agregue caracteres comodín según corresponda. Por ejemplo, si la lista existente tiene una entrada como `http://contoso.com/a` y desea incluir subrutas como `http://contoso.com/a/b` en la directiva, agregue un carácter comodín a la entrada para el aspecto `http://contoso.com/a\*`.</span><span class="sxs-lookup"><span data-stu-id="26248-p107">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a\*`.</span></span>
    
- <span data-ttu-id="26248-p108">No incluya una barra diagonal (/) en las direcciones URL que especifique en la lista de "no volver a escribir". Por ejemplo, en lugar de escribir `contoso.com/` en la lista de "no reescritura", escriba `contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="26248-p108">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="26248-133">Tienen los siguientes ejemplos de listas de tabla de lo que puede escribir y el efecto que esas entradas.</span><span class="sxs-lookup"><span data-stu-id="26248-133">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="26248-134">**Entrada de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="26248-134">**Example Entry**</span></span>|<span data-ttu-id="26248-135">**Para qué sirve**</span><span class="sxs-lookup"><span data-stu-id="26248-135">**What It Does**</span></span>|
|:-----|:-----|
|`\*contoso.com\*`  <br/> |<span data-ttu-id="26248-136">Permite a los destinatarios específicos visite un dominio, subdominios y rutas de acceso, como `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, o`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="26248-136">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="26248-137">Permite a los destinatarios específicos a visitar un sitio como `http://contoso.com/a`, pero no subtrazados like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="26248-137">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a\*`  <br/> |<span data-ttu-id="26248-138">Permite a los destinatarios específicos a visitar un sitio como `http://contoso.com/a` y subtrazados como`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="26248-138">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
  

## <a name="related-topics"></a><span data-ttu-id="26248-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="26248-139">Related topics</span></span>

[<span data-ttu-id="26248-140">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="26248-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="26248-141">Vínculos de ATP seguros en Office 365</span><span class="sxs-lookup"><span data-stu-id="26248-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="26248-142">Configurar directivas de vínculos seguros de ATP en Office 365</span><span class="sxs-lookup"><span data-stu-id="26248-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="26248-143">Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="26248-143">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)

[<span data-ttu-id="26248-144">Visualización de informes para la protección de amenaza avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="26248-144">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="26248-145">Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="26248-145">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


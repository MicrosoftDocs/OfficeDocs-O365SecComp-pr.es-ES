---
title: Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/05/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: Obtenga información sobre cómo configurar una lista de direcciones URL bloqueadas para su organización mediante la protección de amenaza avanzada de Office 365. Las direcciones URL bloqueadas se aplicarán a los mensajes de correo electrónico y documentos de Office según las directivas de vínculos seguros de ATP.
ms.openlocfilehash: 4146424056c9a5b30f51a58fd020df912fa048ef
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741023"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="c9c94-104">Configurar una lista personalizada de direcciones URL bloqueada mediante Office 365 ATP seguros vínculos</span><span class="sxs-lookup"><span data-stu-id="c9c94-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="c9c94-p102">Con [Office 365 avanzada una protección contra amenazas](office-365-atp.md) (ATP), la organización puede tener una lista personalizada de direcciones de sitios Web (URL) que están bloqueados. Cuando se bloquea una dirección URL, se toman las personas que haga clic en vínculos a la dirección URL bloqueada a una [página de advertencia](atp-safe-links-warning-pages.md) que es similar a la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="c9c94-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Este sitio está bloqueado](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="c9c94-108">Se define la lista de direcciones URL bloqueadas por el equipo de seguridad de Office 365 de su organización, y esa lista se aplica a todas las personas de la organización que está cubierta por las directivas de Office 365 ATP seguros vínculos.</span><span class="sxs-lookup"><span data-stu-id="c9c94-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="c9c94-109">Lea este artículo para obtener información sobre cómo configurar la lista de direcciones URL personalizada bloqueada de su organización para [ATP vínculos seguros en Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="c9c94-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="c9c94-110">Ver o editar una lista personalizada de direcciones URL bloqueadas</span><span class="sxs-lookup"><span data-stu-id="c9c94-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="c9c94-p103">[ATP vínculos seguros en Office 365](atp-safe-links.md) usa varias listas, incluida la lista de direcciones URL personalizada bloqueada de su organización. Si tiene los permisos necesarios, puede configurar la lista personalizada de su organización. Para ello, mediante la edición de la directiva de su organización predeterminada vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="c9c94-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="c9c94-114">Para editar las directivas de ATP (o definir), debe asignar uno de los roles que se describen en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="c9c94-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="c9c94-115">Rol</span><span class="sxs-lookup"><span data-stu-id="c9c94-115">Role</span></span>  |<span data-ttu-id="c9c94-116">Dónde y cómo asignado</span><span class="sxs-lookup"><span data-stu-id="c9c94-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="c9c94-117">Administrador Global de Office 365</span><span class="sxs-lookup"><span data-stu-id="c9c94-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="c9c94-p104">La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de Office 365 roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="c9c94-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="c9c94-120">Administrador de seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="c9c94-120">Office 365 Security Administrator</span></span> |<span data-ttu-id="c9c94-121">Centro de administración ([https://aka.ms/admincenter](https://aka.ms/admincenter))</span><span class="sxs-lookup"><span data-stu-id="c9c94-121">Admin center ([https://aka.ms/admincenter](https://aka.ms/admincenter))</span></span>|
|<span data-ttu-id="c9c94-122">Administración de la organización en línea de Exchange</span><span class="sxs-lookup"><span data-stu-id="c9c94-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="c9c94-123">Centro de administración de Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="c9c94-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="c9c94-124">o</span><span class="sxs-lookup"><span data-stu-id="c9c94-124">or</span></span> <br>  <span data-ttu-id="c9c94-125">Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="c9c94-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
1. <span data-ttu-id="c9c94-126">Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="c9c94-126">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="c9c94-127">En la izquierda, en **administración de amenaza**, elija **Directiva** \> **Vínculos seguros**.</span><span class="sxs-lookup"><span data-stu-id="c9c94-127">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="c9c94-128">En la sección de **directivas que se aplican a toda la organización** , seleccione **predeterminado**y, a continuación, elija **Editar** (el botón Editar se parece a un lápiz).</span><span class="sxs-lookup"><span data-stu-id="c9c94-128">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="c9c94-129">![Haga clic en Editar para editar la directiva predeterminada para la protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="c9c94-129">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="c9c94-p105">Permite ver la lista de direcciones URL bloqueadas. En primer lugar, puede que no tenga todas las direcciones URL que se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="c9c94-p105">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="c9c94-132">![Lista de direcciones URL en la directiva predeterminada de vínculos seguros bloqueados](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="c9c94-132">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="c9c94-133">Seleccione el cuadro **Escriba una dirección URL válida** , escriba una dirección URL y, a continuación, seleccione el signo más (**+**).</span><span class="sxs-lookup"><span data-stu-id="c9c94-133">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="c9c94-134">Cuando haya terminado de agregar las direcciones URL, en la esquina inferior derecha de la pantalla, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c9c94-134">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="c9c94-135">Algunas cosas que debe tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="c9c94-135">A few things to keep in mind</span></span>

<span data-ttu-id="c9c94-136">Mientras se agregan las direcciones URL a la lista, tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="c9c94-136">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="c9c94-p106">No incluya una barra diagonal ( **/**) al final de la dirección URL. Por ejemplo, en lugar de escribir `http://www.contoso.com/`, escriba `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="c9c94-p106">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="c9c94-p107">Puede especificar una dirección URL de dominio (como `contoso.com` o `tailspintoys.com`). Esto bloqueará clics en cualquier dirección URL que contiene el dominio.</span><span class="sxs-lookup"><span data-stu-id="c9c94-p107">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="c9c94-p108">Puede especificar un subdominio (al igual que `toys.contoso.com*`) sin bloquear un dominio completo (como `contoso.com`). Esto le permitirá bloque hace clic en cualquier dirección URL que contiene el subdominio, pero no puede bloquear clics a una dirección URL que contiene el dominio completo.</span><span class="sxs-lookup"><span data-stu-id="c9c94-p108">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="c9c94-p109">Puede incluir hasta tres asteriscos comodín (\*) por la dirección URL. La siguiente tabla se enumeran algunos ejemplos de lo que puede escribir y el efecto que esas entradas tienen.</span><span class="sxs-lookup"><span data-stu-id="c9c94-p109">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="c9c94-145">**Entrada de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c9c94-145">**Example Entry**</span></span>|<span data-ttu-id="c9c94-146">**Para qué sirve**</span><span class="sxs-lookup"><span data-stu-id="c9c94-146">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9c94-147">`contoso.com`o`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="c9c94-147">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="c9c94-148">Bloquea el dominio, subdominios y rutas de acceso, como `https://www.contoso.com`, `http://sub.contoso.com`, y`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="c9c94-148">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="c9c94-149">Bloquea un sitio `http://contoso.com/a` pero subtrazados no adicionales, como`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c9c94-149">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="c9c94-150">Bloquea un sitio `http://contoso.com/a` y subtrazados adicionales, como`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c9c94-150">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="c9c94-151">Bloques de un subdominio ("toys" en este caso), pero permiten a los clics a otras direcciones URL de dominio (como `http://contoso.com` o `http://home.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="c9c94-151">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="c9c94-152">Procedimiento para definir excepciones para determinados usuarios en una organización</span><span class="sxs-lookup"><span data-stu-id="c9c94-152">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="c9c94-p110">Si desea que ciertos grupos puedan ver las direcciones URL que podrían estar bloqueadas para que otros usuarios, puede especificar una directiva de vínculos seguros de ATP que se aplica a determinados destinatarios. Consulte [Configurar una "no reescritura" las direcciones URL de lista personalizada con vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="c9c94-p110">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  


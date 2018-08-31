---
title: Desactivar el correo electrónico no deseado en Outlook, en la web de informes
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: Como un administrador de Office 365, puede desactivar la capacidad para los usuarios de correo electrónico de informe como correo no deseado.
ms.openlocfilehash: 8ee5ff87408b80c443e4cf950ce49f624096becb
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272045"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="6a6f8-103">Desactivar el correo electrónico no deseado en Outlook, en la web de informes</span><span class="sxs-lookup"><span data-stu-id="6a6f8-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="6a6f8-p101">Puede enviar correo no deseado, suplantación de identidad y mensajes deseados a Microsoft para su análisis con el de Outlook en el correo electrónico no deseado web reporting opciones, tal como se describe en [las estafas de suplantación de identidad en Outlook en la web y de correo electrónico no deseado de informe ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Si no desea usar estas opciones, los administradores pueden desactivar ellos mediante el cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6a6f8-p101">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a6f8-106">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="6a6f8-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="6a6f8-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="6a6f8-107"></span></span>

- <span data-ttu-id="6a6f8-108">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="6a6f8-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="6a6f8-p102">Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Directivas de buzón de correo de Outlook Web App" en el tema [sobre Outlook Web App](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) Permissions.</span><span class="sxs-lookup"><span data-stu-id="6a6f8-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Outlook Web App mailbox policies" entry in the [Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 
    
- <span data-ttu-id="6a6f8-111">Antes de ejecutar los cmdlets necesarios para desactivar los informes de correo electrónico no deseado, puede resultar útil revisar la información de referencia en los temas [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) y [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6a6f8-111">Before you run the cmdlets required to turn off junk email reporting, it might be helpful to review the reference information in the [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) topics.</span></span> 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="6a6f8-112">Desactivar no deseado, suplantación de identidad, correo no deseado y creación de informes a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a6f8-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="6a6f8-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="6a6f8-113"></span></span>

<span data-ttu-id="6a6f8-114">Primero, ejecute este cmdlet para obtener los directorios virtuales en los que quiere desactivar los informes:</span><span class="sxs-lookup"><span data-stu-id="6a6f8-114">First, run the following cmdlet to get the virtual directories for which you want to turn off reporting:</span></span>
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

<span data-ttu-id="6a6f8-115">Después, ejecute este cmdlet para desactivar los informes de correo no deseado y correo seguro para Microsoft:</span><span class="sxs-lookup"><span data-stu-id="6a6f8-115">Next, run the following cmdlet to turn off junk and not junk reporting to Microsoft:</span></span>
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

<span data-ttu-id="6a6f8-116">Por ejemplo, este cmdlet desactiva los informes para el directorio virtual Contoso\owa:</span><span class="sxs-lookup"><span data-stu-id="6a6f8-116">For example, the following cmdlet turns off reporting for virtual directory Contoso\owa:</span></span>
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6a6f8-117">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="6a6f8-117">How do you know this worked?</span></span>
<span data-ttu-id="6a6f8-118"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="6a6f8-118"></span></span>

<span data-ttu-id="6a6f8-p103">Ejecute Get-OWAMailboxPolicy para comprobar los valores de parámetro y, a continuación, tener acceso a Outlook en la web y compruebe que las opciones para notificar no deseado, suplantación de identidad, correo no deseado y no están disponibles. Aún será capaz de marcar los mensajes como no deseado, suplantación de identidad, correo no deseado y, pero no podrá identificarlos.</span><span class="sxs-lookup"><span data-stu-id="6a6f8-p103">Run Get-OWAMailboxPolicy to check the parameter values, and then access Outlook on the web and verify that the options to report junk, phishing, and not junk are not available. You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
  


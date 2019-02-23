---
title: Desactivar la creación de informes de correo no deseado en Outlook en la web
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: Como administrador de Office 365, puede desactivar la posibilidad de que los usuarios notifiquen el correo electrónico como correo no deseado.
ms.openlocfilehash: efe898f57fdf322ce49edd9e2577daab46dd8d8f
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223829"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="203ce-103">Desactivar la creación de informes de correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="203ce-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="203ce-p101">Puede enviar mensajes de correo no deseado, de suplantación de identidad (phishing) y de correo no deseado a Microsoft para su análisis con la opción de informes de correo no deseado de Outlook en la web (anteriormente conocido como Outlook Web App), tal como se describe en [informes de correo no deseado y estafas de suplantación de identidad en Outlook en la web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Si no quiere usar estas opciones, los administradores pueden desactivarlas mediante el cmdlet [set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="203ce-p101">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="203ce-106">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="203ce-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="203ce-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="203ce-107"></span></span>

- <span data-ttu-id="203ce-108">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="203ce-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="203ce-p102">Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "directivas de buzones de correo de Outlook en la web" en el tema [Outlook on the Web](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) Permissions.</span><span class="sxs-lookup"><span data-stu-id="203ce-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="203ce-111">Para conectarse a Exchange Online PowerShell, consulte [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="203ce-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="203ce-112">Desactivar los informes de correo no deseado, phishing y no deseados en Microsoft</span><span class="sxs-lookup"><span data-stu-id="203ce-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="203ce-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="203ce-113"></span></span>

<span data-ttu-id="203ce-114">En primer lugar, ejecute el siguiente comando para obtener los nombres de las directivas de buzón de correo de Outlook en la web disponibles:</span><span class="sxs-lookup"><span data-stu-id="203ce-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="203ce-115">A continuación, use la siguiente sintaxis para habilitar o deshabilitar los informes de correo no deseado y no deseados para Microsoft en Outlook en la web:</span><span class="sxs-lookup"><span data-stu-id="203ce-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="203ce-116">En este ejemplo se desactiva la creación de informes en la Directiva de buzones de Outlook Web App predeterminada:</span><span class="sxs-lookup"><span data-stu-id="203ce-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="203ce-117">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) y [set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span><span class="sxs-lookup"><span data-stu-id="203ce-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="203ce-118">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="203ce-118">How do you know this worked?</span></span>
<span data-ttu-id="203ce-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="203ce-119"></span></span>

<span data-ttu-id="203ce-p103">Ejecute **Get-OWAMailboxPolicy** para comprobar los valores de parámetro y, a continuación, Abra Outlook en la web para un usuario afectado (que tenga aplicada la Directiva de buzón de Outlook en la web) y compruebe que las opciones para informar de correo no deseado, suplantación de identidad y correo electrónico no deseado no están disponibles. Aún podrá marcar los mensajes como correo no deseado, suplantación de identidad (phishing) y correo deseado, pero no podrá informar sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="203ce-p103">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available. You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 

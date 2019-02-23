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
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Desactivar la creación de informes de correo no deseado en Outlook en la web

Puede enviar mensajes de correo no deseado, de suplantación de identidad (phishing) y de correo no deseado a Microsoft para su análisis con la opción de informes de correo no deseado de Outlook en la web (anteriormente conocido como Outlook Web App), tal como se describe en [informes de correo no deseado y estafas de suplantación de identidad en Outlook en la web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Si no quiere usar estas opciones, los administradores pueden desactivarlas mediante el cmdlet [set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

- Tiempo estimado para finalizar: 5 minutos
    
- Debe tener permisos asignados para poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "directivas de buzones de correo de Outlook en la web" en el tema [Outlook on the Web](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) Permissions. 

- Para conectarse a Exchange Online PowerShell, consulte [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Desactivar los informes de correo no deseado, phishing y no deseados en Microsoft
<a name="sectionSection1"> </a>

En primer lugar, ejecute el siguiente comando para obtener los nombres de las directivas de buzón de correo de Outlook en la web disponibles:
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

A continuación, use la siguiente sintaxis para habilitar o deshabilitar los informes de correo no deseado y no deseados para Microsoft en Outlook en la web:
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

En este ejemplo se desactiva la creación de informes en la Directiva de buzones de Outlook Web App predeterminada:
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) y [set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?
<a name="sectionSection2"> </a>

Ejecute **Get-OWAMailboxPolicy** para comprobar los valores de parámetro y, a continuación, Abra Outlook en la web para un usuario afectado (que tenga aplicada la Directiva de buzón de Outlook en la web) y compruebe que las opciones para informar de correo no deseado, suplantación de identidad y correo electrónico no deseado no están disponibles. Aún podrá marcar los mensajes como correo no deseado, suplantación de identidad (phishing) y correo deseado, pero no podrá informar sobre ellos. 

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
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Desactivar el correo electrónico no deseado en Outlook, en la web de informes

Puede enviar correo no deseado, suplantación de identidad y mensajes deseados a Microsoft para su análisis con el de Outlook en el correo electrónico no deseado web reporting opciones, tal como se describe en [las estafas de suplantación de identidad en Outlook en la web y de correo electrónico no deseado de informe ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Si no desea usar estas opciones, los administradores pueden desactivar ellos mediante el cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?
<a name="sectionSection0"> </a>

- Tiempo estimado para finalizar: 5 minutos
    
- Debe tener asignados los permisos puede llevar a cabo estos procedimientos. Para ver qué permisos necesita, vea la entrada "Directivas de buzón de correo de Outlook Web App" en el tema [sobre Outlook Web App](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) Permissions. 
    
- Antes de ejecutar los cmdlets necesarios para desactivar los informes de correo electrónico no deseado, puede resultar útil revisar la información de referencia en los temas [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) y [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Desactivar no deseado, suplantación de identidad, correo no deseado y creación de informes a Microsoft
<a name="sectionSection1"> </a>

Primero, ejecute este cmdlet para obtener los directorios virtuales en los que quiere desactivar los informes:
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

Después, ejecute este cmdlet para desactivar los informes de correo no deseado y correo seguro para Microsoft:
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

Por ejemplo, este cmdlet desactiva los informes para el directorio virtual Contoso\owa:
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?
<a name="sectionSection2"> </a>

Ejecute Get-OWAMailboxPolicy para comprobar los valores de parámetro y, a continuación, tener acceso a Outlook en la web y compruebe que las opciones para notificar no deseado, suplantación de identidad, correo no deseado y no están disponibles. Aún será capaz de marcar los mensajes como no deseado, suplantación de identidad, correo no deseado y, pero no podrá identificarlos. 
  

